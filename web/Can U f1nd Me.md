## Can U f1nd Me?



## 문제 소개



![15](https://user-images.githubusercontent.com/40850499/66388671-9c520a80-ea01-11e9-9925-4a1c1232ea8e.PNG)

URL에 취약점이 존재하는 웹 사이트를 보고 directory listing 취약점을 알 수 있는지 확인한 후, 간단한 javascript 코드를 이해할 수 있는지를 확인하는 문제



##  풀이 방법

![15](https://user-images.githubusercontent.com/40850499/66388875-036fbf00-ea02-11e9-920a-3570203f93c0.PNG)

url = 127.0.0.1/listing/home.html



![16](https://user-images.githubusercontent.com/40850499/66388876-04085580-ea02-11e9-9a60-aff365265239.PNG)

url = 127.0.0.1/listing/about.html



![17](https://user-images.githubusercontent.com/40850499/66388877-04085580-ea02-11e9-88e2-2e56c8f85aac.PNG)

url = 127.0.0.1/listing/contact.html

버튼을 누르고 페이지가 변경될때마다 url이 변경되는데 모두 일정하게 127.0.0.1/listing 이후의 파일이 변경이 된다.



![18](https://user-images.githubusercontent.com/40850499/66388878-04085580-ea02-11e9-9244-d9c15e44d4c0.PNG)

그래서 directory listing이 존재할 것이라는 추측으로 파일명을 지워서 디렉토리만 남겨주자 예상대로 directort listing 취약점이 발생한다.



리스트 중 누가봐도 수상한 flag.php를 눌러보면 문제가 나온다.

![19](https://user-images.githubusercontent.com/40850499/66388879-04a0ec00-ea02-11e9-88ef-7f3460ce8241.PNG)

비밀번호를 입력하라는 화면이 나온다.



![20](https://user-images.githubusercontent.com/40850499/66388880-04a0ec00-ea02-11e9-8498-b6537b813a5c.PNG)

코드를 읽어보면 간단한 javascript 소스가 보인다.



> substring - 문자열의 길이를 기준으로 자른다고 표현하기보다는 일정 문자열을 반환하는 함수
>
>
>
> substring(시작인덱스, 종료인덱스);
>
> ex ) var string = '1997-01-07';
>
> ​       var year = string.substring(0,4) //1997
>
> ​       var month = string.substring(5,7) //01 
>
> ​       var month = string.substring(8,10) //07 



그래서 if(check.substring(0,str) == 'scpC') { } //이게 참이 되려면 0에서 3까지의 문자열이 scpC 가 되어야하는 것이다.



마찬가지로 다음  if(check.substring(str*4,str*5) == 'scpC') { } 가 참이 되려면 16에서 19까지의 문자열이 nNY_가 되어야 한다.



모든 코드를 다 읽어보면 0~3 - scpC

16~19 - nNY_

24~17 - hAcK

12~15 - _Fun

20~23 - W3B_

4~7 - TF{s

8~11 - S00o

28~31 – 1n9}



이걸 순서대로 정리해보면 



0~3 – scpC

4~7 - TF{s

8~11 - S00o

12~15 - _Fun

16~19 - nNY_

20~23 - W3B_

24~17 - hAcK

28~31 - 1n9}



scpCTF{sS00o_FunnNY_W3B_hAcK1n9}



## flag

scpCTF{sS00o_FunnNY_W3B_hAcK1n9}



## 힌트

페이지가 바뀔때마다 변하는게 있듯이 변하지 않는 것도 있어!



