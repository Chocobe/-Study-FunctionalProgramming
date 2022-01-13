# 01. 함수형 자바스크립트 기본기

## 01-01. 평가와 일급

프로그래밍에서 ``평가`` 와 ``일급`` 이라는 용어가 있습니다.

각 뜻은 다음과 같습니다.

``평가`` 란, 코드가 계산(Evaluation) 되어 값을 만드는 것을 말합니다.

``일급``은 다음과 같은 의미를 가집니다.

* ``값`` 으로 다룰 수 있을 때, ``일급`` 이라고 합니다.
* ``변수`` 에 담을 수 있을 때, ``일급`` 이라고 합니다.
* ``함수``의 ``인자``로 사용할 수 있습니다.
* ``함수``의 ``결과``로 사용할 수 있습니다.



<br /><hr /><br />



## 01-02. 일급 함수

``Javascript`` 에서 ``함수`` 는 ``일급`` 입니다.

즉, ``함수``를 다음과 같이 사용할 수 있습니다.

* ``값``으로 사용하기
* ``변수``에 담기
* 다른 함수의 ``인자``로 사용하기
* 다른 함수의 ``결과``로 사용하기

<br />

``Javascript`` 의 ``함수``는 이러한 특징 (``일급``) 을 가지므로, 다음과 같이 활용할 수 있습니다.

* ``함수``를 ``값``으로 사용하기
* ``조합성``과 ``추상화``의 도구



<br /><hr /><br />



## 01-02 고차 함수

``고차 함수`` 는 ``함수`` 를 ``값으로 사용`` 하는 함수를 말합니다.

고차함수는 크게 2가지가 있습니다.

* ``함수`` 를 인자로 받아서, ``실행`` 해주는 방식
* ``함수`` 를 만들어서 ``반환`` 해주는 방식

<br />

### 01-02-01. ``함수`` 를 인자로 받아서, ``실행`` 해주는 ``고차 함수``

```javascript
const myFunction = f => f(1);
const add2 = value => value + 2;

const result = myFunction(add2);
console.log(result): // 3
```

<br />

``함수`` 의 인자로 ``함수`` 화 ``값``을 받아서, 이 ``값`` 을 ``인자로 받은 함수`` 에 인자로 넘겨 실행해주는 방식을 ``Applicative Programming`` 이라고도 합니다.

즉, ``Applicative Programming`` 은 ``고차 함수`` 가 실행시킬 함수에 넘겨줄 인자를 정해주는 방식 입니다.

```javascript
const myFunction = (f, limit) => {
  let count = -1;

  while(++count < limit) f(count);
}

myFunction(
  (value) => console.log(value + 1),
  3
);
// 1
// 2
// 3
```


<br /><br />


### 01-02-02. ``함수`` 를 만들어서 ``반환`` 해주는 ``고차 함수``

``함수를 반환`` 하는 ``고차 함수`` 는 ``Closure`` 의 특성을 부여한 ``함수`` 를 반환 합니다.

아래의 예시 코드에서 ``인자(a)`` 는 ``10`` 인 ``Closure`` 가 됩니다.

```javascript
const createAddFunction = a => b => a + b;

// a 에 10이 대입된 Closure 함수를 반환
const resultFunction = createAddFunction(10);

// a 가 10 인 Closure 함수의 인자로 20을 넘겨주며 실행
const resultValue = resultFunction(20);

console.log(resultValue): // 30

console.log(
  createAddFunction(10)(20)
); // 30
```



<br /><hr /><br />



[🐫 ``함수형 프로그래밍 01`` 로 이동](https://github.com/Chocobe/-Study-FunctionalProgramming/tree/master/FunctionalProgramming01)

[🐫 ``최상위`` 로 이동](https://github.com/Chocobe/-Study-FunctionalProgramming)
