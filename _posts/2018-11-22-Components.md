---
layout: post
title:  "Components"
date:   2018-11-22
categories: android
image: https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/android.png
---

안드로이드 애플리케이션은 컴포넌트(component)로 구성되어있습니다. 안드로이드의 4대 컴포넌트는 액티비티(activity), 서비스(service), 콘텐트 제공자(content provider), 방송수신자(broadcast receiver) 입니다. 
각 컴포넌트들은 하나의 독립된 형태로 존재하며, 정해진 역할을 수행합니다. 이때, 인텐트를 통하여 다른 애플리케이션의 컴포넌트를 활성화시킬 수 있습니다. 인텐트는 서로 독립적으로 동작하는 4가지 컴포넌트들 간의 상호 통신을 위한 장치입니다. 즉, 컴포넌트 간의 통신수단입니다. 인텐트를 통하여 다른 애플리케이션의 컴포넌트를 활성화시킬 수 있습니다.

## 액티비티(activity)

사용자 인터페이스 화면을 가지며 특정한 작업을 담당하는 컴포넌트입니다. 

일반적으로 UI를 갖는 하나의 스크린을 나타냅니다. 안드로이드 애플리케이션은 반드시 하나의 activity를 가지고 있어야합니다. 각 액티비티는 manifest 파일에 등록되어 있어야 합니다. 엑티비티는 하나 이상의 View를 가질 수 있습니다.

예를 들어 이메일 앱이라면 새 이메일 목록을 표시하는 액티비티가 하나 있고, 이메일을 작성하는 액티비티가 또 하나, 그리고 이메일을 읽는 데 쓰는 액티비티가 또 하나 있을 수 있습니다. 여러 액티비티가 함께 작동하여 해당 이메일 앱에서 짜임새 있는 사용자 환경을 형성하는 것은 사실이지만, 각자 서로와는 독립적인 형태입니다

## 서비스(service)

백그라운드에서 실행되는 컴포넌트로 오랫동안 실행되는 작업이나 원격 프로세스를 위한 작업을 할 때 사용됩니다.

UI가 없습니다. 한번 시작된 Service는 애플리케이션이 종료되고 다른 애플리케이션으로 이동해도 계속 백그라운드에서 실행됩니다. 모든 서비스는 Service 클래스를 상속받아서 작성됩니다. 

예를 들어 서비스는 사용자가 다른 앱에 있는 동안에 백그라운드에서 음악을 재생할 수도 있고, 아니면 사용자와 액티비티 사이의 상호작용을 차단하지 않고 네트워크를 가로질러 데이터를 가져올 수도 있습니다. 또 다른 구성 요소(예: 액티비티)가 서비스를 시작한 다음 실행되도록 두거나 자신에게 바인드하여 상호작용하도록 할 수도 있습니다.

## 콘텐트 제공자(content provider)

데이터를 관리하고 다른 애플리케이션 데이터를 제공하는 컴포넌트입니다.

데이터는 파일 시스템이나 SQLite 데이터베이스, 웹상에 저장될 수 있습니다. 콘텐트 제공자를 통해서 다른 애플리케이션의 데이터를 쿼리하거나 변경 가능합니다.

예를 들어, Android 시스템은 사용자의 연락처 정보를 관리하는 콘텐츠 제공자를 제공합니다. 따라서, 적절한 권한을 가진 앱이라면 어떤 것이든 해당 콘텐츠 제공자의 일부를 쿼리하여(예를 들어 ContactsContract.Data 등) 특정한 사람에 대한 정보를 읽고 쓸 수 있습니다.

## 방송수신자(broadcast receiver)

안드로이드 단말기에서 발생하는 다양한 이벤트/정보를 받고 반응하는 컴포넌트입니다.

예를들면 시스템부팅, 배터리 부족, 전화/문자 수신, 네트워크 끊김을 알려주는 것이 방송입니다. 단말기에서 발생하는 일 중에서 어플리케이션이 알아야 하는 상황이 발생하면 방송을 해줍니다. 수신기(BroadcastReceiver)를 통해 상황을 감지하고 적절한 작업을 수행합니다. 일반적으로 UI가 없습니다.

## Reference

<https://developer.android.com/guide/components/fundamentals?hl=ko>

<http://ggodol.tistory.com/entry/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-4%EB%8C%80-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8>