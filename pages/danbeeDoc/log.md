---
title: 대화 이력 관리
tags: [log]
keywords: Basic Conversation
summary: 
sidebar: danbee_doc_sidebar
permalink: log.html
folder: danbeeDoc
previous: {
    title: 유의어 관리,
    url: synonym.html
}
next: {
    title: 테스트 패널 및 시뮬레이션,
    url: demo_n_test_panel.html
}
---

## 대화 이력 관리

- [의도 추론 이력](log.html#의도-추론-이력)
- [대화흐름 이력](log.html#대화흐름-이력)

### 의도 추론 이력
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도추론 이력(Intent Log)]" type="default" %}

#### 이력 정보
[table로 만들기]
- 대화내용
- Intent
- Date
- NLU 의도 분류

#### 조회 조건
- 일시
- Intent
- 입력 문장

#### 필터링
- Default Fallback 여부

#### 기타 기능
대화 내용 기존 intent에 추가 / 새로운 intent 생성 추가

### 대화흐름 이력
{% include callout.html content="화면 위치 : [대화흐름(Chatflow)] > [대화흐름 이력(Chatflow Log)]" type="default" %}

#### 이력 정보
[table로 만들기]
- 시작 Chatflow 명
- Chatflow 수
- Node 수
- Default Fallback 수
- 감성 분석
- 대화 종료 구분
- Date Time
- 대화 내용
- 연결 Intent/Chatflow

#### 조회 조건
- 일시
- Chatflow
- 대화 내용

#### 필터링
- Default Fallback 여부
- 부정 포함 여부
- 이탈 여부
