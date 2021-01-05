---
layout: post
title: ["[캡스톤] 방학 1주차: 계획"]
description: 캡스톤 프로젝트 계획
tags: [fuzzing, capstone]
author: Hyeonseop Jeong
comments : True
post : false
---


# Php script 대상
- Grey box fuzzer 만들기
- Coverage 재는 소스?
	- interpreter의 로깅 기능 활용하기
- 타임아웃... 정상 동작이지만 무한 루프인 경우도 있기 때문이다.
- C++
- 인풋을 어떻게 넣을 것인지? Command line 상에서 어떻게 넣을 수 있을지 고민을 해봐야 한다.

# 장점: 
- 목표가 concrete 하다.
- 웹과 보안과 연관됨
- 개발이 필요함/ 웹과 관련된 것도
- Coverage 정보를 어떻게 이끌어 내는 것인가?

# 단점:
- 난해한 언어인 php.. 분석하는 그런 기능이 ? 너무 난해한 부분은 스킵
- php가 계속 쓰일 것인가?


# 할일: 
	언제 시작할 것인지? 
	미리 조사하고, A4로 2장정도 뭘 공부할 것인지 자세하게 어떤책? 어떤 사이트?


# 2월 말까지 - 프로토타입정도는 되도록 만들기
0. 공부 계획 세우기
1. Php 공부하기/ 이전에 unit testing을 어떻게 했는지 찾아보고 고민해야!
2. 벤치마킹 - 퍼징에 쓰일 타겟 프로그램 모으기 - 어느 정도 보고, 독립적으로 환경도 구축하고
 seed도 모아서 각 coverage도 측정해보고
3. 논문도 읽고, code scheduling 알고리즘 나온 것도 있다… 우리 tool에 맞게 구현해 보기