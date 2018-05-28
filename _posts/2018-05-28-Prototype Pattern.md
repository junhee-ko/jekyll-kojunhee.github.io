---
layout: post
title:  "Prototype Pattern"
date:   2018-05-28
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Intent
  - specifying the kind of objects to create using a prototypical instance
  - creating new objects by copying this prototype
- Class Diagram
  - Client
    - creates a new object by asking a prototype to clone itself.
  - Prototype 
    - declares an interface for cloning itself.
  - ConcretePrototype
    -  implements the operation for cloning itself.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto01.png) 

- Code

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto02.png) 

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto03.png) 

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto04.png) 

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto05.png) 

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto06.png) 

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto07.png) 

- Reference
  - <https://www.tutorialspoint.com/design_pattern/prototype_pattern.htm>
  - <https://www.oodesign.com/prototype-pattern.html>