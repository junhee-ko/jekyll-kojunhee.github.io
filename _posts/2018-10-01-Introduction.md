---
layout: post
title:  "Introduction"
date:   2018-10-01
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png

---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## 운영체제란

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/oss101.png)

- 컴퓨터 하드웨어 바로 위에 설치되어 사용자 및 다른 모든 소프트웨어와 하드웨어를 연결하느 소픝웨어 계층
  - 협의의 운영체제(커널)
    - 운영체제의 핵심 부분, 메모리에 상주하는부분
  - 광의의 운영체제
    - 커널 뿐만 아니라 각족 주변 시스템 유틸리티를 포함한 개념

## 운영체제의 목표

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/oss102.png)

- 컴퓨터 시스템을 편리하게 사용하도록 환경 제공
  - 운영체제는 동시 사용자/프로그램들이 각각 독자적으로 컴퓨터에서 수행되는 것 같은 환상 제공
  - 하드웨어를 직접 다루는 복잡한 부분을 운영체제가 대행
- 컴퓨터 시슴템의 자원을 효율적으로 관리 (*)
  - 프로세서, 기억장치, 입출력 장치 등의 효율적관리
    - 사용자간의 형평성 있는 자원 분배
    - 주언진 자원으로 최대한의 성능을 내도록
  - 사용자 및 운영체제 자신의 보호
  - 프로세스, 파일, 메시지 등을 관리

## 운영체제의 분류

- 동시작업 가능 여부
  - 단일 작업(single tasking)
    - MS-DON 프롬프르 상에서는 한 명령의 수행을 끝내기 전에 다른 명령을 수행시킬 수 없음
  - 다중 작업(multi tasking)
    - 동시에 두개 이상의 작업 처리
    - UNIX/MS Windows 등에서는 한 명령의 수행이 끝나기 전에 다른 명령이나 프로그램을 수행할 수 있음
- 사용자의 수
  - 단일 사용자
    - MS-DOS, MS Windows
  - 다중 사용자
    - UNIX, NT server
- 처리 방식
  - 일괄처리(batch processing)
    - 작업 요청의 일정량 모아서 한꺼번에 처리
    - 작업이 완전 종료될 때까지 기다려야함
    - 초기 Punch Card 처리 시스템
  - 시분할(time sharing)
    - 여러 작업을 수행할때 컴퓨터 처리 능력을 일정한 시간 단위로 분할하여 사용
    - interactive한 방식
    - 짧은 응답시간을 가짐
  - 실시간(Realtime OS)
    - 정해진 시간안에 어떠한 일이 반드시 종료됨이 보장되어야 하는 실시간 시스템을 위한 OS
    - 원자로/공장제어, 미사일제어, 반도체 장비, 로보트제어
    - Hard realtime system / Soft realtime system

## 몇 가지 용어

- Multitasking
  - 여러 프로그램을 동시에 수행한다는 뜻
- Multiprogramming
  - 메모리에 여러 프로그램이 올라가 있음을 강조
- Time sharing
  - CPU의 시간을 분할하여 나누어쓴다는 의미
- Multiprocessor
  - 하나의 컴퓨터에 CPU가 여러개 붙어 있음을 의미

## 운영 체제의 예

- UNIX 계열
  - 대형 컴퓨터를 위한 OS
  - 코드의 대부분을 C언어로 작성
  - 소스 코드 공개
  - 높은 이식성
    - 하나의 컴퓨터에서 돌아가는 UNIX를 전혀 다른 컴퓨터에 이식하기 쉬움
  - 최소한의 커널 구조
    - 핵심적인 것만 커널에 넣음
  - 다양한 버전
    - System V, FreeBSD, SunOS, Solaris
    - Linux
- Windows 계열
  - DOS
    - MS사에서 개인용 PC를 위해 개발
    - 메모리 관리 능력의 한계 
  - MS Windows 
    - 다중 작업용 GUI 기반 OS
    - 풍부한 지원 소프트웨어

## 운영체제의 구조

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/oss103.png)

