---
layout: post
title:  "Chain of Responsibility Pattern01"
date:   2018-05-09
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Intent

  - It avoids attaching the sender of a request to its receiver, giving this way other objects the possibility of handling the request too.
  - The objects become parts of a chain and the request is sent from one object to another across the chain until one of the objects will handle it.

- Class Diagram

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/corUML.png)


- Code

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cor01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cor02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cor03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cor04.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cor05.png)

- Result

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cor06.png)

- Reference

  - <http://www.oodesign.com/proxy-pattern.html>
  - <https://www.tutorialspoint.com/design_pattern/singleton_pattern.html>



