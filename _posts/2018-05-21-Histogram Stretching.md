---
layout: post
title:  "Histogram Stretching"
date:   2018-05-21
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

There are two methods of enhancing contrast. 

- The first one is called Histogram stretching that increase contrast. 
- The second one is called Histogram equalization that enhance contrast.

## Contrast

- Contrast is the difference between maximum and minimum pixel intensity.

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch01.png)

- Contrast = 225.
- Now we will increase the contrast of the image.

## Increasing the contrast of the image

- The formula for stretching the histogram of the image to increase the contrast is

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch02.png)

- The formula requires finding the minimum and maximum pixel intensity multiply by levels of gray. 

- In our case the image is 8bpp, so levels of gray are 256.

- The minimum value is 0 and the maximum value is 225. So the formula in our case is

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch03.png)

- where f(x,y) denotes the value of each pixel intensity. For each f(x,y) in an image , we will calculate this formula.

- Note the shape and symmetry of histogram. The histogram is now stretched or in other means expand. Have a look at it.

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch04.png)

- In this case the contrast of the image can be calculated as Contrast = 240

- Hence we can say that the contrast of the image is increased.

## Failing of histogram stretching

- the algorithm fails on some cases. 

- Those cases include images with when there is pixel intensity 0 and 255 are present in the image

- Original Formula

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch05.png)

- Putting fail case values in the formula

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch06.png)

- Simplify that expression gives

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisStretch07.png)

- That means the output image is equal to the processed image. 

- That means there is no effect of histogram stretching has been done at this image.