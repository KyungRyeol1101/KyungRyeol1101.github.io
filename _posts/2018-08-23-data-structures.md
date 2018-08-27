---
layout: post
section-type: post
title: Data Structures & Algorithms
category: datastructures
tags: [ 'study' ]
---

# Data Structures & Algorithms : 자료구조 & 알고리즘 (C++)

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
머리1 | 머리2 | 머리3 | 뚝배기
---- | ---- | ---- | ----
다리 | 다리1 | 다리2 | 뚝배기깹니다
금 | 의 | 환 | 향

| |연산자|연산수행위치|
|---|---|---|
| 삽입연산 | push | top |
| 삭제연산 | pop  | top |

* [순차자료구조방식을 통한 스택 구현](https://github.com/)
* [연결자료구조방식을 통한 스택 구현](https://github.com/)
* [스택을 이용한 중위 표기법의 후위표기법 변환](https://github.com/)

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

## Tree
비선형 자료구조 중 자료들 간에 계층관계를 가진 계층형 자료 구조. 연산을 단순화 하기 위해 트리의 노드 구조를 일정하게 정의한 것이 이진트리. 모든 노드의 차수를 2 이하로 정하여 트리의 차수가 2 이하가 되도록 만듬.

### 이진 트리 (Binary Tree)
`n` 개의 노드를 가진 이진 트리는 항상 `n-1` 개의 간선을 가짐. 높이가 `h` 인 이진 트리가 가질 수 있는 노드의 최소 개수는 `h+1` 개.

- [연결자료구조방식을 통한 이진트리 구현](https://github.com/)
	- 전위 순회: `DLR`의 순서로 순회
	- 중위 순회: `LDR`의 순서로 순회
	- 후위 순회: `LRD`의 순서로 순회
- [연결자료구조방식을 통한 이진탐색트리 구현](https://github.com/)
	- 탐색을 위한 자료구조로 이진트리를 사용하기 위해 저장할 데이터의 크기에 따라 노드의 위치를 정한 트리. 
		- 모든 원소는 서로 다른 유일한 키를 가짐.
		- 왼쪽 서브트리의 키 < 그 루트의 키
		- 오른쪽 서브 트리의 키 > 그 루트의 키

### 힙 (Heap)
완전 이진 트리에 있는 노드 중 키 값이 가장 큰 노드나 키 값이 가장 작은 노트를 찾기 위해 만든 자료 구조.

- [순차 자료 구조를 통한 최대 힙 구현.](https://github.com/)

## Graph
모든 연결 구조를 표현할 수 있는 자료구조. 연결할 객체를 나타내는 정점(Vertex)와 간선(Edge)의 집합으로 구성. `G=(V, E)`

- [순차자료구조방식을 이용한 그래프 구현(인접행렬 방법)](https://github.com/)
- [연결자료구조방식을 이용한 그래프 구현(인접리스트 방법)](https://github.com/)

<br>
### 그래프의 종류

#### *- 무방향 그래프 (Undirected Graph)*
두 정점을 연결하는 간선에 방향이 없는 그래프. `(Vi, Vj)`와 `(Vj, Vi)` 는 같은 간선을 나타냄.

#### *- 방향 그래프 (Directed Graph)*
다이그래프(Digraph)라고도 하며, 간선에 방향이 있는 그래프. Vi -> Vj를 `<Vi, Vj>` 로 표현하고 화살표로 나타냄. Vi를 tail, Vj를 head라고 함. `<Vi, Vj>`와 `<Vj, Vi>`  는 서로 다른 간선.

#### *- 완전 그래프 (Complete Graph)*
한 정점에서 다른 모든 정점과 연결되어 최대 간선 수를 가진 그래프. 정점이 `n`개인 무방향 그래프의 최대 간선 수는 `n(n-1)/2`개 이며, 방향 그래프의 경우는 `n(n-1)`개.

#### *- 부분 그래프 (Sub Graph)*
원래 그래프에서 일부의 정점이나 간선을 제외하여 만든 그래프.

#### *- 가중 그래프 (Weight Graph or Network)*
정점을 연결하는 간선에 가중치를 할당한 그래프.

<br>
### 그래프 순회
- [제작 중] (https://github.com/)

#### *- 깊이 우선 탐색 (Depth First Search)*
시작 정점에서 한 방향으로 가장 먼 경로까지 깊이 탐색했다가 더 이상 갈 곳이 없으면 가장 마지막에 만난 갈림길로 되돌아와서 다른 방향의 간선으로 탐색을 계속함. 후입 선출 구조의 스택을 이용.
> (1) 시작 정점 v 방문<br>
> (2) 정점 v에 인접한 정점 중<br>
> 
> - a. 방문하지 않은 정점 w가 있으면 정점 v를 스택에 push하고 w를 방문.<br>
> - b. 방문하지 않은 정점이 없으면 스택을 pop하여 가장 마지막 정점을 v로 설정.<br>
>
> (3) 스택이 공백이 될 때까지 (2)를 반복.

#### *- 너비 우선 탐색 (Breath First Search)*
시작 정점으로부터 인접한 정점들을 모두 차례로 방문 후, 방문했던 정점을 다시 시작점으로 하여 인접한 정점들을 차례로 방문. 선입선출의 구조의 큐를 이용.
> (1) 시작 정점 v 방문<br>
> (2) 정점 v에 인접한 정점 중<br>
> 
> - a. 방문하지 않은 정점이 있으면 차례로 방문하면서 큐에 enQueue.<br>
> - b. 방문하지 않은 정점이 없으면 큐를 deQueue하여 구한 정점을 v로 설정하고 다시 (2)를 반복.<br>
>
> (3) 큐가 공백이 될 때까지 (2)를 반복.


* `Data-Structures`:
  - `Dynamic-Array`
    - C++ implementation + improvised Unit Tests
  - `Linked-List`
    - C++ implementation + improvised Unit Tests
    - Python implementation + Unit Tests
  - `Doubly-Linked-List`
    - C++ implementation + improvised Unit Tests
    - Python implementation + Unit Tests
  - `Priority-Queue`
    - Python implementation + Unit Tests
  - `Stack`
    - C++ implementation using `Dynamic-Array` + improvised Unit Tests
    - C++ implementation using `Linked-List`   + improvised Unit Tests
    - Python implementation using the built-in Python List class + Unit Tests
    - Python implementation using `Linked-List` + Unit Tests
  - `Queue`
    - C++ implementation using `Linked-List` + improvised Unit Tests
    - C++ implementation using `Circular-Array` + improvised Unit Tests
    - Python implementation using `Linked-List` + Unit Tests
    - Python implementation using `Circular-Array` + Unit Tests
  - `Deque`
    - C++ implementation using `Doubly-Linked-List` + improvised Unit Tests
    - Python implementation using `Doubly-Linked-List` + Unit Tests
  - `Graph`
    - BFS, DFS, Dijkstra

### 자료구조와 알고리즘

 알고리즘은 자료구조를 통해 저장된 데이터를 대상으로 어떤 문제의 해결 방법이다. 어떤 자료구조를 택하느냐에 따라 문제 해결을 위한 효율적인 접근이 달라지므로 알고리즘은 자료구조에 의존적이다.

* `Algorithms`:
  - `Sorting`:
    - `Insertion-Sort`
    - `Counting-Sort`
    - `Heap-Sort`
    - `Merge-Sort`
  - `Searching`:
    - `Binary-Search`

# 내부 정렬 (Sort) 

<br>

## 정렬 방법의 분류
- 실행 방법에 따른 분류
	- 비교식 정렬: 비교하고자 하는 각 키 값들을 한번에 두개씩 비교하여 교환
	- 분산식 정렬: 키 값을 기준으로 하여 자료를 여러 개의 부분집합 단위로 분해하여 비교, 정렬
- 정렬 장소에 따른 분류
	- 내부 정렬
		- 교환 방식: 키를 비교하고 교환하여 정렬
		- 삽입 방식: 키를 비교하고 삽입하여 정렬
		- 병합 방식: 키를 비교하고 병합하여 정렬
		- 분배 방식: 키를 구성하는 값을 여러 개의 부분집합에 분배하여 정렬
		- 선택 방식: 이진 트리를 사용하여 정렬
		
	- 외부 정렬 
		- 병합 방식  

## 선택 정렬 (Selection Sort)
- [제작 중] (https://github.com/)

전체 원소들 중 기준 위치에 맞는 원소를 선택하여 자리를 교환하는 방식. 전체 원소 중 가장 작은 원소를 찾아 첫번째 원소와 자리 교환, 두번째로 작은 원소를 찾아 두번째 원소와 자리 교환... 의 과정을 반복. 

- 1단계에서 첫 번째 원소를 기준으로 n 개의 원소 비교
- 2단계에서 두 번째 원소를 기준으로 n-1개의 원소 비교
- ...

## 버블 정렬 (Bubble Sort)
- [제작 중] (https://github.com/)

인접한 두개의 원소를 비교하여 자리를 교환하는 방식. 첫 번째 원소부터 마지막 원소까지 반복하면 가장 큰 원소가 마지막 자리로 정렬하게 됨. 가장 마지막 원소부터 정렬 된다.

## 퀵 정렬 (Quick Sort)
-[제작 중] (https://github.com/)

기준 값(피봇, Pivot)을 중심으로 전체 원소들을 왼쪽 부분집합과 오른쪽 부분집합으로 분할. 왼쪽부분집합에는 기준값보다 작은 원소들을, 오른쪽부분집합에는 기준값보다 큰 원소들을 이동시킴. 

## 삽입 정렬 (Insert Sort)
- [제작 중] (https://github.com/)

정렬할 자료가 두 개의 부분집합으로 나뉘어 있다고 생각하고 정렬을 수행. 정렬 된 앞부분의 원소들은 부분집합 `S`가 되고 정렬되지 않은 나머지 원소들은 부분집합 `U`로 정하여 정렬되지 않은 부분집합 `U`의 원소를 하나씩 꺼내서 이미 정렬되어 있는 부분집합 `S`의 마지막 원소부터 비교하면서 위치를 찾아 삽입하는 방식.

- 정렬할 데이터: {69, 10, 30, 2, 16, 8, 31, 22}
- S= {69}, U= {10, 30, 2, 16, 8, 31, 22}

## 셸 정렬 (Shell Sort)
- [제작 중] (https://github.com/)

일정한 간격으로 떨어져 있는 자료들끼리 부분집합을 구성하고 각 부분집합에 있는 원소들에 대해 삽입 정렬을 수행하는 작업을 반복하면서 전체 원소들을 정렬하는 방법. 삽입 정렬을 수행하는 것보다 비교 연산과 교환 연산의 횟수를 줄일 수 있음.

## 병합 정렬 (Merge Sort)
- [제작 중] (https://github.com/)

여러 개의 정렬된 자료의 집합을 한 개의 정렬된 집합으로 만드는 방법. `n`개의 정렬된 자료의 집합을 결합하여 하나의 집합으로 만드는 병합 방법을 `n`-way 병합이라고 함.

## 기수 정렬 (Radix Sort)
분배 방식의 정렬 방법으로 정렬할 원소의 키 값에 해당하는 버킷(Bucket)에 원소를 분배하였다가 버킷의 순서대로 원소를 꺼내는 방법을 반복.



## 알고리즘의 성능분석 방법

### 시간 복잡도(Time Complexity)

 알고리즘 수행시간을 분석

### 공간 복잡도(Space Complexity)

 알고리즘의 메모리 사용량을 분석

 문제 해결을 위한 최적의 솔루션을 찾기 위해서는 자료구조와 알고리즘을 평가할 수 있어야한다. 일반적으로 알고리즘을 평가할 때 공간 복잡도보다는 시간 복잡도에 초점을 둔다. 공간 복잡도는 특정 알고리즘에 대한 상대적인 우월성을 입증하는 경우에 사용되기도 한다. 무조건적으로 연산 속도가 빠른 알고리즘을 선택하는 것이 아니라 자료의 갯수, 구현의 난이도와 같이 문제 해결 상황에 맞는 알고리즘을 선택해야한다.

### 시간 복잡도 분석 방법

1. 처리해야 할 데이터의 수 n에 대한 연산횟수의 함수 T(n)을 구성한다. (핵심이 되는 연산에 대하여, 또 worst case에 대하여)
2. T(n)을 빅-오 표기법(Big-Oh Notation)으로 표현한다.

### 빅-오 표기법

 데이터 수의 증가에 따른 연산횟수 증가율의 상한선을 표현한 것. (수학적 정의 참고)

**대표적인 빅-오**

> O(1): 상수형 빅-오. 연산횟수가 고정인 유형의 알고리즘
>
> O(logn): 로그형 빅-오. 데이터 수의 증가율에 비해 연산횟수의 증가율이 훨씬 낮은 알고리즘
>
> O(n): 선형 빅-오. 데이터 수와 연산횟수가 비례
>
> O(nlogn): 선형로그형 빅-오.
>
> O(n^2): 중첩된 반복문에서 발생.
>
> O(n^3): 삼중으로 중첩된 반복문에서 발생.
>
> O(2^n): 지수형 빅-오. 사용하기에 무리가 있는 알고리즘.



# 추상 자료형 (Abstract Data Type)

### 추상 자료형

 **추상적 자료형**(Abstract Data Type, 줄여서 ADT)은 자료들과 그 자료들에 대한 연산들을 명기한 것이다. 추상적 자료형은 인터페이스와 구현을 분리하여 추상화 계층을 둔 것이다. 자료에 대한 연산은 자료에 대하여 질의를 던지는 것(size, full, empty …)과 자료를 변경하기 위한 연산(push, pop …)으로 나뉜다.

> 복소수, 리스트, 스택, 큐, 맵, 우선순위 큐, 집합 등

### 추상적 자료 구조

 **추상적 자료 구조**는 자료에 대한 일련의 연산이 정의되며, 각각의 연산에 대한 연산 복잡도가 정의된 가상의 자료 저장 공간이다.

> 스택, 큐, 연결 리스트 등
