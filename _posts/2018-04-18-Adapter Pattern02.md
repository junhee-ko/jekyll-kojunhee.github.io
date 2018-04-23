---
layout: post
title:  "Adapter Pattern02"
date:   2018-04-18
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- 설명 
  - 기존에 MediaPlayer 인터페이스 : mp3 포맷만 play
  - 새로운 AdvancedMediaPlayer 인터페이스 :  vlc, mp4 포맷 play
  - AudioPlayer로 mp3 뿐만 아니라, vlc, mp4 도 play 하고자 한다
- Class Diagram

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/myAda.png)

- Code

### Interface : Media Player and Advanced Media Player

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad03.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad04.png)

### concrete classes 

### implementing the *AdvancedMediaPlayer* interface.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad05.png)

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad06.png)

### adapter class 

### implementing the *MediaPlayer* interface.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad07.png)

### concrete class 

### implementing the *MediaPlayer* interface.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad08.png)

### Use the AudioPlayer  

### to play different types of audio formats. 

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad09.png)

### Result

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/ad02.png)



- Reference
  - <https://www.tutorialspoint.com/design_pattern/adapter_pattern.html>

