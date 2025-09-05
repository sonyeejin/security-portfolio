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

## <리눅스>

### 셸(shell)
유저가 리눅스 시스템을 이용할 수 있는 인터페이스를 의미한다.  
셸이 유저에게 입력을 받고 운영체제가 그것을 프로그램으로 처리 후 그 결과를 유저에게 출력한다.  

<img width="294" height="60" alt="image" src="https://github.com/user-attachments/assets/ef965ac9-82ed-44f0-aa30-24fbb4336bc9" />  

우분투 터미널을 열고 bash가 실행되면 위와 같은 텍스트가 출력되는데 이것이 셸 프롬프트다

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
6.  mv     
     디렉토리 위치 변경  
     mv <현재 파일명> <바꿀 파일명> 으로 파일명 변경 가능  
     mv <파일명> .. 으로 해당 파일을 상위 디렉토리로 옮기기 가능  

<img width="864" height="658" alt="image" src="https://github.com/user-attachments/assets/1621b17f-a204-4f81-a7aa-a1d62ac32fd0" />  
-> new_dir로 새 디렉토리 만든 후 그 안에  new_file 을 생성  
-> new_file을 old_file로 파일명 변경  
-> 디렉토리 안의 old_file을 상위 디렉토리로 옮기기  

7.  rm  
     파일 삭제  
     rm -r 은 디렉토리 삭제  
8.  cat  
     파일의 내용 출력. cat <파일경로> 형식으로 사용  
9.  echo  
     셸에 유저가 입력한 테스트 출력 ex) echo "Hello world!"  
10.  echo "파일내용" > 파일명  
     파일 내용을 담은 새로운 파일을 생성  
11.  cp  
     파일 복사. cp <복사될 파일명> <복사본 파일명>  
     디렉토리 복사 시엔는 cp -r을 사용함  
12.  grep  
     전제에서 특정 문자열 찾기  
     grep <문자열> <파일명> 을 통해 해당 파일안에서 특정 문자열이 포함된 행을 출력  
13. curl  
    client URL. 서버에 데이터 보내거나 받는 명령어  
    curl <옵션> <URL> 향식

### 와일드 카드(wildcards)  
리눅스에서 임의의 다른 문자를 나타낼 수 있는 특수 문자  

1. ?  
   a-z,0-9 범위 내 임의의 1개 문자로 대체  

 2. *  
    a-z,0-9 범위 내 임의의 0개 이상 문자로 대체  

### 리다이렉션(redirection)   
모니터의 표준 출력, 키보드 표준 입력을 다른곳으로 변경하는 작업  

1. 명령어 > 파일  
   명령어 표준 출력을 파일로 변경한다. 파일에 없으면 새로 생성, 있으면 덮어씀  
   예를 들어 명령어 ls test[0-9] > world 는 test뒤에 임의의 숫자를 가진 파일을 출력하는 ls 명령어의 결과를 world라는 파일에 쓴다.
2. 명령어 >> 파일  
   위와 같지만 파일이 있으면 이어쓴다  
3. 명령어 < 파일 
   명령어 표준 입력을 파일로 변경  
   예를 들어 grep  test < world 는  world라는 파일 안의 내용에서 test라는 문자열을 가진 행을 모두 출력한다.
   
** 파이프 : 리다이렉션의 한 형태로 | 의 문자를 사용한다.  
ex) ls -l | grep hello  는 명령어 ls -l 의 출력 결과에서 hello가 포함된 행을 출력한다.  

## <권한>

리눅스에서 유저와 그룹은 각 고유한 ID를 갖고 있음. UID와 GID  
/etc/passwd 는 유저 정보를 /etc/group 은 그룹 정보를 저장하는 텍스트 파일임  

파일과 디렉토리에 접근은 권한을 통해 제어 한다. 읽기(r) 쓰기(w) 실행(e)의 세 종류가 있다.  
권한을 확인하려면 ls -l 명령어를 사용하면 된다. 

<img width="752" height="176" alt="image" src="https://github.com/user-attachments/assets/ed791286-5a78-4198-bac0-c9fd4e5df5ca" />    

첫째 열의 rw- 식의 표기가 권한을 의미한다. 세 번째 열은 소유자를 네 번째 열은 소유 그룹을 나타냄.  

*  drwxrwxr-x  
  여기서 d는 디렉토리를 의미한다. -는 일반 파일 l은 링크파일을 나타낸다.  
  다음 rwx는 소유자의 권한을 , 그 다음의 rwx는 소유 그룹 안의 유저들의 권한을, 마지막의 r-x는 나머지 유저들에 대한 권한을 나타낸다.

### chomd  











     
