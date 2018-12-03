---
layout: post
title:  "HttpServletRequest, HttpServletResponse"
date:   2018-05-07
categories: boostcourse
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/boostcourse.jpg
---

- 요청과 응답

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/http.png)

  - WAS는 웹 브라우저로부터 Servlet요청을 받으면,
    - 요청할 때 가지고 있는 정보를 HttpServletRequest객체를 생성하여 저장합니다.
    - 웹 브라우저에게 응답을 보낼 때 사용하기 위하여 HttpServletResponse객체를 생성합니다.
    - 생성된 HttpServletRequest, HttpServletResponse 객체를 서블릿에게 전달합니다.

- HttpServletRequest

  - http프로토콜의 request정보를 서블릿에게 전달하기 위한 목적으로 사용합니다.
  - 헤더정보, 파라미터, 쿠키, URI, URL 등의 정보를 읽어 들이는 메소드를 가지고 있습니다.
  - Body의 Stream을 읽어 들이는 메소드를 가지고 있습니다.

- HttpServletResponse

  - WAS는 어떤 클라이언트가 요청을 보냈는지 알고 있고, 해당 클라이언트에게 응답을 보내기 위한 HttpServleResponse객체를 생성하여 서블릿에게 전달합니다.
  - 서블릿은 해당 객체를 이용하여 content type, 응답코드, 응답 메시지등을 전송합니다.

- Reference
  - NAVER edwith boostcourse Full-Stack Web Developer 