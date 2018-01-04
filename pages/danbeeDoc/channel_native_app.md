---
title: Native App(API)
tags: [api,channel,messenger]
keywords: Basic Conversation
summary:  danbee.Ai의 API를 활용하여 직접만든 대화채널에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_native_app.html
folder: danbeeDoc
previous: {
    title: 프로그(단비에이아이웹채널),
    url: channel_frogu.html
}
next: {
    title: 페이스북,
    url: channel_facebook.html
}
---

# Native App(API)
채널에서 danbee.Ai 와 연계하기 위해 제공되는 API들과 각 이벤트시에 처리되고 활용되는 데이터 항목에 대해 설명한다.

## Welcome 메시지 API
대화 채널이 처음 사용자와 대화가 시작될때 챗봇이 먼저 인사를 하거나 메뉴 선택지를 제공하고자 할 경우 사용하는 API다.

### 기본 정보

| Field | Infomation |
|--------|--------|
| URL | https://danbee.ai/chatflow/welcome.do |
| METHOD | POST |
| HEADER | "Content-Type" : "application/json;charset=UTF-8" |

### REQUEST 정보 

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| chatbot_id | String | Yes | 챗봇아이디 |
| parameters | JSON | No | 전체 파라미터 정보 (전달할 파라미터가 있는 경우 key, value 값을 전달해야 합니다.) |

### RESPONSE 정보

| KEY | TYPE | Required | Description |
|--------|--------|--------|--------|
| version | String | No | 버전 |
| chatbot_id | String | No | 챗봇 아이디 |
| user_id | String | No | 사용자 아이디 |
| input_sentence | String | No | 사용자 대화 문장 |
| session_id | String | Yes | 대화 세션 아이디(대화창이 오픈되어 끝날 때까지의 대화이력을 식별할 수 있는 정보) |
| ins_id | String | Yes | 챗플로우 인스턴스 아이디 (챗플로우 단위의 대화가 진행될 때 마다 채번되는 인스턴스 아이디) |
| intent_id | String | Yes | 인텐트 아이디 (Slot 노드, Carousel 노드에서 사용함) |
| node_id | String | Yes | 노드 아이디 |
| param_id | String | Yes | 파라미터 아이디 (Slot 노드, Carousel 노드 경우 사용됨) |
| ref_intent_id | String | No | 인텐트 아이디 (참조) |
| chatflow_id | String | No | 챗플로우 아이디 |
| another_result | JSON Array  | No | NLU 에서 파악한 다른 의도 결과 |
| result | JSON Array | No | 답변 메시지 결과 정보 |
| parameters | JSON | No | 파라미터 정보 (내부 파라미터 정보가 표시됩니다)|
| evaluate_setting | String | No | 채널 사용자 평가 문장 사용 여부 (제휴기능) |
| emotions | JSON | No | 감정 정보 (감성정보 설정시에만 값이 표시됩니다)|
| debugCode | String | No | 디버그 코드정보|
| debugMsg | String | No | 디버그 메시지|
| resultStatus | JSON | No | 결과 상태정보|

#### RESPONSE Object 정보
* another_result Object

| KEY | Description |
|--------|--------|
| object_match_rate | 인텐트 매칭률 |
| intent_name | 인텐트 명 |
| intent_id | 인텐트 아이디 |
| intent_alias | 인텐트 별명 |

 * result Object

| KEY | Description |
|--------|--------|
| message | 노드에 설정된 메시지를 표시합니다. |
| imgRoute | 메시지에 표시될 이미지 정보가 표시됩니다. |
| optionList | 버튼, 팝업, 전화연결과 같은 설정정보가 표시됩니다. |
| carouselList | 캐로셀 노드의 카드 정보가 표시됩니다 |

 * parameters Object

| KEY | Description |
|--------|--------|
| 인텐트에 정의된 파라미터 Key | 대화 흐름 시 전달된 파라미터 Value |

 * emotions Object

| KEY | Description |
|--------|--------|
| positive | 긍정 확률 |
| neutral | 중립 확률 |
| negative | 부정 확률 |

 * resultStatus Object
 
