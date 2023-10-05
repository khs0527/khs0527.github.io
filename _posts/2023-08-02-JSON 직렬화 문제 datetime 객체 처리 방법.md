---
title: JSON 직렬화 문제 datetime 객체 처리 방법
date: 2023-08-02 20:00:00 +0900
categories:
  - python
tags:
  - JSON
---

## 문제상황: `datetime` 객체가 JSON 직렬화가 안됩니다

JSON은 웹에서 데이터를 전송하는 데 사용되는 텍스트 기반의 표준 형식입니다. 파이썬에서는 `json` 라이브러리를 사용하여 JSON 데이터를 다룰 수 있습니다. 그런데 이 라이브러리를 사용할 때, `datetime` 객체와 같은 특별한 데이터 타입을 직렬화하려고 하면 `"TypeError: Object of type datetime is not JSON serializable"`라는 에러가 발생합니다.

## 해결방법 1: `isoformat()` 메서드 사용하기

`datetime` 객체를 문자열로 변환하는 가장 간단한 방법은 `isoformat()` 메서드를 사용하는 것입니다. 이 메서드는 `datetime` 객체를 ISO 8601 형식의 문자열로 변환합니다.

```python
import json
from datetime import datetime

time_now = datetime.now()
json_data = json.dumps({'time': time_now.isoformat()})
```

## 해결방법 2: 사용자 정의 직렬화 함수 만들기

`json.dumps()` 함수는 `default` 매개변수를 제공합니다. 이 매개변수에 함수를 전달하여 특별한 객체를 문자열로 변환하는 방법을 지정할 수 있습니다.

```python
def datetime_serializer(obj):
    if isinstance(obj, datetime):
        return obj.isoformat()
    raise TypeError("Type not serializable")

json_data = json.dumps({'time': time_now}, default=datetime_serializer)
```

## 해결방법 3: `str()` 함수 사용하기

`str()` 함수를 사용하여 `datetime` 객체를 문자열로 간단하게 변환할 수 있습니다. 이 경우, 날짜와 시간 정보가 사람이 읽기 쉬운 형태로 출력됩니다.

```python
json_data = json.dumps({'time': str(time_now)})
```

## 결론: 여러 가지 방법으로 문제 해결 가능

`datetime` 객체와 같은 특별한 데이터 타입을 JSON으로 직렬화할 때 발생하는 문제는 여러 가지 방법으로 해결할 수 있습니다. 자신의 필요와 상황에 따라 적절한 방법을 선택하면 됩니다.