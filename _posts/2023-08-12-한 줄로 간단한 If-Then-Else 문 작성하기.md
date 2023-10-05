---
title: 한 줄로 간단한 If-Then-Else 문 작성하기
date: 2023-08-12 20:00:00 +0900
categories:
  - python
tags:
  - if문
---

## Python에서의 한 줄 If-Then-Else 문

Python에서 if-then-else 문을 한 줄로 작성할 수 있습니다. 이 방법을 사용하면 코드가 간결해지고 가독성이 향상될 수 있습니다. `x if condition else y` 형태를 사용하여 이를 구현할 수 있습니다.

```python
result = "참" if True else "거짓"
```

위의 예제에서 `True`라는 조건이 참이므로, `result` 변수에는 "참"이 저장됩니다.

## 다른 프로그래밍 언어에서의 방법

### Java

Java에서는 삼항 연산자를 사용하여 if-then-else 문을 한 줄로 작성할 수 있습니다. 삼항 연산자는 `조건 ? 값1 : 값2` 형태로 사용됩니다.

```java
int result = (10 > 5) ? 1 : 0;
```

### JavaScript

JavaScript에서도 삼항 연산자를 사용하여 if-then-else 문을 한 줄로 작성할 수 있습니다.

```javascript
const result = (10 > 5) ? "참" : "거짓";
```

## 주의사항

한 줄로 작성하는 것이 항상 좋은 것은 아닙니다. 코드의 복잡성이 높아질 경우, 여러 줄에 걸쳐서 작성하는 것이 가독성이 더 좋을 수 있습니다. 따라서, 한 줄로 작성할 때는 해당 코드가 실제로 간결하고 명료한지 확인하는 것이 중요합니다.

## `SyntaxError: invalid syntax` 문제 해결

간혹 한 줄로 if-then-else 문을 작성할 때 `SyntaxError: invalid syntax`라는 오류가 발생할 수 있습니다. 이는 문법에 맞지 않게 작성되었다는 것을 의미합니다. 오류를 해결하기 위해서는 코드의 문법을 정확하게 확인해야 합니다.