---
layout: post
title:  "1406:에디터"
date:   2017-09-05
categories: algorithm
image: https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/algorithm.png
---


<https://www.acmicpc.net/problem/1406>

## 풀이


1. 스택 두개 생성. lStack, rStack

2. 초기 입력 문자열 lStack에 모두 push 

3. 명령어 대로
	* L : lStack의 top 문자를 rStack에 push 
	* D : rStack의 top 문자를 lStack에 push
	* B : lStack pop
	* P $ : lStack에 $ push

4. 왼쪽 스택 문자 하나하나 pop해서 rStack에 push

5. rStack 하나하나 pop 해서 출력
