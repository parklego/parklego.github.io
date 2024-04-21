---
title: JavaScript
author: parklego
date: 2024-03-01
category: til
layout: post
---

## for in

- 객체 순환

```javascript
let object = {
  a: 1,
  b: 2,
  c: 3,
};

// key 값 접근
for (let key in object) {
  console.log(key); // a,b,c
}

// value 값 접근
for (let key in object) {
  console.log(object[key]); // 1,2,3
}
```

## for of

- 배열 순환

```javascript
let array = [1, 2, 3];

for (let value of array) {
  console.log(value); // 1,2,3
}
```

## forEach

- 배열 순환
- return 값 X

```javascript
let array = [1, 2, 3];

array.forEach((value) => console.log(value)); // 1,2,3
```

## map

- 배열 순환
- return 값이 변형된 값(return값)들의 모음

```javascript
let array = [1, 2, 3];

let double = array.map((item) => {
  return item * 2;
});

console.log(double); // [1,2,3]
```

## filter

- 배열 순환
- return 값이 true인 값들의 모음

```javascript
let array = [1, 2, 3, 4];

let odd = array.filter((item) => {
  return item % 2;
});

console.log(odd); // [1,3]
```

## reduce

- 배열 순환
- callback함수의 실행 값을 누적하여 하나의 결과값을 반환
- 초기값 설정 필요 (설정하지 않으면 배열 0번째 요소의 값)

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const sum = numbers.reduce((acc, curr) => {
  return acc + curr;
}, 0);

console.log(sum); // 55
```

## split

- 문자열을 구분자 기준으로 나누어 배열로 변환

```javascript
const str = "apple banana orange";

const arr = str.split(" ");

console.log(arr); // [ 'apple', 'banana', 'orange' ]
```

## join

- 배열의 모든 요소를 쉼표나 지정된 구분 문자열로 구분하여 연결한 새 문자열을 만들어 반환

```javascript
const elements = ["Fire", "Air", "Water"];

console.log(elements.join()); //  Fire,Air,Water
console.log(elements.join("")); // FireAirWater
console.log(elements.join("-")); // Fire-Air-Water
```

## toSorted

- 요소들을 오름차순으로 정렬한 새로운 배열을 반환

## toReversed

- 요소들을 내림차순으로 정렬한 새로운 배열을 반환

## nullish coalescing

- 값이 null 이나 undefined 인지 체크

```javascript
const displayName = name ?? "익명";
```
