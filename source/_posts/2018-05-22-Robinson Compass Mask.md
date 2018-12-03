---
layout: post
title:  "Robinson Compass Mask"
date:   2018-05-22
categories: DIP
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/lenna.jpg
---

Robinson compass masks are another type of derrivate mask which is used for edge detection. 

This operator is also known as direction mask. In this operator we take one mask and rotate it in all the 8 compass major directions that are following:

- North
- North West
- West
- South West
- South
- South East
- East
- North East

There is no fixed mask. 

You can take any mask and you have to rotate it to find edges in all the above mentioned directions. 

All the masks are rotated on the bases of direction of zero columns.

For example let’s see the following mask which is in North Direction and then rotate it to make all the direction masks.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/robinson01.png)![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/robinson02.png)



As you can see that all the directions are covered on the basis of zeros direction. 

Each mask will give you the edges on its direction. 

Now let’s see the result of the entire above masks. 

Suppose we have a sample picture from which we have to find all the edges. 



## Example

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/robinson03.png)

As you can see that by applying all the above masks you will get edges in all the direction. 

Result is also depends on the image. 

Suppose there is an image, which do not have any North East direction edges so then that mask will be ineffective.

