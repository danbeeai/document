---
title: Function 노드
tags: [chatflow]
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
    title: 유의어 관리,
    url: synonym.html
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

Script 정보에는 Javascript 함수를 활용하여 변수(Parameter) 정보를 가공할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_function_script.png" max-width="900" caption="Function노드 Script" %}

Listen 노드에 선언된 변수를 가져다 활용할 수 있습니다.
예를 들어 Listen 노드에 'test' 라는 변수가 선언되어 있고 이를 Function 노드에 임의의 값 10을 입력하고 싶다면
우선 Script 영역에 test 변수를 아래와 같이 바인딩 합니다. 

var test;

test 변수가 바인딩 되었다면 Function 노드에서는 test 변수를 활용할 준비가 되었습니다. 
이제 test 변수를 특정 임의의 값 '10'을 넣도록 하겠습니다. 
다음과 같이 입력하게 되면 test 변수에 '10' 값이 저장됩니다. 

test = 10;

{% include image.html file="chatflow/Chatflow_function_script01.png" max-width="900" caption="Function노드 Script" %}


### 샘플 시나리오 (랜덤 분기 테스트)

Function 노드에 Javascript 함수를 활용하여 랜덤으로 Speak 노드를 실행하도록 샘플 시나리오를 설정해 보겠습니다. 
해당 시나리오는 Function 노드에서 0 ~ 2 에 한정한 랜덤 수를 발생하여 randomNum 변수(Parameter)에 값을 저장하게 되고 Split 노드에서 randomNum 값을 기준으로
'램덤1', '램덤2', '랜덤3' Speak 노드를 선택하여 실행하게 됩니다. 

{% include image.html file="chatflow/Chatflow_function_random01.png" max-width="900" caption="랜덤 테스트 시나리오" %}

Listen 노드에서는 램덤 수를 담기 위한 변수 randomNum을 설정합니다. 

{% include image.html file="chatflow/Chatflow_function_random02.png" max-width="900" caption="Listen 노드 설정" %}

Function 노드에서 랜덤 수를 발생하기 위해 Javascript 함수를 아래와 같이 입력합니다. 

{% include image.html file="chatflow/Chatflow_function_random03.png" max-width="900" caption="Function 노드 설정" %}

Split 노드에 조건을 다음과 같이 randomNum 값이 0, 경우에는 '램덤1'을 1일 경우에는 '램덤2', 2일 경우에는 '랜덤3'을 실행하도록 설정합니다.

{% include image.html file="chatflow/Chatflow_function_random04.png" max-width="900" caption="Split 노드 설정" %}

'램덤1', '램덤2','램덤3' Speak 노드는 단순히 기본 메시지를 출력하도록 설정합니다.

{% include image.html file="chatflow/Chatflow_function_random05.png" max-width="900" caption="Speak 노드 설정" %}

랜덤 분기 테스트를 실행해 보면 다음과 같이 같은 질문에 무작위로 다른 메시지를 내뱉게 됩니다. 

{% include image.html file="chatflow/Chatflow_function_sampleTest.png" max-width="900" caption="랜덤 분기 테스트 결과" %}