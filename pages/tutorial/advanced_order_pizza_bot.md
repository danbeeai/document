---
title: 피자주문봇 만들기
keywords: 피자주문봇
tags: [피자주문봇]
sidebar: tutorial_sidebar
permalink: advanced_order_pizza_bot.html
folder: 피자주문봇 만들기
summary: 피자주문봇을 만들어 봅니다.
previous: {
        title: Function 노드 사용하기,
        url: basic_function_node.html
}
---

## 피자주문봇 만들기

지금까지 피자주문 받는 chatflow 를 단계별로 만들어 보았습니다. 하지만 뭔가가 부족합니다. <br/>
피자 주문할때 1판 이상 주문할 수도 있고 피자를 혼자 먹는 사람은 좀더 작은 피자를 먹고 싶어 할수도 있습니다. <br/>
지금부터는 우리가 진짜 피자 주문할때 겪을법한 상황을 반영하여 챗봇을 만들어 보도록 하겠습니다. <br/>
**Sample Chatbot 가져오기** 를 통해 **피자주문봇** 을 가져오면 챗봇을 확인할 수 있습니다. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Sample Chatbot 가져오는 방법](/samplebot.html#%EC%83%98%ED%94%8C%EC%B1%97%EB%B4%87-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0)</span><br/>
기본적인 개념은 위 챕터에서 학습하셨다고 가정하고 진행하오니 생략이 있을 수 있습니다. <br/>
이해가 안되는 부분은 위에 챕터들을 다시 보시면 설명되어 있습니다.

### 피자주문 Listen Node 설정하기

Intent 를 만들고 Chatflow 화면에 들어와 Listen Node 를 설정합니다. <br/>
예문과 파라미터는 아래와 같이 설정합니다. 예문은 제시된 것 이외의 것을 입력해도 됩니다. 피자주문시 사용자들이 입력할 법한 예문을 추가해 보세요. <br/>

**샘플 예문 :**<br/>
포테이토 피자 라지 주문 해줘<br/>
페퍼로니 피자 1판 시켜줘<br/>
피자 주문할래<br/>
피자 먹고 싶어<br/>
피자주문하기<br/>

**샘플 파라미터 :** <br/>

| Parameter명             |           Entity Type        |
|-------------------------|------------------------|
| 주소                    | sys.any	    |
| 피자_가격               | sys.any	  |
| 피자_선택               | 피자종류	  |
| 피자_계산금액           | sys.any	  |
| 피자_선택수량	          | sys.number	|
| 피자_선택사이즈          | 사이즈	    |
| 주문진행여부	            | sys.confirm	|

예문 추가 방법과 파라미터 추가 방법은 위에 챕터를 참고 하시기 바랍니다. <br/>
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[예문 추가 방법](/basic_create_intent.html#intent-%EC%83%9D%EC%84%B1)</span>
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[파라미터 추가 방법](/basic_entity_parameter.html#parameter-%EC%B6%94%EA%B0%80)</span>
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span>

{% include image.html file="tutorial/ad_1.png" max-width="900" caption="예문 추가된 모습" %}
{% include image.html file="tutorial/ad_2.png" max-width="900" caption="파라미터 추가된 모습" %}

### 피자메뉴 선택 Carausel Node 설정하기

사용자가 원하는 메뉴를 선택할 수 있는 Carausel Node 를 설정합니다. Slot Node 로도 사용자가 선택한 값을 받을 수 있지만 <br/>
피자 이미지를 보여주기 위해 Carausel Node 를 Slot Node 처럼 사용하겠습니다. <br/>
Carausel Node 사용방법 및 Slot Node 처럼 설정하는 방법은 위에 챕터 내용을 참고 하시기 바랍니다.
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Carausel Node 사용하기](/basic_carousel.html)</span> <br/>
선택한 피자메뉴를 저장할 **#{피자_선택}** 변수는 사용자가 정의한 **피자종류** 라는 entity 입니다. <br/>
Sample Chatbot 을 가져 오셨으면 가져온 챗봇의 **단어추출(entity)** 메뉴에서 **피자종류** entity 구성내용 확인하실 수 있습니다.<br/>
사용자정의 entity 에 대한 자세한 내용은 다음을 참고해 주세요.
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[사용자정의 Entity Type](/entity.html#%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98-entity)</span>
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Entity 설정 튜토리얼](/basic_entity_parameter.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity-%EB%A7%8C%EB%93%A4%EA%B8%B0)</span>

{% include image.html file="tutorial/ad_3-1.png" max-width="900" caption="피자종류 entity 정의" %}

{% include image.html file="tutorial/ad_3.png" max-width="900" caption="Carausel Node 설정" %}

### 사이즈 확인/수량 확인 Slot Node 설정하기
사용자가 원하는 사이즈를 선택하고 수량을 입력할 수 있는 Slot Node 를 각각 설정합니다. <br/>
사이즈 확인 Slot Node 에서 선택값을 저장할 **#{피자_선택사이즈}** 변수는 사용자가 정의한 **사이즈** 라는 entity 입니다. <br/>
Sample Chatbot 을 가져 오셨으면 가져온 챗봇의 **단어추출(entity)** 메뉴에서 **사이즈** entity 구성내용 확인하실 수 있습니다.<br/>
수량 확인 Slot Node 에서 사용자 선택값을 저장할 **#{피자_선택수량}** 변수는 시스템에서 제공하는 **sys.number** 라는 entity 입니다. <br/>
system entity 설명은 다음을 참고해 주세요.
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span><br/>
Slot Node 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다. 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Slot Node 사용하기](/basic_slot.html) </span>

{% include image.html file="tutorial/ad_4.png" max-width="900" caption="사이즈 entity 정의" %}
{% include image.html file="tutorial/ad_5.png" max-width="900" caption="사이즈 확인 Slot Node 설정" %}
{% include image.html file="tutorial/ad_6.png" max-width="900" caption="수량 확인 Slot Node 설정" %}

### 메뉴 가격 조회 Api Node 설정하기
사용자가 선택한 메뉴와 사이즈를 가지고 피자 가격을 외부시스템에서 가져오는 Api Node 를 설정합니다. <br/>
Sample Chatbot 을 가져오셨더라도 Api Node 에 설정할 Api 는 가져오지 않습니다. <br/> 
Api 설정 방법 및 Api Node 설정 방법은 위에 챕터 내용 참고해 주세요. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Api 설정 방법](/basic_api_node.html#api-%EB%A7%8C%EB%93%A4%EA%B8%B0)</span>
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Api Node 설정 방법](/basic_api_node.html#api-node-%EB%A7%8C%EB%93%A4%EA%B8%B0)</span><br/>
아래 내용을 Api 설정창에서 입력하시고 저장 후 Api Node 에서 불러와 설정하시기 바랍니다. <br/>

- **Api 명**:  메뉴별_사이즈별_피자가격_가져오기
- **API 설명**:  메뉴별_사이즈별_피자가격_가져오기
- **API 메서드**:  GET
- **Requerst URL**:  https://channel.danbee.ai:3000/pizzaTutorial/getSizePrice
- **Content Type**:  JSON
- **요청 Parameter**: q, s
- **Response API Tree**: size, price, name

{% include image.html file="tutorial/ad_7.png" max-width="900" caption="Api 설정 화면" %}
{% include image.html file="tutorial/ad_8.png" max-width="900" caption="메뉴 가격 조회 Api Node 상세 요청 Parameter 화면" %}
{% include image.html file="tutorial/ad_9.png" max-width="900" caption="메뉴 가격 조회 Api Node 상세 출력 Parameters 화면" %}

### 최종 가격 계산 Function Node 설정하기
사용자가 선택한 메뉴, 사이즈, 주문수량 그리고 외부시스템에서 가져온 피자 가격까지 대화흐름에 가져왔습니다. <br/>
Function Node 를 활용하여 주문수량과 주문한 피자의 가격을 곱해 사용자가 내야하는 금액을 계산하고 <br/>
사용자가 금액을 보기 쉽도록 천단위에 쉼표를 넣어 봅시다. <br/>
Function Node 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다. 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Function Node 사용하기](/basic_function_node.html#function-node-%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%98%EC%97%AC-%EB%B3%80%EC%88%98%EA%B0%92%EC%9D%84-%EA%B0%80%EA%B3%B5%ED%95%98%EA%B8%B0) </span><br/>
Function Node 안에 들어갈 내용은 아래와 같습니다. <br/>

```js
/* 천단위 쉼표 처리 */ 
피자_계산금액 = 피자_계산금액.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,"); 
피자_가격 = 피자_가격.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
피자_선택수량 = 피자_선택수량.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1,");
````

{% include image.html file="tutorial/ad_10.png" max-width="900" caption="최종 가격 계산 Function Node 상세화면" %}

### 주문확인 Slot Node 설정하기
사용자에게 정말 주문을 원하는지를 물어보고 사용자의 답변을 받는 Slot Node 를 설정합니다. <br/>
Slot Node 에서 선택값을 저장할 **#{주문진행여부}** 변수는 시스템에서 제공하는 **sys.confirm** 이라는 entity 입니다. <br/>
system entity 설명은 다음을 참고해 주세요.
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span><br/>
Slot Node 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다. 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Slot Node 사용하기](/basic_slot.html) </span>

{% include image.html file="tutorial/ad_11.png" max-width="900" caption="주문확인 Slot Node 상세화면" %}

### 주문진행여부 분기 Split Node 설정하기
사용자가 선택한 주문진행여부에 따라 다른 답변을 하도록 Split Node 를 설정합니다.<br/>
Split Node 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다. 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Split Node 사용하기](/basic_split.html#split-node) </span>

{% include image.html file="tutorial/ad_12.png" max-width="900" caption="주문진행여부 분기 Split Node 상세화면" %}

### 주소입력 Slot Node 설정하기
주문을 원하는 사용자에게 주소를 받는 Slot Node 를 설정합니다. <br/>
Slot Node 에서 선택값을 저장할 **#{주소}** 변수는 시스템에서 제공하는 **sys.any** 이라는 entity 입니다. <br/>
system entity 설명은 다음을 참고해 주세요.
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Entity Type 설명](/entity.html#%EC%97%94%ED%8B%B0%ED%8B%B0entity)</span><br/>
Slot Node 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다. 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Slot Node 사용하기](/basic_slot.html) </span>

{% include image.html file="tutorial/ad_13.png" max-width="900" caption="주소입력 Slot Node 상세화면" %}

### 주문취소/주문접수완료 Speak Node 설정하기
주문진행을 원하지 않는 사용자에게는 주문취소 메세지를 원하는 사용자에게는 주문 완료 메세지를 보여주는 Speak Node 를 설정합니다.<br/>
Speak Node 사용방법은 위에 챕터 내용을 참고 하시기 바랍니다. 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Speak Node 사용하기](/basic_listen_speak.html#speak-node) </span>

{% include image.html file="tutorial/ad_14.png" max-width="900" caption="주문취소 Speak Node 상세화면" %}
{% include image.html file="tutorial/ad_15.png" max-width="900" caption="주문접수완료 Speak Node 상세화면" %}

## 마무리
지금까지 피자주문봇을 만드시느라 수고 많았습니다. 피지주문봇의 완성된 형태는 아마 아래와 같을 거에요. <br/>

{% include image.html file="tutorial/ad_16.png" max-width="900" caption="피지주문봇 Chaflow" %}