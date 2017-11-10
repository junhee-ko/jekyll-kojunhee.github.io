---
layout: post
title:  "background server"
date:   2017-11-01 00:27:03 +0900
categories: node
---


## background server


aws ec2 접속해서

````
sudo nohup node index.js &
````
	
* 관리자 권한으로 실행해야 SSL protocol 끊겨도 지속
* nohup & : background 	방식으로 프로세스 실행 
* node : nodejs 실행 명령어


```
ps -ef
```

* background에서 구동되는 프로세스 확인가능


```
ps -ef|grep node
```

* node로 시작하는 프로세스 모두 확인가능




	
