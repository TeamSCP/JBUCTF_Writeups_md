# TooEasyXOR 

## 문제

XOR is so cool!



Cipher : 7363704354467b657a5f584f525f61647366676813021f0d07161707595811

Key : xorisntcool



## 문제 취지

ASCII 코드와 XOR에 대한 기초적인 지식을 요구한다. 16진수를 알파벳으로 변환할 수 있음을 인지하여야 상호 간의 XOR 연산을 할 수 있으며 문제가 Cipher와 Key 각각의 바이트끼리 XOR 연산을 수행하는지 Ciphet와 Key의 16진수 값 전체를 XOR 하는지 생각할 수 있어야 한다.



## 풀이 방법

문제의 이름에서 XOR 문제임을 알 수 있고 힌트에서 간략한 방법을 이해할 수 있다. decode 사이트를 이용하거나 직접 프로그래밍 하여 문제를 풀 수 있다. 이 문제는 암호문과 키의 ASCII 코드를 각 바이트 끼리 XOR 연산한다. 



Cipher : 2b2c22a7834313910173a10332d2028283c282222282c37312d657932

Hex(Key) : 584f5249534e4f54434f4f4c

Cipher ^ Hex(Key) : 7363704354467b657a5f584f525f6164736667686b6d6d647478636436377d

Result = scpCTF{ez_XOR_adsfghkmmdtxcd67}

단순하게 Cipher를 ASCII 코드로 바꾸면 아래와 같은 결과가 나온다.

```
+,"§Cs¡2ÒÂ""ÃsÖW
```

**확인**
<img width="1223" alt="Screen Shot 2019-10-14 at 8 58 24 PM" src="https://user-images.githubusercontent.com/16417991/66750943-c8213480-eec8-11e9-98c8-56b67cc4db05.png">



## Flag

scpCTF{ez_XOR_adsfghkmmdtxcd67}



## 힌트

0 ⊕ 0 = 0

0 ⊕ 1 = 1

1 ⊕ 0 = 1

1 ⊕ 1 = 0
