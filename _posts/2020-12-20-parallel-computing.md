---
layout: post
title: ["병렬 컴퓨팅이란?"]
description: 병렬 컴퓨팅이란?
tags: [병렬 컴퓨팅]
author: Hyeonseop Jeong
comments : True
post : false
---


병렬 컴퓨팅(parallel computing)



# 정의

병렬 컴퓨팅은 하나의 문제를 여러 컴퓨팅 자원을 이용해서 푸는 것이다.

이때 컴퓨팅 자원은 core나 computing node를 말한다.

parralel computing이랑 concurrent computing을 구분해야한다.



# 쓰는 곳

연산량이 많이 필요할 때 사용하는데 원래는 군사나 기상청에서 사용했지만 요즘에는 4차산업 혁명이 일어나면서 여러 분야에서 병렬 컴퓨팅의 수요가 높아졌다.

재밌는 이야기로 Moore's Law가 cpu성능이 24개월에 두 배씩 좋아지지만 Blinn's Law로 영화 스튜디오의 렌더링 작업에 걸리는 시간은 constant하다는 말이 있다. 실제 픽사의 평균 렌더링 시간을 연도별로 나타낸 그래프를 보면 20년동안 거의 일정하다. 기술이 발전하는 만큼 원하는 성능의 수요도 계속 커진다는 말이다.

그런데 다른 이야기로 사실 cpu성능이 어느 시점에 도달하고부터는 여러 문제 때문에 더이상 Moore's Law가 적용이 안되서 한 코어에 트렌지스터를 많이 집약해서 성능을 높이던 방식에서 코어를 어러 개 박아서 성능을 높이는 (멀티코어) 방식으로 양상이 바뀌었다.

여튼 이러한 배경이 있기 때문에 병렬 컴퓨팅을 할 줄 알아야한다.



# 목적

병렬 컴퓨팅을 하는 목적은 사용자가 10개의 컴퓨팅자원을 썼으면 성능도 10배로 늘어나는 것이다.

컴파일러 옵션을 잘 보면, 예를 들어 MSVC의 옵션을 보면 "Enable Parallel Code Generation" 이라는 게 있는데 그걸 체크하면 프로그램을 그냥 짜도 컴파일러가 병렬 처리 가능한 영역을 찾아서 자동으로 병렬화를 해준다. (Auto Parallelization 이라 한다.)

그러면 굳이 왜 병렬 프로그래밍을 공부해야하나? 

summation 하는 것을 병렬 프로그래밍으로 했을 때 

Naive algorithm과 Improved algorithm의 방식 차이와 성능차이 비교!

즉 컴파일러의 Auto Parallelization는 정말 단순하게 해주기 때문에 제대로 하려면 프로그래머가 직접 병렬 프로그래밍을 해줘야한다.



# 배경지식
병렬 컴퓨팅을 하려면 기본적으로 병렬 컴퓨팅을 위해 사용하는 병렬 컴퓨팅 아키텍처(parallel computing architecture)에 대한 이해가 필요하다.

작게는 Intel Quad core i7 부터 크게는 Google data center도 병렬 컴퓨팅 아키텍처라고 할 수 있다.

Flynn's Taxonomy (플린의 구분법)



+ Nondeterminism

+ Performance of Parallel Computing


