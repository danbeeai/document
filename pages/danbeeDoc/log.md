---
title: 대화 이력 관리
tags: [log, nlu, chatflow]
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

danbee.Ai에서는 실 챗봇 사용 이력 확인할 수 있도록 다음 2가지 종류의 대화 이력 페이지를 제공하고 있습니다.
- [의도 추론 이력](log.html#의도-추론-이력)
- [대화흐름 이력](log.html#대화흐름-이력)

### 의도 추론 이력
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도추론 이력(Intent Log)]" type="default" %}

의도 추론 이력 페이지에서는 입력된 문장이 어떤 Intent로 파악됐는지 확인할 수 있습니다. 최대 7일간의 대화 이력을 볼 수 있으며 입력 문장 단위로 다음과 같은 정보들을 제공합니다.

#### 이력 정보

**요약 정보**

{% include image.html file="log/nlu_log_01.png" max-width="900" caption="의도 추론 이력 페이지" %}

| 구분 |  설명 |
|------|------|
| 대화내용 | 입력 문장을 보여줍니다. |
| Intent | 입력 문장이 파악된 대표 Intent를 보여줍니다. |
| Date | 입력 문장이 들어온 시간을 보여줍니다. |

**상세 정보**

{% include image.html file="log/nlu_log_02.png" max-width="900" caption="의도 추론 이력 상세" %}

| 구분 |  설명 |
|------|------|
| NLU 의도 분류 | NLU 타입 및 매칭율을 보여줍니다. |
| Intent | 입력 문장이 파악된 Intent를 보여줍니다. |
| Parameter | Intent 내에 존재하는 Parameter 값을 보여줍니다. 여러 Intent로 파악될 때는 해당 정보를 제공하지 않습니다. | 

{% include note.html content="NLU는 A, B, C 타입으로 나눠집니다." %}

#### 조회 조건

의도 추론 이력 페이지에서는 다음과 같이 다양한 조건으로 상세 조회가 가능합니다. 

- 일시
- Intent
- 대화내용

원하는 조회 조건을 설정 후 [조회] 버튼을 누르면 결과를 확인할 수 있습니다.

**일시** : 입력 문장이 들어온 시간 범위를 정하여 조회가 가능합니다.

{% include image.html file="log/nlu_log_filter_01.png" max-width="900" caption="의도 추론 이력 상세" %}

시작 날짜와 마지막 날짜를 선택하시고 시간 범위를 지정해주시면 해당 범위내에 들어온 로그만 확인할 수 있습니다.
 <br/>

**Intent** : 입력 문장이 어떤 Intent로 파악되었는지에 대하여 원하는 일부 Intent를 선택하여 조회가 가능합니다.

{% include image.html file="log/nlu_log_filter_02_1.png" max-width="900" caption="Intent 선택 팝업" %}

가운데 있는 조건을 선택하시면 위와 같이 Intent를 선택할 수 있는 팝업이 노출됩니다. 특정 Intent를 선택하고 싶으실 때는 '모든 Intent 선택' 체크 박스를 해제하고 원하는 Intent를 선택하시면 됩니다. Intent는 최대 10개까지 선택이 가능합니다.

{% include image.html file="log/nlu_log_filter_02_2.png" max-width="900" caption="Intent 선택" %}

선택한 Intent는 [선택된 Intent] 아래에서 확인할 수 있습니다.
 <br/>

**대화 내용** : 입력 문장이 포함하고 단어 또는 어구로 조회가 가능합니다.

{% include image.html file="log/nlu_log_filter_03.png" max-width="900" caption="의도 추론 이력 상세" %}






#### 필터링

상세 조회 후 다음 정보로 추가적인 필터링이 가능합니다.
 <br/>

{% include image.html file="log/nlu_log_filter_04.png" max-width="900" caption="의도 추론 필터 영역" %}

- Default Fallback 여부 : 봇이 어떤 Intent인지 파악하지 못한 문장을 포함할 것인가에 대한 여부를 선택합니다.

{% include image.html file="log/nlu_log_filter_04_2.png" max-width="900" caption="Default Fallback만 보기" %}

예를 들어 Default Fallback만 보면 해당 조회 조건 내에서 봇이 알아듣지 못한 문장만을 표시해줍니다.

#### 기타 기능

의도 추론 페이지를 보다 활용할 수 있도록 danbee.Ai에서는 문장을 Intent에 바로 추가할 수 있는 기능을 제공합니다. 문장을 기존 Intent에 추가에 추가하거나 혹은 새로운 Intent 생성하여 추가하실 수 있습니다.

{% include image.html file="log/nlu_log_add_intent_01.png" max-width="900" caption="다른 Intent에 추가" %}

위의 경우 '할롱'이라는 입력어가 어떤 의미인지 파악하지 못했으므로 해당 문장을 '안녕'아리는 Intent에 추가하려 합니다. 이때 이력 상세 우측 하단 [다른 Intent에 추가] 버튼을 누르면 등록되어 있는 Intent의 목록이 뜹니다. Intent 목록 중 원하는 Intent인 '안녕'을 선택하면 '할롱'이라는 문장이 '안녕'Intent 예문으로 즉시 등록되게 됩니다.

{% include image.html file="log/nlu_log_add_intent_02.png" max-width="900" caption="추가한 Intent 확인" %}

문장을 추가한 다음에는 상세 정보에서 해당 문장이 어디 추가되었는지를 확인할 수 있습니다.

{% include image.html file="log/nlu_log_add_intent_03.png" max-width="900" caption="새 Intent로 추가" %}

만약 분류할만한 Intent가 없다면 바로 새로운 Intent를 생성하여 예문으로 추가가 가능합니다.

{% include image.html file="log/nlu_log_add_intent_04.png" max-width="900" caption="Multi Intent에 즉시 추가" %}

마지막으로 해당 문장이 여러 Intent로 파악될 경우 최우측의 [+]버튼을 누르면 파악된 Intent에 예문으로 즉시 추가가 됩니다.

### 대화흐름 이력
{% include callout.html content="화면 위치 : [대화흐름(Chatflow)] > [대화흐름 이력(Chatflow Log)]" type="default" %}

대화흐름 이력 페이지에서는 해당 챗봇이 실제로 어떤 대화를 나누었는지 확인할 수 있습니다. 최대 7일간의 이력을 볼 수 있으며 대화 세션 단위로 다음과 같은 정보들을 제공합니다.

#### 이력 정보

**요약 정보**

{% include image.html file="log/chatflow_log_01.png" max-width="900" caption="대화흐름 이력 요약" %}

| 구분 |  설명 |
|------|------|
| 시작 Chatflow 명 | 해당 대화가 어떤 Chatflow로 시작되었는지를 보여줍니다. |
| Chatflow 수 | 한 대화 세션에서 몇 개의 Chatflow를 탔는지 보여줍니다. |
| Node 수 | 대화 속에서 사용된 총 Node 수를 보여줍니다. |
| Defualt Fallback 수 | 봇이 알아듣지 못한 문장 개수를 보여줍니다. |
| 감성 분석 | 대화 중 부정적인 감정으로 파악되는 입력 문장이 하나라도 있을 경우만 표시됩니다. |
| 대화 구분 | 대화 도중 이탈하였는지의 여부를 보여줍니다. |
| Date Time | 대화가 시작되고 끝난 시간을 보여줍니다. |

**상세 정보**

{% include image.html file="log/chatflow_log_02.png" max-width="900" caption="대화흐름 이력 상세" %}

| 구분 |  설명 |
|------|------|
| 일시 | 해당 문장이 입력된 시간을 보여줍니다. |
| 감정 | 입력된 문장이 어떤 감정 상태를 가졌는지 긍정/부정/중립으로 보여줍니다. |
| 대화 | 주고 받은 실제 대화를 보여줍니다. 버튼 또는 캐로셀 형태가 출력될 경우 해당 정보도 함께 보여줍니다. |
| Node Type | 현재 문장이 어떤 Node 종류를 타고 있는지 보여줍니다. |
| Node Name | 현재 문장이 타고 있는 Node의 이름을 보여 줍니다. |
| 연계 Intent/연계 파라미터 | 해당 문장이 어떤 Intent와 연결되었는지 보여줍니다. |
| 연계 Chatflow | 해당 문장이 어떤 Chatflow를 탔는지 보여줍니다. |


#### 조회 조건

대화흐름 이력 페이지에서는 다음과 같이 다양한 조건으로 상세 조회가 가능합니다.

- 일시
- Chatflow
- 대화 내용

상세 조회 방법은 [의도 추론 이력 조회 방법](log.html#조회-조건)과 동일하므로 자세한 설명은 생략합니다.

#### 필터링

상세 조회 후 다음 정보로 추가적인 필터링이 가능합니다.

{% include image.html file="log/chatflow_log_filter.png" max-width="900" caption="대화흐름 필터 영역" %}

- Default Fallback 여부 : 봇이 어떤 Intent인지 파악하지 못하거나 헷갈려한 대화를 포함하는가의 여부를 선택합니다.
- 부정 포함 여부 : 부정적인 답변이 포함되었는가의 여부를 선택합니다. 부정만 선택시 감성 분석 결과가 '부정'인 대화 이력들만 조회됩니다.
- 이탈 여부 : 대화도중 이탈한 대화 세션만 볼 것인가의 여부를 선택합니다. 이탈한 대화만 선택시 대화 구분이 '이탈'인 대화 이력들만 조회됩니다.

