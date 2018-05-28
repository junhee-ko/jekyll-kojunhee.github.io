---
layout: post
title:  "Prototype Pattern"
date:   2018-05-28
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Intent
  - specifying the kind of objects to create using a prototypical instance
  - creating new objects by copying this prototype
- Class Diagram
  - Client
    - creates a new object by asking a prototype to clone itself.
  - Prototype 
    - declares an interface for cloning itself.
  - ConcretePrototype
    -  implements the operation for cloning itself.

![image-20180528152012650](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152012650.png) 



- Code

  ![image-20180528152545121](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152545121.png)

  ![image-20180528152604784](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152604784.png)

  ![image-20180528152614792](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152614792.png)

  ![image-20180528152621871](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152621871.png)

  ![image-20180528152630796](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152630796.png)

  ![image-20180528152637190](/var/folders/_f/gngr61ld6_lgrpr0gzzgzd540000gn/T/abnerworks.Typora/image-20180528152637190.png)



- Reference
  - <https://www.tutorialspoint.com/design_pattern/prototype_pattern.htm>
  - <https://www.oodesign.com/prototype-pattern.html>