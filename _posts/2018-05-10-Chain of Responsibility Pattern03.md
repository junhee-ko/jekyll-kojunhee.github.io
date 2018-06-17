---
layout: post
title:  "Chain of Responsibility Pattern03"
date:   2018-05-09
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Definition

Use the Chain of Responsibility Pattern when you want to give more than one object a chance to handle a request. 

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/chain0301.png)

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/chain0302.png)

## Benefits

- Decouples the sender of the request and its receivers. 
- Simplifies your object because it doesn’t have to know the chain’s structure and keep direct references to its members. 
- Allows you to add or remove responsibilities dynamically by changing the members or order of the chain. 

## Reference

Head First Design Pattern



