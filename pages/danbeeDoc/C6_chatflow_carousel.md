---
title: Carousel 노드 
tags: [chatflow, basic]
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
    title: Knowledge 노드,
    url: chatflow_knowledge.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 주요 대화 > 대화 흐름" type="default" %}

## 개요

Carousel 노드는 사용자에게 필요한 정보를 묻는 차원에서 Slot 노드와 유사합니다. 단, Slot 노드는 되묻는 메시지에 버튼 또는 메시지로 답변 했다면 Carousel 노드는 카드 형태로 제공합니다. 
Slot 노드는 하나의 노드에 여러 개의 질문지를 제시할 수 있지만 Carousel은 하나의 질문에 여러 개의 선택지를 카드형태로 제공하는 노드라고 이해하시면 됩니다. 


Carousel 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](chatflow_carousel.html#기본-정보)
- [메시지 카드 설정](chatflow_carousel.html#메시지-카드-설정)

{% include image.html file="chatflow/Chatflow_carousel_canvas.png"  caption="Carousel 노드" %}

## 캐로셀 서브타이틀 채널별 제한

| 채널명 | 캐로셀 서브타이틀 제한 | 참고링크 |
|-------|-------|------|
| Frogue | 제한없음 | https://doc.danbee.ai/channel_frogu.html |
| Facebook | 최대80자 | developers.facebook.com/docs/messenger-platform/reference/templates/generic |
| Telegram | subtitle 사용안함 | https://core.telegram.org/bots |
| Slack | 정보없음 | api.slack.com/reference/messaging/attachments |
| Line Works | 이미지O 100자, 이미지X 120자 | https://developers.worksmobile.com/kr/document/1005008?lang=ko |
| Line | 최소60자, 최대120자 | developers.line.biz/en/reference/messaging-api/#template-messages |
| Naver 톡톡 | 최대1000자 | github.com/navertalk/chatbot-api#composite-object |
| Kakao i Builder | 단일 230자 / 캐로셀 이미지X 76자, 이미지O 40자 | https://i.kakao.com/docs/tutorial-chatbot-response#%EB%A7%90%ED%92%8D%EC%84%A0-%EC%A0%9C%EC%9E%91-%EC%8A%A4%ED%8E%99-%EC%A0%95%EB%B3%B4 |
| Kioscott - beta | 제한없음 | https://doc.danbee.ai/channel_kioscott.html |

## 메시지 카드 설정

### Slot같이 동작하는 Carousel만들기
Carousel 노드는 Slot 노드와 마찬가지로 대화자에게 선택을 받기 위한 노드입니다. 그렇기 때문에 Slot 노드에서 처럼 질문에 대한 메시지와 질문 대상을 파라미터로 입력 받을 수 있습니다. 단, Slot 노드와 동일하게 질문하고자하는 항목 변수의 값이 이미 있는 경우에는 해당 질문을 하지 않습니다. <br/>변수 값이 있는 경우라도 재확인 차원에서 질문을 해야하는 경우 **'무조건 물어보기'** 설정을 체크하면 됩니다.
Carousel은 추가적으로 선택지를 카드형태로 받을 수 있는 노드로 아래 그림처럼 "좋아하는 음식을 선택하시요" 라는 질문으로 짜장면과 짬뽕 카드를 제시할 수 있습니다.

{% include image.html file="chatflow/Chatflow_carousel_card.png"  caption="메시지 카드 설정" %}

### Carousel 버튼 제약사항

**카드**는 **최대 10개**까지 추가가 가능하며 각 **카드 당 버튼**은 **최대 5개**까지 추가할 수 있습니다. 카드 당 버튼 추가시 선택할 수 있는 옵션은 다음과 같습니다.

### 퀵리플라이 설정

카드 형태 메세지와 함께 보낼 Quick Reply 버튼은 리스트를 설정할 수 있습니다. 퀵리플라이 버튼은 입력창 상단에 위치하는 버튼 형태로 선택지와 대화 흐름 호출 두가지 옵션을 선택할 수 있습니다.

{% include image.html file="chatflow/Chatflow_carousel_card02.png" caption="Quick Reply List 설정" %}

{% include image.html file="chatflow/Chatflow_carousel_card03.png" caption="Quick Reply 사용 결과" %}

**Quick Reply 버튼**은 **최대 20개**까지 설정 가능하나 실 사용 개수는 각 메신저에서 지원하는 개수에 따라 달라집니다.
- Facebook : 최대 11개
- 네이버톡톡 : 최대 10개

{% include warning.html content="해당 기능은 ***Facebook***과 ***네이버 톡톡***에서만 제공됩니다. 현재 danbee.Ai 내의 시뮬레이션, 테스트 패널, 기타 다른 메신저에서는 확인이 불가합니다." %}

## 시간 설정

챗봇이 메시지를 대답하는 시간은 1초가 기본값으로 설정되어 있습니다. 챗봇이 바로 대답하기를 원하지 않을 경우, 얼마만큼 지연시킬것인지
시간을 밀리초(millisecond, ms) 단위로 설정할 수도 있습니다. (1초는 1000ms입니다.)

{% include image.html file="chatflow/chatflow_timedelay.png"  caption="메시지 시간 설정" %}

<!-- 
### 샘플 시나리오 (좋아하는 음식은?)

Carousel 노드에서는 Listen 노드에 선언된 단어항목(parameter)들에 한해 값을 카드 형태로 물어보기 위한 설정을 할 수 있습니다.
해당 시나리오는 'question1' 변수값에 좋아하는 음식을 선택 받고 선택 받은 값을 Speak 노드 메시지에 표시합니다.

{% include image.html file="chatflow/Chatflow_carousel_sampleCanvas.png"  caption="좋아하는 음식은 시나리오" %}

#### [캐로셀 테스트] Listen 노드 설정

Listen 노드에 좋아하는 음식을 선택받기 위해 'question1' 변수를 선언한다. 

{% include image.html file="chatflow/Chatflow_carousel_sampleListen.png"  caption="Listen 노드 설정" %}

#### [짜장면, 짬뽕 카드 제시] Carousel 노드 설정

'좋아하는 음식은?' 질문 메시지를 입록하고 'question1' 변수에 선택 카드 정보 값을 받겠다고 설정합니다. 
그리고 좋아하는 '짜장면', '짬뽕' 카드를 아래와 같이 설정합니다. 

{% include image.html file="chatflow/Chatflow_carousel_card.png"  caption="Carousel 노드 설정" %}

#### [답변 메시지] Speak 노드 설정

Speak 노드에 'question1' 변수 기준으로 값이 '짜장면', '짬뽕' 경우에 따라 다른 메시지를 표시하도록 설정합니다.

{% include image.html file="chatflow/Chatflow_carousel_sampleSpeak.png"  caption="Speak 노드 설정" %}

#### 테스트

'좋아하는 음식은?' 질문에 '짬뽕'을 선택하면 아래와 같이 결과가 나타납니다. 

{% include image.html file="chatflow/Chatflow_carousel_sampleTest.png"  caption="좋아하는 음식은? 테스트 결과" %} -->


{% include bottom.html %}
