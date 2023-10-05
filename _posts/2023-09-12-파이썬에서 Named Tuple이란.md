---
title: 파이썬에서 Named Tuple이란
date: 2023-09-12 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬튜플
---

## Named Tuple의 기본 개념

Named Tuple은 파이썬의 표준 라이브러리인 `collections` 모듈에서 제공하는 데이터 구조입니다. 기본적으로, Named Tuple은 일반적인 튜플과 비슷하지만, 각각의 원소에 이름을 붙일 수 있다는 점이 특징입니다. 이렇게 하면 코드를 더 읽기 쉽고 관리하기 쉬워집니다.

## 왜 Named Tuple을 사용하는가?

1. **가독성 향상**: 각 원소에 이름이 있기 때문에, 코드를 읽을 때 이해하기 쉽습니다.
2. **에러 최소화**: 원소의 위치를 기억할 필요가 없어, 인덱스 실수를 줄일 수 있습니다.
3. **데이터 불변성**: Named Tuple은 불변(immutable)이므로, 한번 생성한 후에는 수정할 수 없습니다.

## Named Tuple의 생성 방법

Named Tuple은 `collections` 모듈의 `namedtuple` 함수를 사용하여 생성합니다. 함수의 첫 번째 인자는 Named Tuple의 이름이고, 두 번째 인자는 필드 이름들입니다.

```python
from collections import namedtuple

Person = namedtuple('Person', ['name', 'age'])
p = Person(name="John", age=25)
```

## 예제 코드와 주요 메서드

Named Tuple을 활용한 간단한 예제 코드입니다.

```python
p = Person(name="John", age=25)
print(p.name)  # 출력: John
print(p.age)   # 출력: 25
```

주요 메서드:

- `._fields`: 모든 필드 이름을 반환합니다.
- `._asdict()`: Named Tuple을 `OrderedDict` 형태로 반환합니다.

## 주의사항과 제한사항

- Named Tuple은 불변이기 때문에, 생성 후에는 원소를 수정할 수 없습니다.
- `namedtuple` 함수는 런타임에 새로운 클래스를 생성하므로, 메모리와 CPU에 약간의 부담을 줄 수 있습니다.

## 에러와 문제해결

만약 필드 이름이 파이썬의 키워드와 겹친다면, `SyntaxError`가 발생할 수 있습니다. 이 경우 필드 이름을 변경해야 합니다.

Named Tuple은 데이터를 효율적으로 관리할 수 있게 도와주는 유용한 도구입니다. 이를 활용하여 코드의 품질을 높이세요.