---
title: 엔티티 관리
tags: []
keywords: Basic Conversation
summary: Entity를 통하여 입력 문장에서 필요한 정보를 뽑아낼 수 있습니다.
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

**엔티티(이하 Entity)**란, 사용자의 말 속에서 원하는 정보를 뽑아내기 위해 설정하는 값입니다. 앞서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[Intent의 Parameter](intent.html#파라미터parameter)</span>에서 설명한 것과 같이 Parameter라는 껍데기가 어떤 정보를 담을 수 있을지 결정해주는 역할을 합니다.<br/>

Entity의 종류에는 크게 2가지가 있습니다.
- [시스템 Entity](entity.html#시스템-entity)
- [사용자정의 ENtity](entity.html#사용자정의-entity)

### 시스템 Entity
**시스템 Entity**는 DANBEE.AI에서 기본적으로 제공하는 Entity를 의미합니다. DANBEE.AI에서는 기본적으로 다음과 같은 시스템 Entity를 제공합니다.
- [날짜 Entity : sys.year, sys.month, sys.date](entity.html#날짜-entity)
- [확인 Entity : sys.confirm](entity.html#확인-entity)
- [일반 Entity : sys.any](entity.html#일반-entity)

#### 날짜 Entity

날짜 Entity는 날짜를 가리키는 단어를 구분합니다. 일, 월, 년에 대해 각각의 시스템 Entity를 제공합니다.

| Entity | 대표어 | 
|--------|-------|
| sys.date | 오늘, 내일, 모레, 어제, 그제, 3일 전, 3일 후 등 |
| sys.month | 당월, 익월, 전월, 익익월, 전전월 등 |
| sys.year | 올해, 내년, 작년, 내후년, 재작년 등 |

위 대표어 이외에 당일, 이번달, 금년 등 일반적으로 사용하는 날짜 지칭 단어를 구분할 수 있도록 제공되고 있습니다.

{% include image.html file="entity/Entitiy_system_date01.png" max-width="900" caption="sys.date Entity 추가" %}


{% include image.html file="entity/Entitiy_system_date02.png" max-width="900" caption="sys.date 결과값 확인" %}

Intent에 날짜 Entity를 추가하고 날짜 지칭 단어가 들어가는 문장을 입력하면 단어가 숫자값으로 변환되어 들어오는 것을 확인할 수 있습니다. '오늘', '당월', '올해'를 0으로 잡고 기준으로 부터 떨어진 날짜수를 계산하여 반환하게 됩니다.  

=====Edit=====[대표 예시 연결?]()
 
#### 확인 Entity

확인 Entity는 긍정,부정,중립을 구분합니다. 예를 들어 봇에서 예, 아니오에 관한 질문이 나갔을때 사용자가 긍정적

| Entity | 대표어 | 
|--------|-------|
| sys.confirm | 예, 아니오, 대답회피 |

#### 일반 Entity


| Entity | 대표어 | 
|--------|-------|
| sys.any | N/A |

### 사용자정의 Entity

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [단어 추출(Entity)]" type="default" %}

**사용자정의 Entity**는 직접 정의하여 사용하는 Entity 입니다.




