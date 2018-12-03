---
layout: post
title:  "Frequency domain"
date:   2018-05-22
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

## Frequency domain analysis

Till now, all the domains in which we have analyzed a signal , we analyze it with respect to time. 

But in frequency domain we don’t analyze signal with respect to time, but with respect of frequency.

## Difference between spatial domain and frequency domain

In spatial domain, we deal with images as it is. The value of the pixels of the image change with respect to scene. 

Whereas in frequency domain, we deal with the rate at which the pixel values are changing in spatial domain.

## Spatial Domain

In simple spatial domain, we directly deal with the image matrix

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/frequencyD01.png)

## Frequency Domain

We first transform the image to its frequency distribution. 

Then our black box system perform what ever processing it has to performed, 

and the output of the black box in this case is not an image, but a transformation. 

After performing inverse transformation, it is converted into an image which is then viewed in spatial domain.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/frequencyD02.png)

## Transformation

A signal can be converted from time domain into frequency domain using mathematical operators called transforms. There are many kind of transformation that does this. Some of them are given below.

- Fourier Series
- Fourier transformation
- Laplace transform
- Z transform

## Frequency components

Any image in spatial domain can be represented in a frequency domain. 

We will divide frequency components into two major components.

## Low frequency components

Low frequency components in an image correspond to smooth regions.

## High frequency components

High frequency components correspond to edges in an image.











