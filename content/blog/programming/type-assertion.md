---
title: 왜 타입 단언(Type Assertion)이 위험할까?
date: "2023-12-12"
description: "타입 단언(Type Assertion)이 위험한 이유는 무엇일까?"
meta:
  - name: description
    content: 타입 단언(Type Assertion)이 위험한 이유는 무엇일까?
  - property: og:title
    content: 왜 타입 단언(Type Assertion)이 위험할까?
  - property: og:description
    content: 타입 단언(Type Assertion)이 위험한 이유는 무엇일까?
---

## 타입 단언 이란?

타입 단언이란 개발자가 타입을 강제하고 타입 체커에게 `A는 B타입이다` 라고 알려주는 것이다.
예를 들어, `name` 과 `age`를 속성으로 갖고 있는 `Person` 타입이 있다고 가정하자. 변수 `person1` 에는 빈 객체를 할당했고, 변수 `person2` 에는 빈 객체를 할당함과 동시에 타입 단언을 사용해서 Person 타입이라고 단언했다.`person1.name`을 참조하려고 할 때는 `{} 형식에 'name' 속성이 없습니다.`라고 에러가 발생한다. 하지만 타입 단언을 사용해서 빈 객체로 초기화한 `person2.name`에 참조하려고 할 때는 에러가 발생하지 않는다.

```typescript
type Person = {
  name: string
  age: number
}

const person1 = {}
person1.name = "stella lee" // '{}' 형식에 'name' 속성이 없습니다.

// 타입 단언은 as 키워드를 사용한다.
const person2 = {} as Person
person.name = "stella kim"
```

## 타입 단언이 왜 위험한가?

타입 단언을 사용했을 때 왜 위험한지에 대해 알아보자.

아래 코드 블록의 경우, 타입스크립트는 컴파일 단계에서 에러를 발생시키지 않지만, 런타임 단계에서는 `person.name`이 `undefined`나 `null`이기 때문에 정의되지 않은 속성 `length`를 읽을 수 없다고 에러가 발생할 것이다.

```typescript
type Person = {
  name: string
  age: number
}

const person = {} as Person
person.name.length // Cannot read properties of undefined (reading 'length')
```

위 예제 코드처럼 타입 단언으로 타입을 강제했지만 런타임 단계에서 에러가 발생할 수도 있다. 특히, `any` 타입으로 단언하면 컴파일 단계에서 에러가 발생하지는 않지만, 런타임 단계에서 에러가 발생할 확률이 올라간다.

```typescript
const a = "123.5"
console.log(Math.round(a)) // Argument of type 'string' is not assignable to parameter of type 'number'

const b = "123.5"
console.log(Math.round(b as any).toString()) // "124"

const c = "abcd"
console.log(
  Math.round(c as any)
    .toString()
    .length()
) // Math.round(...).toString(...).length is not a function
```

첫 번째 예제는 변수 `a`에 `string` 타입인 `"123.5"`를 할당했다. 자바스크립트 빌트인 객체인 `Math`의 소수점에서 반올림하는 `round` 메서드는 `number` 타입만 받게 되어 있기 때문에 타입스크립트는 `string` 인수의 형식은 `number` 형식의 매개변수에 할당할 수 없다고 에러를 낸다.

두 번째 예제를 살펴보면 변수 `b`에 동일하게 `string` 타입인 `"123.5"`를 할당했고, `b as any`로 타입을 강제했기 때문에 컴파일 단계에서는 에러가 발생하지 않는다. 자바스크립트 엔진에 의해 `"123.5"`가 암묵적으로 `number` 타입으로 변환되어 런타임 단계에서 에러를 내지 않고 `"124"` 로 출력된다.

마지막 예제에서는 변수 `c`에 `string` 타입인 `"abcd"`를 할당했다. 그리고 `c as any`로 타입을 강제했기 때문에 이 코드는 컴파일 단계에서는 에러가 발생하지 않는다. 하지만 런타임 단계에서는 에러가 발생한다. 그 이유는, `Math.round(c as any)` 이 평가되어 계산된 결괏값이 `NaN` 이고, `NaN.toString()` 연산 역시 `NaN` 으로 평가되기 때문에 `NaN.toString().length()`를 호출하면 에러가 발생하기 때문이다.

이처럼 타입 단언을 사용하면 컴파일 단계에서는 에러가 발생하지 않지만, 개발자의 예상하지 못한 실수로 인해 런타임 단계에서 에러가 발생하고 코드의 실행은 중단될 것이다. 그렇기 때문에 개발자는 코드의 안정성을 보장하기 위해 타입 단언을 최소화하고, 타입스크립트가 타입을 제대로 추론할 수 있도록 코드를 작성해야 한다.

