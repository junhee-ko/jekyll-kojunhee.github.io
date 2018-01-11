---
layout: post
title:  "activity life cycle"
date:   2018-01-07 00:27:03 +0900
categories: android
image: https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/android.png
---

<https://developer.android.com/guide/components/activities/activity-lifecycle.html>

![img](https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/life.png)	

- 엑티비티가 새로운 상태에 들어갈때, 시스템은 콜백을 호출한다.

- 엑티비티의 복잡성에 따라서, 반드시 라이프 사이클 매소드를 실행할 필요는 없다. 하지만 유저 익스페트에 따라 앱이 동작하기 위해서는 라이프사이클을 이해하고 실행해야한다.

##  onCreate()

- 시스템이 처음으로 엑티비티를 생성할 때 실행하는 콜백
- 리스트에 데이터를 바인딩, 백그라운드 스레드를 초기화, 클레스 스코프 변수를 인스터스화
- savedInstanceState를 파라미터로 받음. savedInstanceState는 Bundle object.
- Bundle object는 엑티비티의 예전에 저장된 상태를 contain. 그러므로, 엑티비티가 예전에 존재한적이 없다면, 즉 처음으로 만들어졌다면 Bundle object의 값은 null.
- onCreate() 메소드가 실행을 마친후에, 엑티비티는 Started state에 들어감
- 그리고 시스템은  onStart() 메소드를 실행

## onStart()

- 엑티비티가  Started state에 들어갈때, 시스템은 이 콜백을 호출
- 유저에게 엑티비티를 보여지게 만듦
- 즉, 엑티비티가 foreground에 들어가기 위한 준비단계, interactive 되게 하는 준비단계.
- UI에 반영되는 변화들을 monitor 하는 BroadcastReceiver을 등록
- onStart() 메소드가 실행을 마친후에, 엑티비티는 Resumed state에 들어감
- 그리고 onResume() 메소드를 실행

## onResume()

- 엑티비티가 Resumed state에 들어갈때, 엑티비티는 foreground에 온다.
- 그리고 onResume() 콜백을 호출
- Resumed state 에서 앱은 사용자와 상호작용한다.
- 앱의 포커스를 잃을 때까지 계속 이 상태 유지. 
- 예를 들면, 전화 오기전까지, 다른 엑티비티로 이동하기 전까지, 디바이스의 화면이 off 되기 전까지.
- 이와 같은  interruptive event 가 발생하면,  Paused state에 들어가고
- onPause() 콜백을 호출
- 다시 엑티비티가 Paused state에서 Resumed state에 들어오면, 시스템은 다시  onResume() 메소드를 호출

## onPause()

- 유저가 엑티비티를 떠난다는 표시로서 이 콜백을 호출.
- brief하다. 그러므로, 저장 operations 을 수행하기 위한 시간이 부족
- 따라서, 유저 데이터를 저장하고 database transactions 와 같은 작업을 onPause()가 끝나기 전에 모두 완수를 할 수 없다.
- onStop()에서 이런 작업을 함

## onStop()

- 엑티비티가 사용자에게 더이상 보여이지 않을 때 Stopped state에 들어가고 onStop() callback을 호출
- 예를들면,  새로 launched 된 엑티비티가 전체 화면을 덮을 때.
- 엑티비티가 running을 마치고 terminated 되려고 할때
- 앱은 거의 모든 자원을 release해야함
- 예를 들면,  UI에 영향을 끼치는 변화들을 listen하기 위해 등록한 BroadcastReceiver을 onStart() 에서 등록했다면, onStop()에서 unregister 할 수 있다.
- 또한 메모리를 누수할지도 모르는 자원들을 release
- 또한 cpu 사용량이 많은 shutdown operations을 수행하기 위해 onStop()을 사용
- 예를들면, database에 정보를 저장하기 위한 시간이 충분하지 않을때, onStop()에서 가능
- Stopped state에 들어가도, 메모리에 아직 엑티비티 객체가 남아있음.
- 모든 상태와 맴버 정보를 가지고 있지만, window manager에 붙어있지는 않음
- Stopped state 에서 엑티비티는 사용자와 상호작용하기위해 돌아오거나, 아예 running을 멈추고 사라진다.
- 다시 돌아오면  onRestart() 호출, 사라지면 onDestroy()  호출

## onDestroy()

- finish()를 호출하거나, 시스템이 임시적으로 프로세스를 destroy 시킬때 이 콜백을 호출 
- onStop()에서 아직 releases되지 않은 모든 자원들을 releases




	

