#  문제이름

easy_grep



## 문제

드디어 교수님의 서버의 침투를 성공했다!

 이곳에 숨겨진 파일 하나가 있다던대...



## 문제 취지

리눅스 명령어 grep or find를 실제로 사용해보자



## 풀이 방법

find secret -name flag

![K-20191021-023761](https://user-images.githubusercontent.com/40850499/67162139-446db900-f39c-11e9-8272-1868df199665.png)

grep -r "scp" *

![K-20191021-023287](https://user-images.githubusercontent.com/40850499/67162138-42a3f580-f39c-11e9-8451-85f9b97d0894.png)



깃허브는 빈 디렉토리 같은경우 안보여서 직접 만들어야 할것같음

mkdir -p ./directory{1..10}/directory{1..10}/directory{1..10}

으로 디렉토리를 만들고 directory3/directory6/direcctory9 안에 flag 파일 만들어둔다.


## Flag

scpCTF{N0w_yOu_cAn_6R3p_M3!}



## 힌트

grep 이나 find를 이용하시면 쉽게 찾을 수 있습니다!
