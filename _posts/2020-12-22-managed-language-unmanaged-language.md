---
layout: post
title: Managed code and JIT
description: managed code와 JIT 그리고 프로그래밍 언어의 분류
tags: [용어]
author: Hyeonseop Jeong
comments : True
---

Managed code는 Java, C# 등의 매니지드 언어를 컴파일 했을 때 나오는 코드를 말한다. (e.g. Java의 bytecode)
Managed code는 컴파일이 되었음에도 불구하고 실제 Machine을 동작시키는 코드가 아니라 Virtual Machine (혹은 Common Language Runtime) 위에서 돌아간다.

그래서 Managed code는 아키텍쳐에 종속적이지 않기 때문에 해당 Managed code의 Runtime이 깔려있는 어느 컴퓨터에서나 똑같이 동작할 수 있다.

> Runtime은 Managed code를 어떻게 실행시킬까?
결국에는 managed code를 기계어로 다시 컴파일해야지 컴퓨터에서 돌아갈 것이다.

Runtime은 managed code의 어떤 부분을 실행시켜야 할 때, 빠르게 해당 부분의 manged code를 재빠르게 기계어 코드로 변환시켜서 실행하고 해당 부분이 나중에 또 실행될 수 있으므로 기계어 코드를 caching하여 가지고 있는다.

이러한 방식을 `JIT(Just-In-Time) compile` 이라고 한다.

JVM, V8(= node.js) 같은 런타임들이 JIT compile을 지원한다.

---
Runtime에서는 여러 다양한 서비스를 제공한다. 그 중 대표적인게 메모리 관리 서비스다.

Managed code로 컴파일되는 언어들은 그 언어가 Machine에서 바로 작동하는 코드로 컴파일되지 않기 때문에 컴퓨터의 메모리를 직접적으로 건드리지 않는다. 그래서 C언어로 프로그래밍 할 때 처럼 메모리 누수를 전혀 신경쓰지 않아도 된다. Runtime의 Garbage Collector가 대신 해주기 때문이다.  

그래서 GC가 있냐 없냐에 따라 프로그래밍 언어를 Managed Language와 Unmanaged Language로 분류하기도 한다.


---

1. Unmanaged Language (C, C++, Rust)
2. managed language (Java, C#)

참고
1. https://ko.wikipedia.org/wiki/JIT_%EC%BB%B4%ED%8C%8C%EC%9D%BC
2. https://www.developer.com/net/cplus/article.php/2197621/Managed-Unmanaged-Native-What-Kind-of-Code-Is-This.htm