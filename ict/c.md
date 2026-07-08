---
description: C 언어
---

# C



## \*

> **포인터란?** 메모리의 위치를 표현한 기호, 주소가 가리키는 값을 가져온다.&#x20;

{% hint style="info" %}
**포인터의 특징**

1. 특정 위치를 **간접적으로** 가리킬 수 있다.
2. 하나의 포인터는 **한 번에 한 곳만** 가리킬 수 있다.
3. 같은 곳을 여러 포인터가 **동시에** 가리킬 수 있다.
{% endhint %}

{% code title="C: * 포인터 변수 이해" overflow="wrap" %}
```c
int a = 10;
int *p = a;

printf(%d/n, a);  //10
printf(%d/n, *p); //10
```
{% endcode %}

예를 들어, \
a 변수는 100번지를 가리키고 있고 그 안엔 10이 담겨있다. (주소:100, 값:10)\
p 변수는 200번지를 가리키고 있고, 그 안엔 \&a = 100번지가 담겨있다.&#x20;

{% code title="값 도출하기" overflow="wrap" %}
```c
a = 값 10
&a = 주소 100

*p = a = 값 10
p = &a = 주소 100

*p+1 = 값 10+1 = 11
```
{% endcode %}

{% code title="이런 대입은 불가능하다." overflow="wrap" %}
```c
int a = 10;
int *p = &a; //가능
*p=&a;        //int * = int 가 되므로 타입오류 발생
```
{% endcode %}

{% hint style="danger" %}
표현식에서 역참조 연산자일 때 \*p의 타입은 int \* 인데, \&a 의 타입은 int 이기 때문에 타입 오류가 발생한다.
{% endhint %}

### 포인터 변수와 역참조 연산자의 차이 이해하기

{% code title="선언문의 *는 타입, 표현식의 *는 연산자" overflow="wrap" %}
```c
int *p //자료형 타입이 int * 임을 선언
*p     //* 가 가리키는 주소에 담긴 값을 가져오라는 뜻(역참조 연산자)
```
{% endcode %}







## &

변수의 주소(번지)를 가지고 있다.





## 배열

{% code title="array 와 * 의 관계" overflow="wrap" %}
```c
&배열[0] = *p
```
{% endcode %}

배열의 이름은 배열의 첫번째 주소값이다.

하지만 배열의 이름은 값을 저장하거나, 주소값의 변경이 불가능하다 =  상수 형태의 포인 or 포인터 상수

{% code title="" overflow="wrap" %}
```c
int ar[3] = {1,2,3};

ar = 1;   //ar[0]
ar+1 = 2; //ar[1]
ae+2 = 3; //ar[2]
```
{% endcode %}





## 2차원 배열

{% code title="C: 2차원 배열의 원리 파악하기" overflow="wrap" %}
```c
int ar[3][3] = {1,2,3,4,5,6,7,8,9};
```
{% endcode %}

<table data-first-column-sticky><thead><tr><th width="82.5859375" align="center" valign="middle">ar</th><th width="80.78125" align="center">[0]</th><th width="80.30859375" align="center">[1]</th><th width="86.6484375" align="center">[2]</th></tr></thead><tbody><tr><td align="center" valign="middle">[0]</td><td align="center">1</td><td align="center">2</td><td align="center">3</td></tr><tr><td align="center" valign="middle">[1]</td><td align="center">4</td><td align="center">5</td><td align="center">6</td></tr><tr><td align="center" valign="middle">[2]</td><td align="center">7</td><td align="center">8</td><td align="center">9</td></tr></tbody></table>

{% code title="정처기 실기 기출문제 24년 02회) 아래 C 코드의 수행결과를 쓰시오." overflow="wrap" %}
```c
##include <stdio.h>
int main() {
    int ar[3][3] = {1,2,3,4,5,6,7,8,9};
    int *p[2] = { &ar[1], &ar[2] };
    
    printf(%d, p[0][1] + *(p[1]+2) + **p );
    return 0;
}

```
{% endcode %}

{% tabs %}
{% tab title="p[0][1]" %}
-> ( p\[0] = \&ar\[1] ) \[1]\
-> ar\[1]\[1]\
\= 5;
{% endtab %}

{% tab title="*(p[1]+2)" %}
-> \* (p\[1] = \&ar\[2] + \[0+2])\
-> \* ( \&ar\[2] \[2])\
-> \* ( ar\[2]\[2] )\
\= 9;
{% endtab %}

{% tab title="**p" %}
->  p = p\[0] <mark style="color:$primary;">: p는 배열이므로 배열의 이름은 첫번째 주소값을 가리킨다.</mark>\
-> \*p = \&ar\[1] <mark style="color:$primary;">: 따라서 \*p 는 그 주소 내부로 들어가겠다는 의미고</mark>\
-> \*\*p <mark style="color:$primary;">: 는 그 안으로 한번 더 들어간다는 뜻이므로 4가 된다.</mark>\
\= 4;
{% endtab %}
{% endtabs %}

