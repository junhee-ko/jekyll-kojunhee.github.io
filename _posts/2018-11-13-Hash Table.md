---
layout: post
title:  "Hash Table"
date:   2018-11-13
categories: dataStructure
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dataStructureImg.png
---

## Hash Table이란

Key에 Value를 저장하는 데이타 구조

## Hash Function

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hashtable01.png)

key에 대한 데이터를 찾을때, hash_function을 한번만 수행하면 array내에 저장된 index 위치를 찾아낼 수 있

기 때문에, 데이타의 저장과 삭제가 빠르다.

하지만 어설픈 hash functio을 통해서 key 값들을 결정한다면 동일한 값이 도출될 수가 있다. 

이렇게 되면 동일한 key 값에 복수 개의 데이터가 하나의 테이블에 존재할 수 있게 되는 것인데  

이를 Collision 이라고 한다.

Collision을 해결하는 방법으로, **Separate chaining**과 **Open addressing** 이 있다.

## Separate Chaining

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hashtable02.png)

Linked List를 이용하는 방식이다.

각 index에 데이터를 저장하는 Linked list 에 대한 포인터를 가지는 방식이다.

동일 index로 인해서 충돌이 발생하면 그 index가 가리키고 있는 Linked list에 노드를 추가하여 값을 추가한다.

## Open Addressing

Open addressing  방식은 index에 대한 충돌 처리에 대해서 

Linked List와 같은 추가적인 메모리 공간을 사용하지 않고, hash table array의 빈공간을 사용하는 방법이다. 

여러 가지 구현 방식이 있다. Linear Probing 방식은 index에 대해서 충돌 이 발생했을 때, 

index 뒤에 있는 버킷중에 빈 버킷을 찾아서 데이터를 넣는 방식이다. 

## Reference

<https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/DataStructure#array-vs-linkedlist>

<http://bcho.tistory.com/1072>