---
layout: post
title:  "Flyweight Pattern03"
date:   2018-06-08
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Definition

Use the Flyweight Pattern when one instance of a class can be used to provide many “virtual instances.” 

## Scenario 

You want to add trees as objects in your hot new landscape design application. 

In your application, trees don’t really do very much; 

they have an X-Y location, and they can draw themselves dynamically, depending on how old they are. 

The thing is, a user might want to have lots and lots of trees in one of their home landscape designs. 

It might look something like this: 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fly031.png)

## dilemma 

When they create large groves of trees, the app starts getting sluggish... 

## Solution

What if, instead of having thousands of Tree objects, 

you could redesign your system so that you’ve got only one instance of Tree, and a client object that maintains the state of ALL your trees? 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/fly032.png)

## Benefits

- Reduces the number of object instances at runtime, saving memory. 
- Centralizes state for many “virtual” objects into a single location. 

## Reference

Head First Design Pattern