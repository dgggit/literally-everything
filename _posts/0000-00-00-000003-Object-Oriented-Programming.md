---
layout: post
title: Object Oriented Programming
category: Python Dev
tags: [ Python, OOP, Java ]
date: '2020-03-30'
permalink: '/posts/000003/'
---
(* on draft *)

<div id="Introduction"></div>
# Introduction
---
This would be content
C++ Java Python compare 많이들 헷갈려 하는 
<!-- more -->

<div id="Object-Orientation"></div>
# OOP
---
## Overview

OOP는 하나의 패러다임이다.
Object의 개념부터 시작.

(wikipedia)

여기 잘 설명하자꾸나

중요한 컨셉으로는 Object / Class / Instance 가 있다.

이 세개는 헷갈리지만, 인터넷에는 정말 다양한 설명이 있는데, clear한 설명이 없다. 각자 자기만의 방식으로 설명을 한다.
위에서 말한 것으로는 컨셉이지만
엄밀하게 어떻게 정의되는지 보자.

## Object
Object에서 
OOP Paradigm에서, Object의 정의는, '소프트웨어 설계에 구현할 대상'이다.
OOP의 하위인 CBP 언어들에서, Object의 정의는 'class instance'이다. 

많은 사이트 별로 Object의 정의가 갈리는데, OOP 패러다임에서의 Object의 정의인지 혹은 OOP 언어 중 

## Class
class의 개념은 OOP의 하위 분류인 class-based programming에서 나온다.
 Class-base Programming은 OOP의 하나의 스타일이며, 우리가 아는 대부분의 OOP 언어(C++, Java, Python)들은 Class-Based PL이다.
class의 정의는, 구체적으로 (위키백과 참고) 
class-based에서는 class 개념을 통해 OOP를 구현한다.

## Instance
- instance의 정의는, () 관계이다.
- 즉, 항상 **X의 instance (instance of X)** 의 꼴로 말해야 한다. 바꿔 말하면 [instantiate](https://www.computerhope.com/jargon/i/instantiation.htm)하는 대상이 있어야 한다. instanctiate의 정의는, (정의/설계된 것을 실체화하는 작업) 이다.
- class의 경우를 생각해보면 class는 기능/멤버(이거구체적으로)에 대한 명시이며, 이 class를 바탕으로 class instance가 생성되기 때문에 class instance와 Object를 같은 개념으로 본다. 왜 위에서 Object를 저렇게 정의했는지 알 수 있다.
  - 그러나 이는 이론적인 개념으로, instance와 object를 완전 동일시하면 안되는 것이, 예외가 있으며, 아래 Advanced 탭에 소개한다.

- 흔히 우리가 그냥 instance라고 말하는 것은 class instance를 가리키며, 이는 class를 프로그램 실행 과정에서 instantiate한 결과물이다. 그러나 엄밀한 표현을 위해서는 class instance라고 부르는 것이 정의에 어긋나지 않는다.

## Advanced
object와 class instance가 항상 같으냐, 모든 언어에서 그렇지는 않다. 
- java에서는 object를 다음과 같이 정의한다.
    - > An object is a class instance or an array. (JLS 4.3.1)
    - 즉, object는 항상 class instance가 아닐 수도 있다는 소리다.

python에서는 class instance 뿐 아니라 class 그 자체도 객체이다. (i.e. class object라는 것이 존재함.) 또한, 그 class object의 타입도 class이다. // 이 부분 좀더 명확하게 쓰기.
- 뭔 소리냐?
- 다음 예제를 통해 알아보자.

# Concepts Applied in Java, C++, Python
---
# 전체적으로 읽는 사람이 쉽게 이해할 수 있게 스토리 잘 되나, 모른다고 가정하고 다시 다듬기.
## C++, Java
```java {.line-numbers}
/* Java (similar with C++) */
class A {  /* members */ }
A aa = new A();
```
이 코드를 해석하자면,
`new A()` 는 `A` class의 instance를 생성한다. 
`A aa` 는 생성된 오브젝트를 `A` 타입의 변수로 갖으며, `"aa"`라는 이름을 붙인다는 것을 의미.

Java와 C++에서 class의 개념은 코드에서만 드러난다. 코드에서 틀(class)을 정의하고 이 코드를 실행하면 쿠키(class instance) 를 찍어내어 메모리에 담는 그런 역할을 한다. 이 두 언어에서, 한번 정의된 class는 프로그램이 컴파일 되면 그 정의된 내용을 손볼 수 없다.

## Python
Python에서도 C++/Java와 같이 코드 `class Foo : `의 문법을  통해 이름 / 멤버 / 기능을 정의한다. 하지만 여기서 그치는 것이 아니라, 프로그램 실행 레벨에서 이 정의된 내용들이 담겨 있는 object 또한 생성된다. 이러한 object를 **Class Object**라고 부르며, Java나 Python에는 존재하지 않는 개념이다.

아래 code snippet를 보자.
```python {.line-numbers}
# Python
class A :
    pass

a = A
aa = A()
```
일단 줄 5를 보자. C++이나 Java에서는 class는 갖다 쓰는것 밖에 안되는데 여기서는 class 자체를 변수로 지정할 수 있다.
여기서 a는 클래스 자체를 의미하는 것이고, aa는 A 클래스의 생성자를 호출하며 class instance를 받아오게 되는 것이다.

# 정말정말간단하게만 설명하고 이 아래부분 다 날리자. 다음 포스트에서 설명하는게 더 나을듯. / 동적클래스 형성 부분도.

```python {.line-numbers}
>>> type(a)     # a -> class object (is an 'object')
<class 'type'>
>>> type(aa)    # aa -> class instance (is also an 'object')
<class '__main__.A'>
```
이름이 모호한데, Class의 내용을 담아놓은 object이다. 그렇다면 그 object의 type은 무엇일까? 확인해보면 `'type'`이라는 이름의 클래스를 type로 가진다. C++/Java에서는 이 개념이 존재하지 않는다. class로 object를 만들면 끝나는 것이지.

위에 Advanced에서 어쩌구저쩌구 한게 생각 나는가?
그렇다, 사실 Python에서 모든 것들의 type은 class이며, 프로그램 안에서 모든 것은 object이다.

이게 뭐가 좋냐면, 하나의 예를 들어 보자면, 프로그램 실행 시간에(동적) 새로운 종류의 class를 만드는 것이 (object가 아니라 class이다!) 가능하다는 것이다. (code에서 `class A : ~~` 구문을 사용하지 않고도 새로운 class를 만들 수 있다는 말과 동치이다) 기존 존재하는 class object를 가지고 새로운 class를 만들어 낼 수 있는 것 이다. (뭐로 뭐를 만드는지 명확하게 볼것.) 

Python 언어에서 위 동적 클래스 생성([dynamic class creation](https://stackoverflow.com/questions/15247075/how-can-i-dynamically-create-derived-classes-from-a-base-class))이 가능하다는 개념에 대해 이해할 수 있다면 class object와 python에서의 class 개념에 대해 이해했다고 할 수 있다.

이 쯤에서 OOP 개념과 Python에서의 OOP가 어떻게 적용되었는지에 대해 마무리하고자 한다.
Python의 `<class 'type'>`은 무엇인지, 어떻게 generate되는지는 다른 post에서 다룰 것이다.


<div id="Reference"></div>
## Reference
https://stackoverflow.com/questions/1215881/the-difference-between-classes-objects-and-instances
https://en.wikipedia.org/wiki/Object-oriented_programming
https://en.wikipedia.org/wiki/Instance_(computer_science)