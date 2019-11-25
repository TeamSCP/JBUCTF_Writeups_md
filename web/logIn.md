##   문제 이름

logIn



##   문제 설명

ID, PW가 공개되어있다.

로그인만 하면 되는데 ID,PW를 입력할 폼이 존재하지 않는다?

개발자 너! 이 페이지 잘못 만든거 아니야?



##  문제 취지

이병천 교수님의 웹 프로그래밍 시간에 배웠던 html태그에 대해서 얼마나 이해하고 있는가?

input태그를 이용해 입력 폼을 만들 수 있나?



##  풀이 방법

![3333](https://user-images.githubusercontent.com/40850499/66186664-d3e94b80-e6bd-11e9-80e9-a3e3d48528bd.PNG)

이번 문제는 ID, PW가 모두 주어져있다. 

로그인하기 버튼을 눌러보면 틀렸다는 문구가 나온다.

그렇다면 주어진 ID, PW로 로그인을 하려하는데 로그인 폼이 존재하지 않는 것을 알 수 있다.



![lklk](https://user-images.githubusercontent.com/40850499/66186777-1ad74100-e6be-11e9-87a9-b6278cd84f00.PNG)

그래서 개발자 모드를 켜고 코드를 읽어보니 값을 POST 형식으로 넘겨주는 것이 나온다. 

그렇다면 우리는 로그인 폼만 만들어주면 되겠다.



![lil](https://user-images.githubusercontent.com/40850499/66186814-380c0f80-e6be-11e9-975c-9e9dc93d0d13.PNG)

input 태그를 이용해서 ID, PW를 입력할 두개의 폼을 만들어준다.



![kl](https://user-images.githubusercontent.com/40850499/66186852-53771a80-e6be-11e9-93f1-8a195b8fddeb.PNG)

그러면 이렇게 로그인 폼이 생기고 ID에 admin, PW에 12345를 입력해주면 플래그가 나온다.



## Flag

scpCTF{NULL_J0ah3_Po_ManS3}



## 힌트

개발자가 드라마를 보느라고 개발에 집중을 못했다...ㅎ....
