---
layout: post
title: "Spring framework home.jsp 구동 과정, web.xml, servlet-context.xml"
date: 2017-10-16
excerpt: "Spring framework home.jsp 구동 과정, web.xml, servlet-context.xml"
tags: [spring, framework, java, programmin, process]
comments: true
---

Spring project를 생성하고 바로 실행하면 browser에 home.jsp가 실행된다.
여기서 home.jsp가 구동되는 과정은 아래와 같다.
* ![](/images/spring/spring-process.png)<br/>
1.클라이어트 요청(/, root 페이지 요청)
2.web.xml에서 dispatcherServlet가 클라이언트 요청을 핸들링
3.servlet-context.xml에서 해당 클래스의 웹요청을 처리하는 컨트롤러를 사용(HandlerMapping으로 Controller를 검색)
4.해당 Controller가 요청을 처리 후, home을 리턴)
5.View에 출력

#####DispatcherServlet
######Model, Controller, View를 조합하여 browser로 출력해주는 역할을 수행하는 class
* ![](/images/spring/dispatcherservlet.png)<br/>

#####01) /WEB-INF/web.xml
######웹프로젝트의 배치 기술서(deploy descriptor, 웹프로젝트의 환경 설정 파일)
-Spring project가 실행되면 가장 먼저 web.xml을 읽어 들이게 되고 위에서부터 차례대로 태그들을 해석하기 시작한다.
{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee
                        http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">

    <!-- The definition of the Root Spring Container shared by all Servlets and Filters -->

    <context-param>
        <param-name>contextConfigLocation</param-name>
        <!-- 스프링의 환경설정 파일인 root-context.xml을 가장 먼저 참조한다-->
        <param-value>/WEB-INF/spring/root-context.xml</param-value>
    </context-param>

    <!-- Creates the Spring Container shared by all Servlets and Filters -->
    <listener>
        <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
    </listener>

    <!-- Processes application requests -->
    <servlet>
        <servlet-name>appServlet</servlet-name>
        <!-- 스프링에 내장된 서블릿 클래스-->
        <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
        <init-param>
            <param-name>contextConfigLocation</param-name>
            <!-- /WEB-INF/spring/appServlet/servlet-context.xml을 참조 -->
            <!-- xml 파일 안에 정의된 객체들을 로딩한다. -->
            <param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
        </init-param>
        <!-- 가장 첫번째 우선순위를 뜻한다. -->
        <load-on-startup>1</load-on-startup>
    </servlet>

    <servlet-mapping>
        <servlet-name>appServlet</servlet-name>
        <url-pattern>/</url-pattern>
        <!-- DispatcherServlet이 모든 요청을 가로챌 수 있도록 등록 -->
        <!-- 특정 url으로 변경하여 사용가능 ex) *.do -->
    </servlet-mapping>

</web-app>
{% endhighlight %}
