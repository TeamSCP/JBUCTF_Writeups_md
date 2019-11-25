#  문제이름

babybof



## 문제

자! 단순하게 하나하나 개수 새면서 입력하는 것은 이제 질렸을 것입니다.

이번에는 python을 이용하여 input을 줘봅시다!



## 문제 취지

포너블 가이드에도 있는 python으로 input을 하는 방법을 보면서

직접 input을 하여 해당 방법에 익숙해지며, 또한 0xdeadbeef 를 맞추면서 리틀 앤디안 형식으로 input을 해주어야 한다는것을 알게한다.



## 풀이 방법

buf3 와 buf의 offset을 보면 항상 1200(10진수) 라는것을 알 수 있다

이것을 이용하여 1200개의 더미를 주고 deadbeef를 넘겨주어야 한다.

이때 리틀앤디언이기 때문에 ef be ad de 순으로 넘겨준다.



다음과 같이 실행하면 python으로 input을 하라는 것과 buf,buf2,buf3의 주소를 출력해준다.

![K-20191105-419790](https://user-images.githubusercontent.com/40850499/68176638-00e49300-ffc9-11e9-9548-16ecd27b5559.gif)



다음과 같이 exploit 코드를 짜면 

![K-20191105-455755](https://user-images.githubusercontent.com/40850499/68176753-69cc0b00-ffc9-11e9-9aee-b96cadd9b693.gif)



win함수가 실행되어 flag가 출력되려는것을 볼 수 있다.

![K-20191105-455821](https://user-images.githubusercontent.com/40850499/68176764-70f31900-ffc9-11e9-92a6-c76d5b4b18b0.gif)




## Flag

scpCTF{bbAbbyY_BufFEr_0vERf1oW}



## 힌트

0xdeadbeef는 리틀 앤디언으로 넘겨 주어야 합니다.