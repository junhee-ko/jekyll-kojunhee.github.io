---
layout: post
title:  "System Structure, Program Execution"
date:   2018-10-01
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png

---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## 컴퓨터 시스템 구조

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os101.png)

- mode bit
  - 사용자 프로그램의 잘못된 수행으로 다른 프로그램 및 운영체제에 피해가 가지 않도록 하기 위한 보호 장치 필요
  - 0
    - 운영체제가 CPU를 가지고 있음
    - 모든 인스트럭션 수행 가능
  - 1
    - 사용자 프로그램이 CPU를 가지고 있음
    - 한정된 인스턱션만 수행 가능
- timer
  - 특정 프로그램이 CPU 독점 막기위해 이게 필요
  - 정해진 시간 흐른 뒤 운영체제에게 제어권 넘어가도록 interrupt 발생시킴
  - 매 클럭마다 1씨 감소
  - 타이머 값이 0 이 되면 언터럽트 발생
  - time sharing 구현 위해 널리 이용
- device controller
  - IO 장치 전담하는 작은 CPU
  - 제어 정보를 위해 control register, status register를 가짐
  - local buffer를 가짐 (일종의 data register)
  - IO는 실제 deivce 와 local buffer 사이에서 일어남
  - IO가 끝나면 인터럽트로 CPU에 그 사실을 알림
  - device driver : OS 코드 중 각 장치별 처리 루틴 (소프트웨어)
  - divce controller : 각 장치를 통제하는 작은 CPU (하드웨어)
- DMA controller
  - 직접 메모리에 접근할 수 있는 컨트롤러
  - IO 장치가 인터럽트 너무 많이 거니까 CPU가 너무 많이 방해 받아서 DMA controller가 필요
  - CPU의 중재 없이 device의 buffer storage의 내용을 메모리에 block 단위로 직접 전송

## I/O

- 운영체제를 통해서 함
- 사용자 프로그램은 I/O를 어덯게?
  - system call을 함 (운영체제의 함수를 호출)
  - 인터럽트를 직접 걸어서(trap) mode bit이 0으로 바껴

- 동기식 입출력과 비동기식 입출력

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os102.png)

  - 두 경우 모두 io 완료는 인터럽트로알려줌
  - syncronous I/O
    - I/O 요청 후 입출력 작업이 완료 된 후에야 제어가 사용자 프로그램에게 넘어감
    - 구현 방법 1
      - io가 긑날떄 까지 cpu낭비
      - 매시점 하나의 io만 일어남
    - 구현 방법2
      - io가 완료될때까지 해당 프로그램에게서 cpu를 빼앗음
      - io 처리를 기다리는 줄에 그 프로그램을 줄 세움
      - 다른 프로그램에게 cpu를 줌
  - asyncronous I/O
    - I/O가 시작된후 입출력 작업이 끝나기를 기다리지 않고 제어가 사용자 프로그램에게 즉시 넘어감

## Interrupt

- 인터럽트 당한 시점의 레티스터와 program counter를 save한 후 CPU의 제어를 인터럽트 처리 루틴에 넘김
- 인터럽트 : 하드웨어가 발생 시킨 인터럽트
- trap : 소프트웨어 인터럽트
  - Eception : 프로그램이 오류를 범함
  - System call : 프로그램이 커널 함수를 호출하는 경우
- 인터럽트 백터
  - 해당 인터럽트의 처리 루틴 주소를 가지고 있음
- 인터럽트 처리 루틴 (인터럽트 핸들러)
  - 해당 인터럽트를 처리하는 커널 함수

## System call

- 사용자 프로글매이 운영체제의 서비스를 받기 위해 커널 함수를 호출 하는 것
- 사용자 프로그램이 의도적으로 인터럽트 라인 세팅하면, CPU는 하던일을 멈추고 CPU의 제어권이 사용자 프로그램에서 운영체제에게 넘어감

## 프로그램의 실행

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os103.png)

- vitual memory
  - 프로그램 실행 시키면 각 프로그램의 주소 공간이 만들어짐
- pysical memory
  - 커널은 항상 상주
  - 당장 필요한 것만 올려둠
- swap area
  - 메모리의 연장 공간으로 사용
- address tranlation
  - virtial memory의 주소가 물리주소로 바뀜

## 커널 주소 공간의 내용

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os104.png)

- code
- data
  - 하드웨어를 관리하기 위한 자료구조를 가지고 잇음
  - 각 프로그램들을 관리하기 위한 자료구조를 가지고 잇음 
- stack
  - 함수를 호출하거나 할때 스택을 사용

## 사용자 프로그램이 사용하는 함수

- 함수
  - 사용자 정의 함수
    - 자신의 프로그램에서 정의한 함수
  - 라이브러리 함수
    - 자신의 프로그램에서 정의하지 않고 갖다 쓴 함수
    - 자신의 프로그램 실행 파일에 포함되어 있음
  - 커널 함수
    - 운영체제 프로그램의 함수
    - 커널 함수의 호출 == 시스템 콜

## 프로그램의 실행

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os105.png)

시스템 콜을 하면 커널 모드가 되고, 시스템 콜 끝나면 다시 A가 cpu 제어권을 가짐