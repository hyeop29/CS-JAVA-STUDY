# 자료구조

### 1. 배열

#### Q) Array vs List 차이점
* Array는 메모리 상에 데이터가 연속적으로 저장되고, List는 메모리 상에 데이터가 비연속적으로 저장된다. 배열은 삽입과 삭제의 경우 O(N)의 시간 복잡도를 갖는다.
배열은 크기가 정해져 있고, 메모리 상에 데이터가 연속적으로 있어야 하기 때문에 메모리의 낭비가 발생할 수 있습니다.
* 리스트는 가변적이고 빈 공간을 허용하지 않기 때문에 이러한 메모리의 낭비는 없다. 원소에 접근할 때 O(N)의 시간 복잡도를 갖는다. 삽입과 삭제의 경우 O(N)의 시간 복잡도를 갖는다.(포인터를 통하여 다음 데이터의 위치를 가르켜고 있어) 원소에 접근할 때는 O(1)의 시간 복잡도를 갖는다.

#### Q) ArrayList와 LinkedList를 설명하세요
* ArrayList는 기본적으로 배열을 사용한다. 하지만 일반 배열과 차이점이 존재한다. 일반 배열은 처음에 메모리를 할당할 때 크기를 지정해주어야 하지만,
ArrayList는 크기를 지정하지 않고 동적으로 값을 삽입하고 삭제할 수 있다.index를 통해 무작위 접근 가능 → O(1)의 시간복잡도를 가짐.삽입, 삭제시 배열을 임시배열에 복사하는 방식이기 때문에 O(N) 복잡도

* Linkedlist는 데이터를 하나의 노드로 구성하며, 각 노드는 자신의 이전 노드와 다음 노드만 알고 있다. 시작노드 또한 다음 노드만 가리키고 있지만 포인터의 사용으로 저장공간을 많이 차지한다. (배열의 단점을 보완하기 위해 LinkedList가 고안되었다.) 처음노드부터 찾으려는 노드까지 순차적으로 탐색해야하므로 최대 O(N)의 시간복잡도를 가짐. 삽입, 삭제시 이전노드와 다음 노드를 참조하는 상태만 변경하면 되기 때문에 O(1)의 복잡도

#### Q) 링크드 리스트를 사용해서 구현할 수 있는 다른 자료구조
* 단일 연결리스트
각 노드 당 한 개의 포인터가 있고 포인터는 다음 노드의 위치를 가르킵니다. 가장 마지막이므로 다음을 가리키는 포인터를 갖지 않습니다.
* 이중 연결 리스트 단일 연결 리스트는 포인터를 한 개 가지고 있어 다음 노드만 가리킬 수 있었다면 이중 연결 리스트는 포인터를 두 개 가지고 있어 이전 노드와 다음 노드를 가리킵니다.
* 원형 연결 리스트는 단일 연결 리스트에서 마지막 노드와 처음 노드를 연결시켜 원형으로 만든 구조이다.
---
### 2. Stack & Queue

#### Q) 스택과 큐에 대해 설명해주세요
* 답변
--- 
### 3. Heap

#### Q) 힙에 대해 설명하고, Heap Sort에 대해 설명해 주세요.
* 힙이란?
  - 큐 안에 데이터 들에 우선순위를 주고 그 우선순위가 높은 데이터가 먼저 처리되도록 하는 자료구조를 우선순위 큐(Priority Queue)라고 한다. 원소를 꺼내는 데는 O(n)의 시간이 걸리는데 데이터가 많아지고 꺼내는 횟수가 늘어날 수록 시간이 너무 지연되서 조금 더 빠르게 데이터를 꺼내기 위해 만든것이 힙(heap)이다. 힙은 결국 우선순위 큐를 구현하기 위한 자료구조이다.
  - 힙은 완전 이진 트리(Complete binary tree)의 형태를 띄고 있다.
  - 힙에는 두 가지 종류가 있다. 최대 힙(max heap)과 최소 힙(min heap)
    - 최대 힙 : '부모의 값이 자식의 값보다 항상 큰' 조건을 만족하는 완전이진트리
    - 최소 힙 : '부모의 값이 자식 값보다 항상 작은' 조건을 만족하는 완전이진트리
  - 이 최대힙 혹은 최소힙을 이용하면 항상 첫번째 노드의 키 값을 최대, 혹은 최소값으로 유지된다.
