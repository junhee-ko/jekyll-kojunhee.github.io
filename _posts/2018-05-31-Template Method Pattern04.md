---
layout: post
title:  "Template Method Pattern04"
date:   2018-05-31
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition 

전체적인 알고리즘은 상위 클래스에서 구현하면서 다른 부분은 하위 클래스에서 구현할 수 있도록 하는 디자인 패턴이다. 전체적인 알고리즘 코드를 재사용하는 데 유용하다.

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/template031.png)

- AbstractClass
  - 템플릿 메서드를 정의하는 클래스
  - 하위 클래스에 공통 알고리즘을 정의하고, 하위 클래스에서 구현될 기능을 primitive method 또는 hook method로 정의하는 클래스
- ConcreteClass
  - 물려받은 primitive method 나 hook method 를 구현하는 클래스
  - 상위 클래스에서 구현된 템플릿 메서드의 일반적인 알고리즘에서 하위 클래스에 적합하게 primitive method나 hook method를 오버라이드하는 클래스

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/template032.png)

- Motor 
  - AbstractClass
- HyundaiMotor, LGMotor
  - ConcreteClass
- Motor 클래스의 move method 
  - template method 
- Motor 클래스의 moveMotor method 
  - primitive method

## Reference

Java 객체지향 디자인 패턴 <정인상, 채흥석 지음>