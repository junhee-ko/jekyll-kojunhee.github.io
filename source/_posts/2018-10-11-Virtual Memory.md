---
layout: post
title:  "Virtual Memory"
date:   2018-10-11
categories: OS
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/os.png
---

출처 : 이화여자대학교 반효경 (http://www.kocw.net/home/search/kemView.do?kemId=1046323)

## Demand Paging 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP01.png)

- 실제로 필요할 때 page를 메모리에 올리는 것
  - I/O양의 감소
  - Memory 사용량 감소
  - 빠른 응답 시간
  - 더 많은 사용자 수용

- Valid / Invalid bit의 사용
  - Valid
    - 사용되지 않는 주소 영역인 경우
    - 페이지가 물리적 메모리에 없는 경우
  - 처음에는 모든 page entry 가 invalid로 초기화
  - address translation 시에 invalid bit이 set되어 있으면 "page fault"
    - 요청한 페이지가 메모리에 없는 경우
    - 운영체제가 CPU를 가지고 fault난 페이지를 메모리에 올림 

## Page Fault

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP02.png)

- invalid page를 접근하면 MMU가 trap을 발생시키고 (page fault trap)
  - Kernel mode로 들어가서 page fault handler 가 invoke 됨
- 다음과 같은 순서로 page fault 를 처리
  - invalid reference? (eg. bad address, protection violation) => abort process
    - 잘못된 요청인지 아닌지 체크하는 것
  - get an empty page frame (replace : 없으면 뺏어온다)
  - 해당 페이지를 disk 에서 memory로 읽어온다
    - disk I/O가 끝나기까지 이 프로세스는 CPU를 preempt 당함 (block)
    - Dist read가 끝나면 page tables entry 기록, valid/invalid bit = "valid"
    - ready queue에 process를 insert -> dispatch later
  - 이 프로세스가 CPU를 잡고 다시 running
  - 아까 중단되었던 instruction 재개

## Page Replacement

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP03.png)

- Page replacement
  - 어떤 frame을 빼앗아 올지 결정
  - 곧바로 사용되지 않을 page를 쫗아내는 것이 좋음
  - 동일한 페이지가 여러번 메모리에서 쫓겨났다가 다시 들어올 수 있음
- Replacement Algoritm
  - page fault rate을 최소화 하는 것이 목표
  - 알고리즘을 평가 : 주어진 page reference string에 대해 page fault를 얼마나 내는지 조사

## Optimal Algorithm

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP04.png)

- 미래에 참조되는 페이지들을 미리 다 안다고 가정 : Offiline algorithm
- 가장 먼 미래에 참조되는 페이지를 replace
  - 네모칸 : 메모리
  - 빨간색 : 페이지 폴트 난 경우
  - 연보라 : 페이지 폴트 나지 않고 이미 메모리에 올라가 있는 경우
- 5번이 처음으로 참조 되는 경우
  - 1번이 바로 다음으로 참조되기 때문에, 메모리에서 쫓겨나지 않아
  - 4번이 가장 먼 미래에 참조되기 때문에, 4번이 쫓겨나

## FIFO Algorithm

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP05.png)

메모리에 먼저 들어온 것을 먼저 내쫓음

FIFO Anomaly : 메모리 크기 들어나면 성능이 안좋아져

## LRU(Least Recently Used) Algorithm

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP06.png)

가장 오래전에 참조된 것을 지움

- 5번이 처음으로 참조 되는 경우를 보면,
  - 2번이 가장 최근에 참조
  - 그 다음에 1번, 4번
  - 가장 오래 전에 참조된 것이 3번

## LFU (Least Frequently Used) Algorithm

참조 횟수가 가장 적은 페이지를 지움

- 최저 참조 횟수인 page가 여럿 있는 경우
  - 여러 page 중 임의로 선정
  - 선능 향상을 위해 가장 오래 전에 참조된 page를 지우게 구현할 수도 있다

## LRU / LFU 비교

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP07.png)