* Heap Sort 란?
  - 힙정렬은 최 상위 노드 값을 하나씩 뽑아내면서 정렬을 하는 것이다.
  - 최초 트리가 max heap 또는 min heap 형태가 아닐 수도 있으니 먼저 트리를 힙 생성 알고리즘(heapify)을 통해 힘 구조로 만들어준다.
  - 이후 최상위에 있는 root값과 맨 마지막 값을 바꾼다.
  - 그리고 맨 뒤로 보낸 root 값을 제외하고 다시 힙 생성 알고리즘을 수행하여 힘 구조를 만든다.
  - 마지막으로 보내진 값을 제외하고 다시 최상위 root 값과 마지막 값을 바꾼다. 다시 힙 생성 알고리즘을 수행하여 힘 구조를 만든다.
  - 반복.


#### Q) 힙을 배열로 구현한다고 가정하면, 어떻게 값을 저장할 수 있을까요?
* 배열의 인덱스로 접근할 수 있다. 
* 각 노드는 인덱스를 기준으로 다음과 같은 관계식을 갖게 된다.
* 부모 노드 : i번째 노드의 부모 노드 인덱스는 (i-1)/2
* 왼쪽 자식 노드 : i번째 노드의 왼쪽 자식 노드 인덱스는 2i+1
* 오른쪽 자식 노드 : i번째 노드의 오른쪽 자식 노드 인덱스는 2i+2
* 이러한 관계로 특정 인덱스의 노드에 대한 부모 노드, 왼쪽 자식 노드, 오른쪽 자식 노드를 찾을 수 있다.


#### Q) 힙의 삽입, 삭제 방식에 대해 설명하고, 왜 이진탐색트리와 달리 편향이 발생하지 않는지 설명해 주세요.
* 힙의 삽입
   - 새 data를 마지막 Node에 삽입.
   - 삽입된 노드로부터 계속해서 부모노드와 비교
   - 최대힙, 최소힙 여부에 따라 부모보다 큰지, 작인지 비교하고 swap 함.
* 힙의 삭제
   - 힙에서 Data 의 삭제는 항상 루트 노드를 삭제한다.
   - 최대힙의 경우엔 최대값이 삭제가 되고 최소힙의 경우엔 최소값이 삭제 된다.
   - root 제거 후 가장 마지막 Node가 root 가 된다.
   - 이동 후 최대힙/최소힙 조건을 갖춰야 하므로 계속해서 자식 Node 와 비교하면서 필요시 Swap 한다.
* 이진탐색트리와 달리 편향이 발생하지 않는 이유
   - 이진탐색트리가 편향이 발생하는 이유는 삽입 방식에 있다.
   - 삽입되는 노드의 값이 이전에 삽입된 노드들보다 작은 경우에는 왼쪽 자식 노드로 삽입되고, 큰 경우에는 오른쪽 자식 노드로 삽입된다.
   - 삽입 순서가 1, 2, 3, 4, 5, 6, 7일 때 이진 탐색 트리를 구성하면 높이가 7이 되고 4, 2, 6, 1, 3, 5, 7 이면 완전이진탐색트리와 같은 3의 높이를 같는다.
   - 이처럼 이진탐색트리는 삽입순서에 따라 편향이 발생한다.
   - 반면에 힙은 무조건 삽입은 마지막에, 삭제는 첫번째것 이라고 정해져 있기 때문에 편향 없이 일정하게 구성된다.


#### Q) Heap Sort 공간복잡도는 어떻게 되나요?
* Heap Sort는 주어진 배열 안에서 정렬을 수행하므로, 추가적인 배열이나 데이터 구조가 필요하지 않기 때문에 공간 복잡도는 O(1) 이다.


