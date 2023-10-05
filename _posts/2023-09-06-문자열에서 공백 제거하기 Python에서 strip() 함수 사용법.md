---
title: 문자열에서 공백 제거하기 Python에서 strip() 함수 사용법
date: 2023-09-06 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬strip
---

## 개요
Python에서 문자열(string) 처리를 할 때 종종 문자열 앞뒤에 있는 불필요한 공백을 제거해야 하는 상황이 발생합니다. 이렇게 앞뒤 공백을 제거하는 것을 '문자열 공백 제거'라고 부릅니다. 이 작업은 `strip()` 함수를 사용하여 쉽게 할 수 있습니다. 본 글에서는 이 함수의 사용법을 자세히 알아봅니다.

## `strip()` 함수란?
`strip()` 함수는 문자열 앞뒤에 있는 공백을 제거해주는 Python 내장 함수입니다. 기본적으로 이 함수는 문자열의 앞과 뒤에 있는 모든 공백을 제거합니다. 공백이라 함은 스페이스뿐만 아니라 탭(`\t`), 줄바꿈(`\n`) 등도 포함됩니다.

```python
original_string = "   Hello, World!   "
trimmed_string = original_string.strip()
print(trimmed_string)  # Output: "Hello, World!"
```

## 다양한 사용법
### 사용자 지정 문자 제거
`strip()` 함수는 인자를 받아 해당 인자로 주어진 문자를 앞뒤에서 제거할 수 있습니다. 예를 들어, 문자열 앞뒤의 특정 문자를 제거하고 싶다면 다음과 같이 할 수 있습니다.

```python
original_string = "???Hello, World!???"
trimmed_string = original_string.strip("?")
print(trimmed_string)  # Output: "Hello, World!"
```

### `lstrip()`과 `rstrip()`
문자열의 앞쪽만 혹은 뒷쪽만 공백을 제거하고 싶을 때는 `lstrip()`과 `rstrip()` 함수를 사용합니다. `lstrip()`은 왼쪽(Left) 공백을, `rstrip()`은 오른쪽(Right) 공백을 제거합니다.

```python
original_string = "   Hello, World!   "
left_trimmed = original_string.lstrip()
right_trimmed = original_string.rstrip()
```

## 주의사항과 에러
`strip()` 함수를 사용할 때 주의해야 할 점은 이 함수가 새로운 문자열을 반환한다는 것입니다. 즉, 원래의 문자열은 변경되지 않습니다. 또한, 문자열이 아닌 데이터 타입에 `strip()` 함수를 적용하면 `AttributeError`라는 에러가 발생합니다.

## 결론
Python에서 `strip()`, `lstrip()`, `rstrip()` 함수를 활용하면 문자열의 앞뒤 공백을 효과적으로 제거할 수 있습니다. 이 함수들은 문자열 처리에서 자주 사용되므로, 잘 알아두면 많은 도움이 됩니다.