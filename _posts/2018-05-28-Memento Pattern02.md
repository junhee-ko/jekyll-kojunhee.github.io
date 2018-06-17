---
layout: post
title:  "Memento Pattern02"
date:   2018-05-28
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

Use the Memento Pattern when you need to be able to return an object to one of its previous states; 

for instance, if your user requests an “undo.” 

## Scenario 

Your interactive role playing game is hugely successful, and has created a legion of addicts, all trying to get
 to the fabled “level 13.” 

As users progress to more challenging game levels, the odds of encountering a game-ending situation increase. 

Fans who have spent days progressing to an advanced level are understandably miffed when their character gets snuffed, and they have to start all over. 

The cry goes out for a “save progress” command, so that players can store their game progress and at least recover most of their efforts when their character is unfairly extinguished. 

The “save progress” function needs to be designed to return a resurrected player to the last level she completed successfully. 

## Solution

The Memento has two goals:

- Saving the important state of a system’s key object. 
- Maintaining the key object’s encapsulation. 

Keeping the single responsibility principle in mind, 

it’s also a good idea to keep the state that you’re saving separate from the key object. 

This separate object that holds the state is known as the Memento object. 

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mementoo01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/mementoo02.png)

## Benefits

- Keeping the saved state external from the key object helps to maintain cohesion. 
- Keeps the key object’s data encapsulated.
- Provides easy-to-implement recovery capability. 

## Reference

Head First Design Pattern

