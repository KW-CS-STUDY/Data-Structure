# 자료구조 종류

생성일: 2022년 8월 7일 오후 5:27

# 목차

1. 자료 구조 정의(#자료-구조-정의)
2. 자료 구조 종류
    1. Array(배열)
    2. List(리스트)
    3. Stack(스택)
    4. Queue(큐)
    5. Double-Ended queue, Deque(덱)
    6. Graph(그래프)
    7. Tree(트리)
    8. Heap(힙)

# 1. 자료 구조 정의

자료 구조란 데이터의 편리한 접근과 조작을 가능하게 하는 데이터를 저장하거나 조작하는 방법이다. 문맥과 데이터의 종류에 따라 적절한 자료 구조를 사용하는 것은 전체 개발 시스템에 큰 영향을 끼친다. 그렇기 때문에 자료 구조의 다양한 종류와 각각의 장점과 한계를 잘 이해하고 상황에 맞게 올바른 자료 구조를 선택하고 사용하는 것이 중요하다.

# 2. 자료 구조 종류

## Array(배열)

- 내용
    - 동일한 크기의 메모리 공간이 빈틈없이 연속적으로 나열된 자료구조
    - 배열의 요소는 동일한 크기를 갖으며, 빈틈없이 연속적으로 이어져 있음
    - 따라서 아래와 같이 인덱스를 통해 단 한번의 연산으로 임의의 요소에 접근 가능, 시간복잡도
    Random access, O(1)
        
        ```jsx
        검색 대상 요소의 메모리 주소 = 배열의 시작 메모리 주소 + 인덱스 * 요소의 바이트 수
        ```
        
    - 배열은 인덱스를 통해 효율적으로 요소에 접근할 수 있다는 장점
    - 크기가 정해져 있으며, 기능이 없음 또한, cache hit의 가능성이 커져서 성능에 큰 도움
    - 하지만 정렬되지 않은 배열에서 특정 값을 탐색하는 경우, 모든 배열요소를 탐색 → O(n)
    - 배열에 요소를 삽입하거나 삭제하는 경우, 배열 요소를 연속적으로 유지하기 위해 요소를 이동시켜야 하는 단점
    - 또한 배열의 길이를 바꿀수 없다는 단점을 가진다

## List(리스트)

- 내용
    - 리스트는 배열이 갖고 있는 인덱스라는 장점을 버리고, 대신 빈틈없는 데이터의 적재라는 장점을 취한 자료구조
    - 배열(Array)에서 인덱스는 값에 대한 유일무이한 식별자인데 반해, 리스트에서 인덱스는 몇 번째 데이터 정도의 의미
    - 요소들간의 순서가 리스트의 핵심이다. 따라서 Sequence 라고도 부르며, 순서가 있는 데이터의 모임이라고 할 수 있다.
    - 순차성을 보장하지 못하기 때문에 spatial locality 보장이 되지 않아 cash hit가 어려움.
    - 언어별 list 지원
        - C: X
        - JavaScript: 배열에 리스트 기능 포함
        - Python: 기본 리스트, 배열 지원 X
        - Java: 배열과 리스트 모두 지원, ArrayList, LinkedList로 나뉨
    - ArrayList와 LinkedList는 구현 방법에 따라 나뉨.
        - ArrayList
            - 배열을 이용해 리스트를 구현
            - 접근이 빠름(순차 X), 하지만 데이터 추가와 삭제가 느림
            - 동적으로 사용하기 힘들다(Java의 경우 자동으로 사이즈를 키워서 관리-Dynamic Array)
        - LinkedList
            - 연결로 구현한 리스트
            - 한 원소에서 값과 다음 원소의 주소를 알고 연결하는 방식
            - 순차적으로 접근
            - 삽입, 삭제는 O(1), 하지만 해당 지점까지 접근해야하므로 O(n)
            - 배열과 다르게 논리적 저장 순서와 물리적 저장 순서가 일치하지 않는다.

## Stack(스택)

- 내용
    - LIFO(Last In First Out)
    - 나중에 들어간 요소가 먼저 나옴, 한 쪽 끝에서만 자료를 넣고 뺄 수 있음
    - push: 데이터를 top 위치에 넣기
    - pop: 가장 최근에 push한 데이터가 나옴
    - 삽입, 삭제의 시간 복잡도: O(1) → 장점
    - 사용사례
        - 재귀 알고리즘(재귀적으로 함수 호출 경우, 임시 데이터를 스택에 넣음)
        - 웹 브라우저 방문기록
        - 실행 취소
        - 역순 문자열 만들기

## Queue(큐)

- 내용
    - FIFO(First In First Out)
    - 먼저 들어간 원소가 먼저 나온다. 넣는 방향과 나오는 방향 다름
    - front: 데이터가 삽입(push)되는 곳
    - back: 제거(pop)되는 곳
    - 삽입, 삭제의 시간 복잡도: O(1) → 장점
    - 사용사례:
        - 너비 우선 탐색(BFS)구현
        - 캐시(Cache) 구현
        - 프로세스 관리
        - 윈도 시스템의 메시지 처리기

## Double-Ended queue, Deque(덱)

- 내용
    - 양쪽 끝에서 입출력이 가능한 자료구조
    - 크기가 가변적
    - 삽입, 삭제의 시간 복잡도: O(1)

## Graph(그래프)

- 내용
    - 단순히 노드와 그 노드를 연결하는 간선을 하나로 모아놓은 자료 구조
    - 관련 용어
        - 정점(vertex): 위치라는 개념, 노드라고도 부름
        - 간선(edge): 위치 간의 관계, 노드를 연결하는 선(link, branch 라고도 부름)
        - 인점 정점(adjacent vertex): 간선에 의해 직접 연결된 정점
        - 정점의 차수(degree): 무방향 그래프에서 하나의 정점에 인접한 정점의 수
            - 무방향 그래프에 존재하는 정점의 모든 차수 합 = 그래프 간선 수의 2배
        - 진입 차수(in-degree): 방향 그래프에서 외부에서 오는 간선의 수(내차수 라고도 부름)
        - 진출 차수(out-degree): 방향 그래프에서 외부로 향하는 간선의 수(외차수 라고도 부름)
            - 방향 그래프에 있는 정점의 진입 차수 또는 진출 차수의 합 = 방향 그래프의 간선 수
        - 경로 길이(path length): 경로를 구성하는데 사용된 간선의 수
        - 단순 경로(simple length): 경로 중에서 반복되는 정점이 없는 경우
        - 사이클(cycle): 단순 경로의 시작 정점과 종료 정점이 동일한 경우
    - 특징
        - 그래프는 네트워크 모델
        - 루트 노드, 부모-자식 개념이 없음
        - 순회는 DFS, BFS로 이루어짐
        - 순환(Cyclic) 혹은 비순환(Acyclic)이다.
        - 방향 그래프(A, B)와 무방향 그래프<A, B>, <B, A>로 구성
        - 완전 그래프(Complete Graph), 모든 정점이 서로 연결되어 있는 그래프
    - 2가지 구현
        - 인접 리스트(Adjacency List)
            - 모든 정점을 인접 리스트에 저장, 즉 각각의 정점에 인접한 정점들을 리스트로 표현
            - 배열(혹은 해시테이블)과 배열의 각 인덱스마다 존재하는 또 다른 리스트(배열, ArrayList, LinkedList)등 을 이용해서 표현
            - 정점의 번호만 알면 배열의 인덱스로 하여 각 정점의 리스트에 쉽게 접근 가능
            
            ```jsx
            0: 1
            1: 2
            2: 0, 3
            3: 2
            4: 6
            5: 4
            6: 5
            https://gmlwjd9405.github.io/2018/08/13/data-structure-graph.html
            ```
            
        - 인접 행렬(Adjacency Matrix)
            - NxN Boolean Maxtix로써 matrix[i][j]가 True라면 i → j로의 간선이 있다는 뜻
            - 정점 의 개수가 N인 그래프를 인접행렬로 표현
            - 간선의 수와 무관하게 항상 n^2개의 메모리 공간이 필요
            - 무방향그래프는 대칭행렬이 된다.
            - 인접행렬에 비해 효율성이 조금 떨어짐
    
    ---
    
    **2주차**
    
    - 인접 리스트와 인접 행렬 중 선택 방법
        - 인접 리스트
            - 그래프 내에 적은 숫자의 간선만을 가지는 희소 그래프(Sparse Graph)의 경우
            - 장점
                - 어떤 노드에 인접한 노드 쉽게 찾을 수 있음
                - 그래프에 존재하는 모든 간선의 수는 O(N+E) 안에 알 수 있다.
            - 단점
                - 간선의 존재 여부와 정점의 차수: 정점 i의 리스트에 있는 노드의 수 즉, 정점 차수 만큼의 시간 소요
        - 인접 행렬
            - 그래프에 간선이 많이 존재하는 밀집 그래프(Dense Graph)의 경우
            - 장점
                - 두 정점을 연결하는 간선의 존재 여부 (M[i][j])를 O(1) 안에 즉시 알 수 있다.
                - 정점의 차수는 O(N) 안에 알 수 있다. 인접 배열의 i 번쨰 행 또는 열을 모두 더한다.
            - 단점
                - 어떤 노드에 인접한 노드들을 찾기 위해서는 모든 노드를 전부 순회해야한다.
                - 그래프에 존재하는 모든 간선의 수는 O(N^2) 안에 알 수 있다, 행렬 전체 조사해야함
    - 그래프의 탐색
        1. 깊이 우선 탐색 (DFS, Depth-First Search)
            
            루트 노드(혹은 다른 임의의 노드)에서 시작해서 다음 분기(branch)로 넘어가기 전에 해당 분기를 완벽하게 탐색하는 방법
            
            - 넓게 탐색하기 전에, 깊게 탐색하는 방법
            - 모든 노드를 방문하고자 하는 경우에 해당 방법을 선택한다.
        2. 너비 우선 탐색 (BFS, Breadth-First Search)
            
            루트 노드(혹은 다른 임의의 노드)에서 시작해서 인접한 노드를 먼저 탐색하는 방법
            
            - 깊게 탐색하기 전에, 넓게 탐색하는 방법
            - 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때 사용

## Tree(트리)

- 내용
    - 트리는 하나의 루트 노드를 가짐, 루트 노드는 0개 이상의 자식 노드를 갖고 있고, 
    그 자식 노드 또한 0개 이상의 자식 노드를 가지며, 이는 반복적으로 정의
    - 노드(node)들과 이를 연결하는 간선(edge)들로 구성되어 있다.
        - 트리에는 cycle이 존재 할 수 없다.
    - 비선형 자료구조로 계층적 관계를 표현한다.
    - 관련 용어
        - 루트 노드(root node): 부모가 없는 노드, 트리는 하나의 루트노드만을 가짐
        - 단말 노드(leaf node): 자식이 없는 노드
        - 내부(internal): 단말 노드가 아닌 노드
        - 간선(edge): 노드를 연결하는 선
        - 형제(sibling): 같은 부모를 가지는 노드
        - 노드의 크기(size): 자신을 포함한 모든 자손 노드의 개수
        - 노드의 깊이(depth): 루트에서 어떤 노드에 도달하기 위해 거쳐야 하는 간선의 수
        - 노드의 레벨(level): 트리의 특정 깊이를 가지는 노드의 집합
        - 노드의 차수(degree): 하위 트리의 개수 / 간선 수 (degree) = 각 노드가 지닌 가지의 수
        - 트리의 차수(degree of tree): 트리의 최대 차수
        - 트리의 높이(height): 루트 노드에서 가장 깊숙히 있는 노드의 깊이
    - 특징
        - 그래프의 한 종류
        - 계층 모델
        - DAG(Directed Acyclic Graphs, 방향성이 있는 비순환 그래프)의 한 종류
            - loop나 circuit이 없음, 사이클 없음
        - 노드가 N개인 트리는 항상 N-1개의 간선을 가짐, 간선은 항상 정점 개수-1 만큼 가짐
        - 루트에서 어떤 노드로 가는 경로는 유일
        - 하나의 루트 노드만 존재, 자식 노드는 한개의 부모 노드만을 가짐
        - 이진 트리, 이진 탐색 트리, 균형 트리(AVL 트리, red-black 트리) 이진 힙 등이 있음

- **트리의 종류**
    - 이진 트리
        - **이진 트리(Binary Tree)**
            - 각 노드가 최대 두개의 자식을 갖는 트리
            - 모든 트리가 이진 트리는 아님
            - 순회는 Pre-order, In-order, Post-order로 이루어짐
                - 전위 순회(Pre-Order Traversal): 현재 노드 → 왼쪽 가지 → 오른쪽 가지
                
                ```jsx
                void preOrderTraversal(TreeNode node) {
                  if(node != null) {
                   visit(node);
                   preOrderTraversal(node.left);
                   preOrderTraversal(node.right);
                  }
                }
                https://gmlwjd9405.github.io/2018/08/12/data-structure-tree.html
                ```
                
                - 중위 순회(In-Order Traversal): 왼쪽 가지 → 현재 노드 → 오른쪽 가지
                
                ```jsx
                void inOrderTraversal(TreeNode node) {
                  if(node != null) {
                   inOrderTraversal(node.left);
                   visit(node);
                   inOrderTraversal(node.right);
                  }
                }
                https://gmlwjd9405.github.io/2018/08/12/data-structure-tree.html
                ```
                
                - 후위 순회(Post-Order Traversal): 왼쪽 가지 → 오른쪽 가지 → 현재노드
                
                ```jsx
                void postOrderTraversal(TreeNode node) {
                  if(node != null) {
                   postOrderTraversal(node.left);
                   postOrderTraversal(node.right);
                   visit(node);
                  }
                }
                https://gmlwjd9405.github.io/2018/08/12/data-structure-tree.html
                ```
                
            - **이진 탐색 트리(Binary Search Tree)**
                - 모든 노드가 ‘모든 왼쪽 자식들 ≤ n < 모든 오른쪽 자식들’이라는 특정 순서를 따르는 속성이 있는 이진 트리
                - 각 노드에 중복되지 않는 키(key)가 있다.
                - 좌우 서브 트리도 모두 이진 탐색 트리여야 한다.
                    
                    [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbirxyY%2Fbtq90mluHfW%2FBll0dguHQZTWOq37khBkRk%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbirxyY%2Fbtq90mluHfW%2FBll0dguHQZTWOq37khBkRk%2Fimg.png)
                    
                - 이진 탐색 트리 **탐색**
                    1. 루트 노드의 키와 찾고자 하는 값을 비교한다. 찾고자 하는 값이라면 탐색 종료
                    2. 찾고자 하는 값이 루트 노드의 키보다 작다면 왼쪽 서브 트리로 탐색 진행
                    3. 찾고자 하는 값이 루트 노드의 키보다 크다면 오른쪽 서브 트리로 탐색 진행
                    - 위 과정을 찾고자 하는 값을 찾을 때까지 반복해서 진행. 만약 찾지 못한다면 그대로 종료
                    - 위와 같은 과정을 거치면 최대 트리의 높이(h)만큼의 탐색이 진행되게 된다.
                    
                    [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpEBxn%2Fbtq9ReoXZUX%2F7zobmK5yQPPupKqGRgdHcK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpEBxn%2Fbtq9ReoXZUX%2F7zobmK5yQPPupKqGRgdHcK%2Fimg.png)
                    
                - 이진 탐색 트리 **삽입**
                    1. 삽입할 값을 루트 노드와 비교해 같다면 오류를 발생(중복값 허용 X)
                    2. 삽입할 값이 루트 노드의 키보다 작다면 왼쪽 서브 트리를 탐색해서 비어있다면 추가하고, 비어 있지 않다면 다시 값을 비교.
                    3. 삽입할 값이 루트 노드의 키보다 크다면 오른쪽 서브 트리를 탐색해서 비어있다면 추가하고, 비어있지 않다면 다시 값을 비교.
                    
                    [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FczCET0%2Fbtq9Ov57XGz%2F7HO8dK5PcnF24WwHYwjOOK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FczCET0%2Fbtq9Ov57XGz%2F7HO8dK5PcnF24WwHYwjOOK%2Fimg.png)
                    
                    [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdpBA2w%2Fbtq9RdRgKoI%2Flf9C3qqbPZtLCFYNSnJGXk%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdpBA2w%2Fbtq9RdRgKoI%2Flf9C3qqbPZtLCFYNSnJGXk%2Fimg.png)
                    
                - 이진 탐색 트리의 **삭제**
                    - 이진 탐색 트리에서 특정 노드를 삭제할 때 아래와 같은 3가지 상황을 나누어 구현해야함
                        1. 삭제하려는 노드가 단말 노드(leaf node)일 경우
                            - 삭제할 노드의 부모 노드가 있다면 부모 노드의 자식 노드를 NULL로 만들고, 삭제할 노드를 삭제(메모리 해제) 해주면 된다.
                        2. 삭제하려는 노드의 서브 트리가 하나인 경우(왼쪽 혹은 오른쪽 서브트리)
                            - 삭제할 노드의 자식 노드를 삭제할 노드의 부모 노드가 가리키게 하고 해당 노드를 삭제 하면 된다.
                        3. 삭제하려는 노드의 서브 트리가 두 개인 경우
                            - 가장 복잡한 경우, 두 가지 방법을 사용할 수 있다.
                            1. 삭제할 노드 왼쪽 서브트리의 가장 큰 자손을 해당 노드의 자리에 올린다.
                            
                                
                                [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbcTUrX%2Fbtq92Q1tw0m%2FtyYJcuLUtWj7kD5k3qAeMK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbcTUrX%2Fbtq92Q1tw0m%2FtyYJcuLUtWj7kD5k3qAeMK%2Fimg.png)
                                
                                위와 같이 삭제할 노드의 왼쪽 서브트리에서 가장 큰 자손을 해당 노드의 자리에 올리면, 이진 탐색 트리의 조건을 만족하면서 트리가 유지되는 것을 확인할 수 있다. 또한 자리를 옮기면서 다른 노드들(4번 노드)도 자리가 적절히 이동한 것을 확인할 수 있다.
                                
                            2. 삭제할 노드 오른쪽 서브트리의 가장 작은 자손을 해당 노드의 자리에 올린다.
                                
                                [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbI3IEY%2Fbtq9Rc54r92%2FnDvEWCXdq9qVmYaYiHKAAK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbI3IEY%2Fbtq9Rc54r92%2FnDvEWCXdq9qVmYaYiHKAAK%2Fimg.png)
                                
                                위와 같이 삭제할 노드의 오른쪽 서브트리에서 가장 작은 자손을 해당 노드의 자리에 올리면, 이진 탐색 트리의 조건을 만족하면서 트리가 유지되는 것을 확인할 수 있다. 또한 자리를 옮기면서 다른 노드들도 자리가 적절히 이동한 것을 확인할 수 있다.
                                
    - **균형 트리**
        - O(logN) 시간에 insert와 find를 할 수 있을 정도로 균형이 잘 잡혀 있는 경우
        - Ex) 레드-블랙 트리, AVL 트리
        - **AVL Tree (높이 균형 이진 탐색 트리)**
            - 개요 : 스스로 균형을 잡는 이진 탐색 트리
            트리의 높이가 h일 때, 이진 탐색트리의 최악 시간 복잡도는 $O(h)$이다. 한쪽으로 치우친 편향 이진트리가 되면 트리의 높이가 높아지기 때문에 이를 방지하기 위함.
            - AVL 트리는 이진 탐색 트리의 속성을 가진다.
            - 왼쪽, 오른쪽 서브 트리의 높이 차이가 최대 1이다.
            - 어떤 시점에서 높이 차이가 1보다 커지면, 회전을 통해 균형을 잡아 높이 차이를 줄인다.
            - AVL 트리는 높이를 logN으로 유지하기 때문에 삽입, 탐색, 삭제의 시간 복잡도는 $O(logN)$이다.
            - **Balance Factor(BF)**
                - 왼쪽 서브트리의 높이에서 오른쪽 서브트리의 높이를 뺀 값
                
                ```python
                Balance Factor (k) = height (left(k)) - height(right(k))
                ```
                
                - BF가 1이면 왼쪽 서브트리가 오른쪽 서브트리보다 높이가 한단계 높다는 것을 의미
                - BF가 0이면 왼쪽 서브트리와 오른쪽 서브트리의 높이가 같다는 것을 의미
                - BF가 -1이면 왼쪽 서브트리가 오른쪽 서브트리보다 높이가 한단계 낮다는 것을 의미
                    
                    [https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FblxsRD%2Fbtq21CW9Fw3%2FWOk8F74J254K1pczckskEK%2Fimg.png](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FblxsRD%2Fbtq21CW9Fw3%2FWOk8F74J254K1pczckskEK%2Fimg.png)
                    
                - **회전**
                    - AVL 트리는 이진 탐색 트리이기 때문에 모든 작업은 이진 탐색 트리에서 사용하는 방식으로 수행.
                    - 검색 및 순회 연산은 BF를 변경하지 않지만, 삽입 및 삭제에서는 변경될 수 있음.
                    - 삽입, 삭제 시 불균형 상태(BF가 -1, 0, 1이 아닌 경우) 가 되면 AVL 트리는 불균형 노드를 기준으로 서브트리의 위치를 변경하는 rotation(회전) 작업을 수행하여 트리의 균형을 맞추게 됨
                    - 삽입, 삭제시 노드들의 배열에 따라 4가지(LL, RR, LR, RL) 불균형이 발생할 수 있으며, 각 상황마다 rotation에 방향을 달리하여 트리의 균형을 맞춘다.
                
    - **완전 이진 트리(Complete Binary Tree)**
        - 트리의 모든 높이에서 노드가 꽉 차 있는 이진 트리. 즉, 마지막 레벨을 제외하고 모든 레벨이 완전히 채워져 있음
        - 마지막 레벨은 꽉 차 있지 않아도 되지만, 노드가 왼쪽에서 오른쪽으로 채워져야함.
        - 마지막 레벨 h에서 (1~2h-1)개의 노드를 가질 수 있다.
        - 완전 이진 트리는 배열을 사용해 효율적으로 표현 가능하다.
    - **전 이진 트리(Full Binary Tree 또는 Strictly Binary Tree)**
        - 모든 노드가 0개 또는 2개의 자식 노드를 갖는 트리
    - **포화 이진 트리(Perfect Binary Tree)**
        - 전 이진 트리이면서 완전 이진 트리인 경우
        - 모든 말단 노드는 같은 높이에 있어야 하며, 마지막 단계에서 노드의 개수가 최대가 되어야 한다.
        - 모든 내부 노드가 두개의 자식 노드를 가진다.
        - 모든 말단 노드가 동일한 깊이 또는 레벨을 갖는다.
        - 노드의 개수가 정확히 $2^{k-1}$개여야 한다.($k$: 트리의 높이) → 흔하게 나타는 경우가 아님. 즉, 이진 트리가 모두 포화 이진트리라고 생각하면 안됨
    

