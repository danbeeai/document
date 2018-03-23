---
title: API 노드
tags: [chatflow, API]
keywords: Basic Conversation
summary: Api 노드에 대한 이해와 설정하는 방법을 설명합니다.
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
- [기본정보](Chatflow_api.html#기본정보)
- [API 설정](Chatflow_api.html#API 설정)

{% include image.html file="chatflow/Chatflow_api_canvas.png" max-width="900" caption="Api 노드" %}

### 기본정보

Api 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_api_basic.png" max-width="900" caption="API노드 기본정보" %}

### API 설정

API 노드는 기존에 등록 관리되고 있는 API들을 불러와 선택 설정하는 방식으로 구성이 되어 있습니다. 
이는 동일한 API 서비스를 서로 다른 챗봇, 서로 다른 시나리오에서 쓰고자 할 경우 매번 등록 설정해야하는 번거로움을 해소하고자 별도의 API들을 관리하고 불러서 사용하는 방식으로 구성된 이유이기도 합니다. 
API관리에 대해 자세히 알고자 할 경우 아래 API관리 내용을 확인하시기 바랍니다. 

- [API 관리](external_API_management.html#API 관리)

아래는 API관리에 등록되어 있는 API들을 '사용 API' 선택박스에서 선택하는 그림입니다.
API를 선택하게 되면 기본적으로 등록되었던 정보들이 화면에 표시되며, 추가적인 Parameter를 사용하고 싶다면 Custom Request Parameter에 등록하여 사용하시면 됩니다. 

{% include image.html file="chatflow/Chatflow_api_select.png" max-width="900" caption="API 선택" %}


API설정은 외부의 데이터 서비스와 연계시 서비스에 보내야할 요청 Parameter와 받아야할 출력 Parameter 정보를 설정합니다. 
API 설정은 2개의 Tab으로 구성이 됩니다.

- [요청 Parameter](Chatflow_api.html#요청 Parameter)
- [출력 Parameter](Chatflow_api.html#출력 Parameter)


#### 요청 Parameter

API 선택시 기본적으로 'API관리'에 등록되었던 기본 값들이 value 값으로 초기화 됩니다. 
화면처럼 고정된 값을 value 값으로 입력할 수 있으며, 어떠한 입력값을 받아 Request Parameter로 던지고 싶다면 #{변수명}과 같이 변수값을 지정할 수도 있습니다.

{% include image.html file="chatflow/Chatflow_api_input.png" max-width="900" caption="API노드 요청 Parameters" %}

#### 출력 Parameter

API 서비스로 Request를 보냈다면 결과를 받게 될 것입니다. 
그 결과는 Json형태로 받는 서비스에 한해서 좌측처럼 서비스에서 제공되는 데이터 구조가 Tree 형태로 표현됩니다. 
받은 데이터는 다시 받아서 Parameter에 담아야 하는데, 우측의 '출력 Parameter'에 변수명과 JsonPath 표기된 부분이 서비스에서 제공된 데이터를 매핑하여 담는 역할을 합니다. 
데이터 매핑하고자 할 경우에는 '출력 Parameter' JsonPath 부분에 직접 입력할 수도 있지만 좌측의 'Api Tree' 노드를 선택하여 drag&drop 하는 방식으로 JsonPath 영으로 끌어오면 자동적으로 JsonPath를 입력하실 수 있습니다.

{% include image.html file="chatflow/Chatflow_api_output.png" max-width="900" caption="API노드 출력 Parameters" %}


### 샘플 시나리오 (오늘 날씨 어때?)

오늘 날씨에 대한 의도를 파악하고 API노드를 통해 '기상청'과 같이 날씨 컨텐츠를 제공하는 서비스와 연계를 하고 그 결과를 답변하는 시나리오로 구성되어 있습니다.

{% include image.html file="chatflow/Chatflow_sample_weather.png" max-width="900" caption="샘플 시나리오(오늘날씨 어때?)" %}

API 노드에 날씨 OpenAPI 서비스 연계 설정을 하고 아래와 같이 '최고기온', '최저기온', '기상현황' 출력 Parameter를 매핑 설정합니다.

{% include image.html file="chatflow/Chatflow_api_output.png" max-width="900" caption="API노드 출력 Parameters" %}

Speak 노드에서 답변 메시지와 함께 API 노드에서 얻은 출력 Parameter들을 아래 그림과 같이 설정합니다.

{% include image.html file="chatflow/Chatflow_api_sampleSpeak.png" max-width="900" caption="Speak 노드 설정" %}

'오늘 날씨 어때?' 시나리오를 실행해 보면 아래와 같이 현재 기상정보를 답변하게 됩니다.

{% include image.html file="chatflow/Chatflow_api_sampleTest.png" max-width="900" caption="오늘 날씨 어때? 시나리오 결과" %}