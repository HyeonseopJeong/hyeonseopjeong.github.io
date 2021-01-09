---
layout: post
title: ["[AI Academy 2] Linear Regression"]
description: Machine Learning, Linear Regression
tags: [AI, ML]
author: Hyeonseop Jeong
comments : True
post : false
---

> 중앙대학교 K-MOOC AI 아카데미 온라인 특강 (2021.1.13 ~ 2021.1.14) 을 듣고 정리한 내용.

```
특강일정
- 인공지능의 이해 1 (김진형 교수)
- Linear Regression (홍병우 교수)
- Introduction to deep learning and its application (김은우 교수)
- Recurrent Neural Network (김영빈 교수)
```

> 홍영우 교수님의 Linear Regression 강의.


# 머신러닝이란?
인공지능은 인간이 하고자 하는 것을 자동으로 해주는 시스템이라고 할 수 있다. 인간은 오감으로 들어온 `신호`를 `기존의 학습된 양식`을 통해 어떤 행동을 취해야할지 `판단`한다. 
오감으로 들어온 `신호`를 `입력 데이터`로 보고 그 `기존에 학습된 양식`이라는 것을 입력 데이터에 대한 함수로 보았을때,
인공지능이 이 함수를 찾는 학습의 과정을 머신러닝이라고 한다.

# Linear Regression
linear regression은 주어진 학습데이터를 잘 설명하는 함수를 찾는 기법이다.

해당 함수는 linear(일차) 함수가 아닌 Non-linear 함수가 될 수도 있다. 그래서 주어진 데이터를 잘 설명하는 함수의 모양을 잘 선택해야하는데 그 과정을 모델링이라고 한다.

이번에는 가장 간단한 linear 함수로 모델링하여 regression과정을 해 볼 것이다.

> function이 super position property를 만족하면 linear function이라 한다.
> - f(x + y) = f(x) + f(y)
> - f(ax) = af(x)

일차 함수이기 때문에 f_w(x) = w0 + w1x 이렇게 함수를 표현할 수 있고 parameter가 w0, w1로 두개가 생긴다.

이때 f_w(x)의 w는 (w0, w1)

함수가 주어진 데이터를 잘 설명할 수 있도록 w0와 w1을 조정하는 것이 regression하는 과정이다. 
w0와 w1을 어떻게 설정하냐에 따라 기존의 데이터와의 오차가 달라지게 되는데 그것을 Loss Function(=L(w))으로 정의한다.
즉, Loss function의 값을 최소로 하는 w0와 w1을 찾는것이 목표다.

## Loss function
Loss function(=L(w)) = 각 데이터의 실제 답과 f_w(x)와의 차이의 제곱을 다 더한 후 N으로 나눈 것.

w에 대한 L(w) 함수를 그려보면 모델 파라메터(w)가 하나일 경우 이차 함수가 그려진다. 즉, L(w)의 극소점에서 L(w)가 최소가 되고 그때의 모델 파라메터(w)가 최적의 w가 된다.

하지만 위의 예시에서는 파라메터가 두개이므로 3차원 공간에서의 curve형태의 면으로 L(w) 함수가 그려진다.
근데 어찌됐든 L(w)의 극소점에서 L(w)를 최소로 만드는 최적 w가 나온다.

> 3차원 공간에서의 curve형태의 면으로 L(w)함수가 그려질 때 동심원 형태로 같은 L값을 가지는 w를 그린 그림을 Iso-Contours라고 한다. (Iso-Contours로 w가 두개인 L(w)를 쉽게 그릴 수 있음.)

여튼 Linear regression의 목표는 계속 말했다시피 L(w)를 최소로 만드는 w를 찾는 것인데 그걸 어떻게 할까? 

## gradient descent (경사하강법)
L(w)를 최소로 만드는 w를 경사하강법으로 찾을 수 있다.
경사하강법은 처음 w를 어디서 시작(Initialization)하냐에 따라 최소값으로 도착하는데 걸리는 시간이 달라지기도 하고  
global minimum이 아닌 local minimum으로 밖에 못 갈수도 있게 된다. (이러한 함수가 non convex function. convex funtion일 시 어디서 시작하든 global optimal로 도달.)

> 극대점, 극소점, saddle point, non-convex function

경사하강법으로 w를 업데이트 시키는 과정을 수식화하면 w = w - t * DL(w)/Dw 이다. (t는 learning rate)

저 수식을 계속 적용하면서 w를 업데이트 시켜 DL(w)/Dw = 0 인 곳 (= L(w)가 minimum인 곳) 까지 가게 된다. (이 상태를 convergence라고 한다. 임의의 e를 둬서 보통 L'(w) < e 이면 convergence 상태라고 한다.)

이때 learning rate이 너무 클 경우 발산 할 수 있고 너무 작을 경우 학습시간이 너무 오래걸리게 된다.

최근 딥러닝에서는 training을 할 때 모든 학습데이터를 이용하기에는 데이터가 너무 많아서 일부 데이터만을 학습에 이용하는 stochastic GD(gradient descent) 방식을 사용한다..



# 교수님의 말씀
컴퓨터과학의 머신러닝 문제는 위의 내용이 다다. 인풋데이터에 대한 아웃풋 데이터가 있을 때 그냥 그것을 잘 설명하는 함수를 찾는 것이 머신러닝이다. 절대 쥐의 뇌를 분석하는 biological한 내용이 아니다.
