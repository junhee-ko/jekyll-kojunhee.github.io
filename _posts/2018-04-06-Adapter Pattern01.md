---
layout: post
title:  "Adapter Pattern01"
date:   2018-04-06
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Intent
  - Convert the interface of a class into another interface clients expect.
  - Adapter lets classes work together, that could not otherwise because of incompatible interfaces.
  - 레거시 시스템을 원하는 인터페이스로 사용가능케 함.
  - Wrapper로도 불림


- EX) 

  - Target : Duck
  - Adaptee : Turkey

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/duck.png)



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

<http://www.oodesign.com/adapter-pattern.html>