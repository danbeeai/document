---
title: Parameter 노드 
tags: [chatflow, advanced]
keywords: Basic Conversation
summary: Parameter 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_parameter.html
folder: danbeeDoc
previous: {
    title: Carousel 노드,
    url: chatflow_carousel.html
}
next: {
    title: 버튼식 흐름,
    url: chatflow_tree.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 주요 대화 > 대화흐름" type="default" %}

## 개요

챗봇의 대화 흐름 진행 과정에서 여러 파라미터들이 사용되는데, 경우에 따라서는 파라미터 문자열을 가공한다던가 숫자 계산이 필요한 경우가 있습니다. 
Parameter 노드에서는 이러한 파라미터 데이터를 가공처리 할 수 있는 기능을 제공합니다. 

{% include image.html file="chatflow/Chatflow_parameter_canvas.png"  caption="Parameter 노드" %}

## 사용법

정보를 가공하고자 하는 파라미터를 선택하여 특정 값을 입력하거나 특정 연산을 통해 가공한 정보를 셋팅할 수 있습니다.

먼저 대화흐름에서 선언한 파라미터를 하나 선택합니다.
그리고 나서 숫자 또는 문자 중 원하는 값 유형을 선택합니다.
원하는 값을 입력하여 선택된 파라미터에 값을 셋팅합니다. ( 빈값도 셋팅 가능 )  

### 예시1
예를 들어 'test' 라는 파라미터에 임의의 값임 10을 숫자 유형으로 셋팅하려고 한다면 
해당 파라미터에는 10이라는 값이 셋팅됩니다.

{% include image.html file="chatflow/chatflow_parameter_example.png"  caption="Parameter 노드 예제1" %}

### 예시2
이제 'test' 라는 파라미터에 임의의 값임 10을 숫자 유형으로 셋팅하고 값을 5를 더하여 셋팅도 할 수 있습니다.
해당 파라미터에는 15라는 값이 셋팅됩니다.

{% include image.html file="chatflow/chatflow_parameter_example2.png"  caption="Parameter 노드 예제2" %}

### 예시3
값을 셋팅한 후 해당 값에 추가 연산도 가능합니다.
위의 예제대로 'test' 라는 파라미터에 임의의 값임 10을 숫자 유형으로 셋팅한 후, 해당 값에 5를 더할 수 있습니다.
해당 파라미터에는 15라는 값이 셋팅됩니다.

{% include image.html file="chatflow/chatflow_parameter_example3.png"  caption="Parameter 노드 예제3" %}

### 예시4
문자열 값도 숫자와 동일하게 설정되지만 연산은 더하기만 가능하면 문자열을 합치게 됩니다.
위에 예제대로 문자열로 처리한다면 105 라는 값이 셋팅됩니다.

{% include image.html file="chatflow/chatflow_parameter_example4.png"  caption="Parameter 노드 예제4" %}



{% include bottom.html %}
