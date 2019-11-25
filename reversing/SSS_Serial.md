## **문제 이름**

SSS_Serial



## 문제 

최고의 보안 소프트웨어를 손에 얻었지만 체험판기간이 끝나고 만 당신!

괜찮다. 당신의 최고의 해커니까. 분석을 통해 제품키를 얻어보자.

scpCTF{[Input Key]}

## 문제 취지


<img width="460" alt="12" src="https://user-images.githubusercontent.com/40850499/68067810-e4a9e180-fd8f-11e9-973e-999350e2680d.PNG">

<img width="466" alt="1" src="https://user-images.githubusercontent.com/40850499/68067812-e5427800-fd8f-11e9-81f5-a5a7bf0f18f7.PNG">

쉬운 난이도의 리버싱이다. 프로그램을 분석하는 스킬을 기르며 cmp, push와 같은 어셈블리 구문의 기초적 의미를 배우고, break point의 사용법을 공부할 수 있다.

strcmp를 통해 플래그와 인풋값을 비교하게 해놓았으며 cmp 구문의 의미를 알고 적절한 break point의 사용을 통해 플래그를 쉽게 찾아낼 수 있다.

## 풀이 방법

<img width="532" alt="123" src="https://user-images.githubusercontent.com/40850499/68067813-e673a500-fd8f-11e9-93f0-ed383d2b994a.PNG">

ollydbg에서 입력받는 부분에 break point를 걸고 f8을 통해 하나하나 찾아가다보면 키와 입력값을 비교하는 부분을 확인할 수 있고 플래그를 획득가능하다.

## Flag

 scpCTF{n0_m0r3_ch3at_k3y}



## 힌트

입력을 받으면 비교란걸 할거란 말이지?
