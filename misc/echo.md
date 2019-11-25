#  문제이름

echo



## 문제

만드는 시간은 1시간이 걸렸지만,, 여러분들이 풀이하는데는 1분도 안걸릴거에요...

출력해주는 숫자를 1000번 그대로 되돌려 주시면 flag를 드립니다.



## 문제 취지

문제의 논리는 간단하다. 1000번 출력되는 난수를 그대로 받아서 재전송 해주면 flag를 출력한다.

하지만 이를 손으로 하기에 어려운것이 사실이다.

따라서 간단한 프로그래밍을 통해 문제 풀이를 하는 것이 이 문제의 핵심이다.

문제는 소스코드와 바이너리는 제공하지 않고, nc로 접근만 가능하게 할 것이다.



## 풀이 방법

```python
from pwn import *

p = process('./echo')

p.recvuntil('times.\n\n')
for i in range(1000):
	if i == 0:
		tmp = p.recv(1)
	else :
		p.recvuntil('>> ')
		tmp = p.recv(1)
	p.sendline(tmp)

print p.recvall()
```



## Flag

scpCTF{Y0u_are_a_9re4t_pr0gramm3r!}



## 힌트

python 소켓이나 pwntool을 이용하시면 좋습니다. ^^7
