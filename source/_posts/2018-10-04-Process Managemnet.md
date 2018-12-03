---
layout: post
title:  "Process Management"
date:   2018-10-04
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png
---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## 프로세스 생성

- 부모 프로세스가 자식 프로세스 생성
- 프로세스의 트리(계층 구조) 생성
- 프로세스는 자원을 필요로 함
  - 운영체제로부터 받는다
  - 부모와 공유한다
- 주소 공간
  - 자식은 부모의 공간을 복사
  - 자식은 그 공간에 새로운 프로그램을 올림
- 유닉스의 예 : 복제 생성하고 덮어씌움
  - fork() 시스템 콜이 새로운 프로세스를 복제 생성
    - 부모를 그대로 복사
    - 주소 공간 할당
  - exec()
    - fork 다음에 이어지는  exec() 시스템 콜을 통해 새로운 프로그램을 메모리에 올림 (덮어 씌움)

## 프로세스 종료

- exit
  - exit 시스템 콜을 통해 프로세스가 마지막 명령을 수행한후 운영체제에게 이를 알려줌
  - 자식이 부모에게 output data를 보냄(via wait system call)
  - 프로세의 각종 자원들이 운영체제에게 반납됨
- abort
  - 부모 프로세스가 자식의 수행을 종료시킴
  - 자식이 할당 자원의 한계치를 넘어섬
  - 자식에게 할당된 테스크가 더 이사 필요하지 않음
  - 부모가 종료하는 경우
    - 운영체제는 부모 프로세스가 종료하는 경우 자식이 더 이상 수행되도록 두지 않음
    - 단계적인 종료

## fork() system call

왼쪽은 부모, 오른쪽은 자식. 자식은 fork() 이후의 라인부터 실행

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100401.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100402.png)

## exec() system call

새로운 프로그램을 덮어씌움. 

부모가 자식을 만든다음에, 자식은 오른쪽의 date라는 프로그램으로 완전히 덮어씌었음

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100403.png)

## wait() system call

프로세스 A가 wait() system call을 하면, 

커널은 child가 종료될 때까지 프로세스 A를 slepp 시킴(block 상태)

child process가 종료되면 커널은 프로세스 A를 깨움(ready 상태)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100404.png)

## exit() system call

프로세스의 종료

- 자발적 종료
  - 마지막 statement 수행 후에 exit() 시스템 콜 통해
  - 프로그램에 명싱적으로 적어주지 않아도 main 함수가 리턴되는 위치에 컴파일러가 넣어줌
- 비자발적 종료
  - 부모가 자식을 죽임
    - 자식이 한계치 넘어서는 자원 자원 요청
    - 자식에게 할당된 테스크가 더이상 필요하지 않음
  - 키모드로 kill, break 친 경우
  - 부모가 종료하는 경우
    - 부모가 종료하기 전에 자식들이 먼저 종료됨

## 프로세스 간 협력

- 독릭접 프로세스
  - 프로세는 각자의 주소 공간을 가지고 수행되므로 원친적으로 하나의 프로세스가 다른 프로세스의 수행에 영향을 미치지 못함
- 협력 프로세스
  - 하나의 프로세스가 다른 프로세싀의 수행에 여향을 미칠 수 있음
- 프로세스 간 협력 메커니즘(IPC : Interprocess Communication)
  - 메세지를 전달하는 방법 (message passing)
    - 커널을 통해 메세지 전달
  - 주소 공간을 공유하는 방법 (shraed memory)
    - 서로 다른 프로세 간에도 일부 주소 공간을 공유하게하는 메커니즘

## IPC

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100405.png)

## Message Passing

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100406.png)

- Direcit Communicaiton
  - 통신하려는 프로세스의 이름을 명시적으료 표시

- Indirecit Communicaiton
  - mailbot or port 를 통해 메시지를 간접 전달

