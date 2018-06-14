---
title: API 노드
tags: [chatflow, API, advanced]
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

API 노드는 기존에 등록 관리되고 있는 API들 중 하나를 선택하여 사용할 수 있습니다. 
이는 동일한 API를 서로 다른 챗봇, 서로 다른 시나리오에서 쓰고자 할 경우<br/>
매번 등록 설정해야하는 번거로움을 해소하고자 별도의 API들을 관리하고 불러서 사용하는 방식으로 구성된 이유이기도 합니다.<br/> 
API관리에 대해 자세히 알고자 할 경우 아래 API관리 내용을 확인하시기 바랍니다. 

- [API 관리](external_API_management.html#API 관리)

아래는 미리 등록한 API 목록을 보여주는 '사용 API' 선택박스에서 하나의 API를 선택한 예시입니다.
API를 선택하여 '적용' 버튼을 누르면 등록해둔 Header, 요청 Parameter 등 기본 정보를 불러옵니다.<br/>
기본 정보 외에 추가로 Header나 요청 Parameter를 사용하고 싶다면 각 각의 추가버튼을 클릭하여 추가할 수 있습니다. 

{% include image.html file="chatflow/00_api_node_intro.png" max-width="900" caption="API 선택" %}


API설정은 외부의 데이터 서비스와 연계시 서비스에 보내야할 요청 Parameter와 받아야할 출력 Parameter 정보를 설정합니다. 
API 설정은 2개의 Tab으로 구성이 됩니다.

- [요청 Parameter](Chatflow_api.html#요청 Parameter)
- [출력 Parameter](Chatflow_api.html#출력 Parameter)


#### 요청 Parameter

API 선택시 기본적으로 'API관리'에 등록되었던 Value 값은 초기화 됩니다. 
아래 화면처럼 고정된 값을 입력할 수 있으며, 어떤 변수값을 받아서 입력하고 싶다면 #{변수명}과 같이 입력할 수 있습니다.

{% include image.html file="chatflow/00_api_node_parameters.png" max-width="900" caption="API노드 요청 Parameters" %}

#### 출력 Parameter

API 서비스로 Request를 성공적으로 보냈다면 응답(Response) 결과를 받게 됩니다.<br/>
그 결과는 아래와 같이 JSON 데이터 구조가 Tree로 표현됩니다.(JSON형태로 받는 서비스에 한해서)<br/> 
이렇게 응답으로 받은 데이터를 Parameter에 담아야 하는데, 이 역할을 하는 것이 '출력 Parameter'에 변수명과 JsonPath 표기된 부분입니다.<br/>
응답으로 받은 데이터를 Parameter에 담기위해 매핑하고자 할 경우 두가지 방법이 있습니다.
 - '출력 Parameters'의 JsonPath를 직접 입력(매핑할 경로 직접입력)
 - 'Api Tree'에서 노드를 drag&drop 으로 '출력 Parameters' JsonPath 입력부로 끌어오기(매핑할 경로 자동 입력)

이와 같이 API Request를 통해 응답받은 데이터를 원하는 Parameter에 담아 사용할 수 있습니다.
{% include image.html file="chatflow/00_api_node_response_tree.png" max-width="900" caption="API노드 출력 Parameters" %}


### 샘플 시나리오 (오늘 날씨 어때?)

#### 샘플 시나리오 설계

오늘 날씨에 대한 의도를 파악하고 API노드를 통해 '기상청'과 같이 날씨 컨텐츠를 제공하는 서비스와 연계를 하고 그 결과를 답변하는 시나리오로 구성되어 있습니다.

{% include image.html file="chatflow/Chatflow_sample_weather.png" max-width="900" caption="샘플 시나리오(오늘날씨 어때?)" %}


#### [오늘날씨 요청] Listen 노드 설정

##### 파라미터 생성

날씨 API를 통해 얻어온 정보를 담기 위한 파라미터들을 생성합니다.

- [기상정보] : sky
- [최고온도] : tmax
- [최조온도] : tmin

{% include image.html file="chatflow/Chatflow_api_listen.png" max-width="900" caption="파라미터 생성" %}

#### [날씨 API연계] Api 노드 설정

##### 파라미터 매핑

좌측에 API를 통해 조회된 Tree 구조의 정보에서 사용하고자 하는 우측 파라미터에 드래그 매핑 설정한다.
드래그 매핑을 하게 되면 Tree 구조에서 선택한 파라미터의 위치가 JsonPath 형태로 자동적으로 표시가 됩니다.

{% include image.html file="chatflow/Chatflow_api_drag.png" max-width="900" caption="출력 파라미터 드래그 매핑 설정" %}

{% include image.html file="chatflow/Chatflow_api_output.png" max-width="900" caption="파라미터 매핑" %}

#### [오늘날씨 알려줌] Speak 노드 설정

##### 답변 메시지 설정

Speak 노드에서 답변 메시지와 함께 API 노드에서 얻은 출력 Parameter들을 아래 그림과 같이 설정합니다.

{% include image.html file="chatflow/Chatflow_api_sampleSpeak.png" max-width="900" caption="Speak 노드 설정" %}


#### 테스트

'오늘 날씨 어때?' 시나리오를 실행해 보면 아래와 같이 현재 기상정보를 답변하게 됩니다.

{% include image.html file="chatflow/Chatflow_api_sampleTest.png" max-width="900" caption="오늘 날씨 어때? 시나리오 결과" %}