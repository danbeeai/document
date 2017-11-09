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

### 샘플 시나리오 (좋아하는 음식은?)

Carousel 노드에서는 Listen 노드에 선언된 단어항목(parameter)들에 한해 값을 카드 형태로 물어보기 위한 설정을 할 수 있습니다.
해당 시나리오는 'question1' 변수값에 좋아하는 음식을 선택 받고 선택 받은 값을 Speak 노드 메시지에 표시합니다.

{% include image.html file="chatflow/Chatflow_carousel_sampleCanvas.png" max-width="900" caption="좋아하는 음식은 시나리오" %}

Listen 노드에 좋아하는 음식을 선택받기 위해 'question1' 변수를 선언한다. 

{% include image.html file="chatflow/Chatflow_carousel_sampleListen.png" max-width="900" caption="Listen 노드 설정" %}

'좋아하는 음식은?' 질문 메시지를 입록하고 'question1' 변수에 선택 카드 정보 값을 받겠다고 설정합니다. 
그리고 좋아하는 '짜장면', '짬뽕' 카드를 아래와 같이 설정합니다. 

{% include image.html file="chatflow/Chatflow_carousel_card.png" max-width="900" caption="Carousel 노드 설정" %}

Speak 노드에 'question1' 변수 기준으로 값이 '짜장면', '짬뽕' 경우에 따라 다른 메시지를 표시하도록 설정합니다.

{% include image.html file="chatflow/Chatflow_carousel_sampleSpeak.png" max-width="900" caption="Speak 노드 설정" %}

'좋아하는 음식은?' 질문에 '짜장면'을 선택하면 아래와 같이 결과가 나타납니다. 

{% include image.html file="chatflow/Chatflow_carousel_sampleTest.png" max-width="900" caption="좋아하는 음식은? 테스트 결과" %}