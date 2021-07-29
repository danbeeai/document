---
title: Sleep 노드 
tags: [chatflow, advanced]
keywords: Basic Conversation
summary: Sleep 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_sleep.html
folder: danbeeDoc
previous: {
    title: Parameter 노드,
    url: chatflow_parameter.html
}
next: {
    title: 버튼식 흐름,
    url: chatflow_tree.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 주요 대화 > 대화 흐름" type="default" %}

## 개요

Sleep 노드는 대화흐름 중간에 챗봇이 바로 응답하지않고 일정시간동안 기다렸다가 응답하는 기능을 제공합니다.
{% include image.html file="chatflow/Chatflow_sleep_canvas.png"  caption="Sleep 노드" %}

## 사용법

'Sleep 요청값(ms)' 항목에 챗봇이 기다리기를 원하는 시간을 ms단위로 입력합니다.

- 1초는 1,000ms 입니다.
- 최대 10초(10,000ms)까지 설정할 수 있으며, 초과시 자동 10초로 저장됩니다.
- 외부채널 연결시 각 채널별 제한 응답시간에 따라 대화흐름이 정상적으로 동작하지 않을 수 있습니다.


### 예시1
챗봇이 1초 기다린 후 응답합니다.

{% include image.html file="chatflow/chatflow_sleep_example.png"  caption="Sleep 노드 예제1" %}

### 예시2
챗봇이 3.5초 기다린 후 응답합니다.

{% include image.html file="chatflow/chatflow_sleep_example2.png"  caption="Sleep 노드 예제2" %}

{% include bottom.html %}
