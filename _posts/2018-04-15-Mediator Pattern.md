---
layout: post
title:  "Mediator Pattern"
date:   2018-04-15
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---



- Intent

  - Define an object that encapsulates how a set of objects interact. 
  - Loose coupling by keeping objects from referring to each other explicitly, 
  - and it lets you vary their interaction independently.
  - 부품 객체들 간의 연결을 느슨하게 만든다
  - 각 부품 객체들간의 상호작용을 도맡아 처리하는 객체를 둔다
  - 각 객체들은 Mediator 객체를 제외한 다른 객체는 알지 못한다
  - M:N 의 관계를 M:1로 만든다
  - 객체 간의 상호작용은 Mediator 가 처리

- 문제

  - Colleague 객체들 간의 상호작용을 Mediaotr 객체 하나가 모두 담당하기 때문에
  - Mediaotr 객체가 복잡해져 유지 및 보수가 어려울 수 있음

- Observer Pattern 적용

  - 중재자에게 특정 이벤트가 발생하였음을 알려주기 위한 별도의 인터페이스를 정의
    - Mediator : Subject 
    - Colleague : Observer

- Implementation

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m01.png)

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m02.png)


- EX



#### Mediator class

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m03.png)

#### Create user class

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m04.png)

#### Use the *User* object to show communications between them.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m05.png)

- Reference
  - <http://www.oodesign.com/singleton-pattern.html>
  - <https://www.tutorialspoint.com/design_pattern/singleton_pattern.html>



