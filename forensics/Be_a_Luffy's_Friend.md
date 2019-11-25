# Be a Luffy's Friend- ??pt

## 문제 

밀집 모자 해적단의 대장인 루피가 선원을 모집합니다.

![루피에 대한 이미지 검색결과](http://img.chuing.net/g/?id=mvs&no=36817&num=0&fc=d41d8cd98f00b204e9800998ecf8427e)

자격 조건

1) 일반 휴먼일 것

2) 이 문제를 해결할 것

## 문제 취지

파일 시그니처를 이해할 수 있는가?

Base 64를 구분할 수 있는가?

## 풀이 방법

문제에서 제시한 PNG 파일을 같이 넣어준 HxD 에디터에서 열어보고 파일 시그니처를 확인해보면 PPTX라는 것을 확인할 수 있다.

![image](https://user-images.githubusercontent.com/40850499/66637410-edeed500-ec4d-11e9-8cdb-e9ba823b4ea0.png)

파일의 첫 부분을 보면 50 4B 03 04이다. 이 것을 검색해보면 pptx 확장자라는 것을 확인할 수 있으며

확장자를 변경 후 파일을 열어보면

![image](https://user-images.githubusercontent.com/40850499/66639478-dd405e00-ec51-11e9-8d15-ac22eb273fd1.png)

이러한 화면을 마주할 것이다. 여기서 기존의 그림과 비교하면 코 부분이 다른 것을 확인할 수 있는데 코부분을 확인해보면 텍스트 인것을 확인할 수 있다. 이 텍스트는 그냥 텍스트와 다를 것이다.

이 텍스트는 Base64로 인코딩된 텍스트다. 이 텍스트를 디코딩하면 플래그를 얻을 수 있다.

![image](https://user-images.githubusercontent.com/48209839/67223908-1a36fc80-f46b-11e9-9e06-c2e75e1dec02.png)

## Flag

scpCTF{thi5_i5_g3n3r4l_b4se64_probl3m}

## 힌트

구글에 파일 시그니쳐를 검색해보세요! =로 끝나는 문자열?