| KEY | Description |
|--------|--------|
| resultCmt | 결과 코멘트 |
| resultCode | 결과 코드 |
| resultMsg | 결과 메시지 |
 

## 대화 엔진 API 
대화 채널에서 주고받는 대화를 처리하는 API. 사용자의 질문의 의도를 파악하고 그에 따른 대화흐름을 관리하는 챗플로우를 사용하는 API다.

### 기본 정보

| Field | Infomation |
|--------|--------|
| URL | https://danbee.ai/chatflow/engine.do |
| METHOD | POST |
| HEADER | "Content-Type" : "application/json;charset=UTF-8" |

### REQUEST 정보 

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| chatbot_id | String | Yes | 챗봇아이디 |
| input_sentence | String | Yes | 사용자 대화 문장 |
| user_id | String | No | 사용자 아이디 |
| session_id | String | No | 대화 세션 아이디(대화창이 오픈되어 끝날 때까지의 대화이력을 식별할 수 있는 정보) |
| ins_id | String | No | 챗플로우 인스턴스 아이디 (챗플로우 단위의 대화가 진행될 때 마다 채번되는 인스턴스 아이디) |
| intent_id | String | No | 인텐트 아이디 (Slot 노드, Carousel 노드에서 사용함) |
| node_id | String | No | 노드 아이디 |
| param_id | String | No | 파라미터 아이디 (Slot 노드, Carousel 노드 경우 사용됨) |
| chatflow_id | String | No | 챗플로우 아이디 |
| parameters | JSON | No | 전체 파라미터 정보 (전달할 파라미터가 있는 경우 key, value 값을 전달해야 합니다.) |

#### REQUEST Object 정보

 * parameters Object

| KEY | Description |
|--------|--------|
| 인텐트에 정의된 파라미터 Key | 대화 흐름 시 전달된 파라미터 Value |

### RESPONSE 정보

| KEY | TYPE | Required | Description |
|--------|--------|--------|--------|
| version | String | No | 버전 |
| chatbot_id | String | No | 챗봇 아이디 |
| user_id | String | No | 사용자 아이디 |
| input_sentence | String | No | 사용자 대화 문장 |
| session_id | String | Yes | 대화 세션 아이디(대화창이 오픈되어 끝날 때까지의 대화이력을 식별할 수 있는 정보) |
| log_id | int | Yes | 챗봇 대화의 로그 아이디 ( 사용자 평가 시 사용 )  |
| ins_id | String | Yes | 챗플로우 인스턴스 아이디 (챗플로우 단위의 대화가 진행될 때 마다 채번되는 인스턴스 아이디) |
| intent_id | String | Yes | 인텐트 아이디 (Slot 노드, Carousel 노드에서 사용함) |
| node_id | String | Yes | 노드 아이디 |
| param_id | String | Yes | 파라미터 아이디 (Slot 노드, Carousel 노드 경우 사용됨) |
| ref_intent_id | String | No | 인텐트 아이디 (참조) |
| chatflow_id | String | No | 챗플로우 아이디 |
| another_result | JSON Array | No | NLU 에서 파악한 다른 의도 결과 |
| result | JSON Array | No | 답변 메시지 결과 정보 |
| parameters | JSON | No | 파라미터 정보 (내부 파라미터 정보가 표시됩니다)|
| emotions | JSON | No | 감정 정보 (감성정보 설정시에만 값이 표시됩니다)|
| evaluate_setting | String | No | 채널 사용자 평가 문장 사용 여부 (제휴기능) |
| debugCode | String | No | 디버그 코드정보|
| debugMsg | String | No | 디버그 메시지|
| resultStatus | JSON | No | 결과 상태정보|

#### RESPONSE Object 정보
* another_result Object

| KEY | Description |
|--------|--------|
| object_match_rate | 인텐트 매칭률 |
| intent_name | 인텐트 명 |
| intent_id | 인텐트 아이디 |
| intent_alias | 인텐트 별명 |

 * result Object

