---
layout: post
title:  "adapter VS facade"
date:   2018-04-22
categories: cs
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/cs_img.jpg
---

- Adapter와 Facade 모두 여러 개의 클래스를 감쌀 수 있다. BUT
  - Adapter : 인터페이스를 다른 인터페이스로 변환
  - Facade : 인터페이스를 단순화 
- 이미 존재하는 클래스가 있는가?
  - adpater : yes
  - facade : yes
- 인터페이스를 설계해야하나?
  - adpater : yes
  - facade : no
- 다형적으로 동작하는 객체가 필요하나?
  - adpater : probably
  - facade : no
- 더 간단한 인터페이스가 필요한가?
  - adpater : no
  - facade : yes

