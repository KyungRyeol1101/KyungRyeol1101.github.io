---
layout: post
title: Insertion sort
date: 2016-02-03
excerpt: 삽입정렬
tags: [algorithms, c++, insertion, sort]
comments: true
---

# Insert : 삽입 (C++)

## 삽입(Insert)

- 손안의 카드를 정렬하는 방법과 유사하다.
	- 새로운 카드를 기존의 정렬된 카드 사이의 올바른 자리를 찾아 삽입한다.
	- 새로 삽입될 카드의 수만큼 반복하게 되면 전체 카드가 정렬된다.
- 자료 배열의 모든 요소를 '앞에서부터 차례대로 이미 정렬된 배열 부분과 비교' 하여, 자신의 위치를 찾아 삽입함으로써 정렬을 완성하는 알고리즘
- 매 순서마다 해당 원소를 삽입할 수 있는 위치를 찾아 해당 위치에 넣는다.

### 특징

- 장점
	- 안정한 정렬 방법
	- 레코드의 수가 적을 경우 알고리즘 자체가 매우 간단하므로 다른 복잡한 정렬 방법보다 유리할 수 있다.
	- 대부분위 레코드가 이미 정렬되어 있는 경우에 매우 효율적일 수 있다.
- 단점
	- 비교적 많은 레코드들의 이동을 포함한다.
	- 레코드 수가 많고 레코드 크기가 클 경우에 적합하지 않다.

### 시간복잡도

시간복잡도를 계산한다면

- 최선의 경우
	- 비교 횟수
		- 이동 없이 1번의 비교만 이루어진다.
		- 외부 루프: (n-1)번
	- Best T(n) = O(n)
- 최악의 경우(입력 자료가 역순일 경우)
	- 비교 횟수
		- 외부 루프 안의 각 반복마다 i번의 비교 수행
		- 외부 루프: (n-1) + (n-2) + … + 2 + 1 = n(n-1)/2 = O(n^2)
	- 교환 횟수
		- 외부 루프의 각 단계마다 (i+2)번의 이동 발생
		- n(n-1)/2 + 2(n-1) = (n^2+3n-4)/2 = O(n^2)
	- Worst T(n) = O(n^2)

	
- 단순(구현 간단)하지만 비효율적인 방법
	- 삽입 정렬, 선택 정렬, 버블 정렬
- 복잡하지만 효율적인 방법
	- 퀵 정렬, 힙 정렬, 합병 정렬, 기수 정렬

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
