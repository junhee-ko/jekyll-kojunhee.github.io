---
layout: post
title:  "Prewitt Operator"
date:   2018-05-22
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

Prewitt operator is used for edge detection in an image. It detects two types of edges

- Horizontal edges
- Vertical Edges

Edges are calculated by using difference between corresponding pixel intensities of an image. 

All the masks that are used for edge detection are also known as derivative masks. 

Because image is also a signal so changes in a signal can only be calculated using differentiation. 

So that’s why these operators are also called as derivative operators or derivative masks.

All the derivative masks should have the following properties:

- Opposite sign should be present in the mask.
- Sum of mask should be equal to zero.
- More weight means more edge detection.

Prewitt operator provides us two masks one for detecting edges in horizontal direction and another for detecting edges in an vertical direction.

## Vertical direction

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/prewitt01.png)  

Above mask will find the edges in vertical direction and it is because the zeros column in the vertical direction. When you will convolve this mask on an image, it will give you the vertical edges in an image.

## How it works

When we apply this mask on the image it prominent vertical edges. 

It simply works like as first order derivate and calculates the difference of pixel intensities in a edge region. As the center column is of zero so it does not include the original values of an image but rather it calculates the difference of right and left pixel values around that edge. 

This increase the edge intensity and it become enhanced comparatively to the original image.

## Horizontal Direction

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/prewitt02.png)

Above mask will find edges in horizontal direction and it is because that zeros column is in horizontal direction. When you will convolve this mask onto an image it would prominent horizontal edges in the image.

## How it works

This mask will prominent the horizontal edges in an image. 

It also works on the principle of above mask and calculates difference among the pixel intensities of a particular edge. 

As the center row of mask is consist of zeros so it does not include the original values of edge in the image but rather it calculate the difference of above and below pixel intensities of the particular edge. 

Thus increasing the sudden change of intensities and making the edge more visible. 

Both the above masks follow the principle of derivate mask. 

Both masks have opposite sign in them and both masks sum equals to zero. 

The third condition will not be applicable in this operator as both the above masks are standardize and we can’t change the value in them.

## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/prewitt03.png)

As you can see that in the first picture on which we apply vertical mask, all the vertical edges are more visible than the original image. 

Similarly in the second picture we have applied the horizontal mask and in result all the horizontal edges are visible. 

So in this way you can see that we can detect both horizontal and vertical edges from an image.





