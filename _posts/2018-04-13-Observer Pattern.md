---
layout: post
title:  "Observer Pattern"
date:   2018-04-13
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

- Intent

  - Defines a one-to-many dependency between objects 
  - so that when one object changes state, 
  - all its dependents are notified and updated automatically.
  - 객체 사이에 1:n의 의존 관계이며,
  - 객체 상태의 변화가 다른 의존 객체에 통지되고 자동으로 업데이트 되게 함

- 다른 이름 

  - Publisher-Subscriber

- Implementation

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/obp.png)


- EX

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/subject.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/observer.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/obs01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/obs02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/obs03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/obs04.png)

- Reference
  - <http://www.oodesign.com/singleton-pattern.html>
  - https://www.tutorialspoint.com/design_pattern/singleton_pattern.html



