---
layout: post
title:  "Type Casting"
date:   2018-10-24
categories: Java
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/javaci.png
---

## Primitive Data Types

Java에는 8 개의 기본 데이터 타입이 있다.

정수 타입 : byte / short / int / long 

부동 소수점 타입 : float / double

부울 데이터 타입 : boolean

문자 데이타 타입 : char

## Type Casting

한 type의 값을 다른 type의 변수에 할당하는 것이다. 두 가지로 나뉜다.

1. Widening Casting

   target type이 source type보다 클 때 일어난다.

   명시적으로 casting 하지 않아도 implicit 하게 casting 된다.

2. Narrowing Casting

   더 큰 type의 값을 작은 type의 변수에 할당 할 때, cast 연산자를 명시해야 한다.

## Widening Casting 

byte보다 더 큰 type 인 int 형 변수 b와 c에 byte형 값을 저장하고 있다. 

casting이 implicit 하게 되기 때문에, cast 연산자를 명시하는 것과 명시하지 않는 것의 결과가 같다.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/javatypecasting01.png)

## Narrowing Casting

다음과 같이 double 형 변수 a 에 3.14를 저장하고, 이를 int 형 변수 b에 casting 하지 않고 저장하려면 에러가 발생한다.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/javatypecasting02.png)

따라서 다음과 같이 int 형으로 casting 한다고 명시를 해야한다. 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/javatypecasting03.png)

