---
title: API 노드 
tags: [chatflow, API, advanced]
keywords: Basic Conversation
summary: API 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_api.html
folder: danbeeDoc
previous: {
    title: Carousel 노드,
    url: chatflow_carousel.html
}
next: {
    title: Function 노드,
    url: chatflow_function.html
}
---

## API 노드

API 노드는 챗봇이 ‘날씨’, ‘검색’ 등과 같이 다양한 컨텐츠 서비스 정보를 활용하여 대답할 수 있도록 컨텐츠 서비스들과 연계하기 위해 관련 정보를 설정하는 노드입니다. 
컨텐츠 서비스들은 공공기관에서 오픈 된 컨텐츠 뿐만 아니라 기업 내에 제공하는 기간계 서비스들과도 연계가 가능합니다. 

Function 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](chatflow_api.html#기본정보)
- [API 설정](chatflow_api.html#api-설정)

{% include image.html file="chatflow/Chatflow_api_canvas.png"  caption="Api 노드" %}

### 기본정보

Api 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_api_basic.png"  caption="API노드 기본정보" %}

### API 설정

API 노드는 API관리 메뉴에 등록된 API들 중 하나를 선택하여 사용할 수 있습니다. 
동일한 API를 서로 다른 챗봇, 서로 다른 시나리오에서 쓰고자 할 경우,<br/>
매번 등록 설정해야하는 번거로움이 해소됩니다. <br/> 
아직 API관리메뉴에서 API를 등록하지 않았다면 아래 API관리 내용을 먼저 확인하시기 바랍니다. 

- [API 관리](external_API_management.html#API 관리)

아래는 미리 등록한 API 목록을 보여주는 '사용 API' 선택박스에서 하나의 API를 선택한 예시입니다.
API를 선택하여 '적용' 버튼을 누르면 등록해둔 Header, 요청 파라미터 등 기본 정보를 불러옵니다.<br/>
{% include note.html content="적용 버튼은 API를 테스트하는 역할을 합니다. 실제 사용을 위한 인증키 등은 사용자가 직접 발급받아야 합니다." %}
기본 정보 외에 추가로 Header나 요청 파라미터를 사용하고 싶다면 각 각의 추가버튼을 클릭하여 추가할 수 있습니다. 



{% include image.html file="chatflow/00_api_node_intro.png"  caption="API 선택" %}


API설정은 외부의 데이터 서비스와 연계시 서비스에 보내야할 요청 파라미터와 받아야할 출력 파라미터 정보를 설정합니다. 
API 설정은 2개의 Tab으로 구성이 됩니다.

- [요청 파라미터](chatflow_api.html#요청 파라미터)
- [출력 파라미터](chatflow_api.html#출력 파라미터)


#### 요청 파라미터

API 선택시 기본적으로 'API관리'에 등록되었던 Value 값은 초기화 됩니다. 
아래 화면처럼 고정된 값을 입력할 수 있으며, 어떤 파라미터값(챗플로우에 지정된)을 받아서 입력하고 싶다면 #{파라미터명}과 같이 입력할 수 있습니다.

{% include image.html file="chatflow/00_api_node_parameters.png"  caption="API노드 요청 파라미터s" %}

참고로 시스템에서 제공하는 파라미터도 사용가능합니다. 사용시 다른파라미터와 동일하게 사용가능합니다. ( 예 : #{@message} )  

| 시스템 파라미터 | 표기 | 설명 | 
|--------|-------|-------|
| 사용자 식별정보 | @userId | 사용자ID가 표시됩니다. (ex: email ) |
| 챗봇명 | @chatbotName | 챗봇 생성시 명명했던 이름이 표시됩니다.  |
| 채널아이디 | @channelId | 접속한 채널 아이디가 표시됩니다. <br/>(ex : 5-facebook / 3-kakaotalk / 2-line / 7-navertalk / 6-telegram / 4-slack)  |
| 받은 메시지 | @message | 사용자로부터 받은 질문 메시지 입니다. |
| 현재년도 | @currentDateYYYY | 현재년도 정보입니다. (예:2019) |
| 현재월 | @currentDateMM | 현재월 정보입니다. (예:12) |
| 현재일 | @currentDateDD | 현재일 정보입니다. (예:31) |
| 현재년월 | @currentDateYYYYMM | 현재년월 정보입니다. (예:201912) |
| 현재년월일 | @currentDateYYYYMMDD | 현재년월일 정보입니다. (예:20191231) |
| 현재시간 | @currentTimeHH | 현재시간 정보입니다. (예:23) |
| 현재분 | @currentTimeMI | 현재분 정보입니다. (예:59) |
| 현재초 | @currentTimeSS | 현재초 정보입니다. (예:59) |
| 현재요일 | @currentDateWeek | 현재요일 정보입니다. (예: 1:일, 2:월, 3:화, 4:수, 5:목, 6:금, 7:토) |
{: .table .table-striped}

#### 응답 파라미터 와 출력 파라미터s

API 서비스로 Request를 성공적으로 보냈다면 응답(Response) 결과를 받게 됩니다.<br/>
그 결과 데이터는 아래와 같이 Tree 로 표현되며, 이렇게 응답으로 받은 데이터를 '출력 파라미터'에 담아야 사용할 수 있습니다.<br/>
이 담는 역할을 하는 것이 '출력 파라미터s'에 추가한 변수와 이 변수에 매핑할 '응답 파라미터'의 Tree 경로입니다. 

응답으로 받은 데이터를 파라미터에 담기위해 매핑을 하는 방법에는 다음 두가지 방법이 있습니다.
 - '출력 파라미터s'의 JsonPath를 직접 입력(매핑할 경로 직접입력)
 - 'Api Tree'에서 노드를 drag&drop 으로 '출력 파라미터s' JsonPath 입력부로 끌어오기(매핑할 경로 자동 입력)

이와 같이 API Request를 통해 응답받은 데이터를 원하는 '출력 파라미터'에 담아 사용할 수 있습니다.
{% include image.html file="chatflow/00_api_node_response_tree.png"  caption="API 응답 데이터 매핑하기" %}

{% include note.html content="이제 배열과 JSON 객체를 원하는 파라미터에 담아 사용할 수 있습니다." %}

이제 중간 노드에 해당하는 경로를 '출력 파라미터s'의 변수로 매핑을 하면 해당 데이터 묶음을 사용할 수 있습니다.<br/>
다만 Function 노드를 이용해야 하며, 그 방법을 예시를 통해 알아보겠습니다.<br/>

응답 결과를 표시하는 Tree는 크게 Root, Node, Leaf로 구성되어있습니다.
- Root : 최상위를 의미 ($ 로 표시)
- 노드 : 데이터 구조의 중간지점을 의미하며 노드 명을 key 로 사용 (첫번째 노드 명이 'node1' 일경우 $.node1 로 표시)
- Leaf : 더이상 하위 Node가 없는 Node, 최하위 노드를 의미
{% include image.html file="chatflow/00_api_node_response_tree_desc.png"  caption="응답 파라미터 Tree" %}

아래 그림과같이 'test' 라는 '출력 파라미터' 변수에 데이터 묶음(JSON객체, 배열)을 담는다고 할 때,
{% include image.html file="chatflow/00_api_node_out_mapping.png"  caption="응답 파라미터 Tree" %}
JSON 객체의 경우<br/>
&nbsp;&nbsp; 'soap:Body' 라는 객체를 담는다고 할 경우, 해당 노드를 마우스로 드래그 하거나 '$.soap:Envelope.soap:Body' 를 직접 입력하여 매핑합니다.<br/>
배열의 경우 <br/>
&nbsp;&nbsp; 'newAddressListAreaCd' 라는 배열을 담을경우, 해당 노드를 마우스로 드래그 하거나 '$.NewAddressListResponse.newAddressListAreaCd' 를 직접 입력하여 매핑합니다.

매핑이 완료한 뒤 API 노드 다음에 Function 노드를 연결합니다.
{% include image.html file="chatflow/00_api_node_to_fn_node.png"  caption="응답 파라미터 Tree" %}
연결한 Function Node에서 각 경우에 맞게 데이터를 Parsing 하여 사용합니다.
{% include image.html file="chatflow/00_api_node_parsing.png"  caption="Function Node에서의 Parsing" %}










### 샘플 시나리오 (오늘 날씨 어때?)

#### 샘플 시나리오 설계

오늘 날씨에 대한 의도를 파악하고 API노드를 통해 '기상청'과 같이 날씨 컨텐츠를 제공하는 서비스와 연계를 하고 그 결과를 답변하는 시나리오로 구성되어 있습니다.

{% include image.html file="chatflow/Chatflow_sample_weather.png"  caption="샘플 시나리오(오늘날씨 어때?)" %}


#### [오늘날씨 요청] Listen 노드 설정

##### 파라미터 생성

날씨 API를 통해 얻어온 정보를 담기 위한 파라미터들을 생성합니다.

- [기상정보] : sky
- [최고온도] : tmax
- [최조온도] : tmin

{% include image.html file="chatflow/Chatflow_api_listen.png"  caption="파라미터 생성" %}

#### [날씨 API연계] Api 노드 설정

##### 파라미터 매핑

좌측에 API를 통해 조회된 Tree 구조의 정보에서 사용하고자 하는 우측 파라미터에 드래그 매핑 설정한다.
드래그 매핑을 하게 되면 Tree 구조에서 선택한 파라미터의 위치가 JsonPath 형태로 자동적으로 표시가 됩니다.

{% include image.html file="chatflow/Chatflow_api_drag.png"  caption="출력 파라미터 드래그 매핑 설정" %}

{% include image.html file="chatflow/Chatflow_api_output.png"  caption="파라미터 매핑" %}

#### [오늘날씨 알려줌] Speak 노드 설정

##### 답변 메시지 설정

Speak 노드에서 답변 메시지와 함께 API 노드에서 얻은 출력 파라미터들을 아래 그림과 같이 설정합니다.

{% include image.html file="chatflow/Chatflow_api_sampleSpeak.png"  caption="Speak 노드 설정" %}


#### 테스트

'오늘 날씨 어때?' 시나리오를 실행해 보면 아래와 같이 현재 기상정보를 답변하게 됩니다.

{% include image.html file="chatflow/Chatflow_api_sampleTest.png"  caption="오늘 날씨 어때? 시나리오 결과" %}
