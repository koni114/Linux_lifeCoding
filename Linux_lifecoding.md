# 리눅스 생활 코딩 강좌
### 강의 1
#### 설치 없이 리눅스 사용하기
* codeonweb site에서 무료로 쉘 스크립트 - 리눅스 사용 가능

### 강의 2
####  설치없이 리눅스 사용하기 - cloud9
* 리눅스 설치를 하는 것은 굉장히 까다로운데, 이를 온라인에서 해볼 수 있도록 하는 서비스 제공
* http://c9.io

### 강의 3
#### Linux - install : OSX terminal
* 맥의 운영체제인 linux10은 unix 계열이라고 하는 공통 조상을 가지고 있기 때문에 궂이 linux를 깔지 않아도 mac에서 사용 가능

### 강의 4
#### 가상 머신(virtual machine)
* 하드웨어를 소프트웨어적으로 구현해서 그 위에서 운영체제가 작동하도록 하는 기술
* 가상 머신이라고 하는 프로그램 위에 운영체제가 설치 되는 것

#### 가상 머신을 사용해야 하는 이유
* 다른 운영체제를 사용해야 하는 경우(맥OS에서 윈도우, 윈도우에서 리눅스)
* 독립된 다른 공간이 필요한 경우(바이러스 회피, 백업)
* 하나의 머신러닝에서 여러개의 운영체제를 제공
* 가상 머신을 사용하게 되면 여러개의 운영체제를 사용자에게 제공 가능
* VirtualBox : 무료, 가상머신 솔루션
* 기타 솔루션 : VMWare, VirtualPC

### 강의 5
#### Linux - file & directory 1
* 터미널을 이용해서 리눅스를 제어하기 위해서는 2가지가 중요
  * 명령어를 통해서 제어한다(Command Line Interface)
  * 내리는 명령은 현재 머물고 있는 디렉토리를 대상으로 적용된다
~~~
* pwd   : 현재 디렉토리를 보여줌
* mkdir : 디렉토리 생성
* touch : file 만들기
ex) touch file.txt
* ls -l : 해당 위치의 모든 file 등을 보여줌  
제일 앞에 d가 있으면, folder. d가 아니면 file  
~~~

### 강의 6
#### Linux - file & directory 2
~~~
* cd : change directory의 약자. 보통 file을 입력할 때 절반만 입력하고 tab 키를 누르면 완성형 형태가 나옴   
이 때 복수개가 있다면 해당 문자가 겹치는 여러개의 파일 리스트를 보여줌
~~~

* 상대경로와 절대 경로
  * 상대경로  
    * 부모 경로로 이동
    * 현재 디렉토리
  * 절대경로
    * 최상위 디렉토리를 기준으로 경로를 표현하는 것을 의미
    * 최상위 디렉토리를 root 디렉토리라고 함
    * cd . : 최상위 디렉토리로 이동
* 명령어 앞에 '-'를 붙이면 동작 방법을 바꿈
~~~
rm    : remove. paramter를 붙이지 않으면 file만 삭제됨
rm -r : 해당 디렉토리 삭제
ex) rm -r hello_linux/
~~~  
* 명령어 --help를 사용하면 도움말 확인 가능
* recursively : 재귀적으로 동작한다. 예를들어 rm -r 명령어도 재귀적으로 동작한다고 되어 있는데, 디렉토리 안에 디렉토리를 지우고 ..처럼 볼 수 있음

### 강의 7
#### Linux - help & man
~~~
* man : 해당 명령어 뒤에 궁금한 명령어를 입력하면, 상세한 화면설명서가 화면에 표시됨
help와의 차이는 man은 전용 페이지로 이동. help 해당 디렉토리에서 메뉴얼을 보여줌
키보드 위, 아래를 누르면 script가 움직임
** 만약 여기서 무언가를 찾아보려고 하면, /'찾고자 하는 단어' 를 통해 확인 가능
** 알파벳 q를 누르면, 밖으로 빠져 나가게 됨
ex) /sort -> sort 단어가 들어간 문구들을 하이라이트해서 확인 가능
이때 알파벳 N키를 누르면, sort 단어가 들어간 곳으로 단계 단계 이동시켜줌
 ~~~
* 명령어 사용설명서를 읽는 방법
  * Usage : 사용법. 기본적인 동작방법 설명
  * 대부분의 명령들이 version이라는 것을 가지고 있음

~~~
* mkdir-p : 부모 디렉토리가 필요하면 생성하는 param
            일반적으로 작대기가 1개면 param 2개면 full Name
* ls -a : 있는 모든 목록들을 보여줌
          숨켜저 있는 것까지 보여줌
          숨켜저 있는 파일은 앞에 .가 붙음
