---
title: Carousel 노드
tags: []
keywords: Basic Conversation
summary: Carousel 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_carousel.html
folder: danbeeDoc
previous: {
    title: Split 노드,
    url: chatflow_split.html
}
next: {
    title: API 노드,
    url: chatflow_api.html
}
---

## Corousel 노드

Carousel 노드는 사용자에게 필요한 정보를 묻는 차원에서 Slot 노드와 유사합니다. 단, Slot 노드는 되묻는 메시지에 버튼 또는 메시지로 답변 했다면 Carousel 노드는 카드 형태로 제공합니다. 
Slot 노드는 하나의 노드에 여러 개의 질문지를 제시할 수 있지만 Carousel은 하나의 질문에 여러 개의 선택지를 카드형태로 제공하는 노드라고 이해하시면 됩니다. 


Corousel 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_carousel.html#기본 정보)
- [메시지 카드 설정](Chatflow_carousel.html#메시지 카드 설정)

{% include image.html file="chatflow/Chatflow_carousel_cavas.png" max-width="900" caption="Carousel 노드" %}

### 기본 정보

Carousel 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_carousel_basic.png" max-width="900" caption="기본정보" %}

### 메시지 카드 설정

Carousel 노드는 Slot 노드와 마찬가지로 대화자에게 선택을 받기 위한 노드입니다. 
그렇기 때문에 Slot 노드에서 처럼 질문에 대한 메시지와 질문 대상을 Parameter로 입력 받을 수 있습니다. 
Carousel은 추가적으로 선택지를 카드형태로 받을 수 있는 노드로 아래 그림처럼 "좋아하는 음식을 선택하시요" 라는 질문으로 짜장면과 짬뽕 카드를 제시할 수 있습니다.

{% include image.html file="chatflow/Chatflow_carousel_card.png" max-width="900" caption="메시지 카드 설정" %}