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
  - 운영체제는 다양한 저장 장치를 file이라는 동일한 논리적 단위로 볼 수 있게 해줌
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

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem02.png)

1. open시스템 콜을 하면 운영체제에게 CPU 제어권이 넘어가

2. 운영체제는 root를 먼저 open하여 root의 content를 찾아

3. a라는 파일의 메타데이터를 찾아서 이걸 메모리에 올려

4. a의 메타데이터로부터 a의 내용을 찾아

5. a안의 b의 metadata를 메모리에 올려



각 프로세스마다 그 프로세스가 오픈한 파일들에 대한 메타데이터 포인터를 가지고 있는 일종의 배열이 있어

b의 metadata를 가리키고 있는 index 가 file discriptor (fd) 를 사용자 프로세스에게 리턴

read(fd..)

fd를 가진 파일에서 읽어와

A의 PCB에 가서 해당 fd에 대응하는 파일의 metadata로부터 b의 내용에 접근

b 내용을 읽어서 운영체제가 자신의 메모리 공간 일부에 읽어놓음.

copy해서 사용자 프로그램에게 전달

다른 프로그램이나 이 프로그램이 동일한 파일의 동일한 위치를 read 요청하면

디스크까지 가는것이 아니라 운영체제가 읽어놓은거 바로 전달 

이게 바로 Buffer caching

## File Protection

각 파일에 대해 누구에게 어떤 유형의 접근(read/write/execution) 을 허락할 것인가?

Access Control 방법

- Access Control Matrix

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem03.png)

  - 공간 낭비 발생해서
  - Access Control List : 파일별로 누구에게 어떤 접근 권한이 있는지 ( Linked list )
  - Capability : 사용자 별로 자신이 접근 권한을 가진 파일 및 해당 권한 (Linked List)
- Grouping
  - 전체 user를 owner / group / public 의 세 그룹으로 구분
  - 각 파일에 대해서 세 그룹의 접근 권한(rwx)을 3 비트씩으로 표시
  - 9개의 비트만으로 표현 가능

    ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem04.png)

- password
  - 파일 마다 패스워드 두는 방법 ( 디렉토리 파일에 두는 방법도 가능)
  - 모든 접근 권한에 대해 하나의 패스워드 : all or nothing
  - 접근 권한별 패스워드 : 암기문제, 관리문제

## File System의 Mounting

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem05.png)

루트 파일 시스템의 특정 디렉토리 이름에 또 다른 파티션에 있는 파일 시스템을 마운팅 하면,

마운트 된 디렉토리에 접근하면 또 다른 파일 시스템의 루트 디렉토리에 접근하게 됨



## Access Methods

시스템이 제공하는 파일 정보의 접근 방식

- 순차 접근
  - 카세트 테이프를 사용하는 방식처럼 접근
  - 읽거나 쓰면 offset은 자동적으로 접근
  - a b c 순서대로 저장되어 있는데 b 보고 싶으면 a를 먼저 접근해야함 
- 직접 접근
  - 파일을 구성하는 레코드를 임의의 순서로 접근할 수 있음
  - a b c 순서대로 저장되어 있는데 b 보고 싶으면 바로 볼 수 있음

## Allocation of File Data in Disk

1. contiguous allocation
2. Linked Allocation
3. Indexed Allocation

## Contiguous Allocation

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem06.png)

블럭의 크기가 2면, 0 1 이렇게 들어감.

direcotory 에 5개의 파일 메타데이터를 가지고 있음

0번 위치부터 길이 2면, 0 1 이렇게 저장됨

- 단점
  - 외부 조각이 생길 수 있어
  - 파일 크키가 커질 수 있다는 거에 제약 (=file grow가 어려움)
  - 파일 커질 것을 대비해서 미리 어느 정도 공간 할당하면 내부조각 발생 (공간의 낭비)
- 장점
  - Fast I/O
  - 한번의 seek/rotation 으로 많은 bite transfer
  - Direct access(=random access) 가능
  - mail의 경우, 앞에서부터 5번째 보고 싶다. 그럼 19에다가 5 더하면 돼

## Linked Allocation 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem07.png)

jeep이란 파일의 시작은 9번이고, 두번째 블럭은 9번에 적혀 있어.

시작위치만 directory가 가지고 있어.

- 장점
  - 외부조각 발생하지 않아
- 단점
  - 직접 접근이 안돼
  - 4번째 위치 보려면 1, 2, 3 번째 봐야해
  - 한 sector가 고장나 pointer가 유실되면 많은 부분을 잃음
  - pointer를 위한 공간이 block의 일부가 되어 공간 효율성이 떨어짐
- 변형
  - File allocation table (FAT) 파일 시스템

## Indexed Allocation 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem08.png)

- 장점
  - 외부 조각 발생하지 않아
  - direct access 가능
- 단점 
  - small file의 경우 공간 낭비
  - too large file의 경우 하나의 block으로 index저장하기에 부족
    - 해결
      - linked scheme
      - multil-level index

