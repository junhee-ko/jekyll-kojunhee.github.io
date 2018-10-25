---
layout: post
title:  "Command Pattern03"
date:   2018-06-06
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/com01.png) 

- Command
  - 싱핼됭 기능에 대한 인터페이스. 실행될 기능을 execute method로 선언
- ConcreteCommand
  - 실제로 실행되는 기능을 구현.
  - 즉, Command라는 인터페이스를 구현
- Invoker 
  - 기능의 실행을 요청하는 호출자 클래스
- Receiver
  - ConcreteCommand 에서 execute method를 구현할 때 필요한 클래스
  - 즉, Concrete Command 의 기능을 실행하기 위해 사용하는 수신자 클래스

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/com02.png) 

- Button
  - Invoker
- LampOnCommand, LampOffCommand
  - ConcreteCommand
- Lamp
  - Receiver

## Reference

Java 객체지향 디자인 패턴 <정인상, 채흥석 지음>