* ls -al : 감쳐진 파일과 감쳐지지 않은 파일을 모두 보고 싶을 때
           해당 명령어 사용
~~~
* 다양한 명령어들은 man, help를 이용해서 계속 확인해보자

### 강의 8
#### Linux - 필요한 명령을 검색으로 찾는 법
~~~
* cp : '파일위치 및 파일이름' (한칸 띄고) '목적지 및 파일이름'
* mv : 파일 이동, 이름 수정을 할 때도 이용
  ex) mv rename.txt rename2.txt
~~~

### 강의 9
#### Linux - sudo
* sudo(super user do)
* 유닉스 계열의 운영체제들의 중요한 특징 중 하나는, 다중 사용자 시스템이라는 것(과거에는 컴퓨터가 굉장히 비쌌기 때문에)
* 다중 사용자가 있기 때문에 사용자마다 할 수 있는 일과 할 수 없는 일을 구분하기 위해 permission이라는 체계를 고z안함
* 예를 들어 ubuntu라는 가정하에 apt-get install git 이라고 하면 sudo 권한으로 git을 설치 할 수 있게 됨

### 강의 10
#### Linux - file edit(nano)
  * 명령어 기반의 시스템에서도 편집기가 있음(nano, vi 등..)
  * nano : 초급자, vi : 중,고급자들이 많이 사용함
두 개의 편집기는 대부분의 유닉스 계열에는 다 들어가 있음

### 강의 11
#### Linux manager
* 여기서의 package는 앱, 어플리케이션을 말함
* ls, mkdir도 package 중 하나라고 볼 수 있음
* 오늘날 unix는 package manager를 제공
모바일, 앱스토어 같은 역할을 수행
* package manager 사용 방법
  * 리눅스에서 대표적인 package manager는 apt와 yum 이 있음
* apt 설명
  * apt를 사용하기 위해서 apt를 통해 설치할 수 있는 목록을 최신화 하여야 함
  * apt-get update를 치면 권한이 없다고 나옴
  -> sudo apt-get update : apt를 다운받을 수 있는 서버에서 다운받아 최신상태로 update 해줌(목록을 다운받는 것)
  * sudo apt-cache htop -> htop 이라는 프로그램 search
* htop이 무엇인가?
  * 기본적으로 리눅스에는 top이라고 하는 프로그램이 설치되어 있음(window 작업관리자 같은 것)  
  * top 프로그램은 알아먹기가 조금 어려운데, 좀더 직관적으로(graphical하게) 보고 싶을 때 htop 프로그램 사용

* sudo apt-get install htop -> htop 진행
* 설치되어 있는 program을 update 하고 싶은 경우,
  * sudo apt-get upgrade htop - > htop upgrade
  * sudo apt-get upgrade -> 모든 프로그램 upgrade
* 설치되어 있는 프로그램 삭제
  * sudo apt-get remove htop

### 강의 12
#### Linux - 맥 사용자를 위한 homebrew
* Homebrew
  * 일종의 installer. 앱스토어와 같은 역할을 함
  * 주로 프로그래머들이 사용하는 명령행에서 명령을 통해서 컴퓨터를 제어하는 방식에 사용되는 프로그램을 설치해주는 installer  

* Homebrew 사용하기
  * 먼저 설치를 해야함(MAC에서 하는 방법임)
    * brew.sh 라고하는 주소로 접속
    * 중앙에 있는 코드를 copy
    * 돋보기를 눌러서 terminal이라고 입력
    * 위의 복사한 code를 붙여넣기 해서 설치
    * 원한다면 help 명령어를 통해 확인
    * search 명령어를 이용해서 내가 설치할 수 있는 프로그램이 있는지 확인!

* brew list -> 해당 명령어를 통해 brew를 통해 설치한 프로그램 목록 list를 볼 수 있음
* brew uninstall ~~ 를 이용해서 삭제하면 됨
* update vs upgrade
  * update : upgrade 할 수 있는 목록을 최신화
  * upgrade : 인스톨된 프로그램을 upgrade 시켜 줌

### 강의 13
#### Linux - wget
* 명령어 기반 파일 다운로드 방법
* 보통 GUI에서는 화면에서 다운로드 버튼을 눌러서 파일을 다운로드 받음
* wget 프로그램을 통해 URL을 통한 파일 다운로드가 가능함
* wget을 통한 다운로드 방법
  * 화면에서 우클릭 한 후 Copy link address 를 통해 주소를 알 수 있음
  * wget 'copy link address를 눌러 복사된 주소' 를 입력하면 다운로드 됨
  * 이때 download라는 이름으로 저장이 되는데, mv를 통해 이름 변경

### 강의 14
#### Linux - Source download - git
* git 프로그램 사용법 알아보기
*
