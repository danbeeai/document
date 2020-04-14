---
title: Listen Node 
tags: [chatflow, basic, listen, intent, event, 이벤트, 대화흐름, 리슨Node, 의도추론예문, 파라미터]
keywords: Basic Conversation
summary: Listen Node에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_listen.html
folder: danbeeDoc
previous: {
    title: 대화흐름 기본 설명, 
    url: chatflow.html
}
next: {
    title: Speak Node,
    url: chatflow_speak.html
}
---

Listen Node는 사용자의 의도가 무엇인지 가장 먼저 파악하고 대화의 흐름을 시작하는 가장 첫 번째 Node입니다.
Listen Node는 대화의도나 사용자 이벤트에 연결되어 작동하게됩니다.

{% include image.html file="chatflow/Chatflow_listen_canvas.png"  caption="ListenNode" %}

<!-- 

### 기본정보

Listen Node에 표시될 기본적인 Node명과 Node에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_listen_basic.png"  caption="ListenNode 기본정보" %}


### 대화의도 연결

Listen 노드 연결 방법 라디오 버튼 중 Intent를 선택합니다.
대화의도 연결은 2개의 탭으로 구성되어 있습니다. 
- [의도추론예문](chatflow_listen.html#의도추론예문)
- [파라미터](chatflow_listen.html#parameter)

의도관리에서 등록된 대화의도들을 매핑함으로써 대화의도에 등록된 예문 페턴이 일치될때 해당 Listen Node가 구동되어 Chatflow의 흐름을 타게 됩니다. 
Listen Node와 대화의도는 1:1 매핑 관계를 갖게 됩니다. 그렇기 때문에 대화의도 연결시 이미 매핑된 대화의도와 선택가능한 대화의도가 구분되어 보여지게 됩니다.

{% include image.html file="chatflow/Chatflow_listen_select.png"  caption="대화의도 선택" %}

#### 의도추론예문

선택된 대화의도에 대해서는 등록되었던 의도추론 예문 패턴이 화면에 나열됩니다. 
아래 그림은 야식주문 Listen Node가 구동되기 위한 대화의도가 매핑된 화면 입니다.

{% include image.html file="chatflow/Chatflow_listen_intent.png"  caption="대화의도 탭" %}

#### 파라미터

선택된 대화의도에 등록되었던 파라미터가 화면에 나열됩니다. 
파라미터(단어항목)은 의도관리에서 등록된 '추출된 파라미터' 데이터를 의미합니다. 
사용자가 입력된 문장에서 NLU가 의미 있는 파라미터 정보를 추출하게 되고 그 정보를 매핑된 Listen 노드가 전달받는 구조입니다.
Listen 노드에서 파라미터를 추가적으로 등록하고 싶다면 [+] 버튼을 클릭하여 파라미터 명과 유형을 지정해 주면 됩니다. 

{% include image.html file="chatflow/Chatflow_listen_parameter.png"  caption="파라미터 탭" %} -->

### Event 관리

리슨노드 상세에서 이벤트 플로우에 대한 설정을 진행할 수 있습니다.
이벤트 플로우로 전환하기 토글 버튼을 켜면 이벤트 플로우로 전환됩니다.

>##### Event
만들고자 하는 Event 명칭을 작성합니다. 확인 버튼을 누른 뒤 chatflow 저장 버튼을 눌러 chatflow를 저장합니다.
저장 후 Listen 노드 를 클릭 하면 Event Url 정보를 확인 할 수 있고, 해당 Url로 chatflow를 실행 할 수 있습니다.

>Event호출 방법은 Post방식으로 호출 합니다. 필수 값은 chatbot id, parameters 배열 객체를 기본값 으로 설정 하셔야합니다.
응답 결과는 Json형태로 Return 됩니다.

>{% include image.html file="chatflow/Chatflow_listen_event_result.PNG"  caption="이벤트 결과 탭" %}

>##### Event 파라미터
Event 내부에서 사용하는 파라미터를 설정 할 수 있습니다. Event 에서 파라미터를 등록하고 싶다면 대화흐름 상세 오른쪽 하단 [+] 버튼을
클릭하여 파라미터 명을 설정 합니다. Default Value 는 해당 파라미터의 기본 값으로 입력 값이 없을때 Default Value
를 파라미터 값 으로 다음 Node로 넘기게 됩니다.


{% include bottom.html %}
