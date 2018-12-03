---
layout: post
title:  "High Pass, Low Pass Filters"
date:   2018-05-22
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

## Blurring masks

A blurring mask has the following properties.

- All the values in blurring masks are positive
- The sum of all the values is equal to 1
- The edge content is reduced by using a blurring mask
- As the size of the mask grow, more smoothing effect will take place

## Derivative masks

A derivative mask has the following properties.

- A derivative mask have positive and as well as negative values
- The sum of all the values in a derivative mask is equal to zero
- The edge content is increased by a derivative mask
- As the size of the mask grows , more edge content is increased

## Relationship between blurring mask and derivative mask with high pass filters and low pass filters.

- Blurring masks are also called as low pass filter
- Derivative masks are also called as high pass filter

## High pass frequency components and Low pass frequency components

The high pass frequency components denotes edges whereas the low pass frequency components denotes smooth regions.