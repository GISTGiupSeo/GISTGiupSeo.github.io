---
layout: single
title: "7. 큐"
---

[코딩 테스트 합격자 되기 - 파이썬편]를 참고하여 작성하였습니다.

## __큐 개념__
###  1. 큐란?
  - 선입선출 (First In First Out, FIFO) 규칙을 갖는 자료구조.  
###  2. 연산
  - 푸쉬 (push): 스택에 데이터를 삽입 시 사용함.
  - 팝 (pop): 스택에서 데이터를 꺼낼 때 사용함.

### 큐의 특성을 활용하는 분야
  - 작업대기열: 네트워크 통신을 할 때 다수의 클라이언트에서 서버에 작업을 요청하면 서버는 요청 순서대로 작업을 수행하도록 함.
  - 이벤트 처리: 애플리케이션이나 시스템에서 사용자의 이벤트 (e.g., 키보드 입력, 마우스 처리)를 처리할 때 활용할 수 있음.

###  큐의 ADT 
####  연산
  - void push (itemType item): 큐에 데이터를 푸쉬함.
  - ItemType pop (): 큐에 마지막에 푸시한 데이터를 팝하고, 그 데이터를 반환함.
  - boolean isFull(): 큐에 들어 있는 데이터 개수가 maxsize인지 확인해 boolean 값을 반환함. 가득차면 True, 아니면 False를 반환함.
  - boolean isEmpty(): 큐에 들어 있는 데이터가 하나도 없는지 확인해 boolean값을 반환함. 하나라도 있으면 False, 없으면 True를 반환함.
####  - 상태
  - Int front: 큐에서 가장 마지막에 팝한 위치를 기록함.
  - Int rear: 큐에서 최근에 푸시한 데이터의 위치를 기록함.
  - ItemType data[maxsize]: 큐의 데이터를 관리하는 배열임. 최대 maxsize개의 데이터를 관리함.
    

 ```python
queue = []

# 큐에 데이터 추가
queue.append(1)
queue.append(2)
queue.append(3)

# 큐의 맨 앞 데이터 제거
first_item = queue.pop(0)
print(first_item) # 1 출력

# 쿠에 데이터 추가
queue.append(4)
queue.append(5)


# 큐의 맨 앞 데이터 제거
first_item = queue.pop(0)
print(first_item)  # 2 출력

```


 ```python
from collections import deque

queue = deque()

# 큐에 데이터 추가
queue.append(1)
queue.append(2)
queue.append(3)

# 큐의 맨 앞 데이터 제거
first_item = queue.popleft()
print(first_item) # 1 출력

# 쿠에 데이터 추가
queue.append(4)
queue.append(5)


# 큐의 맨 앞 데이터 제거
first_item = queue.popleft()
print(first_item)  # 2 출력

```

####  - Double Ended Queue (DEQ) 활용 장점
  - list의 pop(0)과 deq의 popleft()를 비교해보면 10만번 결과 기준으로 약 pop(0)는 0.79초 deq는 0.007초로 매우 크게 차이남
