---
layout: single
title: "6. 스택"
---

[코딩 테스트 합격자 되기 - 파이썬편]를 참고하여 작성하였습니다.

## __스택 개념__
###  1. 스택이란?
  - 선입후출 (First In Last Out, FILO) 규칙을 갖는 자료구조.  
###  2. 연산
  - 푸쉬 (push): 스택에 데이터를 삽입 시 사용함.
  - 팝 (pop): 스택에서 데이터를 꺼낼 때 사용함.

## __추상 자료형 (Abstract data type, ADT)__
  - 인터페이스만 존재하고 실제로 구현은 되지 않은 자료형임.
  - 일종의 자료형의 설계도라고 볼 수 있음.
     
###  - 스택의 ADT 
####  - 연산
  - void push (itemType item): 스택에 데이터를 푸쉬함.
  - ItemType pop (): 스택에 최근에 푸시한 데이터를 팝하고, 그 데이터를 반환함.
  - boolean isFull(): 스택에 들어 있는 데이터 개수가 maxsize인지 확인해 boolean 값을 반환함. 가득차면 True, 아니면 False를 반환함.
  - boolean isEmpty(): 스택에 들어 있는 데이터가 하나도 없는지 확인해 boolean값을 반환함. 하나라도 있으면 False, 없으면 True를 반환함.
####  - 상태
  - Int top: 스택에서 최근에 푸시한 데이터의 위치를 기록함.
  - ItemType data[maxsize]: 스택의 데이터를 관리하는 배열임. 최대 maxsize개의 데이터를 관리함.
    

