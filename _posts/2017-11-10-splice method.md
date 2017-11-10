---
layout: post
title:  "splice()"
date:   2017-11-10 00:27:03 +0900
categories: programming
---

## 배열에 기존 요소를 제거, 새 요소를 추가


````
var arr = [1, 2, 3, 4, 5];

arr.splice(2, 1);	//	index 2번째 요소를 시작점으로 1개 원소 삭제

console.log(arr);	//	[1,2,4,5]
````


