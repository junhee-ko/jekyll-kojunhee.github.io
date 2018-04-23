---
layout: post
title:  "Facade Pattern"
date:   2018-04-10
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Intent

  - hides the complexities of the system 
  - provides an interface to the client using which the client can access the system
  - 인터페이스를 단순화 & 클라이언트와, 구성 요소로 이루어진 서브 시스템을 분리

- Implementation

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/facadeImple.png)


- Code

#### Create an interface

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fa01.png)

#### Create concrete classes implementing the same interface

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fa02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fa03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fa04.png)

#### Create a facade class

- 사용하고자 하는 서브 시스템의 모든 구성요들이 인스턴스 변수 형태로 저장

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fa05.png)

#### Use the facade to draw various types of shapes.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fa06.png)

- Reference
  - <https://www.tutorialspoint.com/design_pattern/facade_pattern.htm>

