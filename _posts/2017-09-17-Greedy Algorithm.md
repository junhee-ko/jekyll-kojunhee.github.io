---
layout: post
title:  "Greedy Algorithm"
date:   2017-09-17 00:27:03 +0900
categories: algorithm-concept
---


## 정의

- 어떤 것을 결정해야 하는 순간, 가장 좋다고 생각하는 것을 선택하면서 답 찾는 알고리즘

## Dynamic Programming과 비교 

- DP : 어떤 상황에서 할수 있는 상황 모두 살펴보고 거기서 가장 좋은것 선택

- Greedy : 할수 있는 선택 중에 제일 좋다고 생각되는 것 하나 선택해서 정답 찾아감

## 단점 

- 그 때 그 때는 최적일 수 있지만, 최종적으로는 최적이 아니 수도

````
ex)  12원을 1, 4, 5원으로 거슬러 줄 때, 

5원 2개, 1원 2개 --> 총 4개가 필요

but, 정답은 4원 3개!!!

DP로 풀어야해.

D[n] = n원을 거슬러 주는 동전의 최소 개수

min(D[n-1], D[n-4], D[n-5]) + 1 
````

## 그럼 언제 쓰나

- 지금 이 순간 가장 좋은 경우 선택하는 것이 최적일 때.

- 왜 그게 최적인지 증명해야함 

- 그래서 가장 어려워

- 그래서 시험이나 대회에 나오면 가장 나중에 풀어


## 예제 

<https://www.acmicpc.net/problem/11399>

- 줄 서 있는 사람 N, 각 사람의 인출 시간 Pi. 각 사람이 인출하는데 필요한 시간의 합의 최소값은?

````
ex) P1=3, P2=1, P3=4, P4=3, P5=2

1번  : 3분 소요

2번 : 3 +1 = 4분 소요 

3번 : 3 + 1 + 4 = 8분 소요 

4번 : 3 + 1 + 4 + 3 = 11분  소요 

5번 : 3 + 1 + 4 + 3 + 2 = 13 분 소요      

따라서, 3 + 4 + 8 + 11 + 13 = 39분 소요
````

- 기다리는 시간 짧은 사람부터 인출하는 것이 좋음 ... 이걸 증명해야함.

- p1 <= p2<= ......<=pn 이라고 가정

- S = p1 + (p1+p2) + (p1+p2+p3) +  .... + (p1+p2+p3+...+pn) = n*p1 + (n-1)*p2 + ... + pn

- 중간에 i<j 인 pi<pj 순서를 바꾸면 S는 더 커지거나 같아져야함. 즉, S <= S` ---->  S-S` <=0

- 계산결과, S-S`<=0 을 성립함.  따라서 오름차순이 정답


