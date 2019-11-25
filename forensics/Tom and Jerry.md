## **문제 이름**

Tom and Jerry



## 문제 

제리를 찾아주세요!



## 문제 취지

본 문제는 png 파일 안에 jpg 파일이 들어있다.

파일 시그니처와 스테가노그래피에 대한 기초적인 학습과 파일 카빙에 대해 학습하는 문제이다. 



## 풀이 방법

주어진 압축 파일을 풀어주면 고양이 톰의 사진이 나온다.
![image](https://user-images.githubusercontent.com/40850499/67742631-faea3180-fa5f-11e9-986f-82ce4e6dcf7e.png)

하지만 문제에서는 제리를 찾아달라고 하였고, 힌트로 주어진 텍스트 파일에 HxD와 png 그리고 jpg라는 텍스트가 있다.

주어진 힌트를 다 조합해보면 HxD라는 도구로 분석, PNG파일과 JPG 파일이 안에 같이 들어있고, 톰의 사진이 PNG인 것으로 보아 제리는 JPG 파일인 것으로 보인다.

본 문제를 풀기 위해 파일 시그니처라는 기본적인 내용을 알아야 문제를 해결할 수 있다.

PNG의 헤더 시그니처는 89 50 4E 47 0D 0A 1A 0A 이다.

![image](https://user-images.githubusercontent.com/40850499/67742641-fe7db880-fa5f-11e9-9825-9e2d4ea9f9a1.png)

파일을 HxD로 보았을 때, 처음 내용이다. 

이 부분은 PNG의 헤더 시그니처를 의미한다.

![image](https://user-images.githubusercontent.com/40850499/67742692-16edd300-fa60-11e9-83e6-607a07d23bdb.png)

하지만 끝나는 시그니처는 FF D9이다.

FF D9는 JPG의 푸터 시그니처이다.

추측해보면 PNG 파일과 JPG 파일이 합쳐져 있는 것으로 볼 수 있다.

여기서 문제를 풀기 위해서는 JPG의 헤더 시그니처와 푸터 시그니처까지 드래그하여 JPG 파일만 뽑아내면 된다.

JPG의 헤더 시그니처는 FF D8 FF E0으로 시작한다.

찾기 기능을 통해 FF D8 FF E0의 헥스 값을 찾아준다.

![image](https://user-images.githubusercontent.com/40850499/67742704-1ce3b400-fa60-11e9-9887-963d6275b7a5.png)

![image](https://user-images.githubusercontent.com/40850499/67742711-21a86800-fa60-11e9-9530-effbc065e53b.png)

찾기를 통해 JPG의 헤더 시그니처가 있는 곳으로 바로 이동할 수 있다.

여기서 밑에 블록을 잘 보고 있어야 한다.

처음 시작하는 값인 199C0을 기억하고, 맨 밑으로 이동한다.

맨 밑의 FF D9의 헥스 값은 5205F이다.

블록을 더블 클릭하고, 방금 기억했던 199C0을 오프셋 시작, 5205F를 오프셋 종료 값에 입력해준다.

![image](https://user-images.githubusercontent.com/40850499/67742715-23722b80-fa60-11e9-9476-366c1f0f2402.png)

수락을 누르면 JPG 파일의 데이터 값만 드래그된다.

바로 복사를 누르고, 왼쪽 상단에 파일에서 새로를 클릭하고 붙여넣기를 해준다.

그리고 다른 이름으로 저장을 누르고, 파일 이름 뒤에 .jpg를 써주고 저장을 하면 jpg 파일 형태로 저장된다.

![image](https://user-images.githubusercontent.com/40850499/67742722-28cf7600-fa60-11e9-87d8-222297fdacdf.png)

그러면 제리를 찾을 수 있고, 밑에 플래그 값이 나온다.



## Flag

scpCTF{T0M_ &_ J3rrY!!}



## 힌트

png와 jpg의 파일 시그니처를 확인해보세요~

검색은 Gooooooooooooooooooooooooooooooogle~


