---
layout: post
title:  "Decorator Pattern02"
date:   2018-06-06
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

기본 기능에 추가할 수 있는 많은 종류의 부가 기능에서 파생되는 다양한 조합을 동적으로 구현할 수 있는 패턴이다.

## Class diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dec01.png) 

- Componet
  - 기본 기능을 뜻하는 ConcreteComponent 와 추가 기능을 뜻하는 Decorator의 공통 기능을 정의
  - 즉, 클라이언트는 Component를 통해 실제 객체를 사용
- ConcreteComponent
  - 기본 기능을 구현하는 클래스
- Decorator
  - 많은 수가 존재하는 구체적인 Decorator의 공통 기능을 제공
- ConcreteDecoratorA, ConcreteDecoratorB
  - Decorator의 하위 클래스로 기본 기능에 추가되는 개별적이 기능

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dec02.png)

- Display
  - Component
- RoadDisplay
  - ConcreteComponent
- DisplayDecorator
  - Decorator
- LaneDecorator, TrafficDecorator, CrossingDecorator
  - ConcreteDecorator

## Reference

Java 객체 지향 디자인 패턴 <정인상, 채흥석 지음>
