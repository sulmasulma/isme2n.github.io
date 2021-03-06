---
layout: post
title: "[DEVFEST2019] 테스터블 아키텍쳐"
subtitle: "[DEVFEST2019] 데브페스트 2019"
categories: review
tags: event
---

## 테스처블 아키텍쳐

테스트의 원리

- 원하는 값의 었써트가 트루
- 베리파이가 트루

### 테스트를 어렵게 하는 것

1. 의존 클래스의 동작 - 모킹, 스텁
2. 안드로이드 의존 동작 -

## 테스터블 아키텍쳐

### 아키텍쳐란

코드의 역할을 분리하여 여러 이점을 얻는다.

1. 가독성(높은 응집도)
2. 변경 유연함 (낮은 결합도)

MVP, MVVM 을 주로사용. 그냥 쓰면 테스터블하지 않음. 몇가지를 지켜야함.

### 의존성 원칙은 모두 주입받는다.

생성자에 의존을 넣으면 모킹을 할 수 있다.

근데 이렇게하면 UI에서 데이터를 참조? 이상하다. 그래서 DI를 한다.

### 안드로이드 의존 동작을 Wrapping 한다

UI는 뷰 인터페이스로 래핑

- SDK
- View Interface
- Repository

MVP의 기본임.

### 모든 동작은 프레젠터를 통해서

- 뷰는 프렌젠터 실행만
- 프레젠터 로직 테스트 가능

패시브 뷰

### 안드로이드 의존기능 테스트

- UI test
- DB test

## 테스터블 컬쳐

- QA로 검증하는 것이 빠르다고 생각한다. 테스트 추가할 시간이 없다.
- 테스트의 효용성을 모르겠다. 일정이 너무 바빠 동기가 살지 않는다.

### 테스트의 효용성

1. 동작 확인
2. 변경 유연성 확보
3. 코드리뷰를 돕는다

테스트가 있는 클래스는 변경해도 안심. 장기적으로 테스트 있는 것이 생산성이 훨씬 빠르다.

테스트는 의도를 명시화한것임. 테스트를 파악하고 코드를 보면 리뷰가 수월하다.

테스트부터 보면 의도를 알고 리뷰를 할 수 있다.

### 테스트 동기부여

1. 리포트로 현실을 깨닫자. codecov를 깃에 입히면 pr마다 테스트 커버리지 리포트
2. 익숙해지기까지 강제성을 두자. 커버리지가 이전보다 높지 않으면 어프로브를 하지 않음.
3. 쉬운것부터 차근차근. 프레젠터/유닛테스트가 빠르고 수명이 길다. UI는 솔직히 그냥 넘겨도 된다.

> 비즈니스를 늦추지 않으면서 한달동안 커버리지 5% 증가!

습관을 들이면 편해집니다. 테스터블 컬쳐를 포기하지 마세요.

`테스트가 완벽하여도 버그는 발생한다. QA는 필요합니다. 복잡하지 않은 동작은 테스트로 검증합시다.`