#### Q) 힙 정렬의 시간복잡도는 어떻게 되나요? Stable 한가요?
* 입력 배열을 힙으로 만드는데 O(n)의 시간이 걸리고, 원소를 삭제하면서 정렬하는데 O(n log n)의 시간이 걸리기 때문에 시간복잡도는 O(n log n) 이다.
* 힙정렬은 Stable 하지 않은, 즉 불안정한 정렬이다. Stable 하다, 안정적이다 라는 것은 같은 값을 가지는 원소들의 순서가 정렬 이전과 이후에도 유지되는 것을 말한다. 예를 들면 [2, 1, 3, 2, 3] 과 같은 배열에서 정렬 후에도 두개의 2와 두개의 3이 들어온 순서가 유지된다는 의미인데 힙정렬은 유지 되지 않을 수 있기 때문에 Stable 하지 않다.



--- 
### 4. Tree

#### Q) Binary Tree
* 답변

---
### 5. Graph

#### Q) 그래프를 구현하는 두 가지 방식에 대해 설명해주세요.
* 인접행렬(Adjacency Matrix)
  - 2차원 배열(행렬) 을 이용
  - 두 개의 노드가 간선으로 연결되어 있다면 인접하다.
  - 인접 행렬에 그래프의 간선 정보를 저장한다.
  - 두 노드의 간선 정보를 확인하는것이 빠르다. O(1)
  - 새로운 간선을 추가하고 제거하는것이 빠르다. O(1)
  - 특정한 노드에 인접한 노드를 찾기위해서 모든 노드를 순회해야 한다.
  - 노드를 추가 하거나 제거하는데 오래 걸린다. O(N^2)
  - 그래프의 모든 간선의 수를 찾는데 O(N^2)
* 인접리스트(Adjacency List)
  - 인접 정보를 저장하는 리스트
  - 배열의 크기는 노드의 개수와 같다.
  - 특정 노드에 직접 접근할 수 있어 인접한 노드를 찾기 쉽다.
  - 노드의 추가 삭제가 빠르다.
  - 새로운 간선을 빠르게 추가 할 수 있다. O(1)





#### Q) 두 방식의 시간복잡도, 공간복잡도 차이
* N = Node의 개수, E = Edge의 전체 개수
* 시간복잡도
  - 인접행렬
    - Node 추가 : O(N^2)
    - Node 삭제 : O(N^2)
    - Edge 추가 : O(1)
    - Edge 삭제 : O(1)
    - Node 추가 : 행과 열을 모두 추가해야 하므로 노드 개수의 제곱만큼의 시간이 필요하다. 추가로 새로 생긴 행과 열에 대한 각 셀을 채워야 한다.
    - Node 삭제
    - Edge 추가 : Edge 추가는 특정 셀의 값만 변경(0, 1)하면 되므로 상수 시간만큼 소요된다.
    - Edge 삭제 : Edge 삭제는 특정 셀의 값만 변경(0, 1)하면 되므로 상수 시간만큼 소요된다.
  - 인접리스트
    - Node 추가 : O(1)
    - Node 삭제 : O(N+E)
    - Edge 추가 : O(1)
    - Edge 삭제 : O(E)
    - Node 추가 : 이중연결리스트 꼬리 nextNode로 지정하기 때문에 상수 시간만큼 소요됩니다.
    - Node 삭제 : 노드를 삭제하면 삭제된 공간을 채우기 위해 다시 색인하는 과정이 필요하므로 노드, 정점의 개수를 합한 만큼의 시간이 소요됩니다.
    - Edge 추가
    - Edge 삭제 : 최악의 상황은 한 줄로 노드가 연결되어 있는 경우입니다. 삭제하기 위해 마지막 Edge까지 탐색해야 합니다.
* 시간복잡도
  - 인접행렬
    - O(N^2)
    - 노드수 x 노드수 만큼의 행렬이 필요하기 때문이다.
  - 인접리스트
    - O(N+E)
    - 정점의 수만큼 공간이 필요하고 인접한 정점을 저장하기 위해 간선 수만큼의 추가 공간이 필요하기 때문이다.

   
