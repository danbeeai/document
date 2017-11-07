---
title: API 노드
tags: []
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

{% include image.html file="chatflow/Chatflow_api_cavas.png" max-width="900" caption="Api 노드" %}

### 기본정보

Api 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_api_basic.png" max-width="900" caption="API노드 기본정보" %}

### API 설정

- [요청 Parameter](Chatflow_api.html#요청 Parameter)
- [출력 Parameter](Chatflow_api.html#출력 Parameter)

{% include image.html file="chatflow/Chatflow_api_select.png" max-width="900" caption="API 선택" %}

#### 요청 Parameter

{% include image.html file="chatflow/Chatflow_api_input.png" max-width="900" caption="API노드 요청 Parameters" %}

#### 출력 Parameter

{% include image.html file="chatflow/Chatflow_api_output.png" max-width="900" caption="API노드 출력 Parameters" %}


### 샘플 시나리오 (오늘 날씨 어때?)

오늘 날씨에 대한 의도를 파악하고 API노드를 통해 '기상청'과 같이 날씨 컨텐츠를 제공하는 서비스와 연계를 하고 그 결과를 답변하는 시나리오로 구성되어 있습니다.

{% include image.html file="chatflow/Chatflow_sample_weather.png" max-width="900" caption="샘플 시나리오(오늘날씨 어때?)" %}