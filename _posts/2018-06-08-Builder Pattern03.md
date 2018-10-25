---
layout: post
title:  "Builder Pattern03"
date:   2018-06-08
categories: DesignPattern
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/dpci.png
---

## Definition 

Use the Builder Pattern to encapsulate the construction of a product and allow it to be constructed in steps. 

##Scenario

You’ve just been asked to build a vacation planner for a new theme  park. 

Park guests can choose a hotel and various types of admission tickets, make restaurant reservations, and even book special events. 

To create a vacation planner, you need to be able to create structures like this: 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/newBuilder01.png) 

## You need a flexible design 

Each guest’s planner can vary in the number of days and types of activities it includes. 

For instance, a local resident might not need a hotel, but wants to make dinner and special event reservations. Another guest needs a hotel, dinner reservations, and admission tickets. 

So, you need a flexible data structure that can represent guest planners and all their variations; 

you also need to follow a sequence of potentially complex steps to create the planner. 

How can you provide a way to create the complex structure without mixing it with the steps for creating it? 

## Solution

Remember Iterator? 

We encapsulated the iteration into a separate object and hid the internal representation of the collection from the client. 

It’s the same idea here: 

we encapsulate the creation of the trip planner in an object (let’s call it a builder), 

and have our client ask the builder to construct the trip planner structure for it. 

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/newBuilder02.png) 

## Benefits

- Encapsulates the way a complex object is constructed. 
- Allows objects to be constructed in a multistep and varying process (as opposed to one step factories). 
- Hides the internal representation of the product from the client. 
- Product implementations can be swapped in and out because the client only sees an abstract interface. 

## Reference

Head First Design Pattern