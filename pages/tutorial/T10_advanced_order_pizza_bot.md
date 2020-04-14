---
title: 피자주문봇 만들기 
keywords: 피자주문봇
tags: [tutorial, advanced]
sidebar: tutorial_sidebar
permalink: advanced_order_pizza_bot.html
folder: 피자주문봇 만들기
summary: 피자주문봇을 만들어 봅니다.
search: exclude
previous: {
        title: Function 노드 사용하기,
        url: basic_function_node.html
}
next: {
    title: 선택장애제거, 캡틴초이,
    url: advanced_choice_bot.html
}
---

{% include important_developer.html content="API에 대한 기본적인 이해가 필요한 개발자의 영역입니다. <br /> 튜토리얼에서는 개발자가 아니더라도 동작원리를 이해할 수 있도록 따라할 수 있는 예제가 제공됩니다." type="default" %}

## 피자주문봇 만들기

지금까지 피자주문 받는 대화흐름을 단계별로 만들어 보았습니다. 하지만 현실세계에서는 더 복합적인 정보를 다루게 됩니다. 피자의 크기, 수량 등 여러가지 정보가 필요하고 선택한 메뉴와 수량에 따라 최종 계산되는 금액도 달라집니다. 조금 더 복합적인 기능 구현을 해야하는 경우, 연습삼아 살펴보기 좋은 예제입니다. 심화버전의 튜토리얼에서는 보다 다양한 예제가 준비되어 있습니다. 

