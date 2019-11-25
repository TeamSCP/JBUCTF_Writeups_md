#  문제이름

find_key



## 문제

hacker가 admin의 홈 디렉토리에 한 파일안에 flag를 숨겨두으며, admin의 패스워드 또한 user의 홈 디렉토리 어딘가에 숨겨놓았다고한다.

이것을 찾아 admin으로 로그인 하여 flag를 얻어라!



ssh 114.71.240.152  port 12370

id:user 	pswd:guest



## 문제 취지

기본적인 리눅스 명령어 ls,cat 과  ls의 옵션 사용

리눅스에는 이름앞.으로 숨겨진 파일이 된다는것을 인식

grep을 이용하여 특정 단어가 포함된 문자열을 추출 할 수 있다는것을 인식



## 풀이 방법

1. id:user/pswd:guest 	ssh접속

   ![주석 2019-11-04 130641](https://user-images.githubusercontent.com/40850499/68099207-79355080-ff04-11e9-8126-bd32517e1208.png)

2. ls  -al 로 숨겨진 passwd파일을 찾는다.

   ![주석 2019-11-04 130720](https://user-images.githubusercontent.com/40850499/68099196-67ec4400-ff04-11e9-8b6b-ff6c1445976c.png)

3. passwd파일을 읽어 admin으로 로그인한다.

   ![주석 2019-11-04 130829](https://user-images.githubusercontent.com/40850499/68099238-aaae1c00-ff04-11e9-941f-975f9bea78ae.png)

4. flag파일을 읽으면 다음과 같이 더미로 flag를 찾기 힘들다.

   ![주석 2019-11-04 130851](https://user-images.githubusercontent.com/40850499/68099270-dfba6e80-ff04-11e9-8924-445339dd73b8.png)

5. grep을 이용해서 간단하게 flag를 찾는다

   ![주석 2019-11-04 130913](https://user-images.githubusercontent.com/40850499/68099292-05e00e80-ff05-11e9-82dd-16acb02c1f7a.png)


## Flag

 scpCTF{Gr2AT_sKi11S!.!} 



## 힌트

ls에는 숨긴 파일을 볼 수 있는 옵션이 있습니다.

flag는 grep을 이용하면 더욱 편하게 찾을 수 있습니다.