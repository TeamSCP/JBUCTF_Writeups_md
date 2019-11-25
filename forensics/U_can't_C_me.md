# 문제 이름 : U can't C me - ??pt

## 문제

![image](https://user-images.githubusercontent.com/40850499/66596885-bbef5b80-ebd8-11e9-9b3a-e4f38bfece48.png)

당신은 절대 이 사진을 볼 수 없습니다!!!

당신의 귀는 눈의 역할을 할 수 있습니까?



## 문제 취지

파일 시그니쳐를 통해 (또는 리눅스의 file이라는 명령어를 통해) 무슨 파일인지 알아낼 수 있는가?

음성 파일의 스펙트럼을 분석할 수 있는가?



## 풀이 방법

![image](https://user-images.githubusercontent.com/40850499/66595455-f60b2e00-ebd5-11e9-9750-a78f0821c8c3.png)

![image](https://user-images.githubusercontent.com/40850499/66595537-1dfa9180-ebd6-11e9-9515-046cf712f17f.png)

위처럼 file 명령어를 통해서, 또는 hex editor를 통해 해당 파일이 wav 파일임을 알 수 있다.

파일을 wav로 바꿔 소리를 들어 보면 새소리 같은게 난다. audacity를 힌트로 주었기 때문에 audacity의 기능을 검색해 보거나 하면 spectrogram을 통해 각 주파수 대역의 세기를 알 수 있는 것을 알게 될 것이다.

![image](https://user-images.githubusercontent.com/40850499/66596029-1ab3d580-ebd7-11e9-9c8a-e645d32d7138.png)

Audacity로 열게되면 다음과 같은 상태이다.

![image](https://user-images.githubusercontent.com/40850499/66596120-446cfc80-ebd7-11e9-9a8e-6cb3fe328e08.png)

스펙트로그램을 사용하게 되면 다음과 같이 나오고 플래그를 획득할 수 있다.

![image](https://user-images.githubusercontent.com/40850499/66596198-6ebeba00-ebd7-11e9-85eb-e69a0fe3c97b.png)

이 외에도 소리파일을 사진으로 변환해주는 온라인 툴들을 이용하여도 풀 수 있다.



## Flag

scpCTF{c0nv3R7_t0_p1ctur3}



## 힌트

무슨 파일인지 모르겠을 때 사용하는 명령어가 존재합니다! 아니면, 파일의 시그니처를 확인해 보세요!

Audacity 라는 좋은 포렌식 툴이 존재합니다. Audacity에는 여러가지 기능(pitch 조절, 반전, 늘이기, spectrogram 등)이 있습니다.