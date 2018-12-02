---
layout: post
title:  "Mediator Pattern"
date:   2018-04-15
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

- Intent

  - 여러 객체들 간의 상호 작용 자체를 캡슐화
  - 객체들 끼리 직접 참조하는 것을 피함으로 객체들 간의 연결 강도를 줄임( loose coupling)
  - client는 객체들의 상호작용을 독립적으로 변경할 수 있음 
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

- Class Diagram

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m01.png)

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m02.png)


- Code



#### Mediator class

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m03.png)

#### Create user class

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m04.png)

#### Use the *User* object to show communications between them.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/m05.png)

- Reference
  - <http://www.oodesign.com/singleton-pattern.html>
  - <https://www.tutorialspoint.com/design_pattern/singleton_pattern.html>



