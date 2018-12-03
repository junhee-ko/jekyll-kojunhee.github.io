---
layout: post
title:  "Command Pattern02"
date:   2018-06-06
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command01.png) 

## Code

- Create a command interface.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command02.png) 

- Create a request class.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command03.png) 

- Create concrete classes implementing the *Order* interface.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command04.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command05.png) 

- Create command invoker class.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command06.png) 

- Use the Broker class to take and execute commands.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command07.png) 

- Result

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/command08.png) 

## Reference

<https://www.tutorialspoint.com/design_pattern/command_pattern.htm>

