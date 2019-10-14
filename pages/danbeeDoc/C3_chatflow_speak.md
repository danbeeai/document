---
title: Speak 노드 
tags: [chatflow, basic]
keywords: Basic Conversation
summary: Speak 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_speak.html
folder: danbeeDoc
previous: {
    title: Listen 노드, 
    url: chatflow_listen.html
}
next: {
    title: Slot 노드,
    url: chatflow_slot.html
}
---

## Speak 노드

Speak 노드는 입력되는 메시지 조건을 설정하고 설정된 조건에 일치되는 메시지가 입력되면 답변을 전송하는 노드입니다.
Speak 노드는 메시지, 이미지, 버튼 등의 다양한 기능들의 조합으로 구성이 가능하며,
Speak 노드 내에서 메시지 조건을 설정하여 다양한 답변하는 기능은 복잡한 대화 흐름을 설계하는데 있어 보다 더 나은 간결함을 제공합니다.

그리고 Speak 노드에서 사용자의 의도 질문에 한가지로만 답하는 식상한 챗봇이 아닌 같은 대답을 다양한 표현으로 친근감을 제공하기 위한 랜덤 메시지 기능을 제공 합니다. 
챗봇이 연달아 메시지 답변을 하고자 할 경우에는 Speak 노드를 연이어 배치하면 됩니다. 


