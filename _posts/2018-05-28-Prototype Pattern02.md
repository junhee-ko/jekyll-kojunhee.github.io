---
layout: post
title:  "Prototype Pattern02"
date:   2018-05-28
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

Use the Prototype Pattern when creating an instance of a given class is either expensive or complicated. 

## Scenario 

Your interactive role playing game has an insatiable appetite for monsters. 

As your heros make their journey through a dynamically created landscape, they encounter an endless chain of foes that must be subdued. 

You’d like the monster’s characteristics to evolve with the changing landscape. 

It doesn’t make a lot of sense for bird-like monsters to follow your characters into underseas realms. 

Finally, you’d like to allow advanced players to create their own custom monsters. 

## Solution

The Prototype Pattern allows you to make new instances by copying existing instances. 

(In Java this typically means using the clone() method, or de-serialization when you need deep copies.) 

A key aspect of this pattern is that the client code can make new instances without knowing which specific class is being instantiated. 

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/protoMons02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/protoMons01.png)

## Benefits

- Hides the complexities of making new instances from the client. 
- Provides the option for the client to generate objects whose type is not known. 
- In some circumstances, copying an object can be more efficient than creating a new object. 

## Reference

Head First Design Pattern
