---
layout: post
section-type: post
title: Writing posts
category: tech
tags: [ 'tutorial' ]
---

### Creating a new post

Run the ./scripts/newpost script with the file name of the post as an argument:

<pre><code data-trim class="bash">
cd <your { Personal } repo>
./scripts/newpost hello-world
</code></pre>

A a new post template with name YYYY-MM-DD-hello-world.md will be created under ./\_posts, with the current date.

In the created post, just replace the Title, Category and tags and you can
start writing your post in markdown right bellow the end of the post header.

Every file with the format <i>YYYY-MM-DD-post-title.md</i> will be processed as a
post, with publication date <i>YYYY-MM-DD</i>.

The content starts with:

<pre><code data-trim class="yaml">
---
layout: post
section-type: post
title: Title
category: Category
tags: [ 'tag1', 'tag2' ]
---
</code></pre>

The *layout* and *section-type* variables are used by the theme and you shouldn't remove them.

### Hashtags

Jekyll generates a static pages.
As a result we have to create the tag pages before building and publishing the site.
In order to generate the tag pages, simply run the *generate-tags* script from the repo's root directory:

<pre><code data-trim class="bash">
./scripts/generate-tags
</code></pre>

The script will parse all your posts, and generate the tag pages for the newly added tags.

<small>If you are not using GitHub Pages, you can automate the execution of this script during build time.</small>

### Categories

You can organize your posts under categories. Categories are behaving like hashtags,
they have to be generated offline, by running the ./scripts/generate-categories script.

The category of the post is specified in the yaml header, in the Category variable.

NB! Only one category can be defined per post.

### Syntax highlighting

If you want to demonstrate source code in your posts, syntax highlighting is provided.
If you want to see how to render your code with the highlight, simply check the source
code of this tutorial post :smile:

<pre><code data-trim class="c">
{% raw %}
int main()
{
  printf("Hello, world of syntax highlighting!");

  return 0;
}
{% endraw %}
</code></pre>

<small>If you don't need syntax highlight in your website you can disable it by setting the syntax-highlight variable to False</small>

### Emoji support

You can add emojis to your posts by simply typing their [emoji code](http://www.emoji-cheat-sheet.com/) :wink:

### Author Blurb

You can add a short description of yourself bellow your posts, by setting the next two variables in the site config

<pre><code data-trim class="yaml">
################
# Author Blurb #
################

# The author blurb goes underneath blog posts.
# This works best when your author blurb image has a transparent background, or matches your site background color.

# if the author_blurb is not set, then this feature is skipped
author_blurb: "John Smith is an awesome person. He lives in Flatland, where he works on two-dimensional engineering projects. In his spare time, John likes to eat cotton candy."
author_blurb_image: "/img/author.png"
</code></pre>
## 자료구조란?

 자료구조란 데이터를 표현하고 저장하는 방법이다.

> 선형구조: 리스트, 스택, 큐
>
> 비선형구조: 트리, 그래프
>
> 파일구조: 순차파일, 색인파일, 직접파일
>
> 단순구조: 정수, 실수, 문자, 문자열

## Stack
시간 순서에 따라 가장 마지막에 삽입한 자료가 가장 먼저 삭제되는 **후입선출 (LIFO, Last In First Out)** 방식으로 동작.

| 		  |연산자|연산수행위치|
|--------|--------|--------|
| 삽입연산 | push | top |
| 삭제연산 | pop  | top |

- [순차자료구조방식을 통한 스택 구현](https://github.com/)
- [연결자료구조방식을 통한 스택 구현](https://github.com/)
- [스택을 이용한 중위 표기법의 후위표기법 변환](https://github.com/)

## Queue
리스트 한쪽 끝(rear)에서 삽입이 이루어지고, 반대쪽 끝(front)에서 삭제 작업이 이루어져 삽입된 순서대로 삭제되는 **선입선출 (FIFO, First In First Out)** 방식으로 동작.


| 		  |연산자|연산수행위치|
|--------|--------|--------|
| 삽입연산 | enQueue | rear |
| 삭제연산 | deQueue | front |

- [순차자료구조방식을 통한 큐 구현](https://github.com/)
- [순차자료구조방식을 통한 원형 큐 구현 (선형 큐의 잘못된 포함 상태 문제 해결)](https://github.com/)
- [연결자료구조방식을 통한 큐 구현](https://github.com/)

### Deque (Double-ended Queue)
큐의 양쪽 끝에서 삽입, 삭제가 모두 발생할 수 있는 큐로서 스택의 성질과 큐의 성질을 모두 가짐.

- [이중 연결 리스트를 통한 덱 구현](https://github.com/)


| 		  |연산자|연산수행위치|
|--------|--------|--------|
| 삽입연산 | insert | front 또는 rear |
| 삭제연산 | delete | front 또는 rear |
