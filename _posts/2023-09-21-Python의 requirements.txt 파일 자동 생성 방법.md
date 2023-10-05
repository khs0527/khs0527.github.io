---
title: Python의 requirements.txt 파일 자동 생성 방법
date: 2023-09-21 20:00:00 +0900
categories:
  - python
tags:
  - 파이썬파일
---

## 개요

Python 프로젝트를 진행하다 보면, 다양한 외부 라이브러리를 사용하게 됩니다. 이러한 라이브러리의 버전 정보를 다른 개발자와 공유할 필요가 있는데, 이 때 사용하는 것이 `requirements.txt` 파일입니다. 이 글에서는 이 파일을 자동으로 생성하는 방법을 설명하겠습니다.

## pip freeze 명령어 활용

가장 쉬운 방법은 `pip freeze` 명령어를 사용하는 것입니다. 이 명령어는 현재 환경에 설치된 모든 패키지와 그 버전 정보를 나열합니다. 이를 `requirements.txt` 파일에 저장하면 됩니다.

명령어 예시:
```bash
pip freeze > requirements.txt
```

## pipreqs 도구 사용

`pip freeze`는 가끔 불필요한 패키지까지 목록에 포함되는 경우가 있습니다. 더 정확한 `requirements.txt` 파일을 생성하고 싶다면, `pipreqs`라는 도구를 사용할 수 있습니다. 이 도구는 프로젝트 폴더를 스캔하여 실제로 사용된 라이브러리만을 `requirements.txt`에 추가합니다.

설치 방법:
```bash
pip install pipreqs
```

사용 방법:
```bash
pipreqs /path/to/project
```

## 주의사항: 가상환경 활용

`requirements.txt` 파일을 생성할 때는 가상환경을 사용하는 것이 좋습니다. 가상환경은 프로젝트별로 독립적인 Python 환경을 제공하므로, 필요한 패키지만 정확하게 명시할 수 있습니다.

가상환경 생성과 활성화:
```bash
python -m venv myenv
source myenv/bin/activate
```

## 결론

`requirements.txt` 파일은 Python 프로젝트에서 매우 중요한 역할을 합니다. `pip freeze` 명령어나 `pipreqs` 도구를 사용하여 이 파일을 자동으로 생성할 수 있습니다. 가상환경을 활용하면 더욱 정확한 정보를 제공할 수 있습니다. 이를 통해 다른 개발자와 효율적으로 협업할 수 있습니다.