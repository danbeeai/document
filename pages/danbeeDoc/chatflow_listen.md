---
title: Listen 노드
tags: []
keywords: Basic Conversation
summary: 대화흐름 관리
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

Listen 노드는 사용자의 의도가 무엇인지 가장 먼저 파악하고 대화의 흐름을 시작하는 가장 첫 번째 노드입니다. Listen 노드가 없으면 대화흐름은 어떤 의도를 기반으로 어떤 질문들을 해야 할지 파악할 수 없는 필수 노드입니다.
Listen 노드는 예문 패턴이 등록된 인텐트와 매핑함으로써 예문 패턴과 일치할 때 해당 Listen 노드가 대화 흐름을 시작하게 됩니다.


### 2.3.1. 리슨 노드

Listen Node는 사용자의 의도가 무엇인지 가장 먼저 파악하고 대화의 흐름을 시작하는 가장 첫번째 Node입니다. Listen Node가 없으면 대화흐름은 어떤 의도를 기반으로 어떤 질문들을 해야할지 파악할 수 없는 필수 Node 입니다.  

### 2.3.2. 스피크 노드

speak

### 2.3.3. 슬랏 노드

Slot Node는 사용자에게 필요한 정보를 되물어볼 수 있는 Node 입니다. 

### 2.3.4. 스플릿 노드

Split Node는 입력된 메시지의 조건에 따라 대화의 흐름을 분기시켜주는 Node입니다. Split Node에서 분기할 노드를 추가하기 위해선 연결한 노드가 미리 추가되어있고 Node 연결선으로 Split Node와 연결되어 있어야 합니다. Split Node와 연결된 Node만 분기할 Node로 선택할 수 있습니다

### 2.3.5. 캐로셀 노드

carousel

### 2.3.6. API 노드 > 밑에 (4)로 이동 ??

4.2 에서 확인

### 2.3.7. Function 노드

function
