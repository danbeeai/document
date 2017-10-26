---
title: Slot 노드
tags: []
keywords: Basic Conversation
summary: Slot 노드에 대한 이해와 설정 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_slot.html
folder: danbeeDoc
previous: {
    title: Speak 노드, 
    url: chatflow_speak.html
}
next: {
    title: Split 노드,
    url: chatflow_split.html
}
---

## Slot 노드

Slot Node는 Slot-filling 노드의 줄임말로 챗봇이 사용자의 의도를 파악하여 명령을 수행하는데 있어, 필수적으로 얻어야 하는 정보를 되물어볼 수 있는 노드입니다.

예를 들어 회의실 예약하는 의도라고 한다면 회의실 장소와 일자, 시간, 참여자 정보가 필요 것입니다. 그런데 챗봇에게 “일정 잡아줘” 라고만 요청한다면 챗봇 입장에서는 요청 내용만 가지고는 회의실을 예약할 수 없습니다. 
이런 경우 챗봇은 회의실을 예약하기 위한 기본적인 정보 (일자, 시간, 참여자, 장소)를 되물어봐야 하는데 이때, Slot 노드가 그러한 역할을 수행합니다.

만약 사용자가 “내일 A회의실 예약해줘” 라고 묻는다면, 챗봇이 회의실 예약하는데 필요한 기본 정보 일자, 시간, 참여자, 장소를 다시 되물어봐야 할까요?
Slot 노드에서는 사용자가 물어본 문장에서 ‘내일’ 이라는 일자와 ‘A회의실’ 이라는 장소 정보가 있기 때문에 굳이 ‘일자’ 와 ‘장소’ 정보를 되물을 필요가 없기 때문에 Slot 노드에서는 부족한 정보 참여자, 시간 정보만을 되묻게 됩니다. 


Slot 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_slot.html#기본정보)
- [질문 설정](Chatflow_slot.html#질문 설정)


### 기본정보

{% include image.html file="chatflow/Chatflow_slot_basic.png" max-width="900" caption="Slot노드 기본정보" %}

### 질문 설정

{% include image.html file="chatflow/Chatflow_slot_question.png" max-width="900" caption="질문 설정" %}