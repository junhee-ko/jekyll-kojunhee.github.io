---
layout: post
title:  "Memory Management"
date:   2018-10-09
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png
---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## Logical vs Physical Address

- Logical address (=virtual address)
  - 프로세스마다 독립적으로 가지는 주소 공간
  - 각 프로세스마다 0번지 부터 시작
  - CPU가 보는 주소는 logical address임 

- physical address 
  - 메모리에 실제 올라가는 위치 

- 주소바인딩 : 주소를 결정하는 것
  - Symbolic address ->Logical Address -> Physical address

## Address Binding 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm01.png)

컴파일 타임 바인딩이나 로드 타임 바인딩 모두 실행될때 물리주소가 결정되지만, 

런타임 바인딩은 실행 이후에도 물리 주소가 바뀔 수 있다.

소스코드 : A위치에 있는 값과 B위치에 값을 더해서 A에 저장해라. C위치로 점프해라

- Compile time binding
  - 물리적 메모리 주소가 컴파일 시 알려짐
  - 시작 위치 변경시 재컴파일
  - 컴파일러는 절대코드(absolute code) 생성
- Load time binding
  - Loader의 책임 하에 물리적 주소 부여
  - 컴파일러가 재배치가능코드를 생성하는 경우 가능
- Execution time binding(run time binding)
  - 수행이 시작된 이후에도 프로세스의 메모리 상 위치를 옮길 수 있음
  - CPU가 주소를 참조할 때마다 binding을 점검
  - 하드웨어적인 자원이 필요 (base and limit registers, MMU)

## Memory-Management Unit (MMU)

logical address를 physical address로 매핑해 주는 hardware device

- MMU scheme
  - 사용자 프로세스가 CPU에서 수행되며 생성해내는 모든 주소값에 대해 base regiseter(relocation register)의 값을 더한다.
- user program
  - logical address만을 다룬다
  - 실제 physical address를 볼수 없으며 알 필요가 없다.

## Dynamic Relocation

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm02.png)

CPU가 프로세스 p1의 346번지를 요청한 상태.

프로세스1은 물리주소 14000번지에 올라가있음.

논리주소에 시작위치(relocation register)를 더해서 14346 구함.

한가지 더 체크하는 것은?

프로세스 p1의 크기를 limit register가 가지고 있어.

CPU가 남의 프로그램의 메모리를 보려고 하는 시도를 막을 수 있음.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm03.png)

limit register : CPU가 요청하는 논리주소가 프로그램 크기보다 큰  논리 주소를 요청한 것은 아닌지 먼저 체크 

## Dynamic Loading 

프로세스 전체를 메모리에 미리 다 올리는 것이 아니라 해당 루틴이 불려질 때 메모리에 load 하는 것

- memory utilization 향상
- 가끔씩 사용되는 많은 양의 코드의 경우 유용 (ex) 오류 처리 루틴
- 운영체제의 특별한 지원 없이 프로그램 자체에서 구현 가능 (OS는 라이브러리를 통해 지원 가능)
- Loading : 메모리로 올리는 것

## Overlays

메모리에 프로세스 부분 중 실제 필요한 정보많을 올림

프로세스의 크기가 메모리보다 클 때 유용

운영체제의 지원없이 사용자에 의해 구현

작은 공간의 메모리를 사용하던 초창기 시스템에서 수작으로 프로그래머가 구현

Manual Overlay

프로그램이 매우 복잡

## Swapping

프로세스를 일시적으로 메모리에서 backing store로 쫓아내는것

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm04.png)

- backing store (swap area)
  - 디스크
  - 많은 사용자의 프로세스 이미지를 담을 만큼 충분히 빠르고 큰 저장 공간
- Swap in / Swap out
  - 일반적으로 중기 스케쥴러에 의해 swap out 시킬 프로세스 선정
  - CPU 우선순위가 낮은 프로세스를 swapped out 시킴
  - Compile time 혹은 Load time binding 에서는 원래 메모리 위치로 swap in 해야함
  - Execution time binding 에서는 추후 빈 메모리 영역 아무 곳에서나 올릴 수 있음 
  - swap time은 대부분 transfer time (swap 되는 양에 비례하는 시간) 임

## Dynamic Linking

Linking : 여러 군데 존재하던 컴파일된 파일들을 묶어서 실행 파일 만드는 것

- static linking 
  - 라이브러리가 프로그램의 실행 파일 코드에 포함됨
  - 실행 파일의 크기가 커짐
  - 동일한 라이브러리를 각각의 프로세스가 메모리에 올리므로 메모리 낭비 (ex. printf 함수의 라이브러리 코드)
- dynamic linking
  - 라이브러리가 실행시 연결됨
  - 라이브러리 호출 부분에 라이브러리 루틴의 위치를 찾기 위한 stub이라는 작은 코드를 줌 (라이브러리 위치 찾을 수 있는)
  - 라이브러리가 이미 메모리에 있으면 그 루틴의 주소로 가고 없으면 디스크에서 읽어옴
  - 운영체제의 도움이 필요

## Allocation of Physical Memory

