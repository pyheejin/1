---
title: "함수 인자(Function Parameters)"
date: 2020-03-28
categories: python
---
# Function Parameters

### positional arguments
함수에 parameter가 순서대로 전해지는 경우

```python
def function(x, y):
    print(x+y)

function(5, 1) # 6
```
- 위의 예제에서 x가 non-default value parameter, y는 값을 할당했기 때문에 default value parameter 이다.

### Keyword Arguments
parameter 이름으로 맞추어서 값을 전해주는 경우
```python
def function(x, y):
    print(f'{y}+{x}') 

function(x=4, y='love') # love+4
```
- parameter 순서가 바뀌어도 에러가 발생하지 않음

### Mixing positional arguments and keyword arguments
순서를 맞추어서 parameter 값을 전해주는 positional arguments와 keyword arguments를 혼용하여 사용하는것도 가능
(혼용시에도 인자 순서대로 할당해야 한다.)
```python
def function(x, y):
    print(f'{x} and {y}')

function(3, y=4) # 3 and 4
function(y=4, 3) # SyntaxError: positional argument follows keyword argument
```
- keyword argument가 positional argument 보다 더 앞으로 위치되어 함수가 호출되어서 에러 발생

### Parameter Default Value

```python
def function(x, y='love'):
    print(f'{y}+{x}') 

function(3) #love+3
```
(주의)
```python
def function(x='peach', y):
    print(f'{x}+{y}') # SyntaxError: non-default argument follows default argument
```
- default 값이 정의된 parameter가 default 값이 정의 되지 않은 parameter 보다 앞에 위치해 있기 때문에 에러 발생