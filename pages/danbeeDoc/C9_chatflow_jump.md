---
title: JUMP 노드
tags: [chatflow, advanced]
keywords: Basic Conversation
summary: Jump 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_jump.html
folder: danbeeDoc
previous: {
    title: Carousel 노드,
    url: chatflow_carousel.html
}
next: {
    title: 사용자사전 관리,
    url: dictionary.html
}
---

## JUMP 노드

JUMP 노드는 Chatflow 시나리오 도중에 다른 챗플로우로 이동하는 기능을 제공합니다. 
JUMP 노드를 통해 Chatflow 간 이동하면서 파라미터 값을 전달을 할 수 있는 기능을 함께 제공함으로써 연이은 대화 시나리오 흐름을 이어 갈 수 있도록 구성이 가능합니다. 

Jump 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](chatflow_jump.html#기본정보)
- [Jump 설정](chatflow_jump.html#Jump 설정)

{% include image.html file="chatflow/Chatflow_jump_canvas.png" max-width="900" caption="Jump 노드" %}

### 기본정보

Jump 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_jump_basic.png" max-width="900" caption="Jump노드 기본정보" %}

### Jump 설정

Jump 노드는 이동할 챗플로우를 지정하고 전달하고 싶은 파라미터들을 매핑 설정하는 방식으로 구성이 되어 있습니다. 

챗플로우의 흐름에서 Jump 노드에 도달하게 되면 이후에 다른 노드가 남아 있더라도 Jump 노드에서 지정된 다음 챗플로우로 이동하게 됩니다. 

만약 이동 전 챗플로우에서 사용하던 파라미터를 다음 챗플로우로 전달하고자 할 경우 파라미터 매핑을 하여 값을 전달할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_jump_mapping.png" max-width="900" caption="Jump 노드 설정" %}



### 샘플 시나리오 (처음 뵙겠어요)

샘플 시나리오는 사용자가 챗봇에게 "처음 뵙겠어요" 인사했을때 챗봇이 이름을 물어보고 인사하는 내용으로 구성되어 있습니다. 

이름을 물어보는 챗플로우와 '이름' 정보를 받아 인사를 건내는 챗플로우로 각각 구성이 되어 있고 이 사이에서 Jump 노드가 

대화의 흐름을 자연스럽게 이어줄 것입니다. 


#### 시작 Chatflow

시작 챗플로우에서는 Slot 노드로 이름을 정보(name)를 물어보고 Jump 노드를 활용하여 다음 챗플로우로 Jump 합니다. 

{% include image.html file="chatflow/Chatflow_jump_canvas1.png" max-width="900" caption="시작 Chatflow" %}


#### [이름 문의] Slot 노드 설정

이름을 물어보는 질문과 답변을 받아 저장할 파라미터 'name'을 설정합니다. 

{% include image.html file="chatflow/Chatflow_jump_slot.png" max-width="900" caption="Jump 노드 설정" %}

#### [점프:인사] Jump 노드 설정

Jump 노드에서 이동할 Chatflow '제 이름은 아무개 입니다"를 선택하고 점프할 때 함께 전달할 파라미터 'name'을 매핑 설정합니다.

{% include image.html file="chatflow/Chatflow_jump_mapping2.png" max-width="900" caption="Jump 노드 설정" %}


#### 이동할 Chatflow

{% include image.html file="chatflow/Chatflow_jump_canvas2.png" max-width="900" caption="이동할 Chatflow" %}


#### [Listen Node] Listen 노드 설정

'시작 Chatflow'에서 전달할 파라미터를 받을 파라미터 역시 동일한 이름 'name'으로 설정합니다.

{% include note.html content="챗플로우간에 전달해 주고 받을 파라미터 명칭들은 동일할 필요는 없습니다." %}

{% include image.html file="chatflow/Chatflow_jump_speak.png" max-width="900" caption="Listen 노드 설정" %}

#### [반갑습니다.] Speak 노드 설정

'시작 Chatflow'에서 전달받은 파라미터를 활용하여 답변을 다음과 같이 설정합니다. 

{% include image.html file="chatflow/Chatflow_jump_speak.png" max-width="900" caption="Speak 노드 설정" %}


#### 테스트

아래와 같이 Jump 노드를 활용하여 챗플로우간 이동하면서 파라미터를 전달하는 간단한 인사 시나리오 테스트 확인이 가능합니다.

{% include image.html file="chatflow/Chatflow_jump_test.png" max-width="900" caption="테스트 화면" %}