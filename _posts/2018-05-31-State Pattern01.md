---
layout: post
title:  "State Pattern01"
date:   2018-05-31
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

The State Pattern allows an object to alter its behavior when its internal state changes. 

The object will appear to change its class. 

## Explanation

- The first part of this description makes a lot of sense, right?  Because the pattern encapsulates state into separate classes and delegates to the object representing the current state, we know that behavior changes along with the internal state. The Gumball Machine provides a good example: when the gumball machine is in the NoQuarterState and you insert a quarter, you get different behavior (the machine accepts the quarter) than if you insert a quarter when it’s in the HasQuarterState (the machine rejects the quarter). 
- What about the second part of the definition? What does it mean for an object to “appear to change its class?” Think about it from the perspective of a client: if an object you’re using can completely change its behavior, then it appears to you that the object is actually instantiated from another class. In reality, however, you know that we are using composition to give the appearance of a class change by simply referencing different state objects. 

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/statePatternUML01.png) 

## Code

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/statePatternUML02.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/statePatternUML03.png) 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/statePatternUML04.png) 

## Compared to 'Strategy Pattern'

The State and Strategy Patterns have the same class diagram, but they differ in intent. 

- Strategy Pattern 
  - typically configures Context classes with a behavior or algorithm. 
- State Pattern 
  - allows a Context to change its behavior as the state of the Context changes.

## Reference

Head First Design Pattern