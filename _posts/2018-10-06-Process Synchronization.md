---
layout: post
title:  "Process Sysncronization"
date:   2018-10-06
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png
---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## 데이터의 접근

데이터를 읽어와서 연산하고 다시 저장

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100601.png)

## Race Condition

S-box를 공유하는 E-box가 여럿 있는 경우 Race Condition의 가능성이 있음

ex) 커널 모드 수행 중 인터럽트로 커널모드 다른 루틴 수행시

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100602.png)

## race condition (1/3)

- kernel 수행 중 인터럽트 발생
- 커널모드 running 중 inetrrupt 발생하여 인터럽트 처리 루틴이 수행
- 양쪽 다 커널 코드이므로 kernel address space 공유

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100603.png)

## race condition (2/3)

해결책 : 커널 모드에서 수행 중일 때는 CPU를 preempt 하지 않음. 커널 모드에서 사용자 모드로 돌아 갈때 preempt.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100604.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100605.png)

## race condition (3/3)

- CPU가 여러개인 경우

- 해결
  - 커널 내부에 있는 각 공유 데이터에 접근할 때마다 그 데이터에 lock / unlock을 하는 방법
  - 한번에 하나의 CPU만이 커널에 들어갈 수 있게 하는 방법

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100606.png)​	

## Process Syncronization 문제

- 공유 데이터의 동시 접근은 데이터의 불일치 문제 발생시킬 수 있음
- 일관성 유지를 위해서 협력 프로세스간의 실행순서를 정해주는 매커니즘 필요
- Race condition
  - 여러 프로세스들이 동시에 공유 데이터를 접근하는 상황
  - 데이터의 최정 연산 결과는 마지막에 그 데이터를 다룬 프로세스에 따라다라짐
  - 이를 막기 위해 concurrent processsms 동기화 되어야한다.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100607.png)	

## The Critical-Section Problem

공유 데이터를 접근하는 코드

- n개의 프로세스가 공유 데이터를 동시에 사용하기를 원하는 경우
- 각 프로세스의 code segment에는 공유 데이터를 접근하는 코드인 ciritical sectoin이 존재
- 하나의 프로세스가 ciritical section에 있을 때 다른 모든 프로세스는 ciritical section에 들어갈 수 없어야한다.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/100608.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100701.png)

## 프로그램적 해결법의 충족 조건

- Mutual Exclution
  - 프로세스가 pi가 critical section 부분을 수행중이면 다른 모든 프로세스들은 그들의 critical section에 들어가면 안된다.
- Progress
  - 아무도 critical section에 있지 않은 상태에서 critical section에 들어가고자 하는 프로세스가 있으면 critical section에 들어가게 해주어야 한다.
- Bounded Wating
  - 프로세스가 critical section에 들어가려고 요청한 후부터 그 요청이 허용될 때까지 다른 프로세스들이 critical section에 들어가는 횟수에 한계가 있어야 한다.

## 알고리즘 1

P0

int turn ;

initially turn=0; (turn이 0 : 0번 프로세스 차례)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100702.png)

P0이 빈번히 들어가고 싶으면?

## 알고리즘 2

boolean flag[2];

initially flag[모두] =false; // no one is in CS

Pi ready to enter its critical section if flag[i] == true

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100703.png)

들어가기전에 둘다 깃발을 들으면 아무도 못들어가.

## 알고리즘3 (Peterson's Algorithm)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100704.png)

Busy Wating (spin lock)

내가 CPU를 잡고 while문에 있는데, 그때 다른 애가 CPU를 잡으면 ? 

## Sysnchnization Hardware

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100705.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100706.png)

- 하드웨어적으로 Test & modify를 atuomic하게 수행할 수 있도록 지원하는 경우 앞의 문제는 간단히 해결
- 값을 읽어내고 바꾸는 과정을 한번에

## Semaphores

앞의 방식들을 추상화시킴

- Semaphore S

  - integer variable

  - P(S) : 공유자원 획득

    - If positive, decrement & enter. Ohterwise, wait until positive(busy wait)

    ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100707.png)

  - V(S) : 공유자원 반납

    ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100708.png)

## Critical Section of n Processes

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100709.png)

## Block / Wakeup Impemetation

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100710.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100711.png)

- block
  - 커널은 block을 호출한 프로세스를 suspend 시킴
  - 이 프로세스의 PCB를 semaphore에 대한 wait queue에 넣음
