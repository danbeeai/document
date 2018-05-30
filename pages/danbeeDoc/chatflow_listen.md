---
title: Listen 노드
tags: [chatflow]
keywords: Basic Conversation
summary: Listen 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_listen.html
folder: danbeeDoc
previous: {
    title: 대화흐름 기본 설명, 
    url: chatflow.html
}
next: {
    title: Speak 노드,
    url: chatflow_speak.html
}
---

## Listen 노드

Listen 노드는 사용자의 의도가 무엇인지 가장 먼저 파악하고 대화의 흐름을 시작하는 가장 첫 번째 노드입니다.

Listen 노드가 없으면 대화흐름은 어떤 의도를 기반으로 어떤 질문들을 해야 할지 파악할 수 없는 필수 노드로
매핑된 인텐트의 예문 패턴이 일치할 때 해당 Listen 노드가 대화 흐름을 시작하게 됩니다.



Listen 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_listen.html#기본정보)
- [인텐트 연결](Chatflow_listen.html#인텐트-연결)
- [Event 연결](Chatflow_listen.html#event-연결)

{% include image.html file="chatflow/Chatflow_listen_canvas.png" max-width="900" caption="Listen노드" %}



### 기본정보

Listen 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_listen_basic.png" max-width="900" caption="Listen노드 기본정보" %}


### 인텐트 연결

Listen Node 연결 방법 라디오 버튼 중 Intent를 선택합니다.
인텐트 연결은 2개의 탭으로 구성되어 있습니다. 
- [의도추론예문](Chatflow_listen.html#의도추론예문)
- [Parameter](Chatflow_listen.html#parameter)

의도관리에서 등록된 인텐트들을 매핑함으로써 인텐트에 등록된 예문 페턴이 일치될때 해당 Listen 노드가 구동되어 Chatflow의 흐름을 타게 됩니다. 
Listen 노드와 인텐트는 1:1 매핑 관계를 갖게 됩니다. 그렇기 때문에 인텐트 연결시 이미 매핑된 인텐트와 선택가능한 인텐트가 구분되어 보여지게 됩니다.

{% include image.html file="chatflow/Chatflow_listen_select.png" max-width="900" caption="인텐트 선택" %}

#### 의도추론예문

선택된 인텐트에 대해서는 등록되었던 의도추론 예문 패턴이 화면에 나열됩니다. 
아래 그림은 야식주문 Listen 노드가 구동되기 위한 인텐트가 매핑된 화면 입니다.

{% include image.html file="chatflow/Chatflow_listen_intent.png" max-width="900" caption="인텐트 탭" %}

#### Parameter

선택된 인텐트에 등록되었던 Parameter가 화면에 나열됩니다. 
Parameter(단어항목)은 의도관리에서 등록된 '추출된 Parameter' 데이터를 의미합니다. 
사용자가 입력된 문장에서 NLU가 의미 있는 Parameter 정보를 추출하게 되고 그 정보를 매핑된 Listen 노드가 전달받는 구조입니다.
Listen 노드에서 Parameter를 추가적으로 등록하고 싶다면 [+] 버튼을 클릭하여 Parameter 명과 유형을 지정해 주면 됩니다. 

{% include image.html file="chatflow/Chatflow_listen_parameter.png" max-width="900" caption="파라미터 탭" %}

### Event 연결

Listen Node 연결 방법 라디오 버튼 중 Event를 선택합니다.
Event 연결은 2개의 탭으로 구성되어 있습니다.

- [Event](Chatflow_listen.html#event)
- [Parameter](Chatflow_listen.html#event-parameter)

#### Event

만들고자 하는 Event 명칭을 작성합니다. 확인 버튼을 누른 뒤 chatflow 저장 버튼을 눌러 chatflow를 저장합니다.
저장 후 Listen Node 를 클릭 하면 Event Url 정보를 확인 할 수 있고, 해당 Url로 chatflow를 실행 할 수 있습니다.

{% include image.html file="chatflow/Chatflow_listen_event.PNG" max-width="900" caption="이벤트 탭" %}

Event호출 방법은 Post방식으로 호출 합니다. 필수 값은 chatbot id, parameters 배열 객체를 기본값 으로 설정 하셔야합니다.
응답 결과는 Json형태로 Return 됩니다.

{% include image.html file="chatflow/Chatflow_listen_event_result.PNG" max-width="900" caption="이벤트 결과 탭" %}

#### Event Parameter

Event 내부에서 사용하는 Parameter를 설정 할 수 있습니다. Event 에서 Parameter를 등록하고 싶다면 [+] 버튼을
클릭하여 Parameter 명을 설정 합니다. Default Value 는 해당 Parameter의 기본 값으로 입력 값이 없을때 Default Value
를 Parameter 값 으로 다음 Node로 넘기게 됩니다.

{% include image.html file="chatflow/Chatflow_listen_event_parameter.PNG" max-width="900" caption="이벤트 파라미터 탭" %}