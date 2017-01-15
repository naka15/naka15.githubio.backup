---
layout: post
comments: true
title:  "Welcome to Jekyll!"
date:   2017-01-15 16:40:00
categories: spring
tags: spring
image: /images/pic03.jpg
---  

# 토비의 스프링  
## 스프링이란  
- 자바 엔터프라이즈 애플리케이션 개발에 사용되는 애플리케이션 프레임워크
- 아래와 같은 세 가지 기능 제공
  * 스프링 컨테이
  	* 애플리케이션을 구성하는 오브젝트 생성, 관리
  * 공통 프로그래밍 모델 - IoC/DI, 서비스 추상화, AOP  
    * IOC/DI : 오브젝트의 생명주기 의존관계에 대한 프로그래밍 모델  
    * 서비스 추상화 : 특정 기술에 종속 되지 않고 이식성이 우수함   
    * AOP : 부가기능 독립적 모듈화  
  * 기술 API  
   	* 다양한 기술 API 제공  
## 1장 오브젝트와 의존관계  
    - JDBC 이용한 DB 연결 순서
        * Connection 생성 -> SQL 생성 -> SQL 실행 -> 조회인 경우, 결과를 ResultSet으로 받아 반환 -> 작업 완료 후(에러 처리 시에도 예외 처리로), Connection, Statement, ResultSet Close -> 예외 처리 


