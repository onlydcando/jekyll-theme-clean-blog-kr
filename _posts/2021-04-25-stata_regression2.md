---
layout: post
permalink: /stata/dcando_stata_regression2
title: '예제를통한계량경제학 2장 풀이'
date: 2021-04-23 09:30:00 +09:00
feature: '/img/posts/stata-regression2/stata2_thumbnail.jpeg'
background: '/img/posts/stata-regression/stata1_back.png'
categories:
  - category-stata
tags:
  - 회귀모형 함수
  - 회귀분석 함수
  - 회귀분석 모형
  - 예제를통한계량경제
  - 구자라티
  - 가설검증
description: '구자라티도 지도교수님도 제대로 안 알려주는 회귀모형의 함수'
---


## 마케터D가 알려주는 오늘의 통계풀이: 회귀모형의 함수형태

계량경제분석, 통계분석을 해본 사람이면 안다. 사실 회귀모형이 가장 쉬운 분석방법이었다는 걸.
하지만 주니어 석사생은 회귀니, 로짓이니 모형 이름만 들어도 힘이 빠지는게 현실.
그래서 선배들에게 책이름 조차 어려운 “다모다르 구자라티의 계량경제학”을 추천받는다.
하지만 악순환은 끝나지 않는다. 책이 한국어인데.. 분명 한국어로 쓰여져있는데 이해가 안된다.
그래도 도전해본다. 구자라티도, 지도교수님도 제대로 설명해주지 않는 수많은 분석모형들,  마케터D가 풀이해보겠다.

<br>
<br>
<br>
<br>

## 2장 회귀모형의 함수형태
GDP와 부패지수는 무슨 연관이 있을까? 여기 97년 83개국의 1인당 GDP와 98년도의 부패지수 데이터가 있다. 이 둘은 상관관계가 있는지 알아보겠다.

#### 문제a: 노동자 1인당 GDP와 부패지수를 그래프로 나타내 보라.
  > Code/ .twoway (scatter index gdp_cap)
![이미지1](/img/posts/stata-regression2/img1.png)

> code/ .twoway (scatter index gdp_cap2 )
![이미지1](/img/posts/stata-regression2/img2.png)

그래프를 나타내 본 결과 gdp_cap, gdp_cap2 모두 비선형형태로 나타나진다.
> 참고) 변수에 로그를 취하는 명령어:
gen lngdp_cap=log( gdp_cap) gen
lngdp_cap2=log( gdp_cap2 )

<br>
<br>
<br>
<br>

#### 문제b/ 이 그림을 근거로 부패지수와 노동자 1인당 GDP의 적절한 관계모형은 무엇인가?

> code: .twoway (scatter index lngdp_cap)
![이미지1](/img/posts/stata-regression2/img3.png)

> code: .twoway (scatter index lngdp_cap2)
![이미지1](/img/posts/stata-regression2/img4.png)

설명변수에 로그를 취해주면 선형의 형태가 나타나진다.

<br>
<br>
<br>
<br>

#### 문제c/ 분석 결과를 보여라.
> code: .reg index lngep_cap
![이미지1](/img/posts/stata-regression2/img5.png)

노동자 1인당 gdp가 1% 상승하면 국제투명성지수(index)는 약 1.3% 증가한다.
다시 말해 서 노동자 1인당 gdp가 증가할수록 부패에 대한 인식지수가 높아진다.

<br>
<br>
<br>
<br>


#### 문제d/ 부패와 노동자 1인당 GDP와 정(正)의 관계가 성립하는가? 그렇다면 어떻게 이 결과를 합리화할 것인가?
 정의관계가 정립한다. 이유는 로그를 취한 gdp_cap의 p값이 유의수준 5% 내에서 유의하 기 때문에 양의 관계가 정립하다는 결과가 합리적인 결론이다.

 <br>
 <br>
 <br>
 <br>