- 메모리는 일반적으로 두 영역으로 나뉘어 사용
  - OS 상주 영역 
    - interrupt vector와 함께 낮은 주소 영역 사용
  - 사용자 프로세스 영역
    - 높은 주소 영역
- 사용자 프로세스 영역의 할당 방법
  - Contiguous allocation
    - 각각의 프로세스가 메모리의 연속적인 공간에 적재되록 하는 것
    - 고정분할방식 / 가변분할방식
  - Noncontiguous allocation
    - 하나의 프로세스가 메모리 영역에 분산되어 올라 갈수 있음
    - Paging / Segmentaion / Paged Segmentation

## Contiguous Allocation 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm05.png)

- 고정 분할 방식
  - 물리적 메모리를 몇 개의 영구적 분할(partition) 로 나눔
  - 분할의 크기가 모두 동일한 방힉과 서로  다른 방식이 존재
  - 분할당 하나의 프로그램 적재
  - 융통성 없음
    - 동시에 메모리에 load되는 프로그램의 수가 고정됨
    - 최대 수행 가능 프로그램 크기 제한
  - internal fragmentation, external fragmentation 발생
- 가변 분할 방식
  - 프로그램이 실핼될때마다 차곡차곡 메모리에 올려
  - 프로그램의 크기를 고려해서 할당
  - 분할의 크기, 개수가 동적으로 변함
  - 기술적 관리 기법 필요
  - external fragmenation 발생

## Hole

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm06.png)

- 가용 메모리 공간

- 가변분할 방식에서 생김
- 다양한 크기의 hole들이 메모리 여러 곳에 흩어져 있음
- 프로세스가 도착하면 수용 가능한 hole을 할당
- 운영체제는 다음의 정보를 유지
  - 할당공간(프로그램이 사용하고 있는)
  - 가용공간(hole)

- Dynamic Storage-Allocation Problem
  - 가변 분할 방식에서 size n인 요청을 만족하는 가장 적절한 hole을 찾는 문제
  - First-fit 
    - Size가 n이상인 것 중 최초로 찾아지는 Hole에 할당
  - Best-fit
    - Size가 n이상인 가장 작은 hole을 찾아서 할당
    - hole들의 리스트가 크기 순으로 정렬되지 않은 경우 모든 hole의 리스트를 탐색해야함
    - 많은 수의 아주 작은 hole들이 생성됨
  - Worst-fit
    - 가장 큰 hole에 할당
    - 역시 모든 리스트를 탐색해야함
    - 상대적으로 아주 큰 hole들이 생성됨
- Compaction
  - external fragmentation 문제를 해결하는 방법
  - 사용 중인 메모리 영역을 한구데로 몰고 hole들을 다 한곳으로 몰아 큰 block을 만드는 것
  - 매우 큰 비용이 드는 방법
  - 프로세스의 주소가 실행 시간에 동적으로 재배치 가능한 경우에만 수행될 수 있음

## Paging

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm07.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm08.png)

- Process의 virtual memory를 동일한 사이즈의 page 단위로 나눔
- virtual memory의 내용이 page 단위로 noncontiguous하게 저장됨
- 일부는 backing storage에 일부는 physical memory에 저장
- Basic method
  - physical memory를 동일한 크기의 frame으로 나눔
  - logical memory를 동일 크기의 page로 나눔 (frame과 같은 크기)
  - 모든 가용 frame들을 관리
  - page table을 사용하여 logical address를 physical address로 변환
  - external fragmentation 발생 안함
  - internal fragmentation 발생가능

- page table
  - 페이지들이 물리적인 메모리 어디에 올라가 있나
  - logical memory의 page 개수 만큼 entry 가 존재

- logical address
  - p : page 번호
  - d: 그 페이지 내에서 얼만큼 떨어져 있나

## Implementation of Page Table

- Page table은 main memory 에 상주

- Page table base register (PTBR) 가 page table을 가리킴

- Page table length register (PTLR) 가 테이블 크기를 보관

- 모든 메모리 접근 연산에는 2번의 memory access 필요

  - page table 접근 1번
  - 실제 data/instruction 접근  1번

- 속도 향상을 위해 associative register / translation look-aside buffter(TLB)

  라 불리는 고속의 lookup hardware cache 사용

## Paging Hardware with TLB

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm09.png)

 주소 변환을 위한 케쉬 메모리. 

빈번히 참조되는 엔트리 몇개 만을 가지고 있음.

전체 항목을 검색해야봐야함.  여기 어디에도 없으면 page table을 봄

TLB에서 전체 항목을 다 검색해야하기 때문에, parallel search로 빠르게 함. 병력적으로 한번에 쫙 검색함.

## Two-Level Page Table

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm10.png)

page table이 2단계. 

속도는 더 걸림. page table을 위한 공간은 줄어듦. 

주소공간에서 실제로 사용되지 않는 페이지에 대해서는 안쪽 테이블이 안만들어져.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm11.png)

- p1 
  - 10bit
  - outer page table의 index
- p2
  - 10bit
  - outer page table의 page에서의 변위(displacement)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm12.png)

## Multilevel Paging and Performance

Address space가 더 커지면 다단게 페이지 테이블이 필요.

