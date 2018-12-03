---
layout: post
title:  "Template Method Pattern03"
date:   2018-05-31
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Definition 

The Template Method Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. 

Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure. 

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/templateh01.png)

## Code

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmppattern01.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmppattern02.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmppattern03.png)

## Using the hook 

To use the hook, we override it in our subclass. 

Here, the hook controls whether the CaffeineBeverage evaluates a certain part of the algorithm; 

that is, whether it adds a condiment to the beverage. 

How do we know whether the customer wants the condiment? Just ask ! 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmppattern04.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmppattern05.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmppattern06.png)

## Reference

Head First Design Pattern