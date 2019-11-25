#  MELBORP AMGINE

## 문제

I found this note in my grandfather's cabinet that was old and classified as military intelligence. I wonder what it is but I dont know how to read it.. I can't read this! Help.



M3,B,V,IV,II,21,09,11,W,C,I,AD,PK,TO,SI:owkjmlumuvtjrazymprsnlwwpgsuhvnpbcdhxalmkodonggvoostnhqykinkyluugpavmtcpwoktauzqrgrsxxz



## 문제 취지

암호에는 대칭키 암호, 비대칭키 암호, 블록 암호, 스트림 암호와 같은 여러 가지 알고리즘 대분류가 있고 그 대분류에 포함된 여러 가지 방법과 모델들이 있다. 에니그마도 그중 하나이고 한 번쯤은 경험해볼 만한 암호이다. 이 문제를 풀어봄으로 카이사르나 비즈네르같은 구식 암호보다는 복잡한 방법을 사용하는 암호를 접해보고 근현대 암호 알고리즘으로 넘어오는 (어쩌면 난이도 상의) 관문이 될 수 있다.



## 풀이 방법

[링크](https://cryptii.com/pipes/enigma-machine)와 같은 사이트를 이용하면 금방 풀 수 있다. M3,B,V,IV,II,21,09,11,W,C,I,AD,PK,TO,SI는 에니그마 기계의 세팅이며 



M3은 MODEL.

B는 REFLECTION. 

V, IV, II은 ROTOR 1~3. 

21, 09, 11은 각 ROTOR의 POSITION.

W, C, I는 각 ROTOR의 RING.

AD, PK, TO, SI는 PLUGBOARD에 넣으면 된다.



owkjmlumuvtjrazymprsnlwwpgsuhvnpbcdhxalmkodonggvoostnhqykinkyluugpavmtcpwoktauzqrgrsxxz 부분을 CIPHERTEXT에 입력할 시 결과는 아래와 같다.

ihave thefl agtha tyouw antfl agist hegoo dolpa lplea seput onrig htfla gform atfla gisen igmaa sdflk jh

띄어쓰기를 적당히 조절하면 

i have the flag that you want flag is thegoodolpal please put on right flag format이 된다.





## Flag

scpCTF{thegoodolpal}



## 힌트

[링크](https://cryptii.com/pipes/enigma-machine)
