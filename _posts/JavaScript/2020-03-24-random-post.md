---
title: “Math.random()"
date: 2020-03-24
categories: javascript
---

### Math.random()
Math.random() 함수는 0 이상 1 미만의 구간에서 근사적으로 균일한(approximately uniform) 부동소숫점 의사난수를 반환하며, 이 값은 사용자가 원하는 범위로 변형할 수 있다. 난수 생성 알고리즘에 사용되는 초기값은 구현체가 선택하며, 사용자가 선택하거나 초기화할 수 없다.

<br>

1. 0 이상 1 미만의 난수

```javascript
function getRandom() {
    return Math.random();
}
```

2. 두 값 사이의 난수를 생성(최대값 미포함)

```javascript
function getRandomArbitrary(min, max) {
    return Math.random() * (max - min) + min;
}
```

3. 두 값 사이의 정수 난수 생성

```javascript
function getRandomInt(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min)) + min; //최댓값은 제외, 최솟값은 포함
}
```

4. 

```javascript
function getRandomIntInclusive(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min + 1)) + min; //최댓값도 포함, 최솟값도 포함
}
```