- LRU
  - 1번이 가장 오래 전에 참조되긴 했지만,
  - 과거에 많은 참조가 있었다는 것을 무시
- LFU
  - 비록 4번이 참조횟수가 한 번이지만
  - 이제 막 참조가 시작되는 걸 쫓아냄

## LRU / LFU 구현

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP08.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP09.png)

- LRU
  - 어떤 페이지가 참조될 때마다 그 페이지를 제일 아래 쪽에 매달고
  - 쫓아낼 때는 제일 위에 있는걸 쫓아내
- LFU
  - 참조 횟수 1이 늘어나면
  - 비교를 해서 어디까지 내려갈 수 있는지 체크 (min-heap으로 구현)

## Caching

- 캐슁 기법
  - 한정된 빠른 공강(cache)에 요청된 데이터를 저장해 두었다가 후속 요청히 캐쉬로부터 직접 서비스
  - paging sytem 외에도 cache memory, buffer caching, Web caching등 다양한 분야에 사용
- 시간 제약
  - 교체 알고리즘에서 삭제할 항목을 결정하는 일에 지나치게 많은 시간이 걸리는 경우 실제 시스템에서 사용할 수 없음
  - Buffer caching 이나 Web caching인 경우
    - O(1) 에서 O(logn) 정도까지 허용
  - Pagin System 인 경우
    - page fault 인 경우에만 OS가 관여
    - 페이지가 이미 메모리에 존재하는 경우 참조 시각등의 정보를 OS가 알 수 없음
    - O(1)인 LRU의 list 조작 조차 불가능 

## Paging System에서 LRU, LFU 가능한가?

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP10.png)

- page fault가 발생하면, trap 발생하여 CPU 제어권이 OS에게 넘어가

  - OS가 LRU 알고리즘을 사용한다면, OS가 가장 오래 전에 참조된 페이지를 알 수 있는가? NO

  - OS가 LFU 알고리즘을 사용한다면, OS가 가장 참조 횟수가 적은 페이지를 알 수 있는가? NO

- 프로세스가 요청한 페이지가 이미 메모리에 올라와있으면 
  - 운영체제에게 CPU가 넘어가지 않고
  - 하드웨어적으로 주소 변환해서 CPU가 바로 읽어들여
  - 그러면 이 페이지의 접근 시간을 운영체제는 몰라

## Clock Algorithm

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP11.png)

- LRU의 근사 알고리즘
- 여러 명칭
  - Second chance algorithm
  - NUR ( Not Used Recently)
  - NRU ( Not Recently Used)
- Reference bit을 사용해서 교체 대상 페이지 선정 (circular list)
  - Reference bit가 0 인 것을 찾을 때 까지 포인터를 하나씩 앞으로 이동
  - 포인터 이동하는 중에 reference bit 1은 모두 0으로 바꿈
  - reference bit 이 0인 것을 찾으면 그 페이지를 교체
  - 한 바퀴 되돌아와서도 (second chance) 0이면 그때에는 replace 당함
  - 자주 사용되는 페이지라면 second chance가 올 때 1
- 개선
  - reference bit과 modified bit (dirty bit)을 함께 사용
  - reference bit ==1 : 최근에 참조된 페이지
  - modified bit == 1 : 최근에 변경된 페이지 ( I/O를 동반하는 페이지 )

- 사각형 
  - 페이지 프레임
  - 물리적인 메모리에 들어있는 페이지
- reference bit가 1이면 최근에 참조되 페이지이기 때문에 0으로 바꾸고 다음으로 넘어가
- 어떤 페이지를 쫓아내야하는데, modified bit가 1이면 
  - 그 페이지는 메모리에 올라온 이후로 적어도 한 번은 CPU에서 write를 한것. 내용을 수정한 것. 
  - 이 페이지를 메모리로부터 쫓겨낼 때는 backing store에 수정된 내용을 반영하고 쫓아내.

## Page Frame의 Allocation

각 프로세스에 얼만큼의 page frame을 할당할 것인가.

- Equal allocation
  - 모든 프로세스에 똑같은 개수 할당
