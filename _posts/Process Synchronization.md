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

