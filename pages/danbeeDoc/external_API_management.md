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
 챗봇 설계에 사용할, 사용자 등록 API를 관리하는 메뉴입니다. 
  <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[API란?](http://terms.naver.com/entry.nhn?docId=1179553&cid=40942&categoryId=32837)</span>

해당 메뉴에서는 다음과 같은 내용을 설정할 수 있습니다.<br/> 
 - [API 조회]
 - [API 등록]
 - [API 수정]

### 1. API 조회 
### 2. API 등록 
단비 운영진에, 신규 API를 등록 요청 할 수 있는 기능입니다. <br/>
{% include image.html file="external_API/api_register.PNG" max-width="900" caption="API등록" %} 

#### API 설명
등록 API에 대한 간략한 설명을 등록합니다. 
예시 ) danbee 가입 여부 조회  
{% include image.html file="external_API/api_enroll_desc.PNG" max-width="900" caption="API설명" %} 
#### API 메서드 / Request URL
 - 메서드 : 현재 API 메서드는 REST로 fix 되어있습니다. 
 - Request URL : 등록 요청할 API의 URL을 입력합니다. <br/>
    예시 ) Rest, http://api.openweathermap.org/data/2.5/weather   
{% include image.html file="external_API/api_enroll_method.PNG" max-width="900" caption="API메서드" %} 
    
#### Content Type
현재 API Content Type은 는 JSON으로 fix 되어있습니다.   
{% include image.html file="external_API/api_enroll_conType.PNG" max-width="900" caption="Content Type" %} 

#### 요청 Parameter
단비 측에서, API에 전송할 parameter명과 값을 설정 및 입력합니다. 요청 parameter 추가시 요청 parameter 입력 테이블 우측 상단의 **+ 요청 Parameter 추가** 버튼을 클릭합니다. 
{% include image.html file="external_API/api_enroll_param1.PNG" max-width="900" caption="요청 Parameter" %} 

#### 실행
parameter 입력 후, **실행** 버튼을 클릭해, Response API Tree에서 API 적용 실행 결과를 확인할 수 있습니다. 
적용 실행 성공시, Response API Tree에서 Tree 형태의 데이터가 조회됩니다. 
실패시, 실패 알림창이 조회 됩니다. 

{% include image.html file="external_API/api_enroll_paramComplete.PNG" max-width="900" caption="요청 Parameter 입력 완료 예시" %} 
#### 저장
API 정보 정상 입력 후 **저장** 버튼을 클릭해, API 등록 정보를 저장합니다. 

#### 취소
{% include callout.html content="위치 : [Administrator] - [API 관리] - [API클릭] - [더보기]- [취소]" type="default" %}
화면 우측 상단의  **더보기** 버튼 클릭시, **취소**  버튼이 조회됩니다.  **취소**  클릭시, API 목록화면으로 이동하고, 작성하던 정보는 삭제됩니다. 

### 3. API 수정 
{% include callout.html content="위치 : [Administrator] - [API 관리] - [API클릭] - [수정]" type="default" %}
API 상세 조회 화면 우측 상단에, **수정** 버튼이 조회 됩니다. 로그인한 계정으로 작성한 적 있는 API에 한해, API 수정이 가능합니다. 수정 불가한 API에 대해 **수정** 버튼 클릭시, '수정 권한이 없습니다.' 알림창이 조회되고, 수정이 되지 않습니다.
API 수정 입력 절차는 API 등록 절차와 같습니다. 

### 4. API 사용
등록된  API는 API 노드에서 조회 및 사용 가능 합니다.