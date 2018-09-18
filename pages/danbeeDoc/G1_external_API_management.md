---
title: API 관리
tags: [API, advanced]
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

## 개요
 {% include callout.html content="위치 : [대화흐름(Chatflow)] > [API 관리]" type="default" %}
 <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[API란?](http://terms.naver.com/entry.nhn?docId=1179553&cid=40942&categoryId=32837)</span> 시스템과 시스템이 서로 정보를 주고 받는 메시지 형식입니다. 챗봇이 사용자의 의도를 파악했다면, 실제 정보를 제공하거나 접수를 처리해주기 위해서는 다른 시스템과 정보를 주고받는 것이 필요합니다. [API관리]에서 API를 등록하여 테스트할 수 있는 환경을 제공하고, [API노드](/chatflow_api.html)에서 불러와 재사용 할 수 있습니다.즉, [API 관리]메뉴는 API를 등록하는 기능을 제공하며, [API노드](/chatflow_api.html)는 등록된 API를 활용하여 대화흐름에 적용하는 기능을 제공합니다. 지금 보고 계신 문서는 [API 관리]에 대한 설명입니다.

  

해당 메뉴에서는 다음과 같은 내용을 이용할 수 있습니다.<br/>
 - [API 등록](external_API_management.html#api-등록)  
 - [API 수정](external_API_management.html#api-수정)  
 - [API 조회](external_API_management.html#api-조회) 


### API 등록
신규 API를 등록을 요청 하고 수정할 수 있는 기능입니다.<br/>
[API관리] 메뉴를 클릭하면, API목록이 나타납니다. 우측상단의 'API 등록' 버튼을 클릭하면, API를 등록하기위한 화면이 열립니다.<br/>

### API 수정
이미 등록된 API가 있다면, API목록에 보이게 됩니다. 등록된 API 중 하나를 클릭하면, API상세 화면이 나타나며, 우측 상단에 [수정] 버튼을 클릭하여 수정이 가능합니다. API 수정을 위해서는 API 상세 조회 화면 우측 상단 [수정] 버튼을 클릭하면 됩니다. API 수정 절차는 API 등록 절차와 같습니다.

#### API 기본 정보
연결하고자 하는 API의 기본정보를 입력해야 합니다.

1. API 이름 : (필수입력) API의 특징을 표현하는 이름을 하나 정하시면 됩니다.
2. [API 메서드](external_API_management.html#api-메서드--request-url) : (필수입력) GET 또는 POST 중에서 선택하십시오.
3. Request URL : (필수입력) 요청할 API의 URL을 입력하는 필수 입력란입니다.
4. API 설명 : (선택입력) API설명 또는 가이드 문서의 URL을 입력해두면, 나중에 편리하게 사용이 가능합니다.

#### API 메서드 / Request URL
메서드는 클라이언트와 danbee.Ai 서버 사이에 이루어지는 요청(Request)과 응답(Response) 데이터를 주고받는 국제표준으로 정한 규약입니다. 
danbee.Ai에서는 가장 많이 사용되는 GET과 POST를 제공합니다.
적용하고자 하는 API의 가이드문서에서 어떤 메소드를 지원하는지 확인하고 설정하시기 바랍니다. 나중에 다시 찾을 수 있도록 가이드문서의 URL을 남겨두면 편하겠죠?

 - 메서드 : GET, POST 메소드를 선택합니다. 
 - Request URL : 등록 요청할 API의 URL을 입력합니다. <br/>
    예시 ) http://api.openweathermap.org/data/2.5/weather   
{% include image.html file="external_API/api_enroll_method2.png" max-width="900" caption="API메서드, Request URL, API설명" %} 


#### API 등록시 주의사항    
danbee.Ai에서는 허가된 API만을 연계해드리고 있습니다.

* http의 80포트와 https 443포트는 방화벽 해제요청을 하실 필요가 없습니다.
* 그 외 포트에 대해서는 우측하단 의견보내기 버튼을 눌러 사용하고자 하시는 API URL을 보내주시면 검토후 방화벽을 임시로 열어드립니다. 
    (URL 및 포트번호를 누락한채로 요청하시는 분들이 많이 계십니다. 꼭 보내시기전에 확인해주시기 바랍니다.)
* 특별한 요청이 없으면 2주이내 방화벽을 닫습니다.

#### API 세부 정보
API의 세부 정보에 입력한 정보를 통해 API가 실제로 동작하는지 API를 테스트할 수 있습니다. 정상동작하는 API는 나중에 API노드에서 결과값을 활용하기 위해 Tree를 호출해 올때도 활용됩니다.

##### API Input 정보
1. Header : 입력한 API URL로 보내는 요청의 [Header](external_API_management.html#header-와-content-type) 정보를 설정하는 란입니다.<br/>
    [Content-Type](external_API_management.html#header-와-content-type) 은 고정값이며 현재 JSON 형태만 지원합니다.<br/>
    추가 Header 정보를 'Header 추가' 버튼으로 추가할 수 있습니다.
2. Query Parameter : API URL에서 '?'뒤에 쿼리조건을 입력하는 방식입니다. name=value 형식으로 사용하는 Query Parameter 정보를 설정할 수 있습니다.<br/>
3. Path Parameter : API URL에 '/'부터 '?'사이에 오는 경로로 설정하는 Parameter입니다. 경우에 따라 '?'조건이 없을 수 있습니다.
4. Body : API의 메서드가 'POST'일 경우(API 기본 정보 '2'번에서 POST를 선택한 경우) Body를 입력하는 란이 표시됩니다. Body는 다른 파라미터와 마찬가지로 하나씩 추가하여 입력하거나 Text Editor를 이용하여 입력할 수 있습니다. Header에서 선택한 Content-Type(JSON 또는 XML)에 따라 Body에 입력해야하는 양식이 달라집니다.





#### Header 와 Content Type 
Header에는 여러가지 정보를 담을 수 있습니다.
Content-Type도 그중 하나로써, 서버로 보내는 정보의 유형을 의미하며 다음과 같은 형식을 지원합니다.<br/>
- JSON : 'application/json' 가장 일반적인 JSON 형식
- XML  : 'application/xml', 'text/xml' 두 가지 방식을 지원하며 사용하려는 API에서 정의된 형식을 선택하시면 됩니다.
{% include image.html file="external_API/02_api_manage_c_header.png" max-width="900" caption="Header와 Content-Type" %} 

#### Query Parameter / Path Parameter
API URL에 Parameter를 실어 보내는 방법으로 Query Parameter 방식과 Path Parameter 방식을 제공합니다.
'http://apiurl/api'이라는 API URL이 있을 때 'name'이란 변수명으로 'value'란 값을 보낼 때
Query Parameter는 아래와 같이 '?'뒤에 추가되어 호출하게 됩니다.<br/>
<pre><code>http://apiurl/api?name=value</code></pre><br/>
{% include image.html file="external_API/02_api_manage_c_parameter.png" max-width="900" caption="Query Parameter" %}
API자체에 고정된 Query Parameter가 있거나, 개발경험이 많아 직접 URL에 적용하는 것이 편하다면, 이 기능을 사용하지 않고 직접 URL에 입력해도 무방합니다.


Path Parameter는<br/>
<pre><code>http://apiurl/api/value</code></pre><br/>
와 같이 URL의 경로처럼 사용하여 해당 경로를 값으로 사용하는 방식입니다.<br/>
danbee.Ai에서는 Path Parameter 기능을 값 치환 방법으로 제공합니다.<br/>
즉 아래와 같이 API URL에 '{name}' 과 같이 중괄호로 둘러싼 Path Parameter의 Name을 등록되어있는 Value로 치환합니다.
[주의] Chatflow에서 사용하는 양식인 '#{name}'이 아닌 '{name}'으로 사용해야 합니다.
{% include image.html file="external_API/05_api_manage_path_param.png" max-width="900" caption="Path Parameter" %}

두 가지 방식(Query Parameter와 Path Parameter)은 혼용하여 사용 가능합니다.<br/>

#### Body
등록할 외부 API의 메서드가 POST일 경우 Request Body를 작성할 수 있습니다.<br/>
Header, 요청 Parameter와 같이 'Body 추가' 버튼으로 하나씩 추가하거나,<br/>
Editor를 이용하여 직접 작성할 수도 있습니다 <br/>
(이때, Body 추가 기능을 이용해 입력하면 x-www-form-urlencoded 양식을 따르게 되며,
Editor로 직접입력 하면, raw 양식을 따르게 됩니다.)
{% include image.html file="external_API/04_api_manage_body_editor.png" max-width="600" caption="Body 입력" %}
Editor에 입력할 때는, Header의 Content-Type에 따라 JSON 또는 XML로 입력이 가능합니다.

parameter 입력 후, **[API Test]** 버튼을 클릭해하여<br/>
Response API Tree에서 API 적용 실행 결과를 확인할 수 있습니다.

#### Response API Tree
실행 성공시, Response API Tree에서 Tree 형태의 데이터가 조회됩니다.<br/>
API 적용 결과 조회된 데이터를 Tree형태로 조회해서 보여줍니다. 실패시 아무런 데이터가 조회되지 않습니다.
{% include image.html file="external_API/02_api_manage_c_response_tree.png" max-width="900" caption="Response API Tree 예시" %}
{% include note.html content="이제 배열과 JSON 객체를 원하는 Parameter에 담아 사용할 수 있습니다." %}
- 자세한 사항은 [API 노드](chatflow_api.html#응답-parameter-와-출력-parameters) 에서 확인해 주세요.

#### 저장
API 정보 정상 입력 후 **저장** 버튼을 클릭해, API 등록 정보를 저장합니다. 

#### 취소
{% include callout.html content="위치 : [API 관리] - [API클릭] - [더보기]- [취소]" type="default" %}
화면 우측 상단의  **더보기** 버튼 클릭시, **취소**  버튼이 존재합니다.  **취소**  클릭시, API 목록화면으로 이동하고, 작성하던 정보는 삭제됩니다. 


### API 조회 
API관리 메뉴에 들어가면 등록한 API의 목록을 확인할 수 있습니다. 해당 목록에서는 등록한 API 이름으로 검색이 가능합니다.
{% include image.html file="external_API/03_api_manage_r_list.png" max-width="900" caption="API 조회" %}  

## API 사용
등록된  API는 chatflow 설계의 API 노드에서 조회 및 사용 가능 합니다.
{% include image.html file="external_API/cf_api_node.PNG" max-width="900" caption="API 노드에서의 기등록 API 예시" %} 