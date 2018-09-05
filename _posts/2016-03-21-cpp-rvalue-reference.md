---
layout: post
title: "[C++] Rvalue Reference - Move Semantics"
date: 2016-03-21
excerpt: "Move Semantics란 객체의 리소스(동적으로 할당된 메모리와 같은)를 또 다른 객체로 전송(이동)하는 것을 의미"
tags: [Move Semantics, rvalue, Reference, c++, programming]
comments: true
---

# Move Semantics

**Move Semantics란 객체의 리소스(동적으로 할당된 메모리와 같은)를 또 다른 객체로 전송(이동)하는 것을 의미합니다.** Rvalue 참조자는 Move Semantics의 구현을 가능하게 하고 이로 인해 상당한 성능을 향상시킬 수 있습니다. Rvalue는 프로그램 어디에서도 참조될 수 없는 임시 객체이지만 Rvalue 참조자를 이용하여 임시 객체의 리소스를 이동시킴으로서 쓸데없는 메모리 할당과 복사 작업을 생략하여 성능이 향상되는 것입니다.

## 메모리 버퍼를 관리하는 MemoryBlock이라는 class를 작성하고 이 class 객체를 vector에 삽입하는 code를 아래와 같이 작성해보았습니다.

{% highlight cpp %}
업데이트 예정
{% endhighlight %}
