---
layout: post
title:  "Histograms Introduction"
date:   2018-05-21
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

## Histogram of an image

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/histogram.png)

- The x axis of the histogram shows the range of pixel values. 
- Since its an 8 bpp image, that means it has 256 levels of gray or shades of gray in it. 
- Thats why the range of x axis starts from 0 and end at 255 with a gap of 50. 
- Whereas on the y axis, is the count of these intensities.
-  that most of the bars that have high frequency lies in the first half portion which is the darker portion. 
- That means that the image we have got is darker. 

## Applications of Histograms

- The first use as it has also been discussed above is the analysis of the image. 
  - We can predict about an image by just looking at its histogram. 
  - Its like looking an x ray of a bone of a body.
- The second use of histogram is for brightness purposes. 
  - The histograms has wide application in image brightness. 
  - Not only in brightness, but histograms are also used in adjusting contrast of an image.
- Another important use of histogram is to equalize an image.
- And last but not the least, histogram has wide use in thresholding. 
  - This is mostly used in computer vision.

 