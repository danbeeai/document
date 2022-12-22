---
title: Listen Node 
tags: [chatflow, basic, listen, intent, event, 이벤트, 대화 흐름, 리슨Node, 의도추론예문, 파라미터]
keywords: Basic Conversation
summary: Listen Node에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_listen.html
folder: danbeeDoc
previous: {
    title: 파라미터, 
    url: parameter.html
}
next: {
    title: Speak Node,
    url: chatflow_speak.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 주요 대화 > 대화 흐름" type="default" %}

<br>
{% include image.html file="chatflow/01_chatflow_listen.png" %}


## 개요

Listen Node는 사용자의 의도가 무엇인지 가장 먼저 파악하고 대화의 흐름을 시작하는 가장 첫 번째 Node입니다. 
Listen Node는 대화 의도나 사용자 이벤트에 연결되어 작동하게됩니다. 



## 이벤트 관리

리슨노드 상세에서 이벤트 플로우에 대한 설정을 진행할 수 있습니다. 이벤트 플로우로 전환하기 토글 버튼을 켜면 이벤트 플로우로 전환됩니다.  

{% include image.html file="chatflow/02_chatflow_listen.png" %}

### Event
만들고자 하는 Event 명칭을 작성합니다. 확인 버튼을 누른 뒤 chatflow 저장 버튼을 눌러 chatflow를 저장합니다.   

{% include image.html file="chatflow/03_chatflow_listen.png" %}

저장 후 Listen 노드 를 클릭 하면 Event Url 정보를 확인 할 수 있고, 해당 Url로 chatflow를 실행 할 수 있습니다.

Event호출 방법은 Post방식으로 호출 합니다. 필수 값은 chatbot id, parameters 배열 객체를 기본값 으로 설정 하셔야합니다. 응답 결과는 Json형태로 Return 됩니다.  

{% include image.html file="chatflow/04_chatflow_listen.png" %}

### Event 파라미터

Event 내부에서 사용하는 파라미터를 설정 할 수 있습니다. Event 에서 파라미터를 등록하고 싶다면 대화 흐름 상세 오른쪽 하단 [+] 버튼을 클릭하여 파라미터 명을 설정 합니다.   

{% include image.html file="chatflow/05_chatflow_listen.png" %}  

Default Value 는 해당 파라미터의 기본 값으로, 입력 값이 없을때 Default Value 를 파라미터 값 으로 다음 Node로 넘기게 됩니다.


{% include bottom.html %}