#### Q) node의 개수가 N개, edge의 개수가 N^3 일 경우, 무엇이 더 효율적일까요?
* 인접 리스트가 인접 행렬보다 효율적이다. 이는 인접 행렬의 공간 복잡도가 O(N^2)이고, 간선의 개수가 N^3이므로, 총 공간 복잡도는 O(N^2 + N^3)이 되기 때문이다. 반면 인접 리스트의 공간 복잡도는 O(N + N^3)이므로, 더 효율적이다.
* 또한 간선의 개수가 N^3개인 경우, 인접 리스트를 사용하면 각 노드마다 평균 O(N^2)개의 인접 노드를 가지므로, 인접 리스트를 사용한 그래프 탐색 및 최단 경로 알고리즘의 시간 복잡도는 O(N^5) 이다. 반면 인접 행렬을 사용하면 간선의 개수가 많기 때문에 탐색 및 최단 경로 알고리즘의 시간 복잡도는 O(N^6)이 된다.


#### Q) 각 방법에 대해, "두 노드가 연결되었는지" 확인하는 시간복잡도와 "한 노드에 연결된 모든 노드를 찾는" 시간복잡도, 그리고 공간복잡도를 비교해 주세요.
* 인접행렬
  - 두 노드가 연결되어 있는지 확인하는데는 O(1) 의 시간복잡도
  - 한 노드에 연결된 모든 노드를 찾는데는 O(N)의 시간복잡도
  - 인접행렬은 N x N 크기의 2차원 배열로 구현되므로, 공간복잡도는 O(N^2)
* 인접리스트
  - 두 노드가 연결되어 있는지 확인하는데는 O(E)의 시간복잡도
  - 한 노드에 연결된 모든 노드를 찾는데는 O(E)의 시간복잡도
  - 인접리스트는 각 노드마다 인접한 노드들의 리스트를 저장하므로, 공간복잡도는 O(N+E)


#### Q) Minimum Spanning Tree
  - Minimum Spanning Tree(MST)는 가중치 그래프에서 모든 정점을 연결하는 부분 그래프 중에서 가중치의 합이 최소인 트리이다.
  - 두 가지 대표적인 알고리즘으로 Kruskal 알고리즘과 Prim 알고리즘이 있다.

#### Q) Kruskal algorithm
  - 엣지들을 가중치의 오름차순으로 정렬한다.
  - 가장 가중치가 작은 엣지부터 선택하며, 이때 선택된 엣지가 사이클을 형성하지 않는 경우에만 그래프에 추가한다.
  - 모든 노드를 연결할 때까지 2번의 과정을 반복한다.

#### Q) Prim algorithm
  - 임의의 시작 노드를 선택하고, 해당 노드에 연결된 모든 엣지을 우선순위 큐에 추가한다.
  - 우선순위 큐에서 가장 가중치가 작은 엣지을 선택하고, 해당 엣지와 연결된 노드가 MST에 포함되지 않은 경우에만 해당 노드를 MST에 추가한다.
  - 새로 추가된 노드와 연결된 모든 엣지을 우선순위 큐에 추가한다.
  - 모든 노드가 MST에 포함될 때까지 2~3번의 과정을 반복한다.


#### Q) Kruskal algorithm 은 인접 리스트와 인접 행렬 중 무엇을 쓰나요?
  - 인접 리스트와 인접 행렬 두 가지 방법 모두 사용가능하지만 간선들의 정렬과 사이클 검사에 많은 시간이 소요되므로, 인접 리스트를 사용하면 각 정점마다 연결된 간선들을 쉽게 탐색할 수 있기 때문 더 효율적인 구현이 가능하다.


#### Q) 사이클이 없는 방향 그래프는 모두 트리인가요? 그렇지 않다면, 예시를 들어주세요.
* 비순환 그래프(Acyclic Graph)라고 모두 트리는 아니다. 예로 사이클이 없는 그래프인 DAG와 여러 트리로 이루어진 Forest가 있다.

![image](https://user-images.githubusercontent.com/21374239/230546000-5be08003-c7ba-4ee1-81a5-fe8259ab56d8.png)


#### Q) 그래프에서, 최단거리를 구하는 방법에 대해 설명해 주세요.
* 그래프에 가중치가 없을땐 BFS
* 음의 가중치가 없을땐 다익스트라
* 음의 가중치가 있을땐  벨만포드 를 사용한다.



--- 
### 6. 자료구조 , 시간복잡도/공간복잡도

#### Q) 사용하는 언어가 제공하는 자료구조를 소개하고, 그 자료구조가 어떻게 구현되어 있는지 간단하게 설명해 보세요
* 답변
