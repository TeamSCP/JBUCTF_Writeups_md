#  문제이름

RET magic



## 문제

어떤 마술사가 언어 코드로서의 함수 호출이 아닌 마법으로 다른 함수를 호출해 보겠다고 합니다.

이 마술에 대해 이해하고 능숙히 다루어 주세요!



---

nc 114.71.240.152 12358 



## 문제 취지

함수 에필로그 과정을 이해하고 RET를 덮어 원하는 함수로 호출이 가능하다는것을 인식하게 하고 또한 그것을 이용하도록 한다.



## 풀이 방법

nc접속시 다음과 같이 출력된다.

![K-20191111-569516](https://user-images.githubusercontent.com/40850499/68568187-48be5b00-049e-11ea-9a4e-e35269fc4316.gif)



아래는 소스코드에 main함수이다. 소스코드를 보면 알 수 있듯이 함수호출은 RET를 덮어 호출을 하게 된것이다.

```c
int main(){
	setvbuf(stdout, NULL, _IONBF, 0);
	char buf[32];
	char* p=first;
	printf("I'll show you magic!\n");
	printf("magic is chage RET \n\n");
	printf("Before RET : %p \tuse this : %p\n", *(buf+60),&first);
	memcpy((buf+60),&p,4);
	printf("After RET  : %p \n", *(buf+60));
	sleep(2);
}
```



RET를 덮여 first함수를 호출하게되며, first함수에서 추가적으로 입력을받는다 이떄 bof가 일어나며 RET를 덮어서 win함수를 호출하면 flag를 얻을 수 있다.

```c
void first(){
	printf("\n\nTa-da!!!!~ \n");
	printf("You are now in the first function\n");
	printf("w(ﾟДﾟ)w  ㄴ(°0°)ㄱ \n");
	printf("it's your turn! show me magic\n");
	char buf[32];
	gets(buf);
}
```



![K-20191111-570410](https://user-images.githubusercontent.com/40850499/68568536-309b0b80-049f-11ea-8ea7-810a4372037e.gif)

+93,96,97을 주의깊게 보자

+93 lea eax,[ebp-0x28 ]

+96 push eax

+97 call gets@plt

순으로 진행이 된다 이는 ebp-0x28의 주소를 eax에게 주고 push로 스택에 넣어주고 gets함수가 그것을 인자로 사용을 하는것이다 즉 ebp-0x28부터 입력이 되고 이것으로 RET까지 거리를 알 수 있다

0x28= 40 + 4(sfp) = 44  즉 44개의 더미와 win함수를 리틀엔디안 형식으로 익스코드를 짜면 flag를 얻을 수 있다.





![K-20191111-571397](https://user-images.githubusercontent.com/40850499/68568717-bdde6000-049f-11ea-8e30-dc1ef0406681.gif)



![K-20191111-572014](https://user-images.githubusercontent.com/40850499/68568743-cafb4f00-049f-11ea-808f-c355f1c45492.gif)



다음과 같이 win함수가 호출된것을 볼 수 있다.

![K-20191111-572151](https://user-images.githubusercontent.com/40850499/68568765-d8183e00-049f-11ea-9d65-6812e64817a4.gif)




## Flag

scpCTF{AaaaaaaaaaaaWe_Som2_RET!!!!}



## 힌트

함수 프롤로그와

RET에 대해서 공부하세요!
