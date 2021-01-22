---
layout: post
title: ["[swexpert academy] 1강. 완전탐색"]
description: 완전탐색
tags: ["swexpert academy", 완전탐색]
author: Hyeonseop Jeong
comments : True
post : false
---

> 본 포스트는 [SW Expert Academy](https://swexpertacademy.com/) 의 강의를 보고 정리한 내용입니다.

# 완전탐색 이란?
완전탐색 (exhaustive search)은 `brute force` 혹은 `generate and test` 라고도 부른다.

완전탐색은 정답이 될 수 있는 모든 경우를 생성해서 확인해보는 방식이다.
그래서 문제를 해결하는 가장 `간단`하면서 `정확`한 방법이지만 입력의 크기가 크다면 `시간이 오래 걸린다`. 

그리고 대부분의 문제에 완전탐색을 적용해서 풀 수 있기 때문에 우선 완전탐색으로 푼 다음에 `greedy`나 `dynamic programming` 으로 성능을 높이기도 한다.


# 어느 문제에 적용?

완전 탐색은 말 그대로 모든 경우의 수를 완전히 탐색하는 방식이기 때문에 `조합적 문제`를 풀 때 잘 작용된다.

조합적 문제(Combinational Problem)는 주어진 요소들에서 특정 조건을 만족하는 경우를 찾는 문제인데 실생활의 대부분의 문제는 `조합적 문제`다.

조합적 문제는 3가지 타입으로 나누어 볼 수 있다.
1. 순열(Permutation)
2. 조합(Combination)
3. 부분집합(Subsets)

문제에 따라 완전탐색을 할 때 이 세 가지를 잘 생각하면 `중복 탐색`을 최대한 줄이면서 완전탐색을 할 수 있다.

## 문제들
### 1. 베이비 진 문제
### 2. 순회 외판원 문제(Traveling Salesman Problem)
### 3. 배낭 문제



# 각 타입의 조합적 문제를 해결하는 코드

위에서 말한 세 가지 타입의 조합적 문제 (순열, 조합, 부분집합)를 해결하는 코드를 리뷰하겠다.

## 1. 순열
> n 개의 요소중에 m개를 `나열`하는 모든 경우의 수를 탐색하는 것이다.



