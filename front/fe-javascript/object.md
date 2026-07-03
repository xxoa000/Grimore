---
description: 객체
---

# object

다양한 타입의 자료를 묶은 덩어리\
⇒ 속성(프로퍼티, 변수) 과 동작(메서드, function으로 정의)



### 객체 넣기

```javascript
let member = {
    id:'banana',
    name: '홍길동',
    age: 22,
    weight: 66.77,
    login: function() {
        document.write(`Login 성공 했습니다.`);
    }
}
```

**`function()`** 처럼 name이 붙지 않는 함수는 익명함수라고 정의한다.\
객체의 구성요소 중에 동작(기능)을 담당하고 있기 때문

* 객체를 정의할 때에 중괄호 `{}`를 사용
* 여러 개도 한번에 정의 가능 ( 콤마 `,` 를 사용해서 분리 )
* 실수 f 도 넣을 수 있음



### 정의된 객체를 사용

{% code overflow="wrap" %}
```javascript
document.write(
    `객체(Object) 활용 member: 
    id=${member.id}, name=${member.name}
    age=${member.age}, weight=${member.weight}`
);
```
{% endcode %}

어떤 객체에 정의되어 있는 변수인지를 표시하기 위해 . 을 사용\
객체의 속성에 직접접근하는 규칙 `객체명.속성명;`



### 객체의 동작을 실행(호출)

{% code overflow="wrap" %}
```javascript
member.login();
```
{% endcode %}



***



## **JavaScript Operator**

> 연산자에 대해 이해하기

{% stepper %}
{% step %}
### **4칙(산술) 연산**

```jsx
let a=7, b=3;
document.write(`a+b = ${a+b}`);
document.write(`a-b = ${a-b}`);
document.write(`a*b = ${a*b}`);
document.write(`a/b = ${a/b}`);
document.write(`a%b = ${a%b}`);
```

* JS는 기본적으로 실수형 나누기를 제공한다.
* % 연산자는 나눈 뒤의 나머지 값을 알려준다. (정수형 연산자)
{% endstep %}

{% step %}
### **증감(단항) 연산**

> 단항 연산자는 ++ (1씩 증가) - - (1씩 감소) 의 의미\
> 변수의 전 or 후 에 적용 가능하다. 위치에 따라 적용 시점이 달라진다.

```jsx
a=10; b=10;
document.write(`++a = ${++a} <br>`);
```

* 먼저 증가하고 / 출력문이 실행된다. (결과값: 11)

```jsx
a=10; b=10;
document.write(`b++ = ${b++} <br>`);
```

* 먼저 출력되고 / 증가한다. (결과값: 10)

```jsx
a=10; b=10;
document.write(`b++ = ${b++} <br>`);
document.write(`++b = ${++b} <br>`);
```

* 먼저 증가하고 / (이전 증가량까지 합쳐서) 출력문이 실행된다. (결과값: 12)

```jsx
a=10; b=10;
document.write(`++a = ${++a} <br>`);
document.write(`--a = ${--a} <br>`);
```

* 먼저 감소하고 / 출력문이 실행된다. (결과값: 10)
{% endstep %}

{% step %}
### 축약 대입 연산

> 프로그래밍 에서 `=` 는 우측의 값을 좌측에 할당해주는 대입 연산자\
> `a=a+b` → 현재 a에 할당된 값과 b의 값을 연산하고, 그 결과를 다시 a에 할당한다.\
> 위의 식을 간편하게 처리해주는 연산식이 축약 대입 이다. → `a+=b`

{% code overflow="wrap" %}
```jsx
a=10; b=3;
document.write(`a+=b -> ${a+=b}`); //a=13
document.write(`a-=b -> ${a-=b}`); //a=13-3 -> 10
document.write(`a*=b -> ${a*=b}`); //a=30
document.write(`a/=b -> ${a/=b}`); //a=30/3 -> 10
document.write(`a%=b -> ${a%=b}`); //a=10/3의 나머지인 1
```
{% endcode %}

만약 수가 여럿일 경우

<pre class="language-jsx" data-overflow="wrap"><code class="lang-jsx"><strong>a=10; b=3; let c=5;
</strong>document.write(`a+=b+c -> ${a+=b+c}`);            // a=18
document.write(`연산 후 a=${a}, b=${b}, c=${c}`); // a=18, b=3, c=5
document.write(`a-=b+c -> ${a-=b+c}`);
document.write(`a*=b+c -> ${a*=b+c}`);
document.write(`a*=b+c -> ${(a*=b)+c}`);
</code></pre>

