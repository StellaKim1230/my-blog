---
title: 2020년 회고록
date: "2021-01-01"
description: "2020년을 돌아본다."
meta:
  - name: description
    content: 2020년을 돌아보는 어느 프런트엔드 개발자의 회고록
  - property: og:title
    content: 2020년 회고록
  - property: og:description
    content: 2020년 회고록, 프런트엔드 개발자 회고록, 회고
---

<h2 id="second-heading">들어가며</h2>

올 한해는 시간이 정말 빨리 흘러간 것 같다. 2Q까지는 이직 활동을 활발히 했었고 포기하려던 찰나에 이직했다. 코로나 덕분이라고 말할 수 있다. 매년 회고록에 이직 얘기를 하는 것 같지만, 그만큼 좋은 환경에서 일하기 위해서였다.

그리고 재테크, 다양한 스터디(글쓰기, 사내 기술, SD/UX)를 시작했다. 작년에 회고록을 작성하면서 세웠던 목표들을 많이 못 지켰고, 번아웃도 오면서 게으름도 많이 피웠지만 보람찬 한 해를 보낸 것 같다.

## 1. 이직, 코로나

1월부터 5월까지 이직 활동을 했다. 3월 말에 호텔 가격 비교 서비스를 만드는 곳에서 오퍼를 받았지만, 코로나로 인해 6개월 후에 입사가 가능하다는 연락을 받았다.

그렇게 입사하는 날만 기다리고 있었는데 갑자기 코로나 때문에 더 이상의 채용 프로세스 진행이 어려울 것 같다는 연락을 받았다. 이때 큰 번아웃이 왔고, 다니던 회사에서도 의욕 없이 일했던 것 같다. 이직 준비하는 것도 슬슬 지쳐갔다.

그렇지만, 기회는 반드시 찾아오기 마련이다. 5월 초에 남편과 지인을 통해서 코발트라는 회사를 소개받았고, 2020년 5월 11일에는 수석 개발자님과 티타임을 가졌다. 그때 서비스를 베타버전으로 출시했고, 팀 빌딩을 하는 상황이라고 들었다. 얘기를 들었을 때 회사의 안정성만 본다면 다니던 회사가 더 자리를 잡은 상태였다.

그런데도 이 회사에 지원한 이유는 대표님과 직원들의 능력, 쌓아온 경험, 그리고 회사 분위기였다. 여기서 일을 한다면 그토록 갈망하던 성장을 충분히 할 수 있을 것이라는 생각이 들었다. 게다가 서비스가 재미있을 것 같다는 느낌을 받았고, 새로운 도전이 될 것이 분명했다. 고민할 필요도 없이 2020년 7월 20일에 코발트에 조인했다.

## 2. 새로 참여한 프로젝트

케이플은 기업에 대한 정보, 투자 정보, 주주명부 등 많은 정보를 보여줘야 한다. 왜냐하면 투자사들이 기업에 투자하기 위해서는 이런 정보들을 통해서 투자 가치 여부를 판단하기 때문이다. 그래서 우리 회사는 필요한 몇 가지 기능들을 실험했다.

주로 실험한 서비스는 아래와 같다.

