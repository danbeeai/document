---
title:  "웰컴 메시지 만들기"
published: true
permalink: tutorial_welcome_message.html
summary: "Welcome Message는 챗봇이 사용자에게 첫 인사를 하는 것으로 텍스트 입력 방식과 chatflow 호출 방식 두 가지로 구현할 수 있습니다."
tags: [welcome message, 첫인사]
---

## 기본 웰컴 메시지 만들기

 {% include callout.html content="위치 : [고급설정(Advanced)] - [성격(Personality)] - [기본 답변(General)] - [Welcome Message]" type="default" %}
해당 메시지에서 챗봇의 첫 인사를 **텍스트**로 입력하면 챗봇 창에 그대로 노출 됩니다.<br/>

설정방법은 아래와 같습니다.<br/>
 1. DEFAULT 옵션 선택
 2. 웰컴 메시지 입력

 {% include image.html file="welcome_message_text.PNG" alt="welcome_message_text" caption="welcome_message_text" %}

설정된 웰컴 메시지는 아래와 같이 보여집니다.<br/>

 {% include image.html file="welcome_message_text_channel.PNG" alt="welcome_message_text" caption="welcome_message_text" %}


## 웰컴 메시지에서 버튼 사용하기

 {% include callout.html content="위치 : [고급설정(Advanced)] - [성격(Personality)] - [기본 답변(General)] - [Welcome Message]" type="default" %}
웰컴 메시지에 버튼을 사용하기 위해서는 웰컴 메시지를 **대화흐름**으로 작성해야 합니다.<br/>

설정방법은 아래와 같습니다.<br/>
 1. CHATFLOW 옵션 선택
 2. 웰컴 메시지에 해당하는 대화 흐름 선택

 {% include image.html file="welcome_message_chatflow.PNG" alt="welcome_message_chatflow" caption="welcome_message_chatflow" %}

설정된 웰컴 메시지는 아래와 같이 보여집니다.<br/>

 {% include image.html file="welcome_message_chatflow_channel.PNG" alt="welcome_message_chatflow_channel" caption="welcome_message_chatflow_channel" %}
 
{% include links.html %}
