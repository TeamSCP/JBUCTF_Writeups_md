## 문제 이름

cookie monster



## 문제 설명

쿠키 값을 조작해서 문제를 풀어주세요!



## 문제 취지

1. 쿠키 값을 조작함으로 로그인을 할 수 있다는 사실을 알 수 있나요?

2. 인코딩 된 상태를 보면 디코딩을 떠올릴 수 있나요?

3. Fiddler를 사용해서 값을 조작할 수 있나요?



## 문제 풀이 

![21](https://user-images.githubusercontent.com/40850499/68562460-18ba8c00-048d-11ea-848f-205fb1924e6c.PNG)

문제에 들어가면 보이는 로그인 창에 임의의 id, password를 넣어주고 버튼을 눌러보지만, 버튼이 동작하지 않는다.



![22](https://user-images.githubusercontent.com/40850499/68562461-18ba8c00-048d-11ea-8742-691286598f8f.PNG)

코드를 확인해보면, php언어로 짜여진 코드가 힌트로 제공되고 있다.

cookie에 id와 password에 값이 존재하지 않는다면, 로그인 해달라는 요청이 뜨도록 되어있다.

그렇다면 쿠키에 id, password 값이 존재한다면 로그인을 해달라는 요청이 뜨지 않겠구나!



![23](https://user-images.githubusercontent.com/40850499/68562462-19532280-048d-11ea-81ae-e5babb7c0778.PNG)

editthiscookie 툴을 사용해서 확인해보니, 쿠키값이 어느 것도 존재하지 않는다는 것을 알 수 있다.



![24](https://user-images.githubusercontent.com/40850499/68562463-19532280-048d-11ea-986c-95809d6af0df.PNG)

그래서 쿠키에 id, password를 만들어주고 값은 임의의 값을 넣어주고 실행시켜보자.



![25](https://user-images.githubusercontent.com/40850499/68562464-19532280-048d-11ea-83b4-504017aa104b.PNG)

로그인이 성공했다는 문구가 뜬다.



![35](https://user-images.githubusercontent.com/40850499/68562644-e6f5f500-048d-11ea-8edf-671bbf14663e.PNG)

로그인 후 나타난 메인페이지는 이런 모습으로 있다.



![36](https://user-images.githubusercontent.com/40850499/68562800-8adfa080-048e-11ea-92b6-eb46a2d49543.PNG)

마찬가지로 쿠키값을 확인해보면 로그인 전에는 없던 flag라는 쿠키가 생겨있다. 

그런데 저 flag는 암호화가 되어있는 상태이다.

메인페이지에 쓰여있는 '난 뭐든지 2번 할꺼야' 라는 말처럼 2번 디코딩을 해줘야 한다.



![37](https://user-images.githubusercontent.com/40850499/68562802-8adfa080-048e-11ea-9365-83528693571b.PNG)

한번



![38](https://user-images.githubusercontent.com/40850499/68562803-8b783700-048e-11ea-9dcd-da3087991e79.PNG)

2번 base64 디코딩을 해주면 저런 문구가 flag라고 나온다. 



![40](https://user-images.githubusercontent.com/40850499/68562837-b9f61200-048e-11ea-99d1-90c4e214d380.PNG)

얻은 값을 넣고 확인을 누르면, '빈 값이 넘어왔습니다. Fiddler로 확인해보세요' 라는 문구가 뜬다.

분명 값을 넣어줬는데 왜 빈 값이지? 라는 의문을 갖고 Fiddler를 사용해보자.



![41](https://user-images.githubusercontent.com/40850499/68562883-f32e8200-048e-11ea-9a76-ded9fe2b4ef0.PNG)

passoword 값이 정말 빈 값으로 넘어가고 있다.



![42](https://user-images.githubusercontent.com/40850499/68562884-f32e8200-048e-11ea-8764-fc23d50ee0ff.PNG)

그렇다면 Fiddler에서 password 값을 빈 값이 아닌 아까 얻은 Flag_is_not_yours라는 값으로 변경해주자.

그리고 값을 보내보자.



![43](https://user-images.githubusercontent.com/40850499/68562885-f32e8200-048e-11ea-9e1b-0418359d71ef.PNG)

그러자 드디어 플래그가 나왔다.



## Flag

scpCTF{tH3r3_1s_N0t_R0Ya1_2_l3an1n9}



## 힌트

1. editthiscookie
2. fiddler

