---
layout: post
title:  "Composite Pattern"
date:   2018-04-09
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

- Intent

  - Compose objects into tree structures to represent part-whole hierarchies.
  - Lets clients treat individual objects and compositions of objects uniformly.
  - Part-whole Hierarchy를 표현하기 위하여 객체들을 트리 구조로 구성
  - Client가 개개의 객체와 그룹 객체를 동일하게 취급할 수 있게 만든다
    - Clinet는 모든 객체들을 컴포넌트 객체로 간주하여 이용

- 자식 관리 오퍼레이션

  - add(), remove(), getChild()

    - component와 composite 에 선언 : client가 편하다. 개체과 그룹에 관계없이 부를 수 있다

      ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/compo01.png)

    - composite 에 선언 : client가 불편하다. 개체인지 그룹인지 구별을 해야한다

      ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/compo02.png)

  - remove()

    - 자식을 삭제하는 책임은 composite 객체에 주는것이 가장 좋다

- Implementation

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/compositeUML.png)


- EX )

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/device.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/computer.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/client.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/body.png)



- Reference
  - <http://www.oodesign.com/composite-pattern.html>
  - Java 객체지향 디자인 패턴 (정인상, 채홍석 지음)





