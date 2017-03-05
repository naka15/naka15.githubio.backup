
---
layout: post
comments: tue
title:  "Welcome to Jekyll!"
date:   2017-02-20 03:00:00
categories: spring
tags: spring
---  
# 사전과제 - [교육] 2017.03.06. 성능 - 이상민 수석 
## 1. Map, Set, List, Queue 차이점 
### Map 
    키와 값의 쌍으로 구성된 객체의 집합을 처리하는 인터페이스, 중복되는 키 허용하지 않음 
### Set 
    중복을 허용하지 않는 집합을 처리하기 위한 인터페이스  
### List 
    순서가 있는 집합을 처리하기 위한 인터페이스, 인덱스가 있어 위치 지정하여 값을 찾음, 중복 허용  
### Queue 
    여러 개의 객체를 처리하기 전에 담아서 처리하기 전에 담아서 처리할 때 사용하기 위한 인터페이스, FIFO 

|이름|순서|중복허용|특징|
|-----|:-----:|:---------:|------|
|Map|순서없음|O|키, 값의 쌍으로 구성|
|Set|순서없음|X|SortedSet은 오름차순|
|List|순서있음|O|데이터 개수를 확실히 모를 때 유용 <br>  데이터 삽입, 삭제에 많은 시간이 든다(arrayList)<br> Index가 존재해 위치 지정하여 값을 찾을 수 있다|
|Queue|순서있음|O|선입선출(FIFO)|

## 2. reflection API 를 이용하여 매개변수로 넘어온 클래스의 종류 및 메소드 목록을 출력하는 메소드를 작성하시오.

### 코드
```java
public class test {

	public static void main(String[] args) {
		List<Integer> list = new ArrayList<>();
		printClassInfo(list);
		
	}

	public static void printClassInfo(Object obj){
		System.out.println("class type : " + obj.getClass().getName());
		
		System.out.println("----method List-----------------------");
		Method methodList[] = obj.getClass().getMethods();
		for(int i=0; i<methodList.length; i++){
			System.out.println(methodList[i].getName());
		}
		
		System.out.println("--------------------------------------");
	}
}
```
### 결과
    class type : java.util.ArrayList
    ----method List-----------------------
    add
    add
    remove
    remove
    get
    clone
    indexOf
    clear
    contains
    isEmpty
    iterator
    lastIndexOf
    replaceAll
    size
    subList
    toArray
    toArray
    spliterator
    addAll
    addAll
    forEach
    set
    ensureCapacity
    trimToSize
    listIterator
    listIterator
    removeAll
    removeIf
    retainAll
    sort
    equals
    hashCode
    toString
    containsAll
    wait
    wait
    wait
    getClass
    notify
    notifyAll
    stream
    parallelStream
    --------------------------------------


## 3. XML 파서인 SAX 와 DOM 파서의 특징 및 장단점을 서술하시오.
|구분|DOM|SAX| 
|----|----|---| 
|읽는방식|xml문서 전체를 메모리에 로드하여 읽음|xml문서를 순차적으로 읽음| 
|메모리|메모리 사용량 많음, xml파일의 10배| 메모리 사용량 적음, xml파일의 2배| 
|장점|메모리에 전부 있기 때문에 노드들을 빠르게 검색 가능<br>데이터 수정, 구조변경 용이|메모리 사용량이 적고 읽기 속도가 빠름| 
|단점|메모리사용량이 많다|dom 방식에 비해 구현이 복잡하다| 

## 4. JMX 에 대하여 서술하시오. 
    Java Management Extensions, 자바 애플리케이션 서버 모니터링 기술  
    인스트루먼테이션 레벨, 에이전트 레벨, 분산 서비스 레벨, 추가 가능한 관리용 프로토콜 API 등 4가지 레벨 구조  
    
## 5. JMX를 모니터링할 수 있는 도구를 3개 이상 나열하고 링크도 포함시키시오. 
    Visual VM - http://visualvm.java.net/ 
    Mission Control - http://www.oracle.com/technetwork/java/javaseproducts/mission-control/java-mission-control-1998576.html
    jconsole - http://docs.oracle.com/javase/7/docs/technotes/guides/management/jconsole.html 
    
## 6. Web access log 의 패턴을 확인해 보고, 각 패턴에 대하여 서술하시오.
### Common 로그 형식
     LogFormat "%h %l %u %t \"%r\" %>s %b" common
     CustomLog log/access_log combined
* %h 
    서버에 요청을 한 클라이언트(원격 호스트)의 IP 주소
* %l
    클라이언트 컴퓨터의 identd가 제공할 클라이언트의 RFC 1413 신원, 요청한 정보가 없으면 '-' 기호로 표시
* %u
    문서를 요청한 사용자의 userid
* %t
    서버가 요청처리를 마친 시간
* \"%r\"
    클라이언트가 사용한 메서드, 요청한 리소스 정보, 사용 프로토콜
* %>s
    서버 응답 코드
* %b~~~~
    클라이언트에 보내는 내용의 크기, 없으면 '-'
    
### Combined 로그 형식 
    LogFormat "%h %l %u %t \"%r\" %>s %b \"%{Referer}i\" \"%{User-agent}i\"" combined
    CustomLog log/access_log combined
* \"%{Referer}i\"
    HTTP 요청 헤더
* \"%{User-agent}i\"
    User-Agent HTTP 요청 헤더~~~~
    
## 7. 자바 GC 종류를 모두 나열 하시오.
### Serial Collector
### Parallel Collector
### Parallel Compacting Collector
### Concurrent Mark-Sweep Collector
### Garbage First

## 8. GC 상황을 모니터링할 수 있는 도구를 3개 이상 나열하고, 링크도 포함시키시오.
* Visual GC - http://www.oracle.com/technetwork/java/visualgc-136680.html
* Jstat - http://docs.oracle.com/javase/7/docs/technotes/tools/share/jstat.html
* GCeasy - http://gceasy.io/

## 9. JMH 를 사용하여 Java SE 에 있는 List 를 구현한 클래스들의 추가/조회/삭제 기능의 성능을 비교하시오.
![list.png](/images/list.png)

## 10. JMH 를 사용하여 Java SE 에 있는 Map을 구현한 클래스들의 추가/조회/삭제 기능의 성능을 비교하시오.
![map.png](/images/map.png)
추가 : 트리맵이 다른 맵보다 약 2배정도 느리다
삭제 : 트리맵이 약 3배 정도 느리다
조회: 트리맵이 약 2~3배 정도 느리다
