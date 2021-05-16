---
layout: post
title: RESTful API란?
subtitle: 
categories: CS
tags: [CS,common_sense,Study_for_Beginner]
---

<div style = "font-weight : bold; font-size : 20px; margin-bottom:5%"><span style= "color : #fdcb6e">RE</span>presentational
<br><span style= "color : #fdcb6e">S</span>tate
<br><span style= "color : #fdcb6e">T</span>ransfer
</div>
 
> 웹에서 필요한 자원에 접근할 때  웹의 장점을 최대한 활용할 수 있는 아키텍처이다. <br>
> (기본적으로 웹의 기존 기술과 HTTP 프로토콜을 그대로 활용하기 때문.) <br>
>
> REST의 기본 원칙을 성실히 지킨 서비스 디자인은 “RESTful 하다.” 라고 흔히 표현

## REST API의 구성
---

|구성요소|내용|표현방법|
|------|----------|----|
|자원/Resource|자원|HTTP URI|
|행위/Verb|자원에 대한 행위|HTTP Method|
|표현/Representations|자원에 대한 행위의 내용|HTTP Message Pay Load|

```json
HTTP POST,http://mycompany/members/
{  
   "members":{  
      "name":"Leece"
   }
}

# "members"를 생성하는 리소스
# "POST/생성한다"는 행위
# "이름이 Leece인 회원"이라는 메세지
```

## REST API 중심 규칙
---

1. URI는 정보의 자원을 표현해야 한다.
    - URI는 자원을 표현하는데 중점을 두어야 한다. get 같은 행위에 대한 표현이 들어가서는 안된다.

```php
# bad 
GET/getTodos/1
GET/todos/show/1

# good
GET/todos/1
```

2. 자원에 대한 행위는 HTTP Method으로 표현한다.

```php
# 회원정보 조회
GET /members/1

# 회원 추가
POST /members/2
```

## HTTP Method
---

👉🏻 주로 5가지의 Method를 사용하여 CRUD 구현

|Method|역할|
|------|--------------|
|GET|모든/특정 리소스를 조회|
|POST|리소스를 생성|
|PUT|리소스의 전체를 교체|
|PATCH|리소스의 일부를 수정|
|DELETE|모든/특정 리소스를 삭제|

## REST API 특징
---

<ul> 
<p style="margin-bottom : 1%; font-weight: 700; font-size:15px">Uniform interface/일관된 인터페이스</p>
    <ul style="margin-bottom: 5%">
        <li> 리소스에 대한 요청을 통일되고, 한정적으로 수행하는 아키텍처 스타일 </li>
        <li> 요청을 하는 Client가 플랫폼에 무관하며, 특정 언어나 기술에 종속받지 않는 특징을 의미</li>
    </ul>

<p style="margin-bottom : 10px; font-weight: 700; font-size:15px">Stateless/무상태성 </p>
    <ul style="margin-bottom: 5%">
        <li> 서버는 각각의 요청을 별개의 것으로 인식하고 처리해야하며, 이전 요청이 다음 요청에 연관되어서는 안됨. </li>
        <li> 무상태성은 서버의 처리방식에 일관성을 부여하고, 서버의 부담을 줄이기 위함 </li>
    </ul>

<p style="margin-bottom : 10px; font-weight: 700; font-size:15px">Cacheable/캐시 가능</p>
    <ul style="margin-bottom: 5%">
        <li>  대량의 요청을 효율적으로 처리할 수 있게 도와줌. </li>
        <li> REST API는 기존의 웹표준(HTTP)를 그대로 사용하므로 캐싱 기능 가능. </li>
    </ul>

<p style="margin-bottom : 10px; font-weight: 700; font-size:15px">Self-descriptiveness/자체 표현 구조</p>
    <ul style="margin-bottom: 5%">
        <li>  요청 메세지만 보고도 이를 쉽게 이해할 수 있음 </li>
    </ul>

<p style="margin-bottom : 10px; font-weight: 700; font-size:15px">클라이언트-서버 구조 /Client-Server</p>
    <ul style="margin-bottom: 5%">
        <li>  자원을 가지고 있는 쪽 - 서버 <=> 자원을 요청하는 쪽 - 클라이언트 </li>
        <li>  서버는 API를 제공하며, 클라이언트는 사용자 인증 등을 직접 관리하는 등 역할을 확실히 구분시킴으로써 서로 간의 의존성을 줄임 </li>
    </ul>

<p style="margin-bottom : 10px; font-weight: 700; font-size:15px">계층형 구조</p>
    <ul>
        <li>  Rest API의 서버는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 등을 위한 계층을 추가하여 구조를 변경할 수 있음. </li>
        <li>  Proxy, Gateway와 같은 네트워크 기반의 중간매체를 사용할 수 있음 </li>
        <li>  단, 클라이언트는 어느 계층의 서버와 통신하는지 알 수 없음. </li>
    </ul>
</ul>

## 참고
---
[REST API의 특징](https://mangkyu.tistory.com/46)

[REST API 중심 규칙](https://poiemaweb.com/js-rest-api)

[REST 아키텍처를 훌륭하게 적용하기 위한 몇 가지 디자인 팁](https://spoqa.github.io/2012/02/27/rest-introduction.html)
<br>
.<br>
.<br>
.<br>
.<br>
<a href="https://github.com/Butterfly-effect-19/Study_for_Beginner.git" style="font-weight:700;">[🚦 Study_for_Beginner 바로가기]</a>
