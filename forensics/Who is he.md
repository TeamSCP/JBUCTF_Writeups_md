## **문제 이름**

Who is he?



## 문제 

당신은 포렌식 수사관입니다.

범인이 한국에서 약 60억 원에 달하는 거액의 돈을 가지고 달아났습니다!

범인에 대한 증거는 사진 3장뿐입니다.

당신은 3장의 사진만을 활용하여 범인을 찾아야 합니다.

단, 3장의 사진 중 오직 1장의 사진만이 범인을 찾을 수 있는 결정적 증거라고 합니다.

이제 대한민국은 당신의 손에 달려있습니다.

반드시 당신은 범인을 찾을 것이라고 믿습니다.

Good Luck!



## 문제 취지

압축 파일을 풀어보면 png와 jpg 그리고 gif 이렇게 3개의 사진 파일이 존재한다.

포렌식에서 가장 많이 쓰이는 증거물로 사진 파일이 있다.

그리고 사진 파일은 png, jpg, gif, bmp 등 여러 파일이 존재한다.

그 중, 가장 흔히 쓰이는 파일은 png와 jpg 그리고 gif 파일이다.

출제자는 이 문제에 png, jpg, gif 파일의 특징을 하나씩 넣어 문제를 출제하였다.

먼저 jpg 파일은 손실 압축 방법을 사용하기 때문에 png와 gif 파일보다 화질이나 품질이 심하게 떨어지는 특징이 있다.

그러므로 jpg 파일을 png, gif 파일들과 함께 출제하여 두 파일보다 화질이 많이 떨어지는 이미지 파일을 강조한다.

다음으로 png 파일은 비손실 압축 방법을 사용하여 압축하거나, 반복 저장을 하여도 화질이나 품질이 절대로 떨어지지 않는 고화질 이미지 파일이라는 것을 강조한다.

마지막으로 gif 파일은 비손실 압축 방법을 사용하여 png 파일과 같은 고화질을 지원하고, 무엇보다 gif 파일의 가장 큰 특징은 애니메이션 기능을 제공한다.

png 파일과 jpg 파일은 절대로 지원할 수 없는 애니메이션 기능을 제공하는 게 gif의 가장 큰 최대 장점이다.

그리고 출제자는 gif 파일이 애니메이션 기능을 제공하는 것을 알고, gif 파일에 플래그 이미지를 숨겨두었다.

그리고 플래그 이미지는 10초에 한 번씩만 보이기 때문에, 빠르게 움직이는 이미지를 증거로 포착하는 것을 의도로 하여 문제를 출제하였다.

이로써, 이 문제는 png와 jpg 그리고 gif 파일들의 각각의 특징 그리고 포렌식 관점에서 보면 빠르게 증거 장면을 포착하는 것을 학습하는 것이 이 문제의 목적이자 취지이다.



## 풀이 방법

 evidence(증거)라는 이름으로 된 zip 압축 파일이 주어진다.

압축 파일을 해제하고, 확인해보면 3개의 사진 파일이 있는 것을 확인할 수 있다.

하지만, 3개 파일 모두 확장자가 다른 png, jpg, gif 파일이다.

이 3개의 파일 중에서 하나의 파일만 증거물이 될 수 있다.


![image](https://user-images.githubusercontent.com/40850499/66138712-094c5580-e63a-11e9-9ecb-a1a22ded6cd8.png)


먼저 png 파일이다.

비손실 압축 방법을 사용하기 때문에, 화질이나 품질이 절대로 떨어지지 않는 고화질을 제공한다.

하지만 png파일에서는 어떠한 증거를 찾을 수 없다.



![image](https://user-images.githubusercontent.com/40850499/66138905-6b0cbf80-e63a-11e9-8dd5-792faee772b3.png)


다음으로 jpg 파일이다.

확실히 png나 gif보다 화질이 심하게 떨어지는 특징을 가지고 있다.

jpg 파일에서도 png 파일과 마찬가지로, 증거를 찾을 수가 없다.



![image](https://user-images.githubusercontent.com/40850499/66138712-094c5580-e63a-11e9-9ecb-a1a22ded6cd8.png)

마지막으로 gif 파일이다.

png 파일과 마찬가지로 비손실 압축 방법을 사용하여 고화질을 지원하는 특징이 있다.

그리고 gif 파일만의 특징인 애니메이션 이미지를 제공하는 가장 큰 특징이 있다.

10초 정도 계속 보게 되면 gif 파일의 이미지가 바뀌는 것을 확인할 수 있다.

![image](https://user-images.githubusercontent.com/40850499/66139100-c8087580-e63a-11e9-9a2b-32cb3190dcfd.png)

이렇게 플래그가 보이는 이미지 파일을 확인할 수 있다.

1.5초만에 없어지는 이미지이기에 빨리 증거를 확보하는 것이 문제를 푸는 방법이다.

무엇보다도 gif 파일이 움직이는 애니메이션 이미지 기능을 지원한다는 것을 알고있으면 쉽게 풀 수 있는 문제이다.



## Flag

 scpCTF{h3_i5_N@1_Gan9_D0!!}



## 힌트

가만히 계시면 사진이 움직일 수도 있어요~






