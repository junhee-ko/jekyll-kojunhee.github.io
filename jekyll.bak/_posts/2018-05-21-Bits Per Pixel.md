---
layout: post
title:  "Bits Per Pixel"
date:   2018-05-21
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

Bpp or bits per pixel denotes the number of bits per pixel.

#### Number of different colors

- the number of different colors depend on the number of bits per pixel.

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/bppTable.png)

#### Shades 

- Shades = number of colors = (2)<sup>bpp<sup>
- black color
  -  0 pixel value always denotes black color. 
- white color
  - (2)<sup>bpp<sup> -1
  - In case of 1 bpp, 0 denotes black, and 1 denotes white.
  - In case 8 bpp, 0 denotes black, and 255 denotes white.
- gray color
  - Gray color is actually the mid point of black and white.
  - In case of 8bpp, the pixel value that denotes gray color is 127 or 128bpp (if you count from 1, not from 0).

#### Image Size

- Size of an image = rows * cols * bpp
- Assuming it has 1024 rows and it has 1024 columns. 
- And since it is a gray scale image, it has 256 different shades of gray or it has bits per pixel
- rows * cols * bpp = 1024 * 1024 * 8 = 8388608 bits.
- Converting it into bytes = 8388608 / 8 = 1048576 bytes.
- Converting into kilo bytes = 1048576 / 1024 = 1024kb.
- Converting into Mega bytes = 1024 / 1024 = 1 Mb.

#### Reference

- <https://www.tutorialspoint.com/dip/concept_of_bits_per_pixel.htm>