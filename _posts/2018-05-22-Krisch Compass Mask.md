---
layout: post
title:  "Krisch Compass Mask"
date:   2018-05-22
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

Kirsch Compass Mask is also a derivative mask which is used for finding edges. 

This is also like Robinson compass find edges in all the eight directions of a compass. 

The only difference between Robinson and kirsch compass masks is that in Kirsch we have a standard mask but in Kirsch we change the mask according to our own requirements.

With the help of Kirsch Compass Masks we can find edges in the following eight directions.

- North
- North West
- West
- South West
- South
- South East
- East
- North East

We take a standard mask which follows all the properties of a derivative mask and then rotate it to find the edges.

For example let’s see the following mask which is in North Direction and then rotate it to make all the direction masks.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/krisch01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/krisch02.png)

As you can see that all the directions are covered and each mask will give you the edges of its own direction. 

Now to help you better understand the concept of these masks we will apply it on a real image. 

Suppose we have a sample picture from which we have to find all the edges. Here is our sample picture:

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/krisch04.png)

As you can see that by applying all the above masks you will get edges in all the direction. 

Result is also depends on the image. 

Suppose there is an image, which do not have any North East direction edges so then that mask will be ineffective.