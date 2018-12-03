---
layout: post
title:  "Factory Method Pattern02"
date:   2018-05-13
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Definition 

객체를 생성하는 코드를 별도의 클래스/메소드로 분리함으로써 객체 생성 방식의 변화에 대비하는데 유용하다.

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/factorymethodpa01.png)

- Product 
  - 펙토리 메서드로 생설될 객체의 공통 인터페이스
- ConcreteProduct
  - 구체적으로 객체가 생성되는 클래스
- Creator
  - 팩토리 메서드를 갖는 클래스
- ConcreteCreator
  - 팩토리 매서드를 구현하는 클래스
  - ConcreteProduct 객체를 생성 

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/factorymethodpa02.png)

- ElevatorScheduler interface
  - Prudct
- ResponseTimeScheduler, ThroughputScheduler
  - ConcretePrudct
- ElevatorManger
  - Creator
- ElevatorMangerWithThroughputScheduling, ElevatorMangerWithDynamicScheduling, ElevatorManagerWithResponseTimeScheduling
  - ConcreteCreator

## Reference

Java 객체 지향 디자인 패턴 <정인상, 채흥석 지음>



