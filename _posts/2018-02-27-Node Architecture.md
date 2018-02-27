---
layout: post
title:  "Node Architecture"
date:   2018-02-27 00:27:03 +0900
categories: node
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/node.png
---



https://www.youtube.com/watch?v=TlB_eWDSMt4



- Node.js is a runtime environment for executing JavaScript code
- Before node, we use JavaScript only to build applications that run inside of a browser.
- So, every browser has what we call JavaScript engine that takes our JavaScript code and converts it to code that a computer can understand
- For example, Microsoft eight uses 'Chakra', Firefox uses 'SpiderMonkey',  and Chrome uses 'v8'
- Because of these varieties of engines that sometimes JavaScript code can behave differently in one browser or another
- Now a browser provides a runtime environment for JavaScript code
- For example, in browser we have the window or the document object . 
  - (ex) documnet.getElementById('');
- Thses objects allow us to work with environment in which our code is running 
-  Up to 2009, the only way to excute JavaScript code was inside of a browser
- In 2009,  Brian Dahl creator of node came up with a brilliant idea
- He thought it would be great to execute JavaScript outside of a browser,
- so he took Google's v8 engine which is the fastest JavaScript engine out there and embeded it inside a C++ program and called that program node.
- So, similar to a browser, node is a runtime environment for JavaScript code. 
- It contains a JavaScript engine that execute our JavaScript code,
- but it also has certain objects that provide an environment for our JavaScript code 
- But these objects are different from the environment objects we have in browser
- For example, we don't have the document object.
- Instead , we have other objects that give us more interesting capabilities
- For example, we can work with the file system, listen for requests and a given port and so on.
  - fs.readFile()
  - http.createServer()
- We can't do stuff like that inside of a browser
- In essence, node is a program that includese the v8 JavaScript engine plus some additional modules that give us capabilities not avaliable inside browsers
- We can work with the file system or the network and so on
- Both Chrome and node share the same JavaScript engine, but they provide different runtime environments for JavaScript
- Node is NOT a programming language
- Node is NOT a framework
- It's a runtime environment for executing JavaScript code