**Sample Chatbot 가져오기** 를 통해 **피자주문봇** 을 가져오면 챗봇을 확인할 수 있습니다. <span class="link">[Sample Chatbot 가져오는 방법](/samplebot.html#%EC%83%98%ED%94%8C%EC%B1%97%EB%B4%87-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0)</span><br/>
기본적인 개념은 위 챕터에서 학습하셨다고 가정하고 진행하오니 생략이 있을 수 있습니다. <br/>

### 피자주문 Listen 노드 설정하기

대화의도 를 만들고 대화흐름 화면에 들어와 Listen 노드 를 설정합니다. <br/>
예문과 파라미터는 아래와 같이 설정합니다. 예문은 제시된 것 이외의 것을 입력해도 됩니다. 피자주문시 사용자들이 입력할 법한 예문을 추가해 보세요. <br/>

**샘플 예문 :**<br/>
포테이토 피자 라지 주문 해줘<br/>
페퍼로니 피자 1판 시켜줘<br/>
피자 주문할래<br/>
피자 먹고 싶어<br/>
피자주문하기<br/>

**샘플 파라미터 :** <br/>

| 파라미터명             |           Entity Type        |
|-------------------------|------------------------|
| 주소                    | sys.any	    |
| 피자_가격               | sys.any	  |
| 피자_선택               | 피자종류	  |
| 피자_계산금액           | sys.any	  |
| 피자_선택수량	          | sys.number	|
| 피자_선택사이즈          | 사이즈	    |
| 주문진행여부	            | sys.confirm	|
{: .table .table-striped}

예문 추가 방법과 파라미터 추가 방법은 위에 챕터를 참고 하시기 바랍니다. <br/>
<span class="link">[예문 추가 방법](/basic_create_intent.html#intent-%EC%83%9D%EC%84%B1)</span>
<span class="link">[파라미터 추가 방법](/basic_entity_parameter.html#parameter-%EC%B6%94%EA%B0%80)</span>
<span class="link">[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span>


### 피자메뉴 선택 Carausel 노드 설정하기

사용자가 원하는 메뉴를 선택할 수 있는 Carausel 노드 를 설정합니다. Slot 노드 로도 사용자가 선택한 값을 받을 수 있지만 <br/>
피자 이미지를 보여주기 위해 Carausel 노드 를 Slot 노드 처럼 사용하겠습니다. <br/>
Carausel 노드 사용방법 및 Slot 노드 처럼 설정하는 방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Carausel 노드 사용하기](/basic_carousel.html)</span> <br/>
선택한 피자메뉴를 저장할 **#{피자_선택}** 변수는 사용자가 정의한 **피자종류** 라는 entity 입니다. <br/>
Sample Chatbot 을 가져 오셨으면 가져온 챗봇의 **단어추출(entity)** 메뉴에서 **피자종류** entity 구성내용 확인하실 수 있습니다.<br/>
사용자정의 entity 에 대한 자세한 내용은 다음을 참고해 주세요.
<span class="link">[사용자정의 Entity Type](/entity.html#%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98-entity)</span>
<span class="link">[Entity 설정 튜토리얼](/basic_entity_parameter.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity-%EB%A7%8C%EB%93%A4%EA%B8%B0)</span>


### 사이즈 확인/수량 확인 Slot 노드 설정하기
사용자가 원하는 사이즈를 선택하고 수량을 입력할 수 있는 Slot 노드 를 각각 설정합니다. <br/>
사이즈 확인 Slot 노드 에서 선택값을 저장할 **#{피자_선택사이즈}** 변수는 사용자가 정의한 **사이즈** 라는 entity 입니다. <br/>
Sample Chatbot 을 가져 오셨으면 가져온 챗봇의 **단어추출(entity)** 메뉴에서 **사이즈** entity 구성내용 확인하실 수 있습니다.<br/>
수량 확인 Slot 노드 에서 사용자 선택값을 저장할 **#{피자_선택수량}** 변수는 시스템에서 제공하는 **sys.number** 라는 entity 입니다. <br/>
system entity 설명은 다음을 참고해 주세요.
<span class="link">[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span><br/>
Slot 노드 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Slot 노드 사용하기](/basic_slot.html) </span>


### 메뉴 가격 조회 Api 노드 설정하기
사용자가 선택한 메뉴와 사이즈를 가지고 피자 가격을 외부시스템에서 가져오는 Api 노드 를 설정합니다. <br/>
Sample Chatbot 을 가져오셨더라도 Api 노드 에 설정할 Api 는 가져오지 않습니다. <br/>
Api 설정 방법 및 Api 노드 설정 방법은 위에 챕터 내용 참고해 주세요. <span class="link">[Api 설정 방법](/basic_api_node.html#api-%EB%A7%8C%EB%93%A4%EA%B8%B0)</span>
<span class="link">[Api 노드 설정 방법](/basic_api_node.html#api-node-%EB%A7%8C%EB%93%A4%EA%B8%B0)</span><br/>
아래 내용을 Api 설정창에서 입력하시고 저장 후 Api 노드 에서 불러와 설정하시기 바랍니다. <br/>

- **Api 명**:  메뉴별_사이즈별_피자가격_가져오기
- **API 설명**:  메뉴별_사이즈별_피자가격_가져오기
- **API 메서드**:  GET
- **Requerst URL**:  https://channel.danbee.ai:3000/pizzaTutorial/getSizePrice
- **Content Type**:  JSON
- **요청 파라미터**: q, s
- **Response API Tree**: size, price, name


### 최종 가격 계산 Function 노드 설정하기
사용자가 선택한 메뉴, 사이즈, 주문수량 그리고 외부시스템에서 가져온 피자 가격까지 대화흐름에 가져왔습니다. <br/>
Function 노드 를 활용하여 주문수량과 주문한 피자의 가격을 곱해 사용자가 내야하는 금액을 계산하고 <br/>
사용자가 금액을 보기 쉽도록 천단위에 쉼표를 넣어 봅시다. <br/>
Function 노드 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Function 노드 사용하기](/basic_function_node.html#function-node-%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%98%EC%97%AC-%EB%B3%80%EC%88%98%EA%B0%92%EC%9D%84-%EA%B0%80%EA%B3%B5%ED%95%98%EA%B8%B0) </span><br/>
Function 노드 안에 들어갈 내용은 아래와 같습니다. <br/>

```js
/* 천단위 쉼표 처리 */
피자_계산금액 = 피자_계산금액.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
피자_가격 = 피자_가격.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
피자_선택수량 = 피자_선택수량.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
````


{% include image.html file="tutorial/ad_10.png"  caption="최종 가격 계산 Function 노드 상세화면" %}

### 주문확인 Slot 노드 설정하기
사용자에게 정말 주문을 원하는지를 물어보고 사용자의 답변을 받는 Slot 노드 를 설정합니다. <br/>
Slot 노드 에서 선택값을 저장할 **#{주문진행여부}** 변수는 시스템에서 제공하는 **sys.confirm** 이라는 entity 입니다. <br/>
system entity 설명은 다음을 참고해 주세요.
<span class="link">[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span><br/>
Slot 노드 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Slot 노드 사용하기](/basic_slot.html) </span>


### 주문진행여부 분기 Split 노드 설정하기
사용자가 선택한 주문진행여부에 따라 다른 답변을 하도록 Split 노드 를 설정합니다.<br/>
Split 노드 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Split 노드 사용하기](/basic_split.html#split-node) </span>


### 주소입력 Slot 노드 설정하기
주문을 원하는 사용자에게 주소를 받는 Slot 노드 를 설정합니다. <br/>
Slot 노드 에서 선택값을 저장할 **#{주소}** 변수는 시스템에서 제공하는 **sys.any** 이라는 entity 입니다. <br/>
system entity 설명은 다음을 참고해 주세요.
<span class="link">[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span><br/>
Slot 노드 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Slot 노드 사용하기](/basic_slot.html) </span>

### 주문취소/주문접수완료 Speak 노드 설정하기
주문진행을 원하지 않는 사용자에게는 주문취소 메세지를 원하는 사용자에게는 주문 완료 메세지를 보여주는 Speak 노드 를 설정합니다.<br/>
Speak 노드 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span class="link">[Speak 노드 사용하기](/basic_listen_speak.html#speak-node) </span>


## 마무리
지금까지 피자주문봇을 만드시느라 수고 많았습니다. 더 많은 챗봇 샘플이 준비되어 있습니다. 하나씩 열어보고 챗봇으로 어떤 것을 할 수 있을지 생각해보세요!




{% include bottom.html %}