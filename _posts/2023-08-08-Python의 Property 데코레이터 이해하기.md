---
title: Python의 Property 데코레이터 이해하기
date: 2023-08-08 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬데코레이터
---

## 데코레이터란 무엇인가?

데코레이터는 코드를 변경하지 않고 함수나 메소드의 기능을 수정할 수 있도록 도와주는 파이썬 기능입니다. 데코레이터는 "@" 심볼로 표현되며, 이를 통해 기존 함수에 추가적인 기능을 "붙여넣을" 수 있습니다. 

## Property 데코레이터의 역할

`@property` 데코레이터는 클래스의 메소드를 인스턴스 변수처럼 사용할 수 있게 해줍니다. 이렇게 하면, 객체의 상태를 직접 수정하지 않고도 메소드를 통해 안전하게 데이터에 접근할 수 있습니다. 이 기능은 캡슐화라고 불리며, 객체 지향 프로그래밍에서 중요한 개념 중 하나입니다.

## 예시: Property 데코레이터 사용하기

아래 예시 코드를 보면, `Person` 클래스에 `@property` 데코레이터가 적용된 `full_name` 메소드가 있습니다.

```python
class Person:
    def __init__(self, first_name, last_name):
        self._first_name = first_name
        self._last_name = last_name
    
    @property
    def full_name(self):
        return f"{self._first_name} {self._last_name}"
```

이렇게 설정하면 `full_name` 메소드는 다음과 같이 사용할 수 있습니다.

```python
person = Person("John", "Doe")
print(person.full_name)  # 출력: John Doe
```

여기서 주목할 점은, `full_name`을 메소드 호출 없이 변수처럼 사용했다는 것입니다 (`person.full_name()`이 아니라 `person.full_name`).

## 주의사항: AttributeError

`@property`를 사용할 때 주의해야 할 점은 `AttributeError`입니다. `@property`로 선언된 메소드와 같은 이름의 인스턴스 변수를 생성하면, `AttributeError`가 발생할 수 있습니다. 따라서 이름 충돌을 피하도록 주의해야 합니다.

## 결론

`@property` 데코레이터는 파이썬의 강력한 기능 중 하나로, 코드의 가독성과 유지 관리성을 높일 수 있습니다. 메소드를 변수처럼 쉽게 사용할 수 있게 해주므로, 객체 지향 프로그래밍에서 캡슐화를 실현하는 데 큰 도움이 됩니다.