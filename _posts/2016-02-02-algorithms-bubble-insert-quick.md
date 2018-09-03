---
layout: post
title: Bubble
date: 2016-02-02
excerpt: 버블정렬
tags: [algorithms, c++, bubble, sort]
comments: true
---

# Bubble & Insert & Quick : 버블 & 삽입 & 퀵 (C++)

## 버블(Bubble)

- 서로 '인접한' 두 원소를 검사하여 정렬하는 알고리즘
	- 인접한 2개의 레코드를 비교하여 크기가 순서대로 되어 있지 않으면 서로 교환한다.
- 선택 정렬과 기본 개념이 유사하다.

### 특징

- 장점
	- 구현이 매우 간단하다.

- 단점
	- 순서에 맞지 않은 요소를 인접한 요소와 교환한다.
	- 하나의 요소가 가장 왼쪽에서 가장 오른쪽으로 이동하기 위해서는 배열에서 모든 다른 요소들과 교환되어야 한다.
	- 특히 특정 요소가 최종 정렬 위치에 이미 있는 경우라도 교환되는 일이 일어난다.
	
- 일반적으로 자료의 교환 작업(SWAP)이 자료의 이동 작업(MOVE)보다 더 복잡하기 때문에 버블 정렬은 단순성에도 불구하고 '거의 쓰이지 않는다.'

### 시간복잡도

시간복잡도를 계산한다면

- 비교 횟수
	- 최상, 평균, 최악 모두 일정
	- n-1, n-2, … , 2, 1 번 = n(n-1)/2
- 교환 횟수
	- 입력 자료가 역순으로 정렬되어 있는 최악의 경우, 한 번 교환하기 위하여 3번의 이동(SWAP 함수의 작업)이 필요하므로 (비교 횟수 * 3) 번 = 3n(n-1)/2
	- 입력 자료가 이미 정렬되어 있는 최상의 경우, 자료의 이동이 발생하지 않는다.
- T(n) = O(n^2)






## 퀵(Quick)



Syntax highlighting is a feature that displays source code, in different colors and fonts according to the category of terms. This feature facilitates writing in a structured language such as a programming language or a markup language as both structures and syntax errors are visually distinct. Highlighting does not affect the meaning of the text itself; it is intended only for human readers.[^1]

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

### Highlighted Code Blocks

To modify styling and highlight colors edit `/assets/css/syntax.css`.


### C++로 구현한 스택 & 큐 & 덱 (Stack & Queue & Deque)
[이전에 작성한 양방향 링크드 리스트의 코드를 재활용](https://kyungryeol1101.github.io/data-structures-linked-list-array/)

{% highlight cpp %}
class Queue
{
private:
	DoubleList *doublelist;
public:
	Queue();
	~Queue();
	
	DoubleList *getdouble() { return doublelist; }

	void enqueue(int data, int position);
	void dequeue(int position);
	void display();
};


#include "Queue.h"

Queue::Queue()
{
	doublelist = new DoubleList;
}

Queue::~Queue()
{
}

void Queue::enqueue(int data, int _position) {
	doublelist->insertNode(data, _position);
}

void Queue::dequeue(int position) {
	doublelist->delNode(position);
}

void Queue::display() {
	doublelist->displayNode();
}

class Stack
{
private:
	DoubleList *doublelist;
public:
	Stack();
	~Stack();
	
	DoubleList *getdouble() { return doublelist; }

	void Push(int data, int position);
	void Pop(int position);
	void display();
};

#include "Stack.h"

Stack::Stack()
{
	doublelist = new DoubleList;
}

Stack::~Stack()
{
}

void Stack::Push(int data, int position) {
	doublelist->insertNode(data, position);
}

void Stack::Pop(int position) {
	doublelist->delNode(position);
}

void Stack::display() {
	doublelist->displayNode();
}
{% endhighlight %}
