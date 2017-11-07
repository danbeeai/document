---
title: Listen 노드
tags: []
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
- [인텐트 연결](Chatflow_listen.html#인텐트 연결)


### 기본정보

Listen 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_listen_basic.png" max-width="900" caption="Listen노드 기본정보" %}


### 인텐트 연결

인텐트 연결은 2개의 탭으로 구성되어 있습니다. 
- [의도추론 예문](Chatflow_listen.html#의도추론 예문)
- [단어항목](Chatflow_listen.html#단어항목)


의도관리에서 등록된 인텐트들을 매핑함으로써 인텐트에 등록된 예문 페턴이 일치될때 해당 Listen 노드가 구동되어 Chatflow의 흐름을 타게 됩니다. 
Listen 노드와 인텐트는 1:1 매핑 관계를 갖게 됩니다. 그렇기 때문에 인텐트 연결시 이미 매핑된 인텐트와 선택가능한 인텐트가 구분되어 보여지게 됩니다.

{% include image.html file="chatflow/Chatflow_listen_select.png" max-width="900" caption="인텐트 선택" %}

#### 의도추론 예문

선택된 인텐트에 대해서는 등록되었던 의도추론 예문 패턴이 화면에 나열됩니다. 
아래 그림은 야식주문 Listen 노드가 구동되기 위한 인텐트가 매핑된 화면 입니다.

{% include image.html file="chatflow/Chatflow_listen_intent.png" max-width="900" caption="인텐트 탭" %}

#### 단어항목

선택된 인텐트에 등록되었던 단어항목이 화면에 나열됩니다. 
단어항목(Parameter)은 의도관리에서 등록된 '추출된 Parameter' 데이터를 의미합니다. 
사용자가 입력된 문장에서 NLU가 의미 있는 Parameter 정보를 추출하게 되고 그 정보를 매핑된 Listen 노드가 전달받는 구조입니다.

{% include image.html file="chatflow/Chatflow_listen_parameter.png" max-width="900" caption="파라미터 탭" %}

