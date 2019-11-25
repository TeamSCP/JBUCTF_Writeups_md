# asm1 - ??pt

## 문제

바이너리를 objdump 명령어를 이용하여 알아보았더니 다음과 같은 어셈블리 코드를 얻을 수 있었습니다!! asm1(0xab,0xcd) 은 무엇을 반환하나요? 플래그를 제출형식에 맞게 16진수 형식으로 제출하세요!!('0x'로 시작하는 문자열로 제출!)



## 문제 취지

3학년 수업으로도 있는 리버스 엔지니어링을 이용하여 문제를 내보았다. 학교에서 배운 지식을 이용해 풀 수 있고, 실제로 소스 코드가 주어지지 않은 상황에서는 어셈블리를 읽어 하므로 그 능력을 키울 수 있게 하기 위하여 출제.

상세 : 

반복문을 이해할 수 있는가?

카운트 한 값을 인자1에 추가하는 것이 답임.



## 풀이 방법

```assembly
asm1:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	sub    esp,0x10
	<+6>:	mov    eax,DWORD PTR [ebp+0xc]
	<+9>:	mov    DWORD PTR [ebp-0x4],eax
	<+12>:	mov    eax,DWORD PTR [ebp+0x8]
	<+15>:	mov    DWORD PTR [ebp-0x8],eax
	<+18>:	jmp    0x50c <asm1+31>
	<+20>:	add    DWORD PTR [ebp-0x4],0x1
	<+24>:	add    DWORD PTR [ebp-0x8],0xaf
	<+31>:	cmp    DWORD PTR [ebp-0x8],0xf4d
	<+38>:	jle    0x501 <asm1+20>
	<+40>:	mov    eax,DWORD PTR [ebp-0x4]
	<+43>:	leave  
	<+44>:	ret    
```

인자를 지역 변수로 가져와서 사용. 


asm1(0xab,0xcd) 

loop	:	0xcd + (0x1 * n);	0xab + (0xaf * n)
if 0xab + (0xaf * n) > 0xf4d =====>		jmp to asm1+40

0xaf * n > 0xf4d - 0xab
n > 21.9064...

if n is 22, jmp to asm1+40
eax is 0xcd + 0x1*22 = 0xe3






## Flag

scpCTF{0xb2}



## 힌트

assembly 명령어에 대해 조사해 보세요!

CPU 레지스터의 종류와 용도에 대해 알아보세요!
