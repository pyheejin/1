---
title: "Modules & Packages"
date: 2020-03-30
categories: python
---

# Modules & Packages
- 파이썬은 Modules & Packages를 찾을 떄 다음 3가지 장소를 순서대로 보면서 검색한다.
- 파이썬은 import하고자 하는 모듈과 package를 찾을때에 먼저 sys.modules를 보고, 없으면 파이썬 built-in 모듈들을 확인 하고 마지막으로 sys.path에 지정되어 있는 경로들을 확인해서 찾는다.
- sys.path 에서도 못찾으면 ModuleNotFoundError 에러를 리턴

## sys.modules와 sys.path의 차이점

### 1. sys.modules
- 파이썬이 모듈이나 package를 찾기위해 가장 먼저 확인하는 곳
- sys.modules는 단순한 dictionary 구조로 되어있다.
- 이미 import된 모듈과 package들을 저장하고 있다.
- 한번 import된 모듈과 package들은 파이썬이 또 다시 찾지 않아도 되도록 하는 기능을 가지고 있습니다.
- 새로 import 하는 모듈은 sys.modules 에서 찾을 수 없습니다.
- sys는 파이썬에 포함되어 있는 모듈이라서 sys 모듈을 import 해서 sys.modules와 sys.path 출력 및 수정도 가능하다.

```python
import sys

print(sys.path)
print(sys.modules)
```

### 2. built-in modules
- 파이썬에서 제공하는 파이썬 공식 라이브러리들
- Built-in 모듈들은 이미 파이썬에 포함되어 나오므로 파이썬이 쉽게 찾을 수 있습니다.

### 3. sys.path
- sys.path는 기본적으로 list이며 string 요소들을 가지고 있는 리스트
- 각 string 요소들은 다음 처럼 경로를 나타냅니다
```python
['',
 '/Users/song-eun-u/anaconda3/bin',
 '/Users/song-eun-u/anaconda3/lib/python36.zip',
 '/Users/song-eun-u/anaconda3/lib/python3.6',
 '/Users/song-eun-u/anaconda3/lib/python3.6/lib-dynload',
 '/Users/song-eun-u/anaconda3/lib/python3.6/site-packages',
 '/Users/song-eun-u/anaconda3/lib/python3.6/site-packages/aeosa',
 '/Users/song-eun-u/anaconda3/lib/python3.6/site-packages/IPython/extensions',
 '/Users/song-eun-u/.ipython']
```

## sys도 import 해야하는 모듈입니다. 파이썬은 sys 모듈의 위치를 어떻게 찾을 수 있을까요?
파이썬이 설치될때 내장 모듈도 같이 설치되므로 path의 정보가 기본값으로 정해져 있다.
sys도 이미 built-in 되어있기 때문에 Built-in 모듈에서 찾을 수 있다.

## Absolute path와 Relative path의 차이점
Built-in 모듈, pip 으로 설치한 외무 모듈도 자동으로 site-packages 라는 디렉토리에 설치가 되는데 이 site-packages는 sys.path에 이미 포함되어 있기때문에 찾는데 문제가 없다.

문제는 직접 개발한 local package, 직접 개발한 local package를 import 할때는 해당 package의 위치에 맞게 import 경로를 잘 선언해야 한다.  Local package를 import 하는 경로에는 absolute path와 relative path가 있습니다

Relative path는 선언해야 하는 경로의 길이를 줄여준다는 장점은 있지만 헷갈리기 쉽고 파일 위치가 변경되면 경로 위치도 변경되어야 하는 단점이 있다. 그러므로 웬만한 경우 absolute path 사용하는걸 권장한다.

### Absolute path
```
└── my_app
    ├── main.py
    ├── package1
    │   ├── module1.py
    │   └── module2.py
    └── package2
        ├── __init__.py
        ├── module3.py
        ├── module4.py
        └── subpackage1
            └── module5.py
```
```python
# main.py
from package1 import module1
from package1.module2 import function1
from package2 import class1
from package2.subpackage1.module5 import function2
```
- 이미 my_app 프로젝트 안에 있으므로 my_app 은 생략 가능
- 경로들의 시작점이 전부 "my_app" 프로젝트의 가장 최상위 디렉토리에서 시작하기 떄문에 my_app 프로젝트 내에서는 main.py가 아니더라도 동일한 표기법으로 사용할 수 있다.
- current directory 라고 하는 현재의 프로젝트 디렉토리는 default로 sys.path 에 포함되므로 absolute path는 current directory로 부터 경로를 시작하게 된다.


### Relative path
absolute path와 다르게 프로젝트의 최상단 디렉토리를 기준으로 경로를 잡는게 아니라 import 하는 위치를 기준으로 경로를 정의

```python
# package2/module3.py

from . import class1
from .subpackage1.module5 import function2
```
- dot(.)은 import가 선언되는 파일의 현재 위치를 표시, 현재위치는 package2/module3.py 이므로 현재 위치에서부터 원하는 모듈의 경로만 선언해주면 된다.

```python
# subpackage1/module5.py
from ..module4 import class4
```
- dot 2개를 사용할 수도 있다. dot 2개(..)는 현재위치에서 상위 디렉토리로 가는 경로이다.