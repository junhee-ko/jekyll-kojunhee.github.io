---
layout: post
title:  "flow control"
date:   2018-11-21
categories: network
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/networkDoorimg.png
---

flow control은 송신측과 수신측의 데이터 처리 속도 차이를 해결하기 위한 방법입니다. stop and wait 와 sliding window 방식이 있습니다.

## stop and waitttt

매번 전송한 패킷에 대해 확인응답을 받아야만 그 다음 패킷을 전송하는 방법입니다. 다음 그림과 같이 동작합니다.

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/flowcontrol01.png)

## sliding window

## Reference

<http://jwprogramming.tistory.com/36>