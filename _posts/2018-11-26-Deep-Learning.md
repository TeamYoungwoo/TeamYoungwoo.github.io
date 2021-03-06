---
layout: post
comments: true
title:  "딥러닝이란 무엇일까? part1"
date:   2018-11-26 09:04:30
author: 신승민
categories:
  - AI
tags:
  - AI
  - 딥러닝
  - 퍼셉트론
  - 신경망
cover:
---
## 퍼셉트론

퍼셉트론은 프랑크 로젠블라트가 1957년에 고안한 알고리즘입니다. <br>

사람은 어떤 둥근 물체가 빨갛고 맛있다면 사과라고 판단할 것 입니다. <br>
단순하게 생각해보면 특정 입력 (둥근, 빨간, 맛있는)을 가지고 출력 (사과라고 판단) 하는 형태라고 생각해 볼 수 있습니다. <br>
엄청 단순한 설명이지만 이를 그대로 구현한 하나의 판단 단위가 퍼셉트론이라고 생각할 수 있습니다. <br>

퍼셉트론은 다수의 신호를 입력으로 받아 하나의 신호를 출력합니다.<br>
다음 그림은 퍼셉트론의 예입니다.<br>
![퍼셉트론그림](https://mblogthumb-phinf.pstatic.net/MjAxNzA4MDhfMTAx/MDAxNTAyMjAzNjYxNzc5.sK4JqoJM1DLAWyR5fSFPWQaPLPa6HzjT_8fxxupwplgg.3sX5XGhfkEaJ9ZEkAUkeltjSlK4K2Yds-q_WxKf_xpQg.PNG.infoefficien/image.png?type=w800) <br>
x1, x2는 퍼셉트론의 입력을 w1, w2는 가중치를, b는 편향(bias) 그리고 y는 출력을 의미합니다.<br>
즉, 가중치와 편향을 어떻게 입력하느냐에 따라서 똑같은 입력을 받고도 다른 출력을 내보내는 하나의 생각 단위를 만들어 낸다는 겁니다. <br>

둥글고, 빨간, 맛있는 속성을 가지고 사과라고 판단하는 과정을 극도로 단순하게 표현한 것이죠. <br>

하지만 문제가 있습니다. 사람은 어느정도 둥글고, 어느정도 빨갛고, 어느정도 맛있으면 사과로 판단하는 "어느정도"에 대한 학습이 되어있습니다만. 퍼셉트론은 그렇지 않죠? <br>
즉 퍼셉트론의 가중치와 편향은 사람이 설정해 주어야 한다는 것입니다. <br> 
문제는 판단하는데 엄청나게 많은 입력과, 엄청나게 많은 출력이 있고 이런 판단 단위들을 무수히 엮어 만들어야 우리가 원하는 인공지능이 만들어 질 텐데 그 전부의 정당한 가중치를 사람이 입력하기가 사실상 불가능 하다는 점에 있습니다. <br>

## 신경망

퍼셉트론의 이런 문제점을 신경망이 해결해 줍니다. <br>
바로 신경망은 가중치를 데이터로부터 자동으로 학습시키는 겁니다! <br>

신경망은 다음 그림과 같은 형태입니다. <br>
![신경망그림](https://t1.daumcdn.net/cfile/tistory/273FF8425432D35D13) <br>

제일 왼쪽 뉴런들이 <b>입력층</b> <br>
제일 오른쪽 뉴런들이 <b>출력층</b> <br>
그 사이에 있는 무수히 많은 뉴런들을 <b>은닉층</b> 이라고 부릅니다. <br>
입력과 출력은 사람이 볼 수 있지만 그 중간에 있는 뉴런에서 어떤 신호가 주고가는지는 중요하지도 않고 볼 수 없기 때문에 은닉층이라고 부르는 겁니다. 재밌죠? <br>
<br>
이제 은닉층의 하나의 뉴런을 단순히 <b>박스</b>라고 생각해 봅시다. 이 박스는 여러가지 입력값이있고, 여러개의 출력값이 존재합니다.<br>

더하기 박스는 입력을 1, 2를 받고 3의 출력을 내보내죠. <br>
![+박스그림](https://scontent-icn1-1.xx.fbcdn.net/v/t1.0-9/46837498_1875577872555165_8012644322597928960_n.jpg?_nc_cat=109&_nc_ht=scontent-icn1-1.xx&oh=b07ca19fe4c26fbdf6f149039579e9a0&oe=5C6D269A) <br>
이런 식으로 마치 뉴런을 모듈처럼 생각할 수 있게 되고, 입력과 출력을 가지는 하나의 <b>함수</b>처럼 생각할 수 있게 됩니다. 여기서 함수를 <b>활성화 함수</b>라고 하고 입력 신호는 이 활성화 함수를 거쳐 출력 신호가 됩니다. <br>
<br>

## 신경망 학습이란?

<i>그래서 컴퓨터가 학습? 어떻게?</i>
입력값을 증폭시키는 가중치, 입력값에 경향을 주는 편향 <br>
가중치와 편향을 적절히 하고 다중 뉴런층들을 연결해서 여러 입력값에 여러가지 형태의 출력값을 가질 수 있을겁니다. <br>

신경망은 데이터를 가지고 이 가중치와 편향을 학습한다고 했었습니다. <br>

간단히 생각하면 <br>
가중치와 편향이 제대로 설정되지 않은 모델에 입력 신호를 통과시키면 출력 신호가 나오게 될 것입니다. <br>
해당 출력 신호와 가지고 있는 데이터의 값을 비교해서 그 값이 비슷하게끔 가중치와 편향을 학습하게 됩니다. <br>