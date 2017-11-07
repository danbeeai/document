---
title: Function 노드
tags: []
keywords: Basic Conversation
summary: Function 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_function.html
folder: danbeeDoc
previous: {
    title: API 노드,
    url: chatflow_api.html
}
next: {
    title: 챗봇 성격 설정,
    url: personality_settings.html
}
---

## Function 노드

챗봇의 대화 흐름 진행 과정에서 여러 파라미터들이 사용되는데, 경우에 따라서는 파라미터 문자열을 가공한다던가 날짜, 숫자 계산이 필요한 경우가 있습니다. 
Function 노드에서는 자바스크립트 문법을 사용하여 이러한 파라미터 데이터를 가공처리 할 수 있는 기능을 제공합니다. 


Function 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_function.html#기본정보)
- [Script 연결](Chatflow_function.html#Script 연결)

{% include image.html file="chatflow/Chatflow_function_cavas.png" max-width="900" caption="Function 노드" %}

### 기본정보

Function 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_function_basic.png" max-width="900" caption="Function노드 기본정보" %}

### Script 정보

{% include image.html file="chatflow/Chatflow_function_script.png" max-width="900" caption="Function노드 Script" %}


### 샘플 시나리오

{% include image.html file="chatflow/Chatflow_function_random01.png" max-width="900" caption="랜덤 테스트 시나리오" %}

{% include image.html file="chatflow/Chatflow_function_random02.png" max-width="900" caption="Listen 노드 설정" %}

{% include image.html file="chatflow/Chatflow_function_random03.png" max-width="900" caption="Function 노드 설정" %}

{% include image.html file="chatflow/Chatflow_function_random04.png" max-width="900" caption="Split 노드 설정" %}

