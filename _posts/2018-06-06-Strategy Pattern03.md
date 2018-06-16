---
layout: post
title:  "Strategy Pattern03"
date:   2018-06-06
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

스트레지 패턴은 같은 문제를 해결하는 여러 알고리즘(방식)이 클래스별로 캡슐화되어 있고, 이들이 필요할 때 교체할 수 있도록 함으로써 동일한 문제를 다른 알고리즘으로 해결할 수 있게 하는 디자인 패턴이다.

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/stpa031.png) 

- Strategy 
  - 인터페이스나 추상 클래스
  - 외부에서 동일한 방식으로 알고리즘을 호출하는 방법을 명시
- ConcreteStrategy1, ConcreteStrategy2, ConcreteStrategy3
  - 명시한 알고리즘을 실제로 구현한 클래스
- Context
  - strategy 패턴을 이용하는 역할을 수행
  - 필요에 따라 동적으로 구체적인 전략을 바꿀수 있도록 setter method 제공

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/stpa032.png) 

- Robot, Atom, TeakonV

  - Context

- MovingStrategy, AttackStrategy

  - Strategy

- WalkingStrategy, FlyingStrategy, PunchStrategy, MissileStrategy

  - ConcreteStrategy

  