## UNIX 파일 시스템의 구조

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem09.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem10.png)

- Boot block
  - 어떤 파일 시스템이든 가장 먼저 나와
  - 부팅에 필요한 정보
- Super block
  - 파일 시스템에 관한 총체적인 정보 담고 있음
  - 어디가 빈 블럭이고 어디가 사용되고 있는지
  - 어디부터 Inode list이고 data block 이고 ..
- Inode list
  - 파일 하나당 Inode 하나 할당
  - Inode는 그 파일의 메타데이터를 가지고 있어
  - 파일의 이름은 디렉토리가 직접 가지고 있어
  - indirect : 따라가면 index를 거쳐서 파일의 위치 정보 찾아
- Data block
  - 파일의 실제 내용 보관

## FAT file system

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem11.png)

- FAT
  - 위치 정보만 FAT가 가지고 있어
  - FAT의 217 번지에 217번지의 다음 블럭 번지가 저장되어 있어
  - 직접 접근 가능(메모리에 올라와 있는 FAT만 참고하여 바로 위치 알아낼 수 있어)

## Free-Space Management

중간 중간 비어 있는 블럭은 어떻게 관리?

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem12.png)

- bit
  - 부가적인 공간을 필요
  - 연속적인 n개의 free block을 찾는데 효과적
  - 연속적으로 0인 공간을 찾는데 쉬워

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem13.png)

- Linked Free-Space List on Disk

  - 모든 free block들을 링크로 연결 (free list)
  - 연속적인 가용 공간을 찾는 것은 쉽지 않다
  - 공간의 낭비가 없다

- Grouping

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem20.png)

  - 비어 있는 위치가 index 역할
  - linked list 방법의 변형

  - 첫번째 free block 이 n개의 포인터를 가짐

- Counting

  - (first free block, # of contiguous free blocks) 을 유지 

## Directory Implementation

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem14.png)

- Linear list
  - <file name, file의 metadata)의 list
  - 구현이 간단
  - 디렉토리 내에 파일이 있는지 찾기위해서는 linear search 필요
- Hash table
  - linear list + hashing
  - file name을 이 파일의 linear list의 위치로 바꿔줌
  - search time을 없앰
  - collision 발생 가능

- file 의 metadata 보관 위치

  - 디렉토리 내에 직접 보관
  - 디렉토리에는 포인터를 두고 다른 곳에 보관
    - inode, FAT 등

- Long file name의 지원

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem15.png)

  - <file name, file의 메타데이터> 의 리스트에서 각 entry는 일반적으로 고정 크기
  - file name이 고정 크기의 entry길이보다 길어지는 경우 entry의 마지막 부분에 이름의 뒷 부분이 위치한 곳의 포인터를 두는 방법
  - 이름의 나머지 부분은 동일한 directory file의 일부에 존재

## VFS and NFS 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem16.png)

- Virtual File System (VFS)
  - 서로 다른 다양한 file system에 대해 동일한 시스템콜 인터페이스를 통해 접근할 수 있게 해주는 OS의 layer
- Network File System
  - 분산 시스템에서는 네트워크를 통해 파일이 공유될 수 있음
  - 분산 환경에서의 대표적인 파일 공유 방법

## Page cache and Buffer cache

OS는 사용자 프로그램의 요청을 받아서 디스크에서 읽어온 내용을 그냥 전달하고 끝내는 것이 아니라, 자신의 버퍼 케쉬 영역에 읽어 놓고, 그 내용을 카피해서 사용자 프로그램에게 넘겨줘

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem17.png)

- Page cache
  - Virtual memory의 pagin system에서 사용하는 pafe frame을 caching의 관점에서 설명하는 용어
  - Memory-Mapped I/O를 쓰는 경우 file의 I/O에서도 page cache 사용
- Memory-Mapped I/O
  - file의 일부를 virtual memory에 mapping
  - 매핑 시킨 영역에 대한 메모리 접근 연산은 파일의 입출력을 수행하게 함
- Buffer cache
  - 파일 시스템을 통한 I/O 연산은 메모리의 특정 영역인 buffer cache사용
  - file 사용의 locality 활용
  - 한번 읽어온 block에 대한 후속 요청시 buffer cache에서 즉시 전달
  - 모든 프로세스가 공용으로 사용
  - Replacement algiritm 필요(LRU, LFU 등)
- Unified Buffer Cache
  - 최근의 OS에서는 기존의 buffer cahce가 page cache에 통합

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/osfilesystem18.png)

- 왼쪽
  - read/write system call 하면 항상 OS에게 요청해서 받아옴
  - memory mapped IO를 쓰면, 일단 페이지 케쉬에 올라온 내용을 사용자 프로세스가 직접 메모리 접근해서 IO (이미 메모리에 올라온 내용은 커널의 도움을 받지 않음)