| KEY | Description |
|--------|--------|
| message | 노드에 설정된 메시지를 표시합니다. |
| imgRoute | 메시지에 표시될 이미지 정보가 표시됩니다. |
| optionList | 버튼, 팝업, 전화연결과 같은 설정정보가 표시됩니다. |
| carouselList | 캐로셀 노드의 카드 정보가 표시됩니다 |

 * parameters Object

| KEY | Description |
|--------|--------|
| 인텐트에 정의된 파라미터 Key | 대화 흐름 시 전달된 파라미터 Value |

 * emotions Object

| KEY | Description |
|--------|--------|
| positive | 긍정 확률 |
| neutral | 중립 확률 |
| negative | 부정 확률 |

 * resultStatus Object
 
| KEY | Description |
|--------|--------|
| resultCmt | 결과 코멘트 |
| resultCode | 결과 코드 |
| resultMsg | 결과 메시지 |
 
## Node Option Object
노드 옵션 기능은 챗봇의 답변을 표시하는 speak 노드, slot 노드, carousel 노드에서 설정할 수 있습니다. <figure><img class="docimage" src="images/channel/nptive/nptive_app_node_option.png" alt="Frogue 셋팅" style="max-width: 800px"></figure>

 * 노드 옵션의 정보는 아래와 같습니다. 
 
| 구분 | 속성 설명 |
|--------|--------|
| id | 옵션 아이디가 순서대로 설정됩니다. |
| type | 6 가지의 옵션 구분값이 표시됩니다. |
| label | 채널 화면에서 보여질 명칭이 표시됩니다. |
| value | 채널에서 옵션에 따라 처리할 정보가 표시됩니다. |

 * 노드 옵션의 유형에는 아래와 같습니다.
 
| 구분 | 유형값 | 기능설명 |
|--------|--------|--------|
| 선택지 | btn | 사용자의 답변을 선택지로 받기 위한 정보를 설정합니다. |
| Web Link | link | 웹 팝업을 호출하기위 위한 정보를 설정합니다. |
| 내부 App 실행 | inApp | 스마트폰에서 내부 App 실행을 하기 위한 정보를 설정합니다. |
| 외부 App 실행 | outApp | 스마트폰에서 외부 App 실행을 하기 위한 정보를 설정합니다. |
| Call (전화연결) | call | 스마트폰에서 전화연결을 하기 위한 정보를 설정합니다. |
| Chatflow 호출 | callFlow | 다른 Chatflow 를 진행하기 위한 정보를 설정합니다. |
 

## 사용자 대화 평가 API 
대화 채널에서 챗봇 대화에 대해서 사용자 평가를 처리하는 API. 챗봇에 대답에 대해 약 7가지의 평가를 진행할 수 있다.
 * like : 좋아요
 * love : 사랑해요
 * haha : 빵터짐
 * yay : 흐믓해요
 * wow : 놀라워요
 * sad : 슬퍼요
 * angry : 화나요
 * bad   : 싫어요

### 기본 정보

| Field | Infomation |
|--------|--------|
| URL | https://danbee.ai/chatflow/evaluateMsg.do |
| METHOD | POST |
| HEADER | "Content-Type" : "application/json;charset=UTF-8" |

### REQUEST 정보 

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| log_id | int | Yes | 로그아이디 |
| evaluate_flag | String | Yes | 평가 |

### RESPONSE 정보

| KEY | TYPE | Required | Description |
|--------|--------|--------|--------|
| code | String | Yes | 결과코드  |
| result | JSON | No | 결과 |

#### RESPONSE Object 정보
* result Object

| KEY | Description |
|--------|--------|
| log_id | 로그아이디 |
| evaluate_flag | 평가 |


#### RESPONSE resultStatus 유형

| Code | Description |
|--------|--------------------------|
| 200 | 정상코드 |
| 201 | 여러가지 의도로 해석되는 경우 |
| 400 | [NLU] 의도 파악이 안되었을 경우, EngineHandler 예외상황 |
| 404 | [Chatflow] Intent에 해당하는 flow를 찾지 못할 경우, 노드가 10번이상 진행될 경우, EngineService 예외상황 |
| 405 | [Chatflow] flow 설정 문제 (답변 메시지를 못 찾았을 때, 분기 오류인 경우) |


