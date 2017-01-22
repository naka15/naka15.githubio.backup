---
layout: post
comments: tue
title:  "Welcome to Jekyll!"
date:   2017-01-23 03:10:00
categories: spring
tags: spring
---  

# GET과 POST의 차이
##지금까지 알고있던 차이
  * get은 URL에 파라메터가 보이므로 보안 문제가 있다
  * get은 전달할 수 있는 데이터의 크기에 제한이 있다. POST는 많은 양의 데이터를 보낼 수 있다
  * get은 이미지 파일과 같은 데이터 전송이 어렵다

##새롭게 알게된 점
  * get과 post는 용도가 다르다
  * get은 주로 select와 같이 데이터를 요청
  * post는 서버의 값이나 상태를 바꿈
  * 또한 get은 데이터를 url에 갖고 있기 때문에 링크를 다른 사람에게 전달하면 정확히 그 링크로 이동하나 post는 데이터가 url에 없으므로 불가능함

##구글의 Accelerator
  * 본래는 웹서핑 속도 향상을 목적
  * accelator가 get방식의 링크들을 미리 모두 방문하여 데이터를 미리 받아놓는 방식으로 속도 향상을 도모
  * 하지만 개발자들이 get을 delete update 등에도 사용하여 사용자가 글을 삭제하지도 않았는데 글이 삭제되는 일과 같은 문제들이 발생함.

##결론
  * get/post 뿐만아니라 모든 부분에서 개념과 용도를 확실히 파악하고 활용해야 한다.
  * 그러기위해선 역시 많이 공부하는 방법밖에는 없다.