## 어떻게 해결 해야할까?

개발자는 컴파일 단계에서 타입의 안정성을 보장할 수 있도록 코드를 작성해야 한다. 해결 방법으로는 여러 가지 있겠지만 여기서는 세 가지 방법을 다루려고 한다.

### 타입 선언

아래 코드를 보면 `Person` 타입을 선언한 후 `kim`이라는 변수에는 타입 선언, `lee`라는 변수에는 타입 단언을 사용했다. 변수 `kim` 에는 `Person` 타입의 프로퍼티 외에 다른 프로퍼티 `age`를 추가했기 때문에 에러가 발생한다. 반면, 변수 `lee` 에는 `any`로 타입 단언했기 때문에 에러가 발생하지 않는다. 하지만, 분명히 우리가 살펴봤던 문제들이 발생할 여지가 있기 때문에 타입 선언을 사용해야 한다.

```typescript
type Person = {
  name: string
}

const kim: Person = { name: "dd", age: 1 } // Object literal may only specify known properties, and 'age' does not exist in type 'Person'.

const lee = { name: "dd", age: 1 } as Person
```

### typeof 연산자 이용

예를 들어 함수 `getSplitName`은 매개변수 `name`을 `string` 타입 또는 `undefined` 타입을 받는다고 가정하자. 함수 안에서 매개변수 `name`을 `typeof` 연산자를 이용하여 `string` 타입으로 좁혔다. `if`문 안에서 `name`은 무조건 `string` 타입이기 때문에 `name.split(" ")` 코드는 에러 없이 동작할 것이다. 하지만 `if`문 밖의 `name`은 여전히 `string` 타입이거나 `undefined` 타입이기 때문에 `name.split(" ")` 코드에서 `name` 은 `undefined` 일 수 있다고 컴파일 단계에서 에러가 발생할 것이다. 이렇게 `typeof` 연산자를 사용하여 타입을 좁혀나가면 컴파일 단계와 런타임 단계에서 코드의 안정성을 보장할 수 있다.

```typescript
function getSplitName(name: string | undefined) {
  if (typeof name === "string") {
    console.log(name.split(" ")) // ["stella", "kim"]
  }

  name.split(" ") // Error: 'name' is possibly 'undefined'
}

console.log(getSplitName("stella kim"))
```

### 타입 가드(Type Guard) 사용

아래 코드처럼 `isPerson` 함수는 `unknown` 타입인 인자를 받아 이 인자가 `Person` 타입인지 아닌지 가려낼 수 있게 해주는 함수다. 타입 가드를 사용하면 컴파일러가 타입을 예측할 수 있도록 조건문 안에서 타입을 좁혀 나가면서 타입의 안정성을 보장할 수 있다.

아래 코드에 있는 `isPlainObject` 함수는 `lodash` 라이브러리의 함수로 값이 일반 객체, 즉 객체 생성자에 의해 생성된 객체인지 아닌지 확인하는 함수이다.

```typescript
type Person = {
  name: string
  age: number
}

const isRecordType = (value: unknown): value is Record<string, unknown> =>
  isPlainObject(value)

const isPerson = (person: unknown): person is Person =>
  isRecordType(person) && typeof person.name === "string"

function getNameAndAge(person) {
  if (isPerson(person)) {
    return `${person.name}의 나이는 ${person.age}`
  }
}

const person: unknown = {
  name: "Kim",
  age: 30,
}

console.log(getNameAndAge(person))
```

이렇게 타입 단언 대신 단순한 몇 가지 방법으로 컴파일과 런타임 단계에서 안정성을 높일 수 있다.

## 결론

1. 런타임 단계에서 에러를 줄이기 위해 컴파일 단계에서 타입 안정성을 유지하는 것이 중요하다.
2. 타입 단언은 런타임 단계에서 예상치 못한 에러를 유발할 수 있으므로 신중하게 사용해야 한다.
3. 타입 단언보다는 타입 선언을 활용해 타입을 명시적으로 지정하는 것이 바람직하다.
   - 이는 컴파일러가 타입을 추론하도록 하는 것보다 안정적이다.
4. 조건문 내에서 타입 가드를 활용하여 추론되는 타입의 범위를 좁혀주면, 런타임 단계에서 코드의 안정성을 높일 수 있다.
5. 불가피하게 타입 단언을 사용해야 할 때는 주석을 추가해서 왜 그렇게 했는지 명시하자.
