---
layout: post
title:  "Spring IoC/DI 컨테이너"
date:   2018-05-06
categories: boostcourse
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/boostcourse.jpg
---

- 컨테이너
  - 인스턴스의 생명 주기를 관리
    - Servlet을 실행해주는 WAS는 Servlet 컨테이너를 가지고 있다고 말합니다.
    - WAS는 웹 브라우저로부터 서블릿 URL에 해당하는 요청을 받으면, 서블릿을 메모리에 올린 후 실행합니다.
    - 개발자가 서블릿 클래스를 작성했지만, 실제로 메모리에 올리고 실행하는 것은 WAS가 가지고 있는 Servlet컨테이너입니다.
    - Servlet컨테이너는 동일한 서블릿에 해당하는 요청을 받으면, 또 메모리에 올리지 않고 기존에 메모리에 올라간 서블릿을 실행하여 그 결과를 웹 브라우저에게 전달합니다.

- IoC (Inversion of Control)

  - 예를 들어 서블릿 클래스는 개발자가 만들지만, 
  - 그 서블릿의 메소드를 알맞게 호출하는 것은 WAS입니다.
  - 이렇게 개발자가 만든 어떤 클래스나 메소드를 다른 프로그램이 대신 실행해주는 것을 제어의 역전이라고 합니다.

- DI(Dependency Injection)

  - DI는 클래스 사이의 의존 관계를 빈(Bean) 설정 정보를 바탕으로 컨테이너가 자동으로 연결해주는 것을 말합니다.

- DI가 적용 안된 예

  - 개발자가 직접 인스턴스를 생성합니다.

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/di01.png)

- Spring 에서 DI가 적용된 예

  - 엔진 type의 v5변수에 아직 인스턴스가 할당되지 않았습니다.

    컨테이너가 v5변수에 인스턴스를 할당해주게 됩니다.

  ![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/di02.png)

- Reference
  - NAVER edwith boostcourse Full-Stack Web Developer 