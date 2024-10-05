---
layout: single
title: "8. 해시"
---

[코딩 테스트 합격자 되기 - 파이썬편]를 참고하여 작성하였습니다.

## __해시__
###  1. 해시의 개념
  - 키에 해시 함수를 적용한 출력을 인덱스로 삼아 값을 저장하는 자료구조.
  - 키-값 일대일 대응으로 저장하므로 키를 통해 원하는 값에 바로 접근할 수 있음.
  - 아래 예시 그림에서 키 (key)는 사람의 이름이고 즉, 검색을 위한 정보이고 값 (value)는 찾고자 하는 정보인 전화번호임.
  - 키에 대응되는 값이 저장되어 있는 공간을 해시 테이블 (hash table)이라고 부르고, 해시 테이블의 각 데이터는 버킷 (bucket)이라고 부름. 
  
![해시 그림](https://github.com/user-attachments/assets/a38b990e-e69d-47f7-b4c4-fe92bc5d9d73)

  - 해시 특징:
    - 해시 함수 출력이 인덱스가 되기 때문에 값을 찾기 위한 탐색 과정이 필요 없음.
    - 찾고자 하는 값을 평균 시간복잡도 O(1)에서 찾을 수 있음.
    - 해시를 사용하지 않는다면, 모든 인덱스를 탐색하며 키의 위치를 찾아야 함.
      
  - 해시를 활용하는 분야:
    - 비밀번호 관리: 비밀번호를 그대로 노출해 저장하는 것은 위험하므로 해시 함수를 통해 해싱한 비밀번호를 저장함.
    - 데이터베이스 인덱싱: 저장된 데이터를 효율적으로 검색할 때 해시를 활용함.
    - 블록체인: 각 블록은 이전 블록의 해시값을 포함하고 있으며, 이를 통해 데이터 무결성을 확인함.
      
###  2. 해시 함수
  - 고려사항: 
    - 해시 함수가 반환하는 인덱스가 해시 테이블 크기를 넘으면 안됨.
    - 해시 함수의 변환된 출력에서 충돌이 최대한 적게 발생해야 함. 여기서 충돌이란 서로 다른 두 키에 대해 해시 함수의 출력이 같은 경우임.
      
  - 해시함수 종류: 
    - 나눗셈법 (division method)
      - $h(x) = x \,\text{mod} \, m$
### 큐의 특성을 활용하는 분야
  - 작업대기열: 네트워크 통신을 할 때 다수의 클라이언트에서 서버에 작업을 요청하면 서버는 요청 순서대로 작업을 수행하도록 함.
  - 이벤트 처리: 애플리케이션이나 시스템에서 사용자의 이벤트 (e.g., 키보드 입력, 마우스 처리)를 처리할 때 활용할 수 있음.

###  큐의 ADT 
####  연산
  - void push (itemType item): 큐에 데이터를 푸쉬함.
  - ItemType pop (): 큐에 마지막에 푸시한 데이터를 팝하고, 그 데이터를 반환함.
  - boolean isFull(): 큐에 들어 있는 데이터 개수가 maxsize인지 확인해 boolean 값을 반환함. 가득차면 True, 아니면 False를 반환함.
  - boolean isEmpty(): 큐에 들어 있는 데이터가 하나도 없는지 확인해 boolean값을 반환함. 하나라도 있으면 False, 없으면 True를 반환함.
####  상태
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
