# asm0 - ??pt

## 문제

바이너리를 objdump 명령어를 이용하여 알아보았더니 다음과 같은 어셈블리 코드를 얻을 수 있었습니다!! asm0(0x481)은 무엇을 반환하나요? 플래그를 제출형식에 맞게 10진수 형식으로 제출하세요!



## 문제 취지

3학년 수업으로도 있는 리버스 엔지니어링을 이용하여 문제를 내보았다. 학교에서 배운 지식을 이용해 풀 수 있고, 실제로 소스 코드가 주어지지 않은 상황에서는 어셈블리를 읽어 하므로 그 능력을 키울 수 있게 하기 위하여 출제.



상세 : 

기본적인 cmp->점프 구문과 add 와 같은 기본적인 구문을 읽어낼 수 있는가?

함수의 인자 값이 들어가는 원리를 아는가?

일부러 cmp구문에서 큰 값을 비교하여 비교하기 쉽게 해놓음.



## 풀이 방법

```assembly
asm0:
    <+0>:   push   ebp
    <+1>:   mov    ebp,esp
    <+3>:   xor    eax,eax
    <+5>:   add    eax,0x2e5f
    <+10>:  cmp    DWORD PTR [ebp+0x8],0x7a69       ;0x481 < 0x7a69
    <+17>:  jle    0x11b9 <asm0+32>                 ;jmp to asm0+32
    <+19>:  mov    eax,DWORD PTR [ebp+0x8]
    <+22>:  add    eax,0x7a69
    <+27>:  jmp    0x11ce <asm0+53>
    <+29>:  add    DWORD PTR [ebp+0x8],0xb8         ;0x481 + 0xb8 = 0x539
    <+36>:  cmp    DWORD PTR [ebp+0x8],0x18f        ;0x539 > 0x18f
    <+43>:  jg     0x11cb <asm0+50>                 ;jmp to asm0+50
    <+45>:  jmp    0x11a6 <asm0+13>
    <+47>:  mov    eax,DWORD PTR [ebp+0x8]          ;eax is return value. 
    <+50>:  pop    ebp
    <+51>:  ret    

```



## Flag

scpCTF{1337}



## 힌트

assembly 명령어에 대해 조사해 보세요!

CPU 레지스터의 종류와 용도에 대해 알아보세요!