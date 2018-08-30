---
layout: post
title:  "Markdown Syntax"
date:   2016-03-15
excerpt: "머리글, 단락, 블록 인용 부호, 표, 코드 블록 등 테마에서 스타일을 지정하는 데 필요한 모든 것."
tag:
- markdown
- syntax
- sample
- jekyll
comments: true
---

## HTML Elements

아래는 테마에서 스타일을 지정하는 데 필요한 모든 사항을 보여 줍니다. 소스 코드를 확인하여 단락에 포함된 여러 요소를 확인하세요.

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

### Body text

**풋볼 클럽 바르셀로나**. (카탈루냐어: Futbol Club Barcelona, *축구단 바르셀로나*)는 스페인 카탈루냐 지방의 바르셀로나를 연고지로 하는 세계 최초이자 세계 최대 규모로 협동조합 형태로 운영되는 축구 클럽이다. 홈 경기장은 캄 노우이며, 1899년 11월 29일에 창단되었다.

![Smithsonian Image](https://ko.wikipedia.org/wiki/%ED%8C%8C%EC%9D%BC:FC_%EB%B0%94%EB%A5%B4%EC%85%80%EB%A1%9C%EB%82%98_%EB%A1%9C%EA%B3%A0.png#/media/File:FC_%EB%B0%94%EB%A5%B4%EC%85%80%EB%A1%9C%EB%82%98_%EB%A1%9C%EA%B3%A0.png)
{: .image-right}

리저브 팀으로 FC 바르셀로나 B를 두고 있다. 유스 팀으로는 FC 바르셀로나 후베닐 A, FC 바르셀로나 후베닐 B, FC 바르셀로나 카다테, FC 바르셀로나 인판틸, FC 바르셀로나 알레빈, FC 바르셀로나 벤하민, 순으로 나뉘어 있다. 바르사의 유스 시스템인 라 마시아는 펩 과르디올라, 리오넬 메시, 안드레스 이니에스타, 세르히오 부스케츠, 제라르 피케, 조르디 알바, 카를레스 푸욜, 챠비 에르난데스, 빅토르 발데스, 페페 레이나, 세스크 파브레가스, 페드로 로드리게스, 티아고 알칸타라, 세르지 로베르토 등등 많은 축구 선수들을 배출하였다.

프리메라리가에서 레알 마드리드 CF 와 숙명의 라이벌이며 두 클럽 사이의 대결은 엘 클라시코라고 부른다. 또한 같은 지역을 연고로 하는 RCD 에스파뇰과의 바르셀로나 더비도 유명하다.

팀 명을 줄여서 바르사(바르싸)(Barça)라고도 부르는데 발음할 때에 주의해야 한다. 'ç' 표기가 없는 언어에서는 모양이 유사한 알파벳 'c'로 'ç'를 대체하는 경우가 많아 'Barca'라고 표기되는 경우도 흔한데, 이것은 단순히 표기상의 난점으로 인해 일어나는 현상일 뿐 발음은 '바르카'가 아닌 '바르사(바르싸)' 로 한다.

### Blockquotes

> 스페인 클럽 최초 트레블 및 6관왕 달성 시즌 (2008-2009)

## List Types

### Ordered Lists

1. Item one
   1. sub item one
   2. sub item two
   3. sub item three
2. Item two

### Unordered Lists

* Item one
* Item two
* Item three

## Tables

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}

## Code Snippets

{% highlight css %}
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
{% endhighlight %}

## Buttons

`.btn` 클래스를 적용하여 링크를 만들 수 있습니다.

{% highlight html %}
<a href="#" class="btn btn-success">Success Button</a>
{% endhighlight %}

<div markdown="0"><a href="#" class="btn">Primary Button</a></div>
<div markdown="0"><a href="#" class="btn btn-success">Success Button</a></div>
<div markdown="0"><a href="#" class="btn btn-warning">Warning Button</a></div>
<div markdown="0"><a href="#" class="btn btn-danger">Danger Button</a></div>
<div markdown="0"><a href="#" class="btn btn-info">Info Button</a></div>

## KBD

키보드 버튼에`<kbd>`태그를 사용할 수도 있습니다.

{% highlight html %}
<kbd>W</kbd><kbd>A</kbd><kbd>S</kbd><kbd>D</kbd>
{% endhighlight %}

선수를 움직이려면 <kbd> W </ kbd> <kbd> A </ kbd> <kbd> S </ kbd> <kbd> D </ kbd>를 누르십시오. ** FC바르셀로나 !! **

## Notices

**Watch out!** 단락에 `{: .notice}` 를 추가하여 고지를 추가 할 수도 있습니다.
{: .notice}
