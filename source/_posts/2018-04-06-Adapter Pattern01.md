---
layout: post
title:  "Adapter Pattern01"
date:   2018-04-06
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

- Intent
  - Convert the interface of a class into another interface clients expect.
  - Adapter lets classes work together, that could not otherwise because of incompatible interfaces.
  - 레거시 시스템을 원하는 인터페이스로 사용가능케 함.
  - Wrapper로도 불림


- Class Diagram
  - Clinet : Target Interface 만 볼 수 있다
  - Adapter : Target Interface를 구현, Adaptee로 구성
  - Adaptee : 모든 요청은 Adaptee에게 위임

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/duck.png)



- Code

### Target Interface

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/11111.png)

### Target

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/22222.png)

### Adaptee Interface

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/33333.png)

### Adaptee 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/44444.png)

### Adapter 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/55555.png)

### Client

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/66666.png)

### Reference

- <http://www.oodesign.com/adapter-pattern.html>
- Head First Design Patterns