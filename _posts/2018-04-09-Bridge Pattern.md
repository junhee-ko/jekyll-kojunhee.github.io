---
layout: post
title:  "Bridge Pattern"
date:   2018-04-09
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---



- Intent

  - decouple an abstraction from its implementation so that the two can vary independently.
  - 추상을 구현으로부터 분리하여, 
  - 독립적으로 변하게 함
  - 여기에서 구현의 의미
    - 추상을 구현한 concrete class X
    - 궂은 일을 하는 로직 / 코드
  - 구현 뿐만 아니라 추상화된 부분까지 변경시켜야 하는 경우에는 bridge pattern을 사용



- Class Diagram

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/myBridge.png)

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/myBridgee.png)


- Code

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/b01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/b02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/b03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/b04.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/b05.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/b06.png)



- Reference
  - <https://www.tutorialspoint.com/design_pattern/bridge_pattern.htm>





