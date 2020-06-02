---
layout: post
title: "Algorithm Analysis 란?"
crawlertitle: "About Algorithm Analysis"
date: 2020-06-02T18:23:43+09:00
categories: Algorithm
tags: "whatis"
author: "Hyeonseop Jeong"
---


## Algorithm ?
- 특정 problem을 풀 수 있도록 input 을 넣었을 때 원하는 output이 나오도록 잘 정의된 computational procedure.  
- step-by-step description of a procedure를 따라가면, 끝에 가서 정확한 결과를 얻을 수 있다.

여기서, problem의 내용은 원하는 input/output relationship을 제대로 정확하게 특정할 수 있어야 한다.

---

## Algorithm Analysis ?
알고리즘 분석에는 두 가지 요소가 있다.  
__정확성__ 과 __효율성__ 이다.

- __정확성 (Correctness)__
    - 모든 input에 대해서 올바른 output이 나올 때 그 알고리즘을 정확하다고(correct) 말한다.
    - 증명을 통해 정확성을 증명한다.

- __효율성 (Efficiency)__
    - 해당 알고리즘을 수행하기 위해서 필요한 시간, 공간 자원이 합리적일 때 그 알고리즘을 효율적이라고(efficient) 말한다.
    - 그런데 필요한 시간과 공간은 Input의 크기에 따라 달라지기 때문에, 해당 알고리즘의 시간, 공간 필요량은 __Input의 크기에 따른 식__ 으로 나타낸다.
    - __시간복잡도(Time complexity)__ 와 __공간복잡도(Space complexity)__   
        - Input의 크기에 대한 식으로 필요한 시간 자원, 공간 자원을 나타낸 것을 각각 시간복잡도(Time complexity)와 공간복잡도(Space complexity)를 나타낸다.  
        - 여기서 시간복잡도가 더 중요한 분석 요소로 생각된다.  (하드웨어의 발전양상을 보았을때, 메모리 크기 향상는 빠르지만 CPU의 처리속도 향상은 더디다는 이유 때문.)
