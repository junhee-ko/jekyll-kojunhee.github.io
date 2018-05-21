---
layout: post
title:  "Convolution"
date:   2018-05-21
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

## What is image processing

- In image processing , we are developing a system 
- whose input is an image and output would be an image

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution02.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution04.png)

- It can be mathematically represented as two ways : h(x,y) is the mask or filter.
  - **g(x,y) = h(x,y) \* f(x,y)**
    - “mask convolved with an image”.
  - **g(x,y) = f(x,y) \* h(x,y)**
    - "image convolved with mask"

## What is mask?

- Mask is also a signal. 
- It can be represented by a two dimensional matrix. 
- The mask is usually of the order of 1x1, 3x3, 5x5, 7x7 . 
- A mask should always be in odd number, 
- because other wise you cannot find the mid of the mask. 

## How to perform convolution?

- Flip the mask (horizontally and vertically) only once
- Slide the mask onto the image.
- Multiply the corresponding elements and then add them
- Repeat this procedure until all values of the image has been calculated.

## Example of convolution

- Mask

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution05.png)

- Flipping the mask horizontally

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution06.png)

- Flipping the mask vertically

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution07.png)

- Image

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution08.png)

- Convolution

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/convolution09.png)

- The box in red color is the mask, 

- and the values in the orange are the values of the mask. 

- The black color box and values belong to the image.

-  Now for the first pixel of the image, the value will be calculated as

  First pixel = (5*2) + (4*4) + (2*8) + (1*10)

  = 10 + 16 + 16 + 10

  = 52

- Place 52 in the original image at the first index and repeat this procedure for each pixel of the image.

## Why Convolution

- Convolution can achieve something, that the previous two methods of manipulating images can’t achieve. 
- Those include the blurring, sharpening, edge detection, noise reduction e.t.c.