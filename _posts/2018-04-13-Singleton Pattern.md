---
layout: post
title:  "Singleton Pattern"
date:   2018-04-13
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---



- Intent

  - Ensure that only one instance of a class is created.
  - Provide a global point of access to the object.

- Implementation

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/si.png)


- EX

#### 01 : Early instantiation using implementation with static field

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/SingleObject.png)



#### 02 : Lazy instantiation using double locking mechanism

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/singleton_doublech.png)



#### Client

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/SingletonPatternDemo.png)

- Reference
  - <http://www.oodesign.com/singleton-pattern.html>
  - https://www.tutorialspoint.com/design_pattern/singleton_pattern.html



