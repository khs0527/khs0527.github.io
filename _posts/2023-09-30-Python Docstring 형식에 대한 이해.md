---
title: Python Docstring 형식에 대한 이해
date: 2023-09-30 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬독스트링
---

## 일반적인 Python Docstring 형식 소개

Python에서 Docstring이란, 코드를 작성할 때 해당 코드의 동작이나 사용법을 설명하는 텍스트입니다. 이는 코드를 읽거나 유지 관리하는 데 매우 유용하며, 여러 가지 형식으로 작성할 수 있습니다. 대표적인 Docstring 형식에는 reStructuredText, Google, Numpy 등이 있습니다.

## reStructuredText 형식

reStructuredText 형식은 Python 공식 문서에서도 사용되며, 가장 일반적으로 쓰입니다. 이 형식에서는 문서의 구조를 명확히 표현하고, 강력한 문서 생성 도구인 Sphinx와 호환성이 뛰어납니다.

```python
def function(arg1, arg2):
    """
    :param arg1: 설명1
    :param arg2: 설명2
    :return: 반환 값에 대한 설명
    """
    pass
```

## Google 형식

Google 형식은 읽기 쉬우며, 간결한 설명을 위해 주로 사용됩니다. 이 형식은 Google에서 개발한 것으로, 인자(argument)와 반환 값(return)을 눈에 띄게 표시합니다.

```python
def function(arg1, arg2):
    """
    Args:
        arg1: 설명1
        arg2: 설명2
    
    Returns:
        반환 값에 대한 설명
    """
    pass
```

## Numpy 형식

Numpy 형식은 수학이나 과학 연산을 주로 다루는 코드에 적합합니다. 이 형식은 특히 배열이나 행렬 등 복잡한 데이터 구조를 설명할 때 유용합니다.

```python
def function(arg1, arg2):
    """
    Parameters
    ----------
    arg1 : 설명1
    arg2 : 설명2

    Returns
    -------
    반환 값에 대한 설명
    """
    pass
```

## 어떤 형식을 사용할까?

어떤 Docstring 형식을 선택할지는 프로젝트의 특성과 팀의 결정에 달려있습니다. 어떤 도구를 사용할지, 어떤 정보를 명확히 전달하고 싶은지를 고려하여 선택하면 됩니다.

## 결론

Python Docstring은 코드의 가독성과 유지 관리성을 높이는 중요한 요소입니다. reStructuredText, Google, Numpy 등 다양한 형식이 있으며, 각 형식은 그에 맞는 장점과 용도가 있습니다. 따라서 효과적인 Docstring 작성을 위해 프로젝트의 필요에 맞는 형식을 선택하는 것이 중요합니다.