---
layout: post
title:  "Sampling, Quantization"
date:   2018-05-15
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Conversion of analog signal to digital signal

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/sampling.png)

  - The output of most of the image sensors is an analog signal, 
  - and we can not apply digital processing on it 
  - because we can not store it. 
  - We can not store it because it requires infinite memory 
  - to store a signal that can have infinite values.
  - So we have to convert an analog signal into a digital signal.
  - To create an image which is digital, 
  - we need to covert continuous data into digital form. 
  - There are two steps in which it is done.
    - Sampling
    - Quantization

- Sampling

  - It is done on X axis.

  - It is the conversion of x axis (infinite values) to digital values.

- Quantization

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/quantization.png)

  - It is done on Y axis.
  - digitizing the amplitudes is known as Quantization
  - In the figure shown above, 
  - these vertically ranging values have been quantized into 5 different levels or partitions. 
  - Ranging from 0 black to 4 white. 