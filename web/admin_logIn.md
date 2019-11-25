## 문제 이름

admin_logIn


## 문제 설명

sql injection 문제에 기초적인 암호화를 더한 문제

## 문제 취지

sql query문을 보면 sql 취약점을 알 수 있는지 확인
모르는 부분에 대해서는 구글링을 할 수 있는지 확인


## 풀이 방법

![13](https://user-images.githubusercontent.com/40850499/66329993-762d5b80-e96a-11e9-8eba-a99bc70177b5.PNG)

메뉴바 누르고 Admin Login으로 이동



![1](https://user-images.githubusercontent.com/40850499/66329975-73cb0180-e96a-11e9-90d2-fcd7b5ee4717.PNG)

이렇게 password를 입력하는 창이 나온다.



![2](https://user-images.githubusercontent.com/40850499/66329976-73cb0180-e96a-11e9-9420-934055ab4597.PNG)

먼저 password를 입력해본다.



![3](https://user-images.githubusercontent.com/40850499/66329977-73cb0180-e96a-11e9-8675-27066776972f.PNG)

로그인 버튼을 누르면 화면에 다음과 같은 내용이 나타난다.

password에는 내가 입력한 password라는 값이 들어가있는데 sql query에는 왠 처음보는 cnffjbeq라는 글자가 들어가있다.

일단 여기서 두가지를 알 수 있다.

> 1. sql query문에서 취약점을 찾을 수 있는 것을 보니 sql injection 문제인것 같다.
> 2. 입력한 password가 쿼리문에 들어갈때 cnffjbeq로 변조되는 것 같다.





![4](https://user-images.githubusercontent.com/40850499/66329978-73cb0180-e96a-11e9-9d54-94479d939ae5.PNG)

그래서 sql injection 대표적인 구문들을 찾아보면 ' or '1'='1 이런 것이 나온다.



![9](https://user-images.githubusercontent.com/40850499/66329984-7594c500-e96a-11e9-9e7a-8609734359ee.PNG)

그래서 password에 ' or '1'='1을 넣어보자 이번에는 쿼리문에 ' be '1'='1로 변조되어 들어간 것을 알 수 있다.



![7](https://user-images.githubusercontent.com/40850499/66329981-74fc2e80-e96a-11e9-85a2-a0bc54daed5b.PNG)

그래서 좀 전에 password를 입력했을때 변조되어 나왔던 값을 구글링해보니 친절하게 복호화 사이트가 나온다.



![8](https://user-images.githubusercontent.com/40850499/66329983-74fc2e80-e96a-11e9-986f-8fd3b828a4a8.PNG)

사이트에 cnffjbeq를 넣고 복호화해보니 password라는 값이 나온다.



자 그렇다면 우리는 쿼리문에 들어갈 값이 ' or '1'='1 가 되게 하기 위해서 암호화된 상태가 ' or '1'='1인 것을 찾아야 한다.





![10](https://user-images.githubusercontent.com/40850499/66329988-7594c500-e96a-11e9-8391-1d9f7f1e0993.PNG)



![12](https://user-images.githubusercontent.com/40850499/66329990-762d5b80-e96a-11e9-8f56-78cd6feb16ba.PNG)

바로 ' be '1'='1이라는 구문.

이것을 password에 넣어주면 플래그가 나온다.







## Flag

scpCTF{HacK1n9_15_d1ff1CU17}



## 힌트

scp <-> fpc

