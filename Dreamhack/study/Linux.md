## 가상 머신(Virtual Machine)
VM은 컴퓨터 여러 대를 시뮬레이션 할 수 있게 해준다.  
실제 컴퓨터를 '호스트 머신', 호스트 머신 위에서 돌아가는 VM을 '게스트 머신'이라고 한다.

1. Mac에서 UTM사용하여 리눅스 환경 구축 (실습)
ubuntu 24.04 server

ip addr 명령어로 가상머신의 ip주소 확인-> 이를 통해 확인한 우분투 ip주소를 통해 mac(호스트)에서 가상머신으로 접속 가능
호스트 터미널에서 ssh <가상머신 이름>@<가상머신 ip주소> 를 입력하면 된다. -> 이것으로 복사와 붙여넣기가 자유롭게 된다.
<img width="1266" height="826" alt="image" src="https://github.com/user-attachments/assets/9818ec1f-c64d-4af5-9b9f-d841724c579a" />
   
2. windows에서 VirtualBox 또는 WAL2 사용하여 리눅스 환경 구축
아직 미 진행
virtualBox는 x86아키텍처를 가상화하기 위한 오픈소스 소프트웨어임
WLS2또한 가상머신 생성을 위한 프로그램인데 윈도우 10 이상의 버전을 사용할 경우 컴퓨터 자원을 덜 사용할 수 있다는 장점에 많이 사용됨

## 리눅스 
