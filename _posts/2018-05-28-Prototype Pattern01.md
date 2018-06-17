---
layout: post
title:  "Prototype Pattern01"
date:   2018-05-28
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Intent

- specifying the kind of objects to create using a prototypical instance
- creating new objects by copying this prototype

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto11.png) 

- Client
  - creates a new object by asking a prototype to clone itself.
- Prototype 
  - declares an interface for cloning itself.
- ConcretePrototype
  -  implements the operation for cloning itself.

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto011.png) 

## Code

Create an abstract class implementing *Clonable* interface.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto02.png)

Create concrete classes extending the above class. 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto03.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto04.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto05.png)

Create a class to get concrete classes from database and store them in a *Hashtable*.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto06.png)



PrototypePatternDemo uses ShapeCache class to get clones of shapes stored in a *Hashtable*.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/proto07.png) 

## Reference

<https://www.tutorialspoint.com/design_pattern/prototype_pattern.htm>

<https://www.oodesign.com/prototype-pattern.html>
