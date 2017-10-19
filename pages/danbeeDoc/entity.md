---
title: 엔티티 관리
tags: []
keywords: Basic Conversation
summary: 이 페이지에서는 사용자의 말 속에서 필요한 정보를 뽑아내기 위한 사전작업에 대하여 알 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: entity.html
folder: danbeeDoc
previous: {
    title: 의도 관리, 
    url: intent.html
}
next: {
    title: 대화흐름 기본 설명,
    url: chatflow.html
}
---

## 엔티티(Entity)

**엔티티(이하 Entity)**란, 사용자의 말 속에서 원하는 정보를 뽑아내기 위해 설정하는 값입니다. 앞서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[Intent의 Parameter](intent.html#파라미터parameter)</span>에서 설명한 것과 같이 Parameter라는 껍데기가 어떤 정보를 담을 수 있을지 결정해주는 역할을 한다고 말할 수 있습니다.<br/>

엔티티의 종류에는 크게 2가지가 있습니다.
- [시스템 엔티티](entity.html#시스템-엔티티)
- [사용자정의 엔티티](entity.html#사용자정의-엔티티)

### 시스템 엔티티
시스템 엔티티는 DANBEE.AI에서 기본적으로 제공하는 엔티티를 의미합니다. DANBEE.AI에서는 기본적으로 다음과 같은 시스템 엔티티를 제공합니다.
- [날짜 엔티티 : sys.year, sys.month, sys.day](entity.html#날짜-엔티티)
- [확인 엔티티 : sys.confirm](entity.html#확인-엔티티)
- [일반 엔티티 : sys.any](entity.html#일반-엔티티)

#### 날짜 엔티티



#### 확인 엔티티

#### 일반 엔티티

### 사용자정의 엔티티

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [단어 추출(Entity)]" type="default" %}

사용자정의 엔티티는 직접 정의하여 사용하는 엔티티 입니다.