각 단계의 페이지 테이블이 메모리에 존재하므로 logical address의 physical address 변환에 더 많은 메모리 접근 필요.

TLB를 통해 메모리 접근 시간을 줄일 수 있음.

## Valid / Invalid Bit in a Page Table

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm13.png)

- protection bit
  - page에 대한 접근 권한 (read /write / read-only)
- valid
  - 해당 주소의 frame에 그 프로세스를 구성하는 유요한 내용이 있음
- invalid
  - 프로세스가 그 주소 부분을 사용하지 않는 경우 
  - 해당 페이지가 메모리에 올라와 있지 않고 swap area에 있는 경우

## Inverted Page Table

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm14.png)

- Page table이 매우 큰 이유

  - 모든 process 별로 그 logical address에 대응하는 모든 page에 대해 page table entry 존재
  - 대응하는 page가 메모리에 있든 아니든 간에 page table에는 entry로 존재

- inverted page table

  - Page frame 하나당 page table에 하나의 entry를 둔것

  - 각 page table entry는 각각의 물리적 메모리의 page frame이 담고 있는 내용 표시

    (process-id, process의 logical address)

  - page frame 개수만큼 entry 존재.

  - entry 전부 검색해서 pid랑 p 찾아야함. associative registe 찾아서 병렬 검색을 함

  - 단점

    - 테이블 전체를 탐색

  - 조치

    - associative register 사용 (expensive)

## Shared Page

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm15.png)

공유할 수 있는 코드는 같은 프레임으로 매핑 시켜서 메모리에 한 카피만 올려

- Shared code

  - Re-entrant Code (= Pure code)

  - read-only 로 하여 프로세스 간에 하나의 code만 메모리에 올림

    (eg, text editords, compilers, window systems)

  - Shared code는 모든 프로세스의 logical address space에서 동일한 위치에 있어야함

    - 위 그림에서, ed1, 2, 3 순으로 되어야 함

- Private code and data

  - 각 프로세스들은 독자적으로 메모리에 올림
  - private data는 logical addreess space 의 아무 곳에 와도 무방

## Segmentation

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm16.png)

프로그램은 의미 단위인 여러 개의 segment로 구성

작게는  프로그램을 구성하는 함수 하나하나를 세그먼트로 정의

크게는 프로그램 전체를 하나의 세그먼트로 정의 가능

일반적으로 code, data, stack 부분이 하나씩 세그먼트로 정의됨

Segment는 의미 단위 이기 떄문에 공유와 보안에 있어서 paging 보다 효과적

Segment의 길이가 동일하지 않으므로 가변 분할 방식에서와 동일한 문제점들이 발생

- Logical address는 다음의 두가지로 구성
  - <segment-number, offset>
- Segment table
  - each table entry has
    - base : starting physical address of the segment
    - limit : length of the segment
  - Segment-table base reigster (STLR)
    - 물리적 메모리에서의 segment table의 위치 
  - Segment-table length reigster (STLR)
    - 프로그램이 사용하는 segment의 수

- 체크
  - 세그먼트 번호가 STLR 보다 작은지 체크해야함 
  - 세그먼트의 길이보다 세그먼트안에서 떨어진 offset 값이 더 크지는 않은가

## Segmentation Example 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm17.png)

다섯 개의 segment. 각각의 세그먼트에 대해서 주소 변환을 위한 테이블이 있음

## Sharing of Segments

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm18.png)

0번 세그먼트는 같은 역할을 하는 세그먼트. 이 두 개의 세그먼트는 같은 물리주소에 올라감.

1번 세그먼트는 다른 물리주소에 올라감.

## Segmentation with Paging

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mmmm19.png)

세그먼트 하나가 여러개의 페이지로 구성

먼저 세그먼트에 대해 주소 변환

logical address : 세그먼트 번호와 세그먼트 안에서 얼마나 떨어있는지

STBR에 세그먼트 시작 위치가들어있고, 거기서부터 위에서부터 s번째 엔트리에 가면 page table의 시작 위치가 나옴

 세그먼트의 길이보다 세그먼트 안에서 떨어진 offset이 크다면 잘못된 요청

d는 page 번호와 page 안에서 얼마나 떨어져 있는지 (p, d`)

page table의 시작 위치로부터 page 번호 만큼 떨어진 엔트리에 가면 이 페이지에 대한 주소 변환 결과 (물리적인 메모리의 몇번째 프레임인지) 나와

- pure segmentation 과 차이점
  - segment-table entry가 segment의 base address를 가지고있는 것이 아니라, segment를 구서하는 page table의 base address를 가지고 있음

## 주소 변환을 위한 OS의 역할

어떤 프로세스가 CPU를 가지고 메모리 접근을 하는데, 

주소 변환을 할 때 마다 운영체제가 중간에 개입하면 CPU가 이 프로세스로부터 운영체제에게 넘어가야돼.

주소 변환 다 했으니까 다시 CPU가 이 프로세스에게 넘어온다? 말이 안돼. 

주소 변환은 무조건 하드웨어적으로 일어남. IO 장치에 접근하려면 OS가 끼어들어야돼.