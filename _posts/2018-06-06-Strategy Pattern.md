---
layout: post
title:  "Strategy Pattern"
date:   2018-06-06
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/stpa.png) 

## Motivation

There are common situations when classes differ only in their behavior. For this cases is a good idea to isolate the algorithms in separate classes in order to have the ability to select different algorithms at runtime. 

## Intent

Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from clients that use it. 

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern01.png) 

-  The context object receives requests from the client and delegates them to the strategy object. Usually the ConcreteStartegy is created by the client and passed to the context. From this point the clients interacts only with the context.
- Strategy 
  - defines an interface common to all supported algorithms. Context uses this interface to call the algorithm defined by a ConcreteStrategy.
- Context
  - contains a reference to a strategy object.
  - may define an interface that lets strategy accessing its data.
  - The Context objects contains a reference to the ConcreteStrategy that should be used. When an operation is required then the algorithm is run from the strategy object. The Context is not aware of the strategy implementation. If necessary, addition objects can be defined to pass data from context object to strategy. 
- ConcreteStrategy 
  - each concrete strategy implements an algorithm.

## Code

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern03.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern04.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern05.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern06.png)  

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern07.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/Strategy Pattern08.png) 

## Reference

- <https://www.oodesign.com/strategy-pattern.html>
- <https://www.tutorialspoint.com/design_pattern/strategy_pattern.htm>