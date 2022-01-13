# 02. ES6에서의 순회와 이터러블 - 이터레이터 프로토콜

## 02-01. 리스트 순회

데이터의 순회는 ``Array`` 같은 리스트를 순차적으로 접근하는 것을 말합니다.

``ES6`` 에서는 ``Map`` 과 ``Set`` 이 추가 되었으며, ``for ~ of 문`` 으로 순회할 수 있습니다.

<br />

```javascript
// Array 를 for문 으로 순회하기

const arr = [1, 2, 3];

for(let value of arr) {
  console.log(value);
}
// 1
// 2
// 3
```

<br />

```javascript
// Set 을 for문 으로 순회하기

const set = new Set([1, 2, 3]);

for(let value of set) {
  console.log(value);
}
// 1
// 2
// 3
```

<br />

```javascript
// Map 을 for문 으로 순회하기

const map = new Map([["a", 1], ["b", 2], ["c", 3]]);

for(let value of map) {
  console.log(value);
}
// ["a", 1]
// ["b", 2]
// ["c", 3]
```


<br /><br />


## 02-02. Iteration Protocols

위의 예시 코드 처럼 ``for ~ of 문`` 을 통해 데이터를 순회할 수 있는데, 이는 기존의 ``for (초기값; 조건문; 증감식)`` 방식으로 동작하지는 않습니다.

이유는 ``Array[0]`` 처럼 객체를 접근하던 ``for (초기값; 조건문; 증감식)`` 이 ``Map`` 과 ``Set`` 에는 사용할 수 없기 때문입니다.

``for ~ of 문`` 의 순회방식은 ``ES6`` 에 추가된 ``Iterator`` 에 의해 순회하게 됩니다.

이렇게 ``for ~ of 문`` 을 사용할 수 있는 ``Array`` , ``Map`` , ``Set`` 은 ``Iteration Protocols`` 를 따르는 객체 입니다.

<br />

``Iteration Protocols`` 는 2개의 프로토콜을 합친 표현 입니다.

* ``Iterable``: ``Iterator`` 를 반환할 수 있는 객체 입니다.
  * 이 객체는 ``객체[Symbol.iterator]()`` 로 ``Iterator`` 를 생성할 수 있습니다.
* ``Iterator``: ``next(): { value: T, done: boolean }`` 메서드를 가진 객체 입니다.

<br />

``Iteration Protocols`` 를 따르는 객체는 ``for ~ of 문`` , ``전계 연산자`` 등을 사용할 수 있는 규약을 따르게 됩니다.



<br /><hr /><br />



[🐫 ``함수형 프로그래밍 01`` 로 이동](https://github.com/Chocobe/-Study-FunctionalProgramming/tree/master/FunctionalProgramming01)

[🐫 ``최상위`` 로 이동](https://github.com/Chocobe/-Study-FunctionalProgramming)