- Proportional allocation
  - 프로세스 크기에 비례하여 할당
- Priority allocation
  - 프로세스의 priority 에 따라 다르게 할당

## Global vs Local Replacement

- Globlal replacement

  - 다른 프로그램의 페이지도 쫓아낼 수 있음

  - replace 시 다른 프로세스에 할당된 frame을 빼앗아 올 수 있다
  - 프로세스별 할당량을 조절하는 또 다른 방법
  - FIFO, LRU, LFU 등의 알고리즘을 globla replacement 사용시에 해당
  - working set / PFF 알고리즘 사용

- Local replacement

  - 자신에게 할당된 frame 내에서만 replacement
  - FIFO, LRU, LFU 등의 알고리즘을 프로세스 별로 운영시

## Thrashing

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP12.png)

- 프로세스의 원활한 수행에 필요한 최소한의 page frame 수를 할당 받지 못한 경우 발생

  - pafe fault rate이 매우 높아짐

  - CPU utilization이 매우 낮아짐

- OS는 MPF (Multiprogramming degree)를 높여야 한다고 판단

  - 또 다른 프로세스가 시스템에 추가됨 (higher MPD)

  - 프로세스 당 할당된 프레임의 수가 더욱 감소

  - 프로세스는 페이지의 swap in / swap out 으로 매우 바쁨

  - 대부분의 시간에 CPU는 한가함
  - low throughput

- x 축
  - 지금 메모리에 올라와있는 프로그램의 개수

- 프로그램 하나만 올라가 있으면 
  - CPU utilizaiton이 낮아 => IO를 하러 가면, CPU는 놀아

- 계속해서 메모리에 올라와있는 프로그램의 개수 올리면 thrashing 발생
  - CPU가 인스트럭션 수행하려고 하면 그 페이지게 메모리에 없어서 IO를 해
  - 또 다른 프로그램에게 CPU가 넘어가 또 요청한 페이지가 메모리에 없어서 IO를 해

## Working-Set model

- Locality of reference
  - 프로세스는 특정 시간 동안 일정 장소만을 집중적으로 참조
  - 집중적으로 참조되는 해당 page들의 집합을 locality set이라 함
- working set model
  - locality에 기반하여 프로세스가 일정 시간 동안 원활하게 수행되기 위해 한꺼번에 메모리에 올라와 있어야 하는 page들의 집합을 working set 이라 정의함
  - working set 모델에서는 process의 working set 전체가 메모리에 올라와 있어야 수행되고 그렇지 않을 경우 모든 frame을 반납한 후 swap out(suspend)
  - thrashing을 방지
  - multiprogramming degree를 결정

## Working-Set Algorithm

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP13.png)

Working set의 결정

- Wokring set window를 통해 알아냄
- 과거 델타 시간(window) 동안 참조된 페이지들을 working set이라 간주해서 쫓아내지 않고 메모리에 유지
- 참조된 후 델타 시간 동안 해당 Page를 메모리에 유지한 후 버림

## PFF (Page-Fault Frequency) Scheme

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/demandP14.png)

현재 시점에 page fault 얼마나 났는지 직접 봐. 프로그램이 pafe fault 얼마나 내는지 봐.

- 이 프로그램이 pafe fault 많이 내고 있으면,  

  - 이 프로그램의 working set이 메모리에 보장되고 있지 않구나.

  - 페이지를 더줘.

- pafe fault rate의 상한값과 하한값을 둔다

  - pafe fault rate이 상한값을 넘으면 프레임을 더 할당

  - 하한값 이하이면 프레임 수를 줄임

- 빈 프레임이 없으면 일부 프로세스를 swap out

## Page Size의 결정

- Page size를 감소시키면

  - 페이지 수 증가

  - 페이지 테이블 크기 중가

  - internal fragmentation 감소

  - Disk transfer 의 효율성 감소

- 필요한 정보만 메모리에 올라와 메모리 이용이 효율적
  - locality 활용 측면에서는 좋지 않음

- trend
  - Larger page size