Speak 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](chatflow_speak.html#기본정보)
- [메시지 설정](chatflow_speak.html#메시지 설정)

{% include image.html file="chatflow/Chatflow_speak_canvas.png"  caption="Speak 노드" %}

### 기본정보

Speak 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_speak_basic.png"  caption="Speak노드 기본정보" %}


### 메시지 설정

Speak 노드는 챗봇이 대답할 메시지를 입력하는 노드입니다. 
Speak 노드는 초기 '기본 메시지'로 설정이 되어 있고 사용자 선택에 따라 조건식을 활용하여 메시지를 다르게 표현할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_speak_basicMessage.png"  caption="메시지 기본 설정" %}

조건식을 활용하여 메시지를 표현하고 싶을 경우에는 아래와 같이 조건식을 설정할 수 있습니다. 
조건식에 활용할 수 있는 것은 Listen 노드에서 선언하였던 변수를 활용하거나 이전에 사용자가 질문한 문장을 활용할 수도 있습니다. 
조건식 선택박스에 변수들이 Parameter에 나열이 되게 되며, '받은 메시지'는 사용자가 질문한 문장을 의미하는데 이 변수는 시스템적으로 '@message' 변수명으로 표시됩니다.
조건식은 [+] 버튼을 선택하여 다중 입력이 가능하며, 이 때 조건식을은 and 조건으로 연산처리하게 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_message.png"  caption="메시지 조건 설정" %}


{% include warning.html content="입력된 값이 모든 조건에 부합하지 않을 경우는 답변을 하지 않고 오류가 발생하니, 조건을 꼼꼼히 체크하시기 바랍니다." %}

### 이미지 설정

답변과 함께 내보낼 이미지를 설정할 수 있습니다. 이미지를 불러올 수 있는 인터넷상의 URL을 활용하여 이미지를 올릴 수 있습니다.
가급적 확장자(jpg, png, gif)가 있는 URL을 적용해야 정상적으로 출력됩니다.

{% include tip.html content="[imgur.com](https://imgur.com/){:target='_blank'}나 [giphy.com](https://giphy.com/){:target='_blank'}과 같은 간단 이미지 공유사이트를 활용하면 편리합니다. " %}

### 버튼(선택지) 설정
Speak 노드는 답변 메시지와 함께 사용자에게 다음 버튼을 제공함으로써 사용자 편의성을 제공할 수 있습니다.
버튼은 일부 '단비' 엔진에서 처리하는 버튼과 채널(Web, 스마트폰, IoT디바이스)에서 옵션정보를 활용하여 처리해야하는 항목들로 구성되어 있고
그 항목들은 다음과 같습니다. 


| 버튼 | 설명 | 
|--------|-------|
| 선택지 | 버튼 형태 선택지를 제공합니다. |
| Web Link | 팝업으로 호출할 Link 정보를 제공합니다. |
| 내부 App실행 | 스마트폰에서 내부 App을 실행합니다.  |
| 외부 App실행 | 스마트폰에서 외부 App을 실행합니다.  |
| 전화걸기 | 스마트폰에서 전화걸기로 연결합니다. |
| [Chatflow호출](chatflow_speak.html#chatflow-호출-파라미터-연결) | 다른 Chatflow를 호출합니다. 이때 현재 Chatflow의 파라미터를 넘겨줄 수 있습니다. |
| Quick Reply | 입력창 상단에 버튼 형태의 선택지를 제공합니다. |
{: .table .table-striped}

{% include note.html content="Quick Reply 타입은 facebook, 네이버톡톡에서 해당 형태로 이용 가능하며 제공되지 않는 채널에서는 선택지와 동일하게 표시됩니다." %}

{% include image.html file="chatflow/Chatflow_speak_option.png"  caption="Speak 선택지 설정" %}



### 파라미터 활용

Speak 노드에서는 단순히 입력된 메시지만 출력할 뿐만 아니라, 사용자로부터 입력받은 파라미터 정보들을 활용하여 메시지를 표시할 수 있습니다. 

Speak 노드에서 #{파라미터명} 형태로 표시하면 채널에는 '파라미터명'에 가지고 있는 값이 치환되어 표시됩니다. 

{% include image.html file="chatflow/Chatflow_speak_parameter.png"  caption="파라미터 활용 사례" %}

#### 시스템 파라미터

대화 흐름을 설계하다 보면 챗봇명을 표시해야할 경우도 있고, 사용자가 한 말에 대한 패턴 및 채널별로 달리 처리해 주어야 하는 경우도 있을 것입니다. 
Danbee.Ai에서는 그러한 처리를 위해 몇가지 시스템 변수를 아래와 같이 제공합니다. ( 예 : #{@message} )

| 시스템 파라미터 | 표기 | 설명 | 
|--------|-------|-------|
| 사용자 식별정보 | @userId | 사용자ID가 표시됩니다. (ex: email ) |
| 챗봇명 | @chatbotName | 챗봇 생성시 명명했던 이름이 표시됩니다.  |
| 채널아이디 | @channelId | 접속한 채널 아이디가 표시됩니다. <br/>(ex : 5-facebook / 3-kakaotalk / 2-line / 7-navertalk / 6-telegram / 4-slack)  |
| 받은 메시지 | @message | 사용자로부터 받은 질문 메시지 입니다. |
| 현재년도 | @currentDateYYYY | 현재년도 정보입니다. (예:2019) |
| 현재월 | @currentDateMM | 현재월 정보입니다. (예:12) |
| 현재일 | @currentDateDD | 현재일 정보입니다. (예:31) |
| 현재년월 | @currentDateYYYYMM | 현재년월 정보입니다. (예:201912) |
| 현재년월일 | @currentDateYYYYMMDD | 현재년월일 정보입니다. (예:20191231) |
| 현재시간 | @currentTimeHH | 현재시간 정보입니다. (예:23) |
| 현재분 | @currentTimeMI | 현재분 정보입니다. (예:59) |
| 현재초 | @currentTimeSS | 현재초 정보입니다. (예:59) |
| 현재요일 | @currentDateWeek | 현재요일 정보입니다. (예: 1:일, 2:월, 3:화, 4:수, 5:목, 6:금, 7:토) |
{: .table .table-striped}

#### 일반 파라미터

등록된 파라미터들의 값은 메시지나 조건절 경우에 따라 활용하실 수 있습니다. 

직접 #{파라미터명} 식으로 입력할 수도 있겠지만, 편의성 차원에서 아래와 같이 파라미터를 추가하실 수 있습니다.

팝업에서 파라미터 선택시 해당 파라미터는 #{파라미터명} 식으로 메시지에 추가됩니다.

{% include image.html file="chatflow/Chatflow_parameter_add.png"  caption="일반 변수 추가" %}


#### Chatflow 호출 파라미터 연결

Chatflow 호출 버튼을 눌렀을때 각 Chatflow에서 사용되는 파라미터들끼리 연결이 가능합니다. 버튼형 <span class="link">[Jump 노드](chatflow_jump.html)</span> 기능으로 볼 수 있습니다.<br/>
예를 들어 날씨를 물은 뒤 사용자가 버튼을 클릭하면 날씨에 따라 음식을 추천한다고 가정해보겠습니다.

{% include image.html file="chatflow/Chatflow_callflow_param_01.png"  caption="Chatflow 호출 파라미터 연결" %}

위와 같이 Speak 메세지를 설정하고 Chatflow 호출 버튼을 추가합니다. 호출할 Chatflow를 선택하면 [Parameter 연결] 버튼이 활성화 됩니다.

{% include image.html file="chatflow/Chatflow_callflow_param_02.png"  caption="Chatflow 호출 파라미터 연결 팝업" %}

Parameter 연결 버튼을 클릭하면 호출할 Chatflow와 현재 Chatflow의 파라미터 값을 연결할 수 있는 창이 뜹니다. 예시와 같이 *'tempo'*라는 파라미터를 연결하고 테스트패널에서 테스트 해보면 다음과 같은 결과를 확인할 수 있습니다.

{% include image.html file="chatflow/Chatflow_callflow_param_03.png"  caption="Chatflow 호출 파라미터 연결 테스트" %}

<span class="link">[디버그 모드](demo_n_test_panel.html#디버그-모드)</span>에서 기존 날씨 Chatflow에서 세팅되었던 tempo의 '폭우'라는 값이 야식 Chatflow의 파라미터로 넘어갔음을 확인할 수 있습니다.

### 샘플 시나리오 (랜덤 메시지)

사람과의 대화정에서 하나의 의도에 여러가지 유사한 메시지를 무작위로 답변할 수도 있을 것입니다. 
한가지 대답만으로 무미건조하게 느끼게 되고 
이런 경우 Speak 노드의 Random 설정을 체크하여 해당 기능을 구현할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_speak_randomCanvas.png"  caption="랜덤 메시지 시나리오" %}



Speak 노드의 메시지 설정에 Random 설정을 체크하면 메시지 입력창을 여러 개 추가할 수 있게 됩니다. 
유사한 답변을 등록하면 등록된 갯수 내에서 메시지를 무작위로 답변하게 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_random.png"  caption="기본 메시지 랜덤 설정" %}

### 샘플 시나리오 (변수값 표시)

Speak 노드에서는 Listen 노드에 선언된 단어항목(parameter)들의 값을 메시지에 표시할 수 있습니다. 
해당 시나리오는 'name' 변수값에 이름을 입력 받고 입력 받은 값을 메시지에 표시합니다.

{% include image.html file="chatflow/Chatflow_speak_paramCanvas.png"  caption="변수값 표시 시나리오" %}

#### [의도파악] Listen 노드 설정

Listen 노드에 'name' 변수를 다음과 같이 선언합니다.

{% include image.html file="chatflow/Chatflow_speak_paramListen.png"  caption="Listen 노드 설정" %}

#### [변수값 물어보기] Slot 노드 설정

Slot 노드에서는 'name' 값을 입력 받기 위해 다음과 변수를 지정하고 질문 메시지를 등록합니다. 

{% include image.html file="chatflow/Chatflow_speak_paramSlot.png"  caption="Slot 노드 설정" %}

#### [변수값 표시] Speak 노드 설정

Speak 노드에서는 답변 메시지를 입력할때 변수 값을 표시하고 싶은 경우 #{변수명} 과 같이 표시하면 됩니다. 
해당 시나리오 실행시에는 #{변수명} 은 변수값으로 치환되어 보여지게 됩니다.

{% include image.html file="chatflow/Chatflow_speak_paramSpeak.png"  caption="Speak 노드 설정" %}

#### 테스트

'변수값 표시' 시나리오를 테스트해 보면 Speak 노드에 입력된 메시시 중에 변수처리 된 부분은 #{name} 은 입력 받은 값이 치환되어 다음과 같은 결과가 나오게 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_paramTest.png"  caption="변수값 표시 테스트 결과" %}
