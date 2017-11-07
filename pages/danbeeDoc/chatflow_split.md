---
title: Split 노드
tags: []
keywords: Basic Conversation
summary: Split 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_split.html
folder: danbeeDoc
previous: {
    title: Slot 노드,
    url: chatflow_slot.html
}
next: {
    title: Carousel 노드,
    url: chatflow_carousel.html
}
---

## Split 노드

Split 노드는 입력된 메시지 및 파라미터 조건에 따라 대화의 흐름을 분기 시켜주는 노드입니다. Split 노드에서 분기할 노드를 추가하기 위해선 연결한 노드가 미리 추가되어있고 노드들은 연결선으로 Split 노드와 연결되어 있어야 합니다. Split 노드와 연결된 노드만 분기할 노드로 선택할 수 있습니다.


Split 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_split.html#기본정보)
- [분리조건 설정](Chatflow_split.html#분리조건 설정)

{% include image.html file="chatflow/Chatflow_split_cavas.png" max-width="900" caption="Split 노드" %}


### 기본정보

Split 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_split_basic.png" max-width="900" caption="Split노드 기본정보" %}

### 분리조건 설정

{% include image.html file="chatflow/Chatflow_split_select.png" max-width="900" caption="분기 선택" %}

{% include image.html file="chatflow/Chatflow_split_condition.png" max-width="900" caption="분기조건 설정" %}