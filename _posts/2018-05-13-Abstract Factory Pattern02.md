---
layout: post
title:  "Abstract Factory Pattern02"
date:   2018-05-13
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

관련성 있는 여러 종류의 객체를 일관성 있는 방식으로 생성할 때 유용하다.

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/abstractF01.png)

- Abstarct Factory
  - 실제 팩토리 클래스의 공통 인터페이스
  - 각 제품의 부품을 생성하는 기능을 추사 메서드로 정의
- ConcreteFactory
  - 구체적인 팩토리 클래스
  - AbstractFactory 클래스의 추상 메서드를 오버라이드함으로써 구체적인 제품을 생성
- AbstractProduct
  - 제품의 공통 인터페이스
- ConcreteProduct
  - 구체적인 팩토리 클래스에서 생성되는 구체적인 제품

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/abstractF02.png)

- ElevatorFactory
  - AbstractFactory
- LGElevatorFactory, HyundaiElevatorFactory
  - ConcreteFactory
- Motor
  - AbstractProductA
- LGMotor, HyundaiMotor
  - ConcreteProductA
- Door
  - AbstractProductB
- LGDoor, HyundaiDoor
  - ConcreteProductB

## Reference

Java 객체 지향 디자인 패턴 <정인상, 채흥석 지음>



