---
title: 대화흐름 기본 설명
tags: []
keywords: Basic Conversation
summary: 대화흐름 관리
sidebar: danbee_doc_sidebar
permalink: chatflow.html
folder: danbeeDoc
previous: {
    title: 엔티티 관리, 
    url: entity.html
}
next: {
    title: Listen 노드,
    url: chatflow_listen.html
}
---

## 대화흐름 기본 설명

사람과 사람간의 대화에는 이야기 흐름이 있습니다. 처음에 인사를 하고 안부를 묻고 둘 사이의 관심사 등에 대해서 서로 이야기를 진행해 나가듯이 대화 과정에서 하나하나의 이야기 단위들이 (인사, 날씨문의, 취미 등) 모여 대화의 흐름을 구성하게 됩니다. 
여기에서 그 하나하나의 이야기 단위를 Danbee.Ai 에서는 Chatflow 라는 이야기 단위로 명명을 하고 있습니다. 
대화할 때에는 상대방의 이야기를 듣고 대답하는 것이 기본일 것입니다. Chatflow에서도 챗봇이 사람과 대화하는데 있어서 말귀를 알아 듣고 (Listen 노드) 대답 (Speak 노드) 하는 기본 방식으로 구성이 되어 있습니다. 
대화 과정에서 확인해야 할 사항이 있다면 되묻는 질문을 할 수 도 있겠고, 상대방의 답변에 대해 논리적으로 판단하여 대화의 흐름을 달리 이야기해야 할 경우도 있을 것입니다. 
Chatflow는 이러한 대화 과정에서 필요한 기본적인 듣고, 말하고, 판단하고 정보를 활용하는 기본적인 대화 노드들의 조합으로 대화의 흐름을 구성할 수 있는 역할을 담당하고 있습니다. 
다음 내용에서는 Chatflow에서 사용되고 있는 각각의 대화 노드들에 대해 자세히 알아보겠습니다

{% include callout.html content="화면 위치 : [대화흐름(Chatflow)] > [대화흐름 목록(Chatflow List)]" type="default" %}

### 2.3.1. 리슨 노드

listen

### 2.3.2. 스피크 노드

speak

### 2.3.3. 슬랏 노드

slot

### 2.3.4. 스플릿 노드

split

### 2.3.5. 캐로셀 노드

carousel

### 2.3.6. API 노드 > 밑에 (4)로 이동 ??

4.2 에서 확인

### 2.3.7. Function 노드

function