## Heap(힙)

- 완전 이진 트리의 일종으로 우선순위 큐를 위하여 만들어진 자료구조
- 여러 개의 값들 중에서 최댓값이나 최솟값을 빠르게 찾아내도록 만들어진 자료구조
- 힙은 일종의 반정렬 상태(느슨한 정렬 상태)를 유지한다.
    - 큰 값이 상위 레벨에 있고, 작은 값이 하위 레벨에 있다는 정도
    - 간단히 말하면 부모 노드의 키 값이 자식 노드의 키 값보다 항상 큰(작은) 이진 트리를 말함
- 힙 트리에서는 중복된 값을 허용한다. (이진 탐색 트리에서는 중복된 값을 허용하지 않는다.)
- **힙의 종류**
    - 최대 힙(Max heap)
        - 부모 노드의 키 값이 자식 노드의 키 값보다 크거나 같은 완전 이진 트리
        - key(부모 노드) ≥ key(자식 노드)
    - 최소 힙(Min heap)
        - 부모 노드의 키 값이 자식 노드의 키 값보다 작거나 같은 완전 이진 트리
        - key(부모 노드) ≤ key(자식 노드)
        
        ![https://gmlwjd9405.github.io/images/data-structure-heap/types-of-heap.png](https://gmlwjd9405.github.io/images/data-structure-heap/types-of-heap.png)
        
- **힙의 구현**
    - 힙을 저장하는 표준적인 자료구조는 배열
    - 구현을 쉽게 하기 위하여 배열의 첫번째 인덱스인 0은 사용안함
    - 특정 위치의 노드 번호는 새로운 노드가 추가 되어도 변하지 않는다.
        - 예를 들어 루트 노드의 오른쪽 노드의 번호는 항상 3이다.
    - 힙에서의 부모 노드와 자식 노드의 관계
        - 왼쪽 자식의 인덱스 = (부모의 인덱스) * 2
        - 오른쪽 자식의 인덱스 = (부모의 인덱스) * 2 + 1
        - 부모의 인덱스 = (자식의 인덱스) / 2
        
        ![https://gmlwjd9405.github.io/images/data-structure-heap/heap-index-parent-child.png](https://gmlwjd9405.github.io/images/data-structure-heap/heap-index-parent-child.png)
        

---

- **힙의 삽입**
    1. 힙에 새로운 요소가 들어오면, 일단 새로운 노드를 힙의 마지막 노드에 이어서 삽입한다.
    2. 새로운 노드를 부모 노드들과 교환해서 힙의 성질을 만족시킨다.
    
    ![https://gmlwjd9405.github.io/images/data-structure-heap/maxheap-insertion.png](https://gmlwjd9405.github.io/images/data-structure-heap/maxheap-insertion.png)
    
- **힙의 삭제**
    1. 최대 힙에서 최댓값은 루트 노드이므로 루트 노드가 삭제된다.
        - 최대 힙에서 삭제 연산은 최댓값을 가진 요소를 삭제하는 것이다.
    2. 삭제된 루트 노드에는 힙의 마지막 노드를 가져온다.
    3. 힙을 재구성한다.
    
    ![https://gmlwjd9405.github.io/images/data-structure-heap/maxheap-delete.png](https://gmlwjd9405.github.io/images/data-structure-heap/maxheap-delete.png)