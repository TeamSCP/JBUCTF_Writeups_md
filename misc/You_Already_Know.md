# 문제 이름 : You_Already_Know - ??pt

## 문제

당신은 이미 답을 알고있습니다. 모르겠다구요? ¯\\\_(ツ)_/¯ 어쩔수 없군요!
그들은 공기와 함께 존재합니다!



## 문제 취지

무선 랜카드 인터페이스의 모드에는 여러가지가 있다.(AP, Managed, Monitor, Ad-Hoc) 네트워크 패킷을 monitor mode 로 수신하였을 때 얻을 수 있는 정보가 많다. 하지만 꼭 모니터모드로 캡쳐하지 않아도 수집가능한 패킷이 존재한다. beacon frame 패킷은 AP가 ESSID 를 알려주기 위한 패킷이고, (모든 station에게 도달해야 하므로)암호화 되어있지 않다. 따라서 모든 스마트폰에서 이런 메세지를 띄우는 공격 또한 가능하다는 것을 알려주기 위해 이 문제를 출제함.



## 풀이 방법

[SCP]

개인 노트북, raspberryPi 또는 서버에서 github의 바이너리를 실행시켜 놓는다.

usage : you_already_know \<monitor mode network interface\>



[Solver]

패킷을 확인하게 되면, "y0u_4lr3ady_have_B34c0n_Fr4m3"이 ESSID인 beacon frame이 캡쳐되는 것을 확인할 수 있다.



## Flag

scpCTF{y0u_4lr3ady_have_B34c0n_Fr4m3}



## 힌트

SCP 동아리방 근처의 와이파이 목록을 확인하십시오! (아이폰에서 잘보임!) 
Flag format : scpCTF{...}
