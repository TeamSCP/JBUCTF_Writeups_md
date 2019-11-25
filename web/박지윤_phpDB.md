## 문제 이름

phpDB



## 문제 설명

두개의 문제가 숨겨져있다.

1번은 html 코드를 보고 제한을 없앨 수 있어야하는 문제이고 

2번은 PHP와 mysql의 차이점을 알 수 있어야 풀 수 있는 문제이다.



## 문제 취지

코드를 보고 설정되어 있는 제한을 변경할 수 있는지, PHP는 대소문자를 구분하지만 mysql은 대소문자를 구분하지 않는 것을 알고 있는지 확인



## 풀이 방법

![1](https://user-images.githubusercontent.com/40850499/66733475-ac069e80-ee9a-11e9-8588-3f53514158fc.PNG)



패스워드는 password123 이라고 공개되어 있는 페이지가 있다.



![2](https://user-images.githubusercontent.com/40850499/66799810-9d2cf400-ef4d-11e9-8a06-8423ab7c5eeb.PNG)

공개되어 있는대로 패스워드에 password123을 입력하려하는데 패스워드가 5자리 이상은 입력이 되지를 않는다.

코드를 확인해보면 input 태그 안에 maxlength="5"로 설정이 되어있는 것을 알 수 있다.



![3](https://user-images.githubusercontent.com/40850499/66799811-9d2cf400-ef4d-11e9-817f-79a2b6e94da6.PNG)

최대 5자리 입력 제한을 풀어주기 위해서 maxlength의 숫자를 크게 바꿔준다.



![4](https://user-images.githubusercontent.com/40850499/66799812-9d2cf400-ef4d-11e9-9657-7ebdbe081197.PNG)

그리고 패스워드에 password123을 입력했는데 틀렸다는 답이 나온다.



왜냐하면?

패스워드를 입력하고 값이 넘어가는 부분에 password123이 로그인 되지 못하게 하는 필터링을 걸어두었기 때문이다.



![5](https://user-images.githubusercontent.com/40850499/66799813-9dc58a80-ef4d-11e9-9a3e-41ed11a6f431.PNG)

그래서 password123으로 로그인을 하기 위해서 PHP는 대,소문자를 구분하지만 mysql은 대,소문자를 구분하지 않는다는 취약점을 이용하여

패스워드에 대,소문자를 섞어 PassWord123을 입력하자 플래그가 나온다.



## Flag

scpCTF{D0_2_kN0w_Php_N_D6_N_Ht3L}



## 힌트 

1. 여기에는 두개의 문제점이 존재합니다.

2. PHP는 할 수 있지만, mysql은 할 수 없어요!



