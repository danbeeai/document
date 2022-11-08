---
title: 대화 이력 관리 
tags: [log, nlu, chatflow, basic]
keywords: Basic Conversation
summary: 챗봇 사용 이력을 확인합니다.
sidebar: danbee_doc_sidebar
permalink: log.html
folder: danbeeDoc
previous: {
    title: 단비와 연결 가능한 채널,
    url: channel_connection_settings.html
}
next: {
    title: 학습 추천,
    url: learning_recommend.html
}
---

단비Ai에서는 실 챗봇 사용 이력 확인할 수 있도록 다음 2가지 종류의 대화 이력 페이지를 제공하고 있습니다.

- [의도 추론 이력](log.html#의도-추론-이력)
- [대화 흐름 이력](log.html#대화 흐름-이력)

## 의도 추론 이력
{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 운영 > 대화 의도 이력" type="default" %}

{% include image.html file="log/nlu_log_01.png"  caption="의도 추론 이력 페이지" %}

의도 추론 이력 페이지에서는 입력된 문장이 어떤 Intent로 파악됐는지 확인할 수 있습니다. 최대 7일간의 대화 이력을 볼 수 있으며 입력 문장 단위로 다음과 같은 정보들을 제공합니다.

### 이력 목록
>##### 대화 의도
실행된 대화 의도입니다.
##### 대화 내용
사용자가 입력한 문장입니다.
##### 추론률
추론한 결과의 신뢰도입니다.
##### 학습한 대화 의도
해당 이력을 대화 의도에 학습했다면 학습한 대화 의도에 나타납니다.
##### 채널구분
대화가 이루어진 채널입니다.


### 이력 상세 정보
{% include image.html file="log/0_1.PNG" %}
>##### NLU 의도 분류
의도 추론이 완료된 단계 입니다. A, B, C단계가 있으며 자세한 내용은 [챗봇 추론 설정](settings_nlu.html)을 참고해주세요.
##### 대화 의도
실행된 대화 의도입니다.
##### 파라미터
대화에 의해 입력된 파라미터입니다.
##### 학습추가
해당 대화를 대화 의도에 추가합니다.


### 의도 추론 이력 검색
{% include image.html file="log/0_2.PNG" %}
3가지 필터를 이용해 의도 추론 이력을 검색할 수 있습니다.

>##### 기간
시작 날짜와 끝 날짜를 설정해 이력을 조회할 기간을 설정합니다.
##### 대화 의도
대화 의도를 선택하여 특정 대화 의도만의 이력을 조회합니다.
##### Default Fallback
추론 실패한 경우를 필터링하여 조회합니다.


## 대화 흐름 이력

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 운영 > 대화 흐름 이력" type="default" %}
{% include image.html file="log/1_0.PNG" %}
대화 흐름 이력 페이지에서는 해당 챗봇이 실제로 어떤 대화를 나누었는지 확인할 수 있습니다. 최대 7일간의 이력을 볼 수 있으며 대화 세션 단위로 다음과 같은 정보들을 제공합니다.

### 이력 목록
>##### 대화 흐름명
대화가 시작된 대화 흐름명입니다.
##### 시간
대화가 이루어진 시간입니다.
##### 노드 수
대화 속에서 사용된 총 노드 수 입니다.
##### Default Fallback
봇이 알아듣지 못한 문장 갯수입니다.
##### 감정분석
대화 중 부정적인 감정으로 파악되는 입력 문장이 하나라도 있을 경우만 표시됩니다.
##### 대화 구분
대화 도중 이탈 여부입니다.
##### 대화종료 구분
현재 대화 상태입니다.

### 상세 정보
{% include image.html file="log/1_1.PNG" %}
>##### 대화
주고 받은 실제 대화를 보여줍니다. 버튼 또는 캐로셀 형태가 출력될 경우 해당 정보도 함께 보여줍니다.
##### 노드 타입
현재 문장의 노드 타입입니다.
##### 대화감정
입력된 문장이 어떤 감정 상태를 가졌는지 긍정/부정/중립으로 보여줍니다.
##### 대화평가
주고 받은 실제 대화를 보여줍니다. 버튼 또는 캐로셀 형태가 출력될 경우 해당 정보도 함께 보여줍니다.
##### 연계 대화 의도/파라미터
해당 문장이 어떤 대화 의도와 연결되었는지 보여줍니다.
##### 연계 대화 흐름
해당 문장이 어떤 대화 흐름을 탔는지 보여줍니다.

### 대화 흐름 이력 검색
{% include image.html file="log/1_2.PNG" %}
>##### 기간
시작 날짜와 끝 날짜를 설정해 이력을 조회할 기간을 설정합니다.
##### 대화 흐름
대화 흐름을 선택하여 특정 대화 흐름만의 이력을 조회합니다.
##### 기타 필터 적용하기
기타 여러가지 기준으로 필터를 적용하여 이력을 조회합니다.



## 의도추론이력 조회 API
의도추론이력을 일자별로 조회 가능한 API. 

의도추론이력 다운로드 KEY 발급은 [의도추론 이력 관리-다운로드-api-key-관리](log.html#다운로드-api-key-관리) 에서 확인 가능합니다.

### 기본 정보

| Field | Infomation |
|--------|--------|
| URL | https://danbee.ai/chatbot/chatbotlog/nlu/retrieve |
| METHOD | GET |
| HEADER | "Content-Type" : "application/json;charset=UTF-8" |
{: .table .table-striped}

### REQUEST 정보 

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| chatbotId | String | Yes | 챗봇아이디 |
| baseDate | String | Yes | 기준일자 ( YYYYMMDD : 예 - 20180101 ) |
| apiKey | String | Yes | 챗봇 이력 다운로드 키 ( 의도추론이력 화면에서 생성 및 조회 가능 ) |
{: .table .table-striped}

### REQUEST 브라우저 테스트
아래의 예시로 브라우저에서 간단히 테스트가 가능함.

https://danbee.ai/chatbot/chatbotlog/nlu/retrieve?chatbotId=챗봇아이디&baseDate=년월일&apiKey=XXXXXXXXXXXXXXXXX

### RESPONSE 정보

| KEY | TYPE | Required | Description |
|--------|--------|--------|--------|
| logId | String | Yes | 의도추론이력 로그 아이디 |
| logSdatetime | Date | Yes | 의도추론 이력 시작일시 |
| logDatetime | Date | Yes | 의도추론 이력 일시 |
| inputSentence | String | Yes | 사용자 입력 문장 |
| intentId | String | No | 의도추론 아이디 |
| intentName | String | No | 의도추론 명 |
| resultScore | Number | No | 의도 추론율 |
| opIntentId | String | No | 의도추론 아이디 ( 의도추론 상세화면에서 설정된 값 ) |
| userId | String | Yes | 사용자 아이디 ( 채널별로 형식이 상이함 ) |
| chatSessionId | Number | Yes | 챗봇과 사용자 대화 세션 아이디 |
{: .table .table-striped}

## 대화이력 조회 API
대화 이력을 일자별로 조회 가능한 API. 제휴회원만 사용가능.

대화이력 다운로드 KEY 발급은 [대화 이력 관리-다운로드-api-key-관리](log.html#다운로드-api-key-관리) 에서 확인 가능합니다.

### 기본 정보

| Field | Infomation |
|--------|--------|
| URL | https://danbee.ai/chatbot/chatbotlog/chatflow/retrieve |
| METHOD | GET |
| HEADER | "Content-Type" : "application/json;charset=UTF-8" |
{: .table .table-striped}

### REQUEST 정보 

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| chatbotId | String | Yes | 챗봇아이디 |
| baseDate | String | Yes | 기준일자 ( YYYYMMDD : 예 - 20180101 ) |
| apiKey | String | Yes | 챗봇 이력 다운로드 키 ( 대화이력 화면에서 생성 및 조회 가능 ) |
{: .table .table-striped}

### REQUEST 브라우저 테스트
아래의 예시로 브라우저에서 간단히 테스트가 가능함.

https://danbee.ai/chatbot/chatbotlog/chatflow/retrieve?chatbotId=챗봇아이디&baseDate=년월일&apiKey=XXXXXXXXXXXXXXXXX

### RESPONSE 정보

| KEY | TYPE | Required | Description |
|--------|--------|--------|--------|
| logId | Number | Yes | 대화이력 로그 아이디 |
| sessionId | Number | Yes | 챗봇과 사용자 대화 세션 아이디 |
| flowId | String | Yes | 대화 흐름 아이디 |
| flowName | String | Yes | 대화 흐름 명 |
| nodeName | String | No | 노드 명 |
| nodeType | String | No | 노드 유형 |
| userId | String | No | 사용자 아이디 ( 채널별로 형식이 상이함 ) |
| message | String | No | 사용자 또는 챗봇의 대화내용 |
| createDate | String | Yes | 로그 생성 일시 |
| updateDate | String | Yes | 로그 수정 일시 |
| neg | Number | No | 대화내용 감정 부정 수치 |
| neu | Number  | No | 대화내용 감정 중립 수치 |
| pos | Number | No | 대화내용 감정 긍정 수치 |
{: .table .table-striped}

## 대화이력 API 엑셀로 불러오기
대화이력 API를 엑셀에서 사용하는 방법을 공유드립니다.

<ol>
    <li>
        엑셀에서 "데이터 > 새쿼리 > 기타 원본에서 > 웹"을 선택합니다.
        {% include image.html file="log/excel_webquery01.png"  caption="엑셀에서 새쿼리에서 웹 선택" %}
    </li>
    <li>
        API 조건에 맞는 URL을 입력하여 데이터를 가져옵니다.
        <ul>
            <li>
                대화의도이력 URL 
                https://danbee.ai/chatbot/chatbotlog/nlu/retrieve?chatbotId=챗봇아이디&baseDate=년월일&apiKey=XXXXXXXXXXX
             </li>
             <li>
                대화흐름이력 URL 
                https://danbee.ai/chatbot/chatbotlog/chatflow/retrieve?chatbotId=챗봇아이디&baseDate=년월일&apiKey=XXXXXXXXXXX
             </li>
         </ul>
        챗봇아이디와 특정년월일, API까지 입력하시면됩니다.        
        https://danbee.ai/chatbot/chatbotlog/chatflow/retrieve?chatbotId=bbec1b2a-0722-41d9-ac3a-e7a9edf481d3&baseDate=20210430&apiKey=c258ce022faa9e3f9dd6ebf5e4e8f722531e2680e7adb9b4f381926b93573a
        {% include image.html file="log/excel_webquery02.png" caption="대화이력 url 입력" %}        
    </li>
    <li>
        왼쪽 상단에 있는 [테이블로] 버튼을 클릭하고, 옵션을 구분자 "없음"을 선택합니다.
        {% include image.html file="log/excel_webquery03.png" caption="테이블로 클릭" %}
        {% include image.html file="log/excel_webquery04.png" caption="옵션 없음 선택" %}
    </li>
    <li>
        엑셀 테이블이 하나 생깁니다. 이때 "새 행으로 확장"한 후에 데이터를 불러 옵니다.
        {% include image.html file="log/excel_webquery05.png" caption="필터에서 새 행으로 확장 클릭" %}
        {% include image.html file="log/excel_webquery06.png" caption="필터를 눌러 데이터를 가져온다." %}
    </li>
    <li>
        [닫기 및 로드]를 클릭하여 데이터 가져오기를 하면 대화이력을 깔끔하게 엑셀로 받으실 수 있습니다.
        {% include image.html file="log/excel_webquery07.png" caption="닫기 및 로드 클릭" %}
        {% include image.html file="log/excel_webquery08.png" caption="대화이력 데이터 엑셀화면에 표시" %}
    </li>
</ol>



<!-- 

| 구분 |  설명 |
|------|------|
| 대화내용 | 입력 문장을 보여줍니다. |
| 대화 의도 | 입력 문장이 파악된 대표 Intent를 보여줍니다. |
| Date | 입력 문장이 들어온 시간을 보여줍니다. |
{: .table .table-striped}

**상세 정보**

{% include image.html file="log/nlu_log_02.PNG"  caption="의도 추론 이력 상세" %}

| 구분 |  설명 |
|------|------|
| NLU 의도 분류 | NLU 타입 및 매칭율을 보여줍니다. |
| 대화 의도 | 입력 문장이 파악된 Intent를 보여줍니다. |
| 파라미터 | 대화 의도 내에 존재하는 파라미터 값을 보여줍니다. 여러 Intent로 파악될 때는 해당 정보를 제공하지 않습니다. | 
{: .table .table-striped}

{% include note.html content="NLU는 A, B, C 타입으로 나눠집니다." %}

#### 조회 조건

의도 추론 이력 페이지에서는 다음과 같이 다양한 조건으로 상세 조회가 가능합니다. 

- 일시
- Intent
- 대화내용

원하는 조회 조건을 설정 후 [조회] 버튼을 누르면 결과를 확인할 수 있습니다.

**일시** : 입력 문장이 들어온 시간 범위를 정하여 조회가 가능합니다.

{% include image.html file="log/nlu_log_filter_01.PNG"  caption="의도 추론 이력 상세" %}

시작 날짜와 마지막 날짜를 선택하시고 시간 범위를 지정해주시면 해당 범위내에 들어온 로그만 확인할 수 있습니다.
 <br/>

**Intent** : 입력 문장이 어떤 Intent로 파악되었는지에 대하여 원하는 일부 Intent를 선택하여 조회가 가능합니다.

{% include image.html file="log/nlu_log_filter_02_1.PNG"  caption="대화 의도 선택 팝업" %}

가운데 있는 조건을 선택하시면 위와 같이 Intent를 선택할 수 있는 팝업이 노출됩니다. 특정 Intent를 선택하고 싶으실 때는 '모든 대화 의도 선택' 체크 박스를 해제하고 원하는 Intent를 선택하시면 됩니다. Intent는 최대 10개까지 선택이 가능합니다.

{% include image.html file="log/nlu_log_filter_02_2.PNG"  caption="대화 의도 선택" %}

선택한 Intent는 [선택된 Intent] 아래에서 확인할 수 있습니다.
 <br/>

**대화 내용** : 입력 문장이 포함하고 단어 또는 어구로 조회가 가능합니다.

{% include image.html file="log/nlu_log_filter_03.PNG"  caption="의도 추론 이력 상세" %}






#### 필터링

상세 조회 후 다음 정보로 추가적인 필터링이 가능합니다.
 <br/>

{% include image.html file="log/nlu_log_filter_04.PNG"  caption="의도 추론 필터 영역" %}

- Default Fallback 여부 : 봇이 어떤 Intent인지 파악하지 못한 문장을 포함할 것인가에 대한 여부를 선택합니다.

{% include image.html file="log/nlu_log_filter_04_2.PNG"  caption="Default Fallback만 보기" %}

예를 들어 Default Fallback만 보면 해당 조회 조건 내에서 봇이 알아듣지 못한 문장만을 표시해줍니다.

#### 기타 기능

의도 추론 페이지를 보다 활용할 수 있도록 단비Ai에서는 문장을 대화 의도에 바로 추가할 수 있는 기능을 제공합니다. 문장을 기존 대화 의도에 추가에 추가하거나 혹은 새로운 대화 의도 생성하여 추가하실 수 있습니다.

{% include image.html file="log/nlu_log_add_intent_01.PNG"  caption="다른 대화 의도에 추가" %}

위의 경우 '할롱'이라는 입력어가 어떤 의미인지 파악하지 못했으므로 해당 문장을 '안녕'아리는 대화 의도에 추가하려 합니다. 이때 이력 상세 우측 하단 [다른 대화 의도에 추가] 버튼을 누르면 등록되어 있는 대화 의도의 목록이 뜹니다. 대화 의도 목록 중 원하는 Intent인 '안녕'을 선택하면 '할롱'이라는 문장이 '안녕'대화 의도 예문으로 즉시 등록되게 됩니다.

{% include image.html file="log/nlu_log_add_intent_02.PNG"  caption="추가한 대화 의도 확인" %}

문장을 추가한 다음에는 상세 정보에서 해당 문장이 어디 추가되었는지를 확인할 수 있습니다.

{% include image.html file="log/nlu_log_add_intent_03.PNG"  caption="새 Intent로 추가" %}

만약 분류할만한 Intent가 없다면 바로 새로운 Intent를 생성하여 예문으로 추가가 가능합니다.

{% include image.html file="log/nlu_log_add_intent_04.PNG"  caption="Multi 대화 의도에 즉시 추가" %}

마지막으로 해당 문장이 여러 Intent로 파악될 경우 최우측의 [+]버튼을 누르면 파악된 대화 의도에 예문으로 즉시 추가가 됩니다.

### 대화 흐름 이력
{% include callout.html content="화면 위치 : [대화 흐름 ] > [대화 흐름 이력(대화 흐름 Log)]" type="default" %}

대화 흐름 이력 페이지에서는 해당 챗봇이 실제로 어떤 대화를 나누었는지 확인할 수 있습니다. 최대 7일간의 이력을 볼 수 있으며 대화 세션 단위로 다음과 같은 정보들을 제공합니다.

#### 이력 정보

**요약 정보**

{% include image.html file="log/chatflow_log_01.PNG"  caption="대화 흐름 이력 요약" %}

| 구분 |  설명 |
|------|------|
| 시작 대화 흐름 명 | 해당 대화가 어떤 대화 흐름으로 시작되었는지를 보여줍니다. |
| 대화 흐름 수 | 한 대화 세션에서 몇 개의 대화 흐름을 탔는지 보여줍니다. |
| 노드 수 | 대화 속에서 사용된 총 노드 수를 보여줍니다. |
| Defualt Fallback 수 | 봇이 알아듣지 못한 문장 개수를 보여줍니다. |
| 감성 분석 | 대화 중 부정적인 감정으로 파악되는 입력 문장이 하나라도 있을 경우만 표시됩니다. |
| 대화 구분 | 대화 도중 이탈하였는지의 여부를 보여줍니다. |
| Date Time | 대화가 시작되고 끝난 시간을 보여줍니다. |
{: .table .table-striped}

**상세 정보**

{% include image.html file="log/chatflow_log_02.PNG"  caption="대화 흐름 이력 상세" %}

| 구분 |  설명 |
|------|------|
| 일시 | 해당 문장이 입력된 시간을 보여줍니다. |
| 감정 | 입력된 문장이 어떤 감정 상태를 가졌는지 긍정/부정/중립으로 보여줍니다. |
| 대화 | 주고 받은 실제 대화를 보여줍니다. 버튼 또는 캐로셀 형태가 출력될 경우 해당 정보도 함께 보여줍니다. |
| 노드 Type | 현재 문장이 어떤 노드 종류를 타고 있는지 보여줍니다. |
| 노드명  | 현재 문장이 타고 있는 노드의 이름을 보여 줍니다. |
| 연계 Intent/연계 파라미터 | 해당 문장이 어떤 Intent와 연결되었는지 보여줍니다. |
| 연계 대화 흐름 | 해당 문장이 어떤 대화 흐름을 탔는지 보여줍니다. |
{: .table .table-striped}

#### 조회 조건

대화 흐름 이력 페이지에서는 다음과 같이 다양한 조건으로 상세 조회가 가능합니다.

- 일시
- Chatflow
- 대화 내용

상세 조회 방법은 [의도 추론 이력 조회 방법](log.html#조회-조건)과 동일하므로 자세한 설명은 생략합니다.

#### 필터링

상세 조회 후 다음 정보로 추가적인 필터링이 가능합니다.

{% include image.html file="log/chatflow_log_filter.PNG"  caption="대화 흐름 필터 영역" %}

- Default Fallback 여부 : 봇이 어떤 Intent인지 파악하지 못하거나 헷갈려한 대화를 포함하는가의 여부를 선택합니다.
- 부정 포함 여부 : 부정적인 답변이 포함되었는가의 여부를 선택합니다. 부정만 선택시 감성 분석 결과가 '부정'인 대화 이력들만 조회됩니다.
- 이탈 여부 : 대화도중 이탈한 대화 세션만 볼 것인가의 여부를 선택합니다. 이탈한 대화만 선택시 대화 구분이 '이탈'인 대화 이력들만 조회됩니다.


## 다운로드 API KEY 관리

제휴회원인 경우 대화이력을 조회 할 수 있는 API 가 제공됩니다.

해당 화면에서 대화이력 조회 API 키를 발급받아 사용가능합니다.

API 사용법은 [의도추론이력 조회 API](channel_native_app.html#의도추론이력-조회-api) / [대화이력 조회 API](channel_native_app.html#대화이력-조회-api)에서 확인 가능합니다.

 -->


{% include bottom.html %}