- <b>[비상장 주식 예약](https://caple.ai/reservations)</b>  
   사람들이 비상장 주식에 얼마나 관심을 두고 있는지 알기 위해 실험을 했다. 약 3주에 걸쳐서 실험한 것 같다. 우리도 광고를 처음 해보는 상황이어서 모든 것이 다 도전이었다. GA 연동, 페이스북 광고, Goole Ads 연동, 광고 성과 리포트에서 가장 보편적으로 보는 지표인 CPC, CPM, CTR을 분석했다.

  > - CPC(Cost per click) - 소비자가 광고를 1회 클릭할 때마다 발생하는 광고비용
  > - CPM(Cost per Mile) - 1000번 노출당 과금되는 방식
  > - CTR(Clic-through rate) - 온라인 광고를 100명에게 노출시켰을 때 몇 명이 클릭했는지 나타내는 지표

  처음에는 생각보다 사용자가 많지 않았다. GA를 분석해본 결과 다음 페이지로 이동을 안 했고, 스크롤 이벤트가 많이 안 일어났다. 우리는 첫 화면에 나오는 내용이 부족하고, 문구들이 너무 부담스러워서 사용자가 다음 페이지로 이동을 안 하는 것 같다고 결론을 내렸다. 그렇게 내린 결과를 토대로 다시 실험했다.

  사용자 수는 조금 늘었지만, 기대한 만큼 수치가 나오지는 않았다. 이번 실험을 통해서 서비스 홍보와 사용자 타깃을 어느 정도 확보했다고 생각하고 다음 서비스를 실험했다.

- <b>[스톡옵션 계산기](https://caple.ai/stockoption)</b>  
  다음 실험한 서비스는 스톡옵션 계산기다. 처음에는 스톡옵션 계산에 필요한 정보만 받아서 수동으로 보고서를 만들고 전달했다. 몇 번 보고서를 만들어 보니 작업이 반복되었고, 생각보다 많은사람들이 관심을 두고 있다고 판단했다. 그래서 우리는 사람들이 직접 스톡옵션 계산을 하고 바로 결과를 볼 수 있게 스톡옵션 계산기를 만들기로 했다. (이 시점부터 회사 블로그도 같이 운영했다. [케이플 블로그](https://blog.naver.com/cobaltrun/222147712838))

  기획부터 개발, 배포까지 약 3주가 걸렸다. 나는 개발을 하기 위해서 도메인 지식을 먼저 공부했다. 우리는 `행사조건 입력 > 행사 > 양도 > 세금계산 > 최종 결과` 의 흐름으로 기획했다. 간략히 설명하자면, 세금이 계산되는 시점은 행사 시점과 양도 시점이다. 우리가 내는 세금은 `장내/장외`와 `행사 시점/양도 시점`에 따라서 내는 세금이 많이 달라진다. 세금이 어떻게 달라지는지는 [회사 블로그](https://blog.naver.com/cobaltrun/222147712838)와 [서비스](https://caple.ai/stockoption)에서 직접 확인할 수 있다.

  실험 결과는 나쁘지 않았다. 처음 실험했던 비상장 주식 예약보다는 사용자도 꾸준히 들어오고 있다. 그 이유는 서비스 홍보도 어느 정도 되고, 광고 집행과 사용자 실험에 대해 우리가 지식이 쌓이고 있는 만큼 더 잘하고 있는 게 아닌가 싶다. 확실히 사용자 피드백도 있어서 그런지 더 나은 서비스를 만들게 되는 것 같다.

  이번 프로젝트는 나한테도 좋은 경험이었다. 예전에 회계팀에서 일했던 경험이 많은 도움이 되었다. 프로젝트 마무리도 잘했고, 앞으로 우리가 기획하는 서비스들도 더 잘 만들어야겠다는 동기부여도 됐다.

- <b>[투자 지분율 계산기](http://caple.ai/investment/stake)</b>  
  다음 프로젝트 들어가기 전에 한 가지를 더 실험하기로 했다. 투자 지분율 계산기 서비스다. 스톡옵션 계산기보다는 더 간단해서, 기획부터 개발까지 1주일이 걸렸다. 글 쓰는 시점 2021년 1월 3일 일요일인 지금은 배포가 아직 안 되었고, 내일 출근하면 배포하지 않을까 싶다.

  이 실험 또한 기대된다.

## 3. 재테크 시작

소소한 이슈가 있었다면 남편과 재테크를 시작했다. 처음에는 적금만으로 돈을 모으고, 어떻게 노후 준비를 해야 될지 둘이서 한참 고민했다. 그러던 와중에 youtube에서 어떤 분이 [재테크](https://www.youtube.com/channel/UCr7XsrSrvAn_WcU4kF99bbQ)에 대해 자세히 설명해 놓은 채널을 찾았다. 퇴근하고 둘이서 매일 이것만 봤던 것 같다.

그러면서 시작한 게 연금저축이다. 알고 보니 우리가 들어놓은 상품은 소득공제도 못 받는 저축보험이었다. 그래서 소득공제 혜택부터 받기 위해 연금저축을 시작했다. 연금저축과 IRP가 무엇인지, 소득공제는 얼마만큼 받을 수 있는지, 절세 등에 대한 자세한 내용은 위 영상에 잘 설명되어있다.

연금저축과 더불어 주식을 시작했다. 우리의 투자성향을 분석한 결과 안정 추구형에 속했고, 장기투자를 원해서 해외 ETF로 시작했다. 그렇게 반년 정도 주식에 대해 알아가다 보니 생각보다 공부할 게 많고, 공부 안 하고 시작했다간 망하기 딱 좋을 것 같다고 생각하기도 했다.

재테크는 이제 막 시작단계여서 작성할 내용이 많지는 않지만, 그래도 나름 2020년의 우리에게 변화를 가져다 준 이슈였다.

## 4. 참여한 스터디

혼자서 뭘 하려니 잘 하지도 않고 마무리도 잘하지 못해서, 동기부여를 얻기 위해 여러 스터디에 참여하게 되었다.
코로나와 바쁜 업무로 인해 사내 스터디, SD/UX 스터디는 중간에 몇 번 못했지만, 다행히 꾸준히 잘 이어지고 있다.

- <b>사내 스터디</b>  
  처음에는 알고리즘 스터디를 시작했다. 일주일에 3문제씩 풀어와서 코드를 공유하고 페어하면서 리팩토링도 같이했다. 좋았던 것이 몇 가지 있는데 그중 새로운 언어(Python)를 공부했고, 동료들 덕분에 몰랐던 알고리즘 기법에 대해서 알게 되었다는 것이다. 정리하지 않으면 잊어버릴 것 같아 공부한 내용([트라이 알고리즘](https://wiki.jieunkim.site/Algorithm/01.trie.html))을 블로그에 작성하기도 했다.

  어느 정도 스터디가 진행되었을 때, 수석 개발자님께서 당장 우리에게 필요한 것은 알고리즘이 아닌 우리 서비스와 관련 있는 기술을 공부하는 것 같다고 말씀하셨다. 그래서 우리는 스터디의 방향을 바꾸어 파트별로 공부하고 싶은 기술을 정리하고, 일주일에 한 시간씩 공부한 내용을 공유했다.

  잘 진행했던 기술 스터디도 코로나 때문에 잠시 중단되었다. 조만간 온라인으로라도 스터디를 시작하자고 제안해볼 생각이다.

- <b>SD/UX 스터디</b>  
  공유 오피스 내의 사람들을 대상으로 한 SD/UX 스터디원 모집 공고를 보자마자 가입을 신청했다. 이 스터디는 각자 주제를 정하고 발표 후 토론하는 방식으로 진행했다. 사실 스터디를 가입한 이유 중에 하나가 발표 연습을 하기 위해서였기 때문에 나에게는 괜찮았다고 생각한다. 11월 초에 디자이너, 기획자, 프런트엔드 개발자 다양한 직군이 모인 7명의 인원으로 시작했고, 코로나 때문에 잠시 쉬었지만, 온라인 모임으로 다시 진행되었다.

  지금까지 스터디에서 공유된 내용은 서비스 디자인, 후기 작성 UI/UX, Retention, 사용성 테스트, 인터페이스 없는 인터페이스, 게슈탈트 이론, UX Writing System, Hindsight bias 등 모르고 있던 다양한 개념들을 알게 되었다. 특히 많은 직군이 모여 하나의 주제로 토론을 하는 것이 생각보다 재미있었다. 서로가 고민하는 부분과 경험담을 공유하는 것이 중요한 것 같다.

- <b>글또 스터디</b>  
  남편의 추천으로 글 쓰는 스터디(글또 5기)를 시작했다. 글은 써보고 싶은데 작성이랑 마무리가 잘 안 된다고 했더니, 이 스터디를 추천해줬다. 남편도 글또 1기에 참여하면서 글 쓰는 좋은 습관이 생겨서 지금까지 꾸준히 쓰고 있다고 했다. (본인도 처음에는 잘 못 썼고, 시간도 오래 걸렸다고 한다)

  스터디 진행방식을 설명하자면, 100,000원의 예치금을 납부하고 6개월 기간의 2주에 걸쳐 글을 하나씩 배포한다. 물론 약속을 못 지키면 페널티도 부여한다. 블로그를 개설한 지 2년이 되어가는데 3개 밖에 없던 글이 6개로 늘어났다. 그리고 공유한 글에 대해 매주 한사람이 두 명의 글을 읽고 피드백을 준다.

  직접 해보니 2주마다 글을 배포하는 것은 생각보다 어려운 작업이라는 생각이 든다. 그렇지만 마지막까지 꾸준히 글을 작성할 생각이다.

## 5. 마치며

늦었지만, 시니어 개발자가 되기 위해서 준비를 해야겠다. 2021년이면 6년 차 개발자가 된다. (SI 경력을 빼고 싶지만, 이 경력도 무시 못 하기에) "몇 년 차 개발자에요?" 이 질문이 제일 안받고 싶은 질문이었다.~~현실을 부정하고 싶었다~~.

갑자기 연말에 남편이 문득 "당신도 내년이면 벌써 6년 차 개발자네?" 했을 때 이제는 받아들여야 할 때가 온 거 같다.

- <b>아쉬웠던 점</b>

  - 2019년 말에 세웠던 2020년 목표
    - 토이프로젝트 배포
    - 하루 1커밋 (잔디심기)
    - 독서
    - 다른 언어 공부
    - 글쓰기
    - 십자수
    - 운동
    - 짬짬영어

  하나씩 체크를 해보자니 해놓은 게 아무것도 없다. 굳이 한 것을 따지자면 운동(필라테스), 독서(3~4권), 다른 언어 공부(알고리즘을 파이썬으로 풀기) 이 정도인 것 같다. 역시 회고록 작성은 나를 반성하게 된다.

- <b>내년 목표</b>

  - 독서 (10권 이상)
  - 블로그 (15회 이상)
  - 토이프로젝트
  - 운동 (필라테스 & 라이딩)
  - Web Accessibility, Semantic Web (깊이있게 공부해보기)
  - AWS, 네트워크, 브라우저 동작 등 기초 다지기
  - 동료와 페어프로그래밍 하는 시간 많이 갖기
  - 영어단어 외우기

2021년에는 우리 팀이 성장할 수 있는 방향으로 고민하고, 시니어 개발자가 되기 위해서 준비하는 해가 될 것 같다.
