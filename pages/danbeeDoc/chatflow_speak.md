---
title: Speak 노드
tags: []
keywords: Basic Conversation
summary: Speak 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_speak.html
folder: danbeeDoc
previous: {
    title: Listen 노드, 
    url: chatflow_listen.html
}
next: {
    title: Slot 노드,
    url: chatflow_slot.html
}
---

## Speak 노드

Speak 노드는 입력되는 메시지 조건을 설정하고 설정된 조건에 일치되는 메시지가 입력되면 답변을 전송하는 노드입니다.
Speak 노드는 메시지, 이미지, 버튼 등의 다양한 기능들의 조합으로 구성이 가능하며,
Speak 노드 내에서 메시지 조건을 설정하여 다양한 답변하는 기능은 복잡한 대화 흐름을 설계하는데 있어 보다 더 나은 간결함을 제공합니다.

그리고 Speak 노드에서 사용자의 의도 질문에 한가지로만 답하는 식상한 챗봇이 아닌 같은 대답을 다양한 표현으로 친근감을 제공하기 위한 랜덤 메시지 기능을 제공 합니다. 
챗봇이 연달아 메시지 답변을 하고자 할 경우에는 Speak 노드를 연이어 배치하면 됩니다. 


Speak 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_speak.html#기본정보)
- [메시지 설정](Chatflow_speak.html#메시지 설정)

{% include image.html file="chatflow/Chatflow_speak_cavas.png" max-width="900" caption="Speak 노드" %}

### 기본정보

Speak 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_speak_basic.png" max-width="900" caption="Speak노드 기본정보" %}


### 메시지 설정

{% include image.html file="chatflow/Chatflow_speak_message.png" max-width="900" caption="메시지 설정" %}

### 샘플 시나리오 (랜덤 메시지 테스트)

{% include image.html file="chatflow/Chatflow_speak_randomCanvas.png" max-width="900" caption="기본 메시지 랜덤 설정" %}

{% include image.html file="chatflow/Chatflow_speak_random.png" max-width="900" caption="기본 메시지 랜덤 설정" %}

### 샘플 시나리오 (변수값 표시)

{% include image.html file="chatflow/Chatflow_speak_paramCanvas.png" max-width="900" caption="변수값 표시 시나리오" %}

{% include image.html file="chatflow/Chatflow_speak_paramListen.png" max-width="900" caption="Listen 노드 설정" %}

{% include image.html file="chatflow/Chatflow_speak_paramSlot.png" max-width="900" caption="Slot 노드 설정" %}

{% include image.html file="chatflow/Chatflow_speak_paramSpeak.png" max-width="900" caption="Speak 노드 설정" %}