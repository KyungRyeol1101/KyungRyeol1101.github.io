---
layout: post
title: Stack & Queue & Deque
date: 2016-01-29
excerpt: 스택, 큐, 덱
tags: [data structures, c++, stack, queue, deque]
comments: true
---

# Stack & Queue & Deque : 스택 & 큐 & 덱 (C++)

## 스택(Stack)

- 스택은 마지막에 저장한 데이터를 가장 먼저 꺼내는 후입선출(LIFO:Last In First Out) 구조로 되어 있다.
- 입출력이 모두 한 방향에서 이루어지는 데이터 구조이다.
- 입출력이 가능한 쪽을 TOP, 바닥을 BOTTOM이라고 한다.
- TOP은 출력 우선순위가 가장 높은 요소를 가리키고 있다.
- 입출력을 할 위치를 표시하기 위해서 TOP(포인터 사용)이 필요하다.
- TOP을 통해서 데이터를 넣는 것을 PUSH라고 하고, 꺼내는 것을 POP이라고 한다.
- 스택을 구현하는 방법은 배열과 연결 리스트가 있다. 배열의 큰 단점은 처음 생성한 크기를 바꿀 수 없다는 점이다. 그래서 순차적으로 데이터를 추가하고 삭제하는 스택은 배열리스트(Array List)와 같은 배열기반의 컬렉션 클래스가 적합하다.
overflow 스택의 모든 기억장소가 꽉 채워져 있어서 더 이상 데이터를 삽입(PUSH할 때)할 수 없다.
underflow 자료가 없다면(TOP포인터가 주소 0을 가지고 있다면) 스택에는 삭제(POP할 때)할 자료가 없다.

### 스택의 단점

- 먼저 들어온 것이 나중에 출력되는 후입선출의 구조로 우선순위에 관련된 문제가 생길 수 있다.
- 새로운 입력이 들어오면 바닥에 있는 데이터가 오랫동안 잔류하게 되는 경우가 생긴다.

### 스택의 용도

- 지역변수 저장
- 함수의 콜스택
- 문자열을 역순으로 출력할 때, 연산자 후위표기법 등
- 임시데이터 백업
- 함수 호출의 순서 제어
- 인터럽트 처리
- 수식계산


## 큐(Queue)

- 큐는 처음에 저장한 데이터를 가장 먼저 꺼내는 선입선출(FIFO:First In First Out) 구조로 되어 있다.
- 입출력이 양방향에서 이루어지는 데이터 구조이다.
- FRONT)는 가장 먼저 삽입된 자료의 기억공간을 가리키는 포인터이고 , REAR는 가장 마지막에 삽입된 자료가 위치한 기억장소를 가리키는 포인터이다.
- 데이터 입력은 FRONT 포인터를 통해서 하고, 데이터 삭제는 REAR 포인터를 통해서 한다.
- 삽입연산을 Enqueue 또는 Put, 삭제연산을 Dequeue 또는 Get라고 한다.
- 큐에서는 FRONT와 REAR가 같을 때 비어있는 공백큐 임을 알수 있다.
overflow 큐의 모든 기억장소가 꽉 채워져 있어서 더 이상 데이터를 삽입(Enqueue할 때)할 수 없다.
underflow 자료가 없다면 스택에는 삭제(Dequeue할 때)할 자료가 없다.

### 큐의 단점

- 데이터 삽입 후 계속 항목을 삭제하면 REAR와 FRONT가 만나게 되어 공백큐가 됨에도 불구하고 오버 플로우 현상이 발생한다. 즉, 메모리 낭비가 생기게 된다.

### 개선된 원형 큐가 나옴.

- 원형 큐의 단점 : 메모리 공간은 잘 활용하나 배열로 구현되어 있기 때문에 큐의 크기가 제한되는 단점이 존재한다.

### 링크드 리스트로 큐가 나옴.

- 링크드 리스트로 구현한 큐는 큐의 크기가 제한이 없고, 삽입, 삭제가 효과적이다.

### 큐의 용도

- 운영체제 작업 스케쥴링
- 컴퓨터 버퍼에서 주로 사용, 마구 입력이 되었으나 처리를 하지 못할 때, 버퍼(큐)를 만들어 대기 시킨다.
- 대기행렬 처리
- 인쇄작업 대기목록

- 큐는 데이터를 꺼낼 때 항상 첫 번째 저장된 데이터를 삭제하므로 배열리스트와 같은 배열 기반의 컬렉션 클래스를 사용한다면 데이터를 꺼낼 때마다 빈 공간을 채우기 위해서 데이터의 복사가 발생하므로 비효율적이다. 따라서 큐를 사용할때는 연결 리스트(Linked List)로 구현하는 것이 적합하다.


## 데큐(double-ended queue)

- 큐와 스택의 장점을 합쳐놓은 개념이다.
- 양쪽 끝에서 삽입과 삭제가 모두 가능한 자료구조이다.
- 두 개의 포인터를 사용하여, 양쪽에서 삽입과 삭제를 발생시킬 수 있다.
- 입력이 한쪽 끝으로만 가능하도록 설정한 데크인 입력제한데크(Scroll), 출력이 한쪽 끝으로만 가능하도록 설정한 데크인 출력제한데크(Shelf)가 있다.



Syntax highlighting is a feature that displays source code, in different colors and fonts according to the category of terms. This feature facilitates writing in a structured language such as a programming language or a markup language as both structures and syntax errors are visually distinct. Highlighting does not affect the meaning of the text itself; it is intended only for human readers.[^1]

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

### Highlighted Code Blocks

To modify styling and highlight colors edit `/assets/css/syntax.css`.

{% highlight css %}
#container {
    float: left;
    margin: 0 -240px 0 0;
    width: 100%;
}
{% endhighlight %}

{% highlight html %}
{% raw %}
<nav class="pagination" role="navigation">
    {% if page.previous %}
        <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
    {% endif %}
    {% if page.next %}
        <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
    {% endif %}
</nav><!-- /.pagination -->
{% endraw %}
{% endhighlight %}

{% highlight ruby %}
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
{% endhighlight %}


### Standard Code Block

    {% raw %}
    <nav class="pagination" role="navigation">
        {% if page.previous %}
            <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
        {% endif %}
        {% if page.next %}
            <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
        {% endif %}
    </nav><!-- /.pagination -->
    {% endraw %}


### Fenced Code Blocks

To modify styling and highlight colors edit `/assets/css/syntax.css`. Line numbers and a few other things can be modified in `_config.yml`. Consult [Jekyll's documentation](http://jekyllrb.com/docs/configuration/) for more information.

~~~ css
#container {
    float: left;
    margin: 0 -240px 0 0;
    width: 100%;
}
~~~

~~~ html
{% raw %}<nav class="pagination" role="navigation">
    {% if page.previous %}
        <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
    {% endif %}
    {% if page.next %}
        <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
    {% endif %}
</nav><!-- /.pagination -->{% endraw %}
~~~

~~~ ruby
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
~~~

### GitHub Gist Embed

An example of a Gist embed below.

{% gist mmistakes/6589546 %}
