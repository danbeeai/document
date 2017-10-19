---
title: API 관리
tags: [API]
keywords: Basic Conversation
summary: 챗플로우 설계에 사용할 외부 API를 등록 및 수정하는 페이지입니다.
sidebar: danbee_doc_sidebar
permalink: external_API_management.html
folder: danbeeDoc
previous: {
    title: 카카오톡,
    url: channel_kakaotalk.html
}
next: {
    title: 사용자 의견 보내기,
    url: feedback.html
}
---

## API 관리
 {% include callout.html content="위치 : [Administrator] - [API 관리]- [API 등록]" type="default" %}

### 1. API 등록 
신규  API를 등록 요청 할 수 있습니다. 

#### API 설명
등록 API에 대한 간략한 설명을 등록합니다. 
예시 ) danbee 가입 여부 조회  

#### API 메서드 / Request URL
 - 메서드 : 현재 API 메서드는 REST로 fix 되어있습니다. 
 - Request URL : 등록 요청할 API의 URL을 입력합니다. 
    예시 ) Rest, http://api.openweathermap.org/data/2.5/weather   
    
#### Content Type
현재 API Content Type은 는 JSON으로 fix 되어있습니다.   

#### 요청 Parameter
API에 전송할 parameter명과 값을 설정 및 입력합니다. 

#### 실행
parameter 입력 후, **실행** 버튼을 클릭해, Response API Tree에서 API 적용 실행 결과를 확인할 수 있습니다. 
적용 실행 성공시, Response API Tree에서 Tree 형태의 데이터가 조회됩니다. 
실패시, 실패 알림창이 조회 됩니다. 

#### 저장
API 정보 정상 입력 후 **저장** 버튼을 클릭해, API 등록 정보를 저장합니다. 

### 2. API 수정 
{% include callout.html content="위치 : [Administrator] - [API 관리] - [API클릭] - [수정]" type="default" %}
로그인한 계정으로 기작성 되었던 API에 한해, API 수정이 가능합니다. 