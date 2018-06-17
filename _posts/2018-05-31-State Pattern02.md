---
layout: post
title:  "State Pattern02"
date:   2018-05-31
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition 

상태에 따라 동일한 작업이 다른 방식으로 실행될 때 해당 상태가 작업을 수행하도록 위임하는 디자인 패턴이다. 

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/sp031.png) 

- State
  - 시스템의 모든 상태에 공통의 인터페이스를 제공
  - 이 인터페이스를 실체화한 어떤 상태 클래스도 기존 상태 클래스를 대신해 고체해서 사용할 수 있다.
- State1, State2, State3
  - Context 객체가 요청한 작업을 자신의 방식으로 실제 실행
  - 대부분의 경우 다음 상태를 결정해 상태 변경을 Context 객체에 요청하는 역할도 수행 
- Context
  - State를 이용하는 역할 수행
  - 현재 시스템의 상태를 나타내는 상태 변수(state) , 실제 시스템의 상태를 구현하는 여러가지 변수가 있다
  - 각 상태 클래스에서 상태 변경을 요청해 상태를 바꿀수 있도록 하는 method (setState) 가 제공된다.
  - Context 요소를 구현한 클래스의 request method는 실제 행위를 실행하는 대신 해당 상태 객체에 행위 실행을 위임

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/sp032.png) 

- Light 
  - Context
- State inteface
  - State
- ON, OFF
  - State1, State2

## Reference

Java 객체지향 디자인 패턴 <정인상, 채흥석 지음>