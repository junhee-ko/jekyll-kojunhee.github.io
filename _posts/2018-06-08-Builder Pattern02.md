---
layout: post
title:  "Builder Pattern02"
date:   2018-06-08
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Implementation

We have considered a business case of fast-food restaurant where a typical meal could be a burger and a cold drink. 

Burger could be either a Veg Burger or Chicken Burger and will be packed by a wrapper. 

Cold drink could be either a coke or pepsi and will be packed in a bottle.

We are going to create an *Item* interface representing food items such as burgers and cold drinks and concrete classes implementing the *Item* interface and a *Packing* interface representing packaging of food items and concrete classes implementing the *Packing* interface as burger would be packed in wrapper and cold drink would be packed as bottle.

We then create a *Meal* class having *ArrayList* of *Item* and a *MealBuilder* to build different types of *Meal* objects by combining *Item*. *BuilderPatternDemo*, our demo class will use *MealBuilder* to build a *Meal*.

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/builderPattern02.png) 

## Code

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp01.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp02.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp03.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp04.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp05.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp06.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp07.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp08.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp09.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp10.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp11.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp12.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp13.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bp14.png) 

## Reference

<https://www.tutorialspoint.com/design_pattern/builder_pattern.htm>