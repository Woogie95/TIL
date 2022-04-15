### 이중 연결리스트 Doubly LinkedList

- 단일 연결리스트와 차이라면 단일 연결리스트는 노드에 데이터와 다음 노드를 가리키는 노드 변수만을 갖고 있었다면 `이중 연결리스트는 하나 더 추가되어**'이전 노드'를 가리키는 변수가 추가`** 된다.

> Doubly LinkedList 메소드
 
- addAtHead : 리스트 맨 앞에 노드 추가
- get : 값 반환
- addAtTail : 리스트 맨 마지막에  노드 추가
- addAtIndex : 특정 인덱스에 node 추가
- deleteAtIndex : 특정 인덱스의 node 삭제

### 원형 연결리스트 Circular LinkedList

- 원형 링크드 리스트는 끝이 없고 리스트가 원형으로 순환하는 것을 말합니다. 끝이 없고 계속 순환하기 때문에 잘못하면 무한히 순환할 수 있습니다. (라운드 로빈 알고리즘과 같이 경우에 따라 유용하게 사용)
- 단순 연결 리스트에서 마지막 노드가 리스트의 첫 번째 노드를 가리키게 하여 리스트의 구조를 원형으로 만든 리스트

### Stack

- 후입선출 구조 (Last-In-First-Out : LIFO)
- 먼저 삽입한 값이 밑으로 계속 쌓이는 형식
- 시스템 해킹에서 버퍼오버플로우 취약점을 이용한 공격을 할 때 스택 메모리의 영역에서 함
- 재귀적(Recursion) 함수를 호출 할 때 사용

```java
// <선언 방법>
Stack<Integer> strck = new Stack<>();
```

> stack 메소드

- push : 값 추가
- pop : 값 제거
- peek : 제일 상단의 값 출력

### Queue

- 선입선출 구조 (First-In-Frist-Out : FIFO)
- 그대로 먼저 들어온 데이터가 가장 먼저 나가는 구조를 말합니다.
- 큐는 한 쪽 끝은 프런트(front)로 정하여 삭제 연산만 수행함
- 다른 한 쪽 끝은 리어(rear)로 정하여 삽입 연산만 수행함
- **Enqueue :** 큐 맨 뒤에 데이터 추가
- **Dequeue :** 큐 맨 앞쪽의 데이터 삭제

```java
// <선언 방법>
Queue<Integer> queue = new LinkedList<>();

// 자바에서 Queue 는 LinkedList를 활용해서 생성해야 한다.
// 그렇기에 Queue 와 LinkedList가 다 import 되어 있어야
// 사용 가능
```

> Queue 메소드
> 
- offer : 값 추가
- poll : 값 삭제 Queue 가 비어있으면 null 을 반환
