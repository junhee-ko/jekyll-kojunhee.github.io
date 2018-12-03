---
layout: post
title:  "Histogram Sliding"
date:   2018-05-21
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

## Histogram sliding

- In histogram sliding, we just simply shift a complete histogram rightwards or leftwards. 
- Due to shifting or sliding of histogram towards right or left, 
- a clear change can be seen in the image.

## Increasing brightness using histogram sliding

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisSl01.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisSl02.png)

- On the y axis of this histogram are the frequency or count. 
- And on the x axis, we have gray level values. 
- As you can see from the above histogram, that those gray level intensities whose count is more then 700, lies in the first half portion, means towards blacker portion. 
- Thats why we got an image that is a bit darker.
- In order to bright it, we will slide its histogram towards right, or towards whiter portion. 
- In order to do we need to add atleast a value of 50 to this image. 
- Because we can see from the histogram above, that this image also has 0 pixel intensities, that are pure black. 
- So if we add 0 to 50, we will shift all the values lies at 0 intensity to 50 intensity and all the rest of the values will be shifted accordingly.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisSl03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisSl04.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/hisSl05.png)

## Decreasing brightness using histogram sliding

- Now if we were to decrease brightness of this new image to such an extent that the old image look brighter, 
- we got to subtract some value from all the matrix of the new image. 
- The value which we are going to subtract is 80. 
- Because we already add 50 to the original image and we got a new brighter image, 
- now if we want to make it darker, we have to subtract at least more than 50 from it.

