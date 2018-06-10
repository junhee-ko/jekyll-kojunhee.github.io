---
layout: post
title:  "Builder Pattern01"
date:   2018-06-08
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

## Motivation

- Builder pattern builds a complex object using simple objects and using a step by step approach. 
- This type of design pattern comes under creational pattern as this pattern provides one of the best ways to create an object.
- A Builder class builds the final object step by step. This builder is independent of other objects.

## Intent

- Defines an instance for creating an object but letting subclasses decide which class to instantiate
- Refers to the newly created object through a common interface

## Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/builderPattern01.png) 

- **Builder** 
  - specifies an abstract interface for creating parts of a Product object.
- **ConcreteBuilder** 
  - constructs and puts together parts of the product by implementing the Builder interface. It defines and keeps track of the representation it creates and provides an interface for saving the product.
- **Director**  
  - constructs the complex object using the Builder interface.
- **Product** 
  - represents the complex object that is being built.

The client, that may be either another object or the actual client that calls the main() method of the application, initiates the Builder and Director class. 

The Builder represents the complex object that needs to be built in terms of simpler objects and types. 

The constructor in the Director class receives a Builder object as a parameter from the Client and is responsible for calling the appropriate methods of the Builder class. 

In order to provide the Client with an interface for all concrete Builders, the Builder class should be an abstract one. 

This way you can add new types of complex objects by only defining the structure and reusing the logic for the actual construction process. 

The Client is the only one that needs to know about the new types, the Director needing to know which methods of the Builder to call.

## Head First Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/builderPattern33.png) 

## Reference

<https://www.oodesign.com/builder-pattern.html>

Head First