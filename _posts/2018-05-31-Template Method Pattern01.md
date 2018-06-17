---
layout: post
title:  "Template Method Pattern01"
date:   2018-05-31
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Intent

- Define the skeleton of an algorithm in an operation, deferring some steps to subclasses. 
- Template Method lets subclasses redefine certain steps of an algorithm without letting them to change the algorithm's structure.

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/tmplate01.png) 

- AbstractClass 
  - defines abstract primitive operations that concrete subclasses define to implement steps of an algorithm. 
  - implements a template method which defines the skeleton of an algorithm. The template method calls primitive operations as well as operations defined in AbstractClass or those of other objects.
- ConcreteClass 
  -  implements the primitive operations to carry out subclass-specific steps of the algorithm. When a concrete class is called the template method code will be executed from the base class while for each method used inside the template method will be called the implementation from the derived class.

## Reference

<https://www.oodesign.com/template-method-pattern.html>