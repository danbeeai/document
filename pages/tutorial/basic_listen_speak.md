---
title: Chatflow 생성하기
tags: [chatflow, liten_node, speak_node]
keywords: Tutorial
summary: Chatlflow의 개념을 이해하고, Listen Node와 Speak Node로 대화를 만들 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_listen_speak.html
folder: tutorial
previous: {
    title: Intent 생성하기,
    url: basic_create_intent.html
}
next: {
    title: Entity와 Parameter 이해하기, 
    url: basic_entity_parameter.html
}
---

## Chatflow 만들기
{% include callout.html content="화면 위치 : [대화흐름(Chatflow)] > [대화흐름 목록(Chatflow List)]" type="default" %}
Chatflow란, 사용자가 어떤 말을 입력했을 때, 적절한 답을 해주기까지 필요한 내용들을 정의하는 하나의 대화묶음 단위입니다. 사용자가 입력한 말에 대하여 단답형으로 대답할 수도 있겠지만 상황에 따라 질문을 하거나 다르게 대답을 할 수도 있습니다. 그러한 대화의 흐름을 설계하고 구체적으로 정의할 수 있는 곳이 Chatflow입니다.

지금부터 차근차근 Chatflow를 만들어보겠습니다.

### 대화흐름(Chatflow) 메뉴로 이동
Step 1에서 만든 피자주문 Intent 페이지를 보면 연관 Chatflow에 생성된 Chatflow가 없다는 메시지를 볼 수 있습니다. 우측의 ***“Chatflow 생성”*** 버튼을 클릭하여 Chatflow 설정 화면으로 이동해 보겠습니다.

{% include image.html file="tutorial/basic02_create_chatflow.png" max-width="900" caption="Intent 상세페이지에서 Chatflow 생성" %}

### Chatflow 생성
Intent 상세 페이지에서 “Chatflow 생성” 버튼을 클릭하면 해당 Intent와 동일한 이름의 Chatflow가 자동으로 생성되어 상세페이지로 이동합니다.
Chatflow 목록에서 직접 Chatflow를 생성하는 방법은 document의 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Chatflow 생성](/chatflow.html#chatflow-%EC%83%9D%EC%84%B1)</span>을 보시면 더욱 자세히 알 수 있습니다.

Chatflow에는 각각 역할을 지닌 여러 Node들이 존재하는데 처음 Chatflow 상세화면으로 진입하면 Listen Node와 Speak Node가 기본적으로 생성되어 있습니다. 이 두 가지가 대화를 만들 수 있는 가장 기본적인 노드입니다. 그럼 Listen Node와 Speak Node를 이용하여 대화를 만들어보겠습니다.

{% include image.html file="tutorial/basic02_chatflow_detail.png" max-width="900" caption="Chatflow 상세화면" %}

### Listen Node
Listen Node는 Chatflow에서 항상 첫 번째로 시작하는 노드로, 앞서 생성했던 Intent를 포함하고 있는 노드입니다. 사용자가 입력한 말이 어떤 Intent인지 파악되면, 그 Intent로 설정되어 있는 Chatflow가 시작되는 것입니다.

Listen Node를 더블 클릭하여 상세 화면으로 들어가면, 생성된 Intent를 조회하여 연결할 수 있는데, 피자주문 Intent에서 바로 Chatflow를 생성하여 넘어왔기 때문에 피자주문 Intent가 이미 선택되어 있는 것을 확인할 수 있습니다. Intent와 Chatflow는 1 대 1로만 연결되며, 선택된 Intent에 포함된 다른 정보들도 Listen Node에서 함께 조회할 수 있습니다.

{% include image.html file="tutorial/basic02_listen_detail.png" max-width="900" caption="Listen Node 상세화면" %}

#### Node 명 수정
기본정보 탭을 클릭하면, Node Name을 수정할 수 있습니다. Node Name을 잘 정리하여 관리하면 Chatflow가 어떻게 구성되어 있는지 한 눈에 확인할 수 있습니다.

{% include image.html file="tutorial/basic02_node_info.png" max-width="900" caption="기본정보 탭" %}

우측 하단의 ***”확인”*** 버튼을 클릭하여 Node 명이 바뀐 것을 확인해보세요.
Node를 한번만 클릭하면 Node에서 직접 Node 명을 바꿀 수도 있습니다.

{% include image.html file="tutorial/basic02_edit_node_name.png" max-width="900" caption="Node 명 수정상태" %}

### Speak Node
Speak Node는 챗봇이 어떻게 응답할지 챗봇 메시지를 정의하는 노드입니다. 기본적으로는 텍스트 형태로 메시지를 작성할 수 있고, 필요에 따라 메시지를 여러 개 작성하거나 이미지나 버튼을 포함시킬 수 있습니다. 다양한 Speak Node 사용 방법은 document의 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Speak 노드](/chatflow_speak.html)</span>를 보시면 더욱 자세히 알 수 있습니다.
이번 Step에서는 간단히 텍스트 메시지 형태로 만들어보도록 하겠습니다.

#### 기본 메시지 작성
1) Speak Node를 더블 클릭하여 상세화면을 띄워주세요.

2) 기본조건에서 ***“기본메시지”***를 선택해주세요. 다른 Speak Node 설정이 없다면, 항상 이 기본메시지로 응답하게 됩니다.

3) ***“피자를 주문할게요”***를 Message 입력란에 입력하고 우측 하단의 확인 버튼을 클릭해주세요.

{% include image.html file="tutorial/basic02_speak_detail.png" max-width="900" caption="Speak Node 상세화면" %}

### 선 연결하기
Listen Node와 Speak Node 작성을 완료하면, 두 노드 끝에 있는 점과 점을 마우스로 드래그하여 연결해주세요. 이 선은 대화흐름을 만들어주는 역할을 하며, Listen Node에서 시작해서 마지막으로 연결된 노드까지 순차적으로 실행되어 하나의 대화흐름을 완료하게 됩니다.

Chatflow가 완성되었으니 우측 상단의 ***"Chatflow 저장"*** 버튼을 클릭하여 데이터를 저장해주세요.

{% include image.html file="tutorial/basic02_connect_line.png" max-width="900" caption="Listen Node와 Speak Node 선으로 연결" %}


## Chatflow 테스트
우측의 테스트 패널에서 저장한 Chatflow가 제대로 동작하는지 테스트 해볼 수 있습니다.
Chatflow 탭에서 ***“피자 주문해줘”*** 예문을 입력해보면 Speak Node에 등록했던 메시지로 응답하는 것을 확인할 수 있습니다.

{% include image.html file="tutorial/basic02_test_chatflow.png" max-width="900" caption="Chatflow 테스트 패널" %}


## 다음 Step에서는
Intent와 예문을 등록하고, Listen Node와 Speak Node로 간단하게 대화를 만들어보았는데요. 이 방식으로 대화를 만들면, 모든 피자 메뉴에 대한 예문과 그에 대응하는 응답 메시지를 각각 만들어주어야 하는 불편함이 발생합니다. 이러한 불편함을 해결하기 위해 Entity와 Parameter를 등록하고 사용하는 방법을 배워보도록 하겠습니다.

