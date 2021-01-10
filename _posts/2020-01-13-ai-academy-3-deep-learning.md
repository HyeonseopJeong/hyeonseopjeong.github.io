---
layout: post
title: ["[AI Academy 3] Deep Learning"]
description: Deep Learning
tags: [AI, ML]
author: Hyeonseop Jeong
comments : True
post : false
---

> 중앙대학교 K-MOOC AI 아카데미 온라인 특강 (2021.1.13 ~ 2021.1.14) 을 듣고 정리한 내용.


```
1일차 특강일정
- 인공지능의 이해 1 (김진형 교수)
- Linear Regression (홍병우 교수)
- Introduction to deep learning and its application (김은우 교수)
- Recurrent Neural Network (김영빈 교수)
```

> 김은우 교수님의 Deep Learning 강의.


# Machine Learing
Machine Learning 의 Elements.

# Deep Learning
딥러닝이 나오고 딥러닝이 기존의 머신러닝의 다른 방식들을 성능으로 모두 압도함. 

Traditional Machine Learing에서는 데이터 사이즈가 작았고 통계적모델을 정해놓고 했다면 Deep Learing에서는 데이터 사이즈가 굉장히 컸고 파라미터가 엄청 많아졌고 black box architecture라서 결과가 나와도 그 이유를 모른다.

하드웨어 성능이 좋아지면서 deep learning 방식이 빛을 발했나.?

## Single-Layer Neural Networks

## Multi-Layer Neural Networks
그냥 기존의 고차함수로 설명(모델링)이 안되는 데이터들을 멀티 레이어 뉴럴 네트워크를 이용해서는 설명(모델링)이 가능해짐.

# Convolutional Neural Network (CNN)
CNN은 딥러닝 모델 중 하나.

> filter(kernal), Image, convolution
> filter가 학습이 되는 존재
> filter를 여러개 만들면 결과 output도 그만큼 나옴.
> 이거를 여러겹으로 할 수 있음.
> stride : filter가 image를 sliding하는 보폭 (보폭이 커지는 만큼 output 사이즈도 줄어드는데 그게 싫으면 output의 테두리를 zero padding 할 수 있음.)
> 1x1 convolution도 있음. (3번째 dimension을 바꾸기 위해 자주 사용. 왜냐하면 1, 2 dimension은 그대로 나올 것이기 때문.)

> Activation function : output의 각 element에 적용하는 함수
> ReLU라는게 있음. 0보다 작으면 0, 아니면 y = x
> Sigmoid, maxout 등등도 있는데 자신이 풀고자하는 문제에 맞춰서 활성화 함수를 선택해서 사용하는 것임.

> Pooling

이 정도 알면 논문에 나온 CNN 구조 그림을 이해할 수 있음.
![CNN structure](/assets/post_images/AI/CNN-structure-in-paper.png)


> Gradient Descent, Momentum
> 사용하는 Loss Function 도 다양함.



## Summary
이것들을 다 알았으니 이제 CNN논문을 읽을 수 있음.


# case study


# RNN
Sequence 를 처리하기 위한 딥러닝 방식