- wakeup(P)
  - block 된 프로세스 P를 wakeup 시킴
  - 이 프로세스의 PCB를 ready queue로 옮김

## Implementation

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100712.png)

## Which is better

busy-wati vs block/wakeup

CS 길이가 긴 경우 Block/Wakeup이 적당

CS 길이가 매우 짧은 경우 Block/Wakeup 오버헤드가 busy-wait 오버헤드보다 더 커질 수 있음

일반적으로  block/wakeup 방식이 더 좋음

## Deadlock and Starvation

- Deadlock

  둘 이상의 프로세스가 서로 상대방에 의해 충족될 수 있는 event를 무한히 기다리는 현상

  P0와 P1은 S와 Q 모두가 필요하다.

  P0가 S를 차지했을 때, P1이 CPU를 가져가버리면, Deadlock 발생

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100713.png)

- Starvation

  indefinite blocking. 프로세스가 suspend된 이유에 해당하는 세마포어 큐에서 빠져나갈수 없는 현상

## Bounded-Buffer Problem

Producer-Consumer Problem

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100714.png)

주황색은 Producer가 생성한다.

생산자 둘이 한 위치에 생성하면?

하나를 소비자 둘이 동시에 소비 하려고 하면?

비버있는 버퍼가 없는데 또 생산자가 만들려고 하면?

- Syncrhonization variables

  - mutual exclution
    - need binary semaphore (shared data의 mutual exlusion을 위해)
    - lock 걸고 풀고
  - resource count 
    - need integer semaphore (남은 full/empty buffer의 수 표시)
    - 자원 개수

  semaphore full =0, empty =n, mutex =1;

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100715.png)

- Produer
  - 빈 버퍼가 있으면 버퍼 획득하고, 버퍼에 락 걸고, 버퍼에 데이터 넣고, 버퍼에 락 풀고, full++

- Consumer
  - 내용이 들어잇는 버퍼 있으면, 버퍼에 락 걸고, 버퍼에서 데이터 빼고, 버퍼 락 풀고, empty ++

## Readers-Writes Problem

한 process가 DB에 write 중일 때 다른 process가 접근하면 안됨 / read는 동시에 여럿이 해도 됨

- Shared data
  - DB 자체
  - int readcount=0; //현재 DB에 접근 중인 Reader의 수
- Sysncronization variablees
  - semaphore mutex =1 ( 공유변수 readcount를 접근하는 코드의 mutual exlution 보장), db=1;

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100716.png)

## Dining-Philosophers Problem

배가 고파지면 자기의 왼쪽과 오른쪽에 놓아져 있는 젓가락을 잡음

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100717.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100718.png)

- 문제
  - 모두다 왼쪽 젓가락을 잡아버리면? 
  - Deadlock

- 해결
  - 4명의 철학자만이 테이블에 동시에 앉을 수 있도록
  - 젓가락을 두개 모두 집을 수 있을 때에만 젓가락을 잡을 수 있도록 (아래의 경우)
  - 비대칭. 짝수 철학자는 왼쪽 젓가락부터 집도록



enum {thinking, hungry, eating} state[5];

semaphore self[5]=0;	// 동시에 젓가락 두개 모두 잡을 수 있는 권한

semaphore mutex=1;

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100719.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100720.png)

## Monitor

- Semaphore의 문제점
  - 코딩이 힘들다
  - 정확성의 입증이 어려움
  - 자발적 협력이 필요
  - 한번의 실수가 모든 시스템에 영향

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100721.png)

- 동시 수행중인 프로세스 사이에서 abstract data type의 안전한 공유를 보장하기위한 high-level syncronization  construct 
  - 모니터 내에서는 한번에 하나의 하나의 프로세스만이 활동 가능
  - 프로그래머가 동기화 제약 조건을 명시적으로 코딩할 필요 없음
  - 프로세스가 모니터 안에서 기다릴수 있도록 하기 위해 condition variable 사용. condition x, y
  - condition variable 은 wait와 signal 연산에 의해서만 접근 가능
    - x.wait();
      - x.wait()을 invoke한 프로세스는 다른 프로세스가 x.signal()을 invoke 하기 전까지 suspend
    - x.siganl();
      - x.signal()은 정확하게 하나의 suspend된 프로세스를 resume한다. Suspend된 프로세스가 없으면 아무 일도 일어나지 않는다. 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100722.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100723.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os100724.png)