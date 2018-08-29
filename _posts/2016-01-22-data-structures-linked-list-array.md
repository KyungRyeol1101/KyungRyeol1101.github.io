---
layout: post
title: "Linked List & Array"
date: 2016-01-22
excerpt: 링크드리스트와 배열
tags: [data structures, c++, linked list, array]
comments: true
---

# Linked List & Array : 링크드 리스트 & 배열 (C++)

## 배열(Array)

<figure>
    <img src="/images/data_structures/array.jpg">
</figure>

- 데이터를 물리적 주소에 순차적으로 저장하며 인덱스를 가지고 있어 바로 접근할 수 있기 때문에 접근 속도가 매우 빠르다. 그러나, 배열은 크가가 고정되어 있기 때문에 처음 지정된 사이즈보다 더 많은 데이터를 넣으려면 배열의 크기를 늘리는 연산을 해야하고 데이터 삽입/삭제시 해당 위치 다음칸에 있는 데이터를 모두 한칸씩 뒤로 밀거나 앞으로 당겨오는 연산을 해야하기 때문에 데이터 삽입/삭제에는 약한 모습을 보인다.

## 연결리스트(LinkedList)

<figure>
    <img src="/images/data_structures/linkedlist.jpg">
</figure>

- 데이터를 저장할 때 데이터만 저장하는 것이 아니라 다음 데이터의 물리적 주소까지 같이 저장한다. (단순 연결리스트는 다음 데이터의 주소를, 이중 연결리스트는 이전 주소와 다음 주소를 모두 저장) 특정 데이터에 접근할 때 인덱스로 바로 접근할 수 있었던 배열과 달리 첫 노드부터 원하는 노드까지 링크를 따라가야 접근이 가능하기 때문에 배열에 비해 접근 속도는 떨어진다. 하지만 반대로, 데이터를 삽입/삭제 할 때에는 물리적 주소에 구애받지 않고 앞/뒤 노드의 주소만 끼워넣을 노드의 주소로 바꿔주면 되기 때문에 삽입/삭제는 배열보다 빠르다.

### C++로 구현한 양방향 연결 리스트(Double Linked List)

{% highlight c++ %}

void DoubleList::insertNode(int _data, int _position) {
	++IDCount;
	Node *newNode = new Node;
	newNode->setData(_data);
	newNode->SetID(IDCount);
	
	if (Head == NULL) {
		Head = newNode;
		Tail = Head;
	}
	else {
		if (_position == 0) {
			newNode->setRlink(Head);
			Head->setLlink(newNode);
			Head = newNode;
		}
		else if (_position == -1) {
			newNode->setLlink(Tail);
			Tail->setRlink(newNode);
			Tail = newNode;
		}
		else {
			Node *before = Head;
			while ((--_position) > 0)
			{
				before = before->getRlink();
			}
			if (before->getRlink() != NULL) {
				before->getRlink()->setLlink(newNode);
			}
			newNode->setLlink(before);
			newNode->setRlink(before->getRlink());
			before->setRlink(newNode);
		}
	}
}

void DoubleList::delNode(int _location) {
	if (_location == 0) {
		Head = Head->getRlink();
		if (Head != NULL) {
			Head->setLlink(NULL);
		}
	}
	else {
		Node *before = Head;
		while ((--_location) > 0)
		{
			before = before->getRlink();
		}
		Node *after = before->getRlink()->getRlink();
		if (after != NULL) {
			before->setRlink(after);
			after->setLlink(before);
		}
		else {
			before->setRlink(NULL);
		}
	}
}

void DoubleList::displayNode() {
	Node *Temp = Head;
	while (true)
	{
		if (Temp == NULL) {
			break;
		}
		else {
			cout << "ID:" << Temp->GetID() << " Data:" << Temp->getData() << endl;
			Temp = Temp->getRlink();
		}
	}
}

void DoubleList::AllDel() {
	while (true)
	{
		if (Head == NULL) {
			break;
		}
		else {
			delNode(0);
		}
	}
}

int DoubleList::CountNode() {
	int count = 0;

	Node *now = new Node;
	for (now = Head; now; now = now->getRlink()) {
		count++;
	}
	return count;
}

int DoubleList::Find(int _location) {
	Node *current = Head;
	while ((--_location) >= 1) {
		current = current->getRlink();
	}
	return current->getData();
}

void DoubleList::Swap(Node * tmp1, Node * tmp2)
{
	Node *tmp1Llink = tmp1->getLlink();
	Node *tmp1Rlink = tmp1->getRlink();
	Node *tmp2Llink = tmp2->getLlink();
	Node *tmp2Rlink = tmp2->getRlink();

	if (tmp1 == tmp2) {
		return;
	}
	else if (tmp1->getRlink() == tmp2) {
		if (tmp1 == Head) {
			Head = tmp2;
			if (tmp2 != Tail) {
				tmp2Rlink->setLlink(tmp1);
			}
			else {
				Tail = tmp1;
			}
		}
		else if (tmp2 == Tail) {
			Tail = tmp1;
			tmp1Llink->setRlink(tmp2);
		}
		else
		{
			tmp2Rlink->setLlink(tmp1);
			tmp1Llink->setRlink(tmp2);
		}
		tmp1->setRlink(tmp2Rlink);
		tmp2->setLlink(tmp1Llink);

		tmp1->setLlink(tmp2);
		tmp2->setRlink(tmp1);
	}
	else {
		if (tmp1 == Head) {
			Head = tmp2;
			if (tmp2 != Tail) {
				tmp2Rlink->setLlink(tmp1);
			}
			else {
				Tail = tmp1;
			}
		}
		else if (tmp2 == Tail) {
			Tail = tmp1;
			tmp1Llink->setRlink(tmp2);
		}
		else {
			tmp2Rlink->setLlink(tmp1);
			tmp1Llink->setRlink(tmp2);
		}
		tmp1Rlink->setLlink(tmp2);
		tmp2Llink->setRlink(tmp1);

		tmp1->setRlink(tmp2Rlink);
		tmp2->setLlink(tmp1Llink);

		tmp1->setLlink(tmp2Llink);
		tmp2->setRlink(tmp1Rlink);
	}
}

void DoubleList::Reverse()
{
	Node *current = Head;
	while (current != NULL)
	{
		Node *next = current->getRlink();
		current->setRlink(current->getLlink());
		current->setLlink(next);
		if (next == NULL) {
			Tail = Head;
			Head = current;
			break;
		}
		current = next;
	}
}
{% endhighlight %}
