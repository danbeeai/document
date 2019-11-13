---
title: Function 노드 
tags: [chatflow, advanced]
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
    title: Jump 노드,
    url: chatflow_jump.html
}
---

챗봇의 대화 흐름 진행 과정에서 여러 파라미터들이 사용되는데, 경우에 따라서는 파라미터 문자열을 가공한다던가 날짜, 숫자 계산이 필요한 경우가 있습니다. 
Function 노드에서는 자바스크립트 문법을 사용하여 이러한 파라미터 데이터를 가공처리 할 수 있는 기능을 제공합니다. 


Function 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](chatflow_function.html#기본정보)
- [Script 연결](chatflow_function.html#Script 연결)

{% include image.html file="chatflow/Chatflow_function_canvas.png"  caption="Function 노드" %}

### Script 정보

Script 정보에는 Javascript 함수를 활용하여 변수(파라미터) 정보를 가공할 수 있습니다. 

선언된 파라미터를 가져다 활용할 수 있습니다.
예를 들어 'test' 라는 파라미터가 선언되어 있고 이를 Function 노드에 임의의 값 10을 입력하고 싶다면
우선 Script 영역에 test 변수를 아래와 같이 바인딩 합니다. 

var test;

test 변수가 바인딩 되었다면 Function 노드에서는 test 변수를 활용할 준비가 되었습니다. 
이제 test 변수를 특정 임의의 값 '10'을 넣도록 하겠습니다. 
다음과 같이 입력하게 되면 test 변수에 '10' 값이 저장됩니다. 

test = 10;

{% include image.html file="chatflow/Chatflow_function_script01.png"  caption="Function노드 Script" %}

#### 시스템 파라미터

시스템에서 제공하는 파라미터도 사용가능합니다. 해당 파라미터는 스크립트내에서 읽기 전용으로만 사용가능합니다. ( 예 : var danbee_message; )

| 시스템 파라미터 | 표기 | 설명 | 
|--------|-------|-------|
| 사용자 식별정보 | danbee_userId | 사용자ID가 표시됩니다. (ex: email ) |
| 챗봇명 | danbee_chatbotName | 챗봇 생성시 명명했던 이름이 표시됩니다.  |
| 채널아이디 | danbee_channelId | 접속한 채널 아이디가 표시됩니다. <br/>(ex : 5-facebook / 3-kakaotalk / 2-line / 7-navertalk / 6-telegram / 4-slack)  |
| 받은 메시지 | danbee_message | 사용자로부터 받은 질문 메시지 입니다. |
| 현재년도 | danbee_currentDateYYYY | 현재년도 정보입니다. (예:2019) |
| 현재월 | danbee_currentDateMM | 현재월 정보입니다. (예:12) |
| 현재일 | danbee_currentDateDD | 현재일 정보입니다. (예:31) |
| 현재년월 | danbee_currentDateYYYYMM | 현재년월 정보입니다. (예:201912) |
| 현재년월일 | danbee_currentDateYYYYMMDD | 현재년월일 정보입니다. (예:20191231) |
| 현재시간 | danbee_currentTimeHH | 현재시간 정보입니다. (예:23) |
| 현재분 | danbee_currentTimeMI | 현재분 정보입니다. (예:59) |
| 현재초 | danbee_currentTimeSS | 현재초 정보입니다. (예:59) |
| 현재요일 | danbee_currentDateWeek | 현재요일 정보입니다. (예: 1:일, 2:월, 3:화, 4:수, 5:목, 6:금, 7:토) |
{: .table .table-striped}
<!-- 
### 샘플 시나리오 (랜덤 분기 테스트)

Function 노드에 Javascript 함수를 활용하여 랜덤으로 Speak 노드를 실행하도록 샘플 시나리오를 설정해 보겠습니다. 
해당 시나리오는 Function 노드에서 0 ~ 2 에 한정한 랜덤 수를 발생하여 randomNum 변수(파라미터)에 값을 저장하게 되고 Split 노드에서 randomNum 값을 기준으로
'램덤1', '램덤2', '랜덤3' Speak 노드를 선택하여 실행하게 됩니다. 

{% include image.html file="chatflow/Chatflow_function_random01.png"  caption="랜덤 테스트 시나리오" %}

#### [랜덤 테스트] Listen 노드 설정

Listen 노드에서는 램덤 수를 담기 위한 변수 randomNum을 설정합니다. 

{% include image.html file="chatflow/Chatflow_function_random02.png"  caption="Listen 노드 설정" %}

#### [랜덤 함수] Function 노드 설정

Function 노드에서 랜덤 수를 발생하기 위해 Javascript 함수를 아래와 같이 입력합니다. 

{% include image.html file="chatflow/Chatflow_function_random03.png"  caption="Function 노드 설정" %}

#### [랜덤 분기] Split 노드 설정

Split 노드에 조건을 다음과 같이 randomNum 값이 0, 경우에는 '램덤1'을 1일 경우에는 '램덤2', 2일 경우에는 '랜덤3'을 실행하도록 설정합니다.

{% include image.html file="chatflow/Chatflow_function_random04.png"  caption="Split 노드 설정" %}

#### [랜덤1, 랜덤2, 랜덤3] Speak 노드 설정

'램덤1', '램덤2','램덤3' Speak 노드는 단순히 기본 메시지를 출력하도록 설정합니다.

{% include image.html file="chatflow/Chatflow_function_random05.png"  caption="[랜덤1] Speak 노드 설정" %}

{% include image.html file="chatflow/Chatflow_function_random06.png"  caption="[랜덤2] Speak 노드 설정" %}

{% include image.html file="chatflow/Chatflow_function_random07.png"  caption="[랜덤3] Speak 노드 설정" %}


#### 테스트

랜덤 분기 테스트를 실행해 보면 다음과 같이 같은 질문에 무작위로 다른 메시지를 내뱉게 됩니다. 

{% include image.html file="chatflow/Chatflow_function_sampleTest.png"  caption="랜덤 분기 테스트 결과" %} -->