* 결과값: 우측 연산이 먼저 된 후 대입이 됨

<details>

<summary>연산자의 우선순위</summary>

1순위: `( )` , 단항`++` `- -`

2순위: `*` , `/` , `%`

3순위: `+` , `-`

최하위: 대입연산자`=`

</details>
{% endstep %}

{% step %}
### 관계(비교) 연산

> 모든 관계연산의 결과는 참(true) or 거짓(false)\
> Boolean Type Test 와 같은 계산 및 결과

```jsx
a=10; b=3;
document.write(`a > b : ${a>b}`);    //true
document.write(`a < b : ${a<b}`);    //true
document.write(`a >= b : ${a>=b}`);  //true
document.write(`a <= b : ${a<=b}`);  //false
document.write(`a == b : ${a==b}`);  //a의 값이 b인가? : false
document.write(`a != b : ${a!=b}`);  //a의 값이 b가 아닌가? : true
```

* JS의 동일성 비교\
  기본 연산자 `==` 은 Type 은 비교하지 않고, 값만 비교함.

```jsx
a=100;
b='100';
document.write(`a(정수) == b(문자) : ${a==b}`);
document.write(`a(정수) === b(문자) : ${a===b}`);
```

* Type 까지 비교하고 싶을때는 `===` 를 사용


{% endstep %}

{% step %}
### 삼항식(조건연산)

> 난이도 : 💢💢💢💢💢\
> `(조건식) ? (참)제공하는 결과값 : (거짓)제공하는 결과값 ;`

```jsx
a=20; b=50;
document.write(`a, b 중 큰 수는 : ${ (a>b)? a:b }`); 
// 결과값) a, b 중 큰 수는 : 50
```

* a가 b보다 더 크다면 a 를 출력하고, 아니라면 b 를 출력해라.

```jsx
document.write(`a, b 의 차이는 : ${ (a>b)? a-b:b-a } <br>`);
// 결과값) a, b 의 차이는 : 30
```

* a가 b보다 더 크다면 a-b 를 출력하고, 아니라면 b-a 를 출력해라.

**삼항식 안의 삼항식**

{% code overflow="wrap" %}
```javascript
let result = a > b ? (
    a%2 == 0 ? 'a는 짝수' : 'a는 홀수'
    ) : (
    b%2 == 0 ? 'b는 짝수' : 'b는 홀수'
    );

document.write(`삼항식 중첩 result: ${result}`);
//결과값) 삼항식 중첩 result: b는 짝수
```
{% endcode %}

* a가 b보다 더 크다면,&#x20;
  * (a가 2로 나눴을 때 0이라면 ‘a는 짝수’,&#x20;
  * 아니라면 ‘a는 홀수’를 result에 할당해라.)
* 더 크지 않다면,&#x20;
  * (b가 2로 나눴을 때 0이라면 ‘b는 짝수’,&#x20;
  * 아니라면 ‘b는 홀수’를 result에 할당해라.)

<details>

<summary>문자열의 경우에는 <code>‘’</code> 안에 작성한다.</summary>

개발자는 변수에 다른 값을 입력하는 모든 경우의 수를 전제로 두고 만들어야 하기에, 삼항식이 중첩될 경우엔 앞쪽이 아니라 뒤쪽에 `()`치고 선택지를 늘려나가는 식으로 작성한다.

</details>
{% endstep %}

{% step %}
### 집합(논리) 연산

> 관계식과 관계식의 연산\
> && , || , !

{% code overflow="wrap" %}
```jsx
a=10; b=20;
document.write(${ a > b && a % 2 == 0});

//결과값) false
```
{% endcode %}

* a가 b보다 크고 and(`&&`) a가 2로 나눴을 때 0(짝수)인가? \
  결과값은 true / false

```jsx
document.write(`OR 결과: ${ a > b || a % 2 == 0}`);

//결과값) OR 결과: true
```

```jsx
document.write(`Not 결과1: !(a>b) => ${ !(a>b) }`);

//결과값) Not 결과1: true
```

```jsx
document.write(`Not 결과2: !a>b => ${ !a>b }`);
//결과값) Not 결과2: false
```

#### !a>b

1. 연산자 우선순위: !(논리 NOT) 는 > (비교연산자) 보다 우선순위 높음.
2. 그러므로 처리순서는 (!a) > b
3. JS 에서는 0 -> false, 0외 숫자 -> true
4. (!a) > b 는 false > b , 즉 boolean 과 숫자비교
5. boolean false 는 0, true 는 1 -> 최종비교는 0>b 가 됨
{% endstep %}
{% endstepper %}





