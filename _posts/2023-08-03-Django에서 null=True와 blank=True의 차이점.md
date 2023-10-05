---
title: Django에서 null=True와 blank=True의 차이점
date: 2023-08-03 20:00:00 +0900
categories:
  - python
tags:
  - 장고Null
---

## 개요

Django 웹 프레임워크에서 모델을 작성할 때, 필드에 대한 다양한 옵션을 설정할 수 있습니다. 이 중에서 `null=True`와 `blank=True`는 특히 중요한데, 이 두 옵션의 차이점을 명확하게 이해하는 것은 효율적인 Django 개발에 중요합니다. 이 글에서는 두 옵션의 차이점과 적절한 사용 시나리오를 자세히 설명합니다.

## `null=True`의 의미와 사용법

`null=True`는 데이터베이스 수준에서의 설정입니다. 이 옵션을 설정하면, 해당 필드는 데이터베이스에 `NULL` 값을 저장할 수 있게 됩니다. 주로 숫자나 날짜와 같은 `non-string` 데이터 타입의 필드에 사용됩니다.

```python
class MyModel(models.Model):
    my_field = models.IntegerField(null=True)
```

이렇게 설정하면 `my_field`에는 정수 값이 들어갈 수도 있고, `NULL` 값이 들어갈 수도 있습니다.

## `blank=True`의 의미와 사용법

`blank=True`는 어플리케이션 로직 수준에서의 설정입니다. 이 옵션은 관리자 패널이나 양식에서 필드가 비어 있어도 되는지를 결정합니다. 주로 문자열 필드에 사용되지만, 다른 데이터 타입의 필드에도 사용할 수 있습니다.

```python
class MyModel(models.Model):
    my_field = models.CharField(max_length=100, blank=True)
```

## 둘의 주요 차이점

- `null=True`: 데이터베이스 수준에서 `NULL` 값을 허용합니다.
- `blank=True`: 어플리케이션 로직에서 해당 필드가 비어 있어도 괜찮다고 명시합니다.

## 언제 무엇을 사용해야 할까?

- 숫자, 날짜 등의 `non-string` 필드에서는 `null=True`를 사용합니다.
- 문자열 필드에서는 `blank=True`를 사용하면 좋습니다. 문자열 필드에서 `null=True`를 사용하면 데이터베이스에 불필요한 `NULL`과 빈 문자열(`""`) 두 가지가 저장될 수 있어 혼란을 줄 수 있습니다.

## 정리

`null=True`와 `blank=True`는 Django에서 중요한 필드 옵션입니다. 둘은 다르며, 적절한 상황에서 올바르게 사용하는 것이 중요합니다. 이해를 돕기 위해 예제 코드를 포함했으니, 이를 참고하여 Django 개발을 더욱 효율적으로 해보세요.