### 강의 27
#### Linux - process 1 : Computer structure
* process가 무엇인가?
  * command, rm, mkdir,top 같은 것들은 명령어인데, 명령어들은 bin, sbin 파일 형태로 스토리지에 존재  
  이를 프로그램이라고 함
  * 이 프로그램이 실행되면 메모리에 적재되고, 이를 CPU가 처리. 이때 메모리에 띄어져 있는 프로그램을 process라고 함  
* Hardware에 대한 얘기를 해보자
![img](https://github.com/koni114/Linux_lifeCoding/blob/master/processor.JPG)
  * SSD, HDD 라고 하는 것들이 있는데, 이는 저장장지임 -> 스토리지라고 함
  * RAM 같은 것들은 memory라고 함
  * CPU는 processor라고 함
* memory나 storage는 공통적으로 데이터를 저장한다는 것에 있음
* 이러한 저장장치가 다르게 공존하는 이유는 최고의 memory를 만드는 것을 인류가 도달하지 못하였기 때문
* 스토리지 vs 메모리
  * 스토리지
    * 가격이 싸고, 용량이 크고, 속도가 매우 느림
    * 프로그램은 스토리지에 깔려있음
  * 메모리
    * 가격이 비싸고, 용량이 작고, 속도가 매우 빠름
* CPU가 동작할 때 굉장히 빠르게 동작하는데, 스토리지가 가지고 있는 처리속도로는 CPU 처리속도를 따라올 수없음
* 프로그램은 스토리지에 깔려있는데, 이 프로그램을 읽어서 메모리에 적재 시킴. 그리고 실행되지 않는 프로그램은 적재 시키지 않음
* 메모리에 올려있는 프로그램을 CPU가 읽어서 동작한다음에 데이터를 처리

### 강의 28
#### Linux - process 2 : ps top htop
~~~
* ps
프로세스 리스트를 보여줌
ex) ps aux
백그라운드에서 돌아가고 있는 모든 프로세스를 보고 싶을 때 사용
ex) ps aux | grep apache
apache 라고 하는 텍스트를 포함하고 있는 프로세스 출력
ex) sudo kill 22142
22142 라고 하는 PID를 강제로 죽임
** PID : process ID
~~~
##### top/htop program
* MEM% : 물리적인 메모리 크기
* RES : 실제적인 메모리 크기
* COMMAND : 해당 프로세스를 실행 시키는 명령어
* CPU core 수 등을 확인 가능
* Load average : CPU 점유율과 관련된 것
  * 첫 번째 자리 : 1분간의 CPU 점유율
    * ex) 8 : 총 7개의 processor가 대기를 하고 있다는 의미
  * 두 번째 자리 : 5분간의 CPU 점유율
    * ex) 위와 동일한데 5분간의 통계
  * 세 번째 자리 : 10분간의 CPU 점유율
    * ex) 위와 동일한데 10분간의 통계
* core가 4개인데 위의 load average 숫자가 4개면 잘 사용하고 있다!는 의미
  core가 4개인데 위의 load average 숫자가 1개이면 코어 4개 중 1개만 일을 하고 있다는 의미


### 강의 29
#### Linux - background execute (Ctrl + Z, &)
* 독특한 실행 방법에 대해서 설명
* 2개의 창이 있다고 하자. 왔다갔다 하면서 수행을 할 수 있는데, 이를 <b/>멀티 테스킹</b>이라고 함
##### ctrl + z
* 우리가 예를 들어 nano에서 html file을 작성하고, 다른 작업을 수행하고 싶을 때
나갔다가 다시 들어오면 불편하므로, ctrl + z 를 누르면 프로그램을 종료하지 않고 다른 작업을 수행 할 수 있음
~~~
fg
background에 있는 프로세스가 foreground로 수행 됨
fg %2
background에 있는 2번 프로세스가 수행 됨
jobs
background로 수행되고 있는 process가 보임
jobs 에서 + 로 표시된 프로세스가 fg 명령어 수행시 foreground로 나오는 프로세스
-로 표시된 프로세스는 + 프로세스가 종료된 다음 foreground 로 나오는 프로세스를 의미!
kill %4
정상적으로 종료하는 방법. 종료가 안될 수도 있음
kill -9 %4
더 강력한 종료 방법. killed 라고 뜸
ls -R
현재 디렉토리 밑에 있는 모든 파일과 디렉토리를 보여줌
ls -alR / 1> result.txt 2> error.log &
프로그램을 실행 할 때부터 background로 보내고 싶은 경우 제일 뒤에 & 를 쓰면 바로 다음 명령어 수행 가능
이 때 jobs를 수행하면 running 이라고 표기
~~~
### 강의 30
#### Linux - daemon 1: intro
