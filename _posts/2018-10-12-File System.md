---
layout: post
title:  "File System"
date:   2018-10-12
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png
---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## File and File System

- File 
  - 이름을 통해 접근 (cf. 메모리는 주소를 통해 접근)
  - A named collection of related information
  - 일반적으로 비화발성의 보조기억장치에 저장
  - 운여체제는 다양한 저장 장치를 file이라는 동일한 논리적 단위로 볼 수 있게 해줌
  - 연산
    - create / read / write / reposition (lseek) / delete / open / close

- File attritbute ( or 파일의 metadata)
  - 파일 자체의 내용이 아니라 파일을 관리하기 위한 각종 정보들
    - 파일 이름, 유형, 저장된 위치, 파일 사이즈
    - 접근 권한 (읽기, 쓰기, 실행), 시간 (생성, 변경, 사용), 소유자 등
- File System
  - 운영체제에서 파일을 관리하는 부분
  - 파일 및 파일의 메타데이터, 디렉토리 정보 등을 관리 
  - 파일의 저장 방법 결정
  - 파일 보호 등 

## Directory and Logical Disk

- Directory
  - 파일의 메타데이터 중 일부를 보관하고 있는 일종의 특별한 파일 
  - 그 디렉토리에 속한 파일 이름 및 파일 attribute 들
  - 연산
    - search for a file, create a file, delete a file
    - list a direcotry, rename a file, traverse the file system
- Partition (==Logical Disk)
  - 하나의 물리적 디스크 안에 여러 파티션을 두는게 일바적
  - 물리적 디스크를 파티션으로 구성한 뒤 각각의 파티션에 file system을 깔거나 swapping 등 다른 용도로 사용 가능

## open()

![image-20181012100206345](/Users/junhee/Library/Application Support/typora-user-images/image-20181012100206345.png)

![image-20181012100705152](/Users/junhee/Library/Application Support/typora-user-images/image-20181012100705152.png)

open도 시스템 콜

운영체제에게 CPU 제어권이 넘어가

운영체제는 root를 먼저 open

root의 content를 찾아

a라는 파일의 메타데이터를 찾아서 이걸 메모리에 올려

a의 메타데이터로부터 a의 내용을 찾아

a안의 b의 metadata를 메모뢰에 올려

각 프로세스마다 그 프로세스가 오픈한 파일들에 대한 메타데이터 포인터를 가지고 있는 일종의 배열이 있어

b의 metadata를 가리키고 있는 index 가 file discriptor (fd) 를 사용자 프로세스에게 리턴

read(fd..)

fd를 가진 파일에서 읽어와

A의 PCB에 가서 해당 fd에 대응하는 파일의 metadata로부터 b의 내용에 접근

b 내용을 읽어서 운영체제가 자신의 메모리 공간 일부에 읽어놔 ( )

copy해서 사용자 프로그램에게 전달

다른 프로그램이나 이 프로그램이 동일한 파일의 동일한 위치를 read 요청하면

디스크까지 가는것이 아니라 운영체제가 읽어놓은거 바로 전달 

이게 바로 buffer caching

## File Protection

각 파일에 대해 누구에게 어떤 유형의 접근(read/write/execution) 을 허락할 것인가?

Access Control 방법

- Access Control Matrix
  - ![image-20181012101358308](/Users/junhee/Library/Application Support/typora-user-images/image-20181012101358308.png)
  - 공간 낭비 발생해서
  - Access Control List : 파일별로 누구에게 어떤 접근 권한이 있는지 ( Linked list )
  - Capability : 사용자 별로 자신이 접근 권한을 가진 파일 및 해당 권한 (Linked List)
- Grouping
  - 전체 user를 owner / group / public 의 세 그룹으로 구분
  - 각 파일에 대해서 세 그룹의 접근 권한(rwx)을 3 비트씩으로 표시
  - 9개의 비트만으로 표현 가능
    - ![image-20181012101548393](/Users/junhee/Library/Application Support/typora-user-images/image-20181012101548393.png)



- password
  - 파일 마다 패스워드 두는 방법 ( 디렉토리 파일에 두는 방법도 가능)
  - 모든 접근 권한에 대해 하나의 패스워드 : all or nothing
  - 접근 권한별 패스워드 : 암기문제, 관리문제

## File System의 Mounting

루트 파일 시스템의 특정 디렉토리 이름에 또 다른 파티션에 있는 파일 시스템을 마운팅 하면

마운트 된 디렉토리에 접근하면 또 다른 파일 시스템의 루트 디렉토리에 접근하게 됨

![image-20181012101831384](/Users/junhee/Library/Application Support/typora-user-images/image-20181012101831384.png)

## Access Methods

시스템이 제공하는 파일 정보의 접근 방식

- 순차 접근
  - 카세트 테이프를 사용하는 방식처럼 접근
  - 읽거나 쓰면 offset은 자동적으로 접근
  - a b c 순서대로 저장되어 있는데 b 보고 싶으면 a를 먼저 접근해야함 
- 직접 접근
  - 파일을 구성하는 레코드를 임의의 순서로 접근할 수 있음
  - a b c 순서대로 저장되어 있는데 b 보고 싶으면 바로 볼 수 있음