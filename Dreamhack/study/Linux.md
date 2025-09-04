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

### 셸(shell)
유저가 리눅스 시스템을 이용할 수 있는 인터페이스를 의미한다.
셸이 유저에게 입력을 받고 운영체제가 그것을 프로그램으로 처리 후 그 결과를 유저에게 출력한다.

<img width="294" height="60" alt="image" src="https://github.com/user-attachments/assets/ef965ac9-82ed-44f0-aa30-24fbb4336bc9" />
우분투 터미널을 열고 bash가 실행되면 위와같은 텍스트가 출력되는데 이것이 셸 프롬프트다

* 명령어
  
  1. pwd
     print Working directory. 현재 작업중인 디렉토리의 경로를 출력
  2. ls
     List. 디렉토리 안의 것들을 출력 / ls -l 은 더 자세한 정보를 출력함
  3. cd
     change directory. 디렉토리 변경
     cd ..은 현재 디렉토리에서 이전(부모) 디렉토리로 돌아감
  4. mkdir
     새로운 '디렉토리' 생성
  5. touch
     비어있는 새로운 '파일' 생성
  6. mv 
     디렉토리 위치 변경
     mv <현재 파일명> <바꿀 파일명> 으로 파일명 변경 가능
     mv <파일명> .. 으로 해당 파일을 상위 디렉토리로 옮기기 가능

<img width="864" height="658" alt="image" src="https://github.com/user-attachments/assets/1621b17f-a204-4f81-a7aa-a1d62ac32fd0" />
-> new_dir로 새 디렉토리 만든 후 그 안에  new_file 을 생성
-> new_file을 old_file로 파일명 변경
-> 디렉토리 안의 old_file을 상위 디렉토리로 옮기기

  7. rm
     파일 삭제
     rm -r 은 디렉토리 삭제
  8. cat
     파일의 내용 출력. cat <파일경로> 형식으로 사용















     
