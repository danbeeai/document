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
 {% include callout.html content="위치 : [API 관리]" type="default" %}
 챗봇 설계에 사용할, 사용자 등록 API를 관리하는 메뉴입니다. 
  <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[API란?](http://terms.naver.com/entry.nhn?docId=1179553&cid=40942&categoryId=32837)</span>

해당 메뉴에서는 다음과 같은 내용을 이용할 수 있습니다.<br/> 
 - [API 조회](external_API_management.html#api-조회)
 - [API 등록](external_API_management.html#api-등록)
 - [API 수정](external_API_management.html#api-수정)

### API 조회 
API관리 메뉴에 들어가면 등록한 API의 목록을 확인할 수 있습니다. 해당 목록에서는 등록한 API 이름으로 검색이 가능합니다.
{% include image.html file="external_API/api_find.png" max-width="900" caption="API 조회" %} 

### API 등록 
단비 운영진에, 신규 API를 등록 요청 할 수 있는 기능입니다. <br/>
{% include image.html file="external_API/api_register.PNG" max-width="900" caption="API 등록" %} 

#### API 설명
등록 API에 대한 간략한 설명을 등록합니다. 
예시 ) danbee 가입 여부 조회  
{% include image.html file="external_API/api_enroll_desc.PNG" max-width="900" caption="API 설명" %} 
#### API 메서드 / Request URL
메서드는 클라이언트와 danbee.Ai 서버 사이에 이루어지는 요청(Request)과 응답(Response) 데이터를 전송하는 방식입니다. 
  <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[http와 메소드](http://terms.naver.com/entry.nhn?docId=2271985&cid=51207&categoryId=51207)</span>
 - 메서드 : GET, POST 메소드를 선택합니다. 
 - Request URL : 등록 요청할 API의 URL을 입력합니다. <br/>
    예시 ) Rest, http://api.openweathermap.org/data/2.5/weather   
{% include image.html file="external_API/api_enroll_method2.png" max-width="900" caption="API메서드" %} 
    
#### Content Type
Content Type 은 danbee.Ai 서버로 넘길 내용의 유형을 의미합니다. 현재 API Content Type은 는 JSON으로 fix 되어있습니다.   
{% include image.html file="external_API/api_enroll_conType.PNG" max-width="900" caption="Content Type" %} 

#### 요청 Parameter
danbee.Ai 측에서, API에 전송할 parameter명과 값을 설정 및 입력합니다. 요청 parameter 추가시 요청 parameter 입력 테이블 우측 상단의 **+ 요청 Parameter 추가** 버튼을 클릭합니다. 
{% include image.html file="external_API/api_enroll_param1.PNG" max-width="900" caption="요청 Parameter" %} 

#### Response API Tree
API 적용 결과 조회된 데이터를 Tree형태로 조회해서 보여줍니다. 실패시 아무런 데이터가 조회되지 않습니다. 

#### 실행
parameter 입력 후, **실행** 버튼을 클릭해, Response API Tree에서 API 적용 실행 결과를 확인할 수 있습니다. 
적용 실행 성공시, Response API Tree에서 Tree 형태의 데이터가 조회됩니다. 
실패시, 실패 알림창이 조회 됩니다. 

{% include image.html file="external_API/api_enroll_paramComplete.PNG" max-width="900" caption="요청 Parameter 입력 완료 예시" %} 
#### 저장
API 정보 정상 입력 후 **저장** 버튼을 클릭해, API 등록 정보를 저장합니다. 

#### 취소
{% include callout.html content="위치 : [API 관리] - [API클릭] - [더보기]- [취소]" type="default" %}
화면 우측 상단의  **더보기** 버튼 클릭시, **취소**  버튼이 존재합니다.  **취소**  클릭시, API 목록화면으로 이동하고, 작성하던 정보는 삭제됩니다. 

### API 수정 
{% include callout.html content="위치 : [API 관리] - [API클릭] - [수정]" type="default" %}
API 수정을 위해서는 API 상세 조회 화면 우측 상단 **수정** 버튼을 클릭하면 됩니다. API 수정 입력 절차는 API 등록 절차와 같습니다. 

## API 사용
등록된  API는 chatflow 설계의 API 노드에서 조회 및 사용 가능 합니다.
{% include image.html file="external_API/cf_api_node.PNG" max-width="900" caption="요청 Parameter 입력 완료 예시" %} 