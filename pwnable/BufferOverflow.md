#  문제이름

BufferOverflow



## 문제

Bufferoverflow 를 체험해보기 위한 문제입니다.

가장 기본적이고 overflow를 이해하기 위한 문제이니 꼭 풀어봐 주세요.

nc 접속 후 글을 자세히 읽어 봐주시길 바랍니다.



nc 114.71.240.152 12355

## 문제 취지

사람들이 익숙치 않은 bof에 대해 이해를 시키기 위한 문제



## 풀이 방법

다음 출력대로 문자 5개를 입력한다.

![K-20191104-748407](https://user-images.githubusercontent.com/40850499/68118886-8114e500-ff44-11e9-94df-1dadfa2d0dcd.gif)

다음과 같이 주소와 버퍼 값을 알려주며 이번에는 10개를 입력하여 오버플로우를 발생시킨다.

![K-20191104-748544](https://user-images.githubusercontent.com/40850499/68118888-82dea880-ff44-11e9-8da4-a61deb2b1a5b.gif)



다음과 같이 오버플로우가 일어났다고 알려주며 buf2[2] = s, buf2[3] = c, buf2[4] = p 를 들어가도록 입력하라고 알려준다

![K-20191104-748709](https://user-images.githubusercontent.com/40850499/68118893-84a86c00-ff44-11e9-9bd6-f9ea8fa6dd9e.gif)

아무 문자 7개와 scp를 입력하면 flag가 출력된다.

![K-20191104-748831](https://user-images.githubusercontent.com/40850499/68118896-85d99900-ff44-11e9-9b23-766dae8487aa.gif)


## Flag

scpCTF{wE1_C0mE_BOf!!!}



## 힌트

없음
