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

{% include callout.html content="화면 위치 : 챗봇 > 챗봇 제작 > 대화흐름" type="default" %}

Speak 노드는 입력되는 메시지 조건을 설정하고 설정된 조건에 일치되는 메시지가 입력되면 답변을 전송하는 노드입니다.
Speak 노드는 메시지, 이미지, 버튼 등의 다양한 기능들의 조합으로 구성이 가능하며,
Speak 노드 내에서 메시지 조건을 설정하여 다양한 답변하는 기능은 복잡한 대화 흐름을 설계하는데 있어 보다 더 나은 간결함을 제공합니다.

그리고 Speak 노드에서 사용자의 의도 질문에 한가지로만 답하는 식상한 챗봇이 아닌 같은 대답을 다양한 표현으로 친근감을 제공하기 위한 랜덤 메시지 기능을 제공 합니다. 
챗봇이 연달아 메시지 답변을 하고자 할 경우에는 Speak 노드를 연이어 배치하면 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_canvas.png"  caption="Speak 노드" %}

## 메시지 설정

Speak 노드는 챗봇이 대답할 메시지를 입력하는 노드입니다. 
Speak 노드는 초기 '기본 메시지'로 설정이 되어 있고 사용자 선택에 따라 조건식을 추가하여 상황에 따라 메시지를 다르게 표현할 수 있습니다. 


### 랜덤 메시지
사람과의 대화정에서 하나의 의도에 여러가지 유사한 메시지를 무작위로 답변할 수도 있을 것입니다. 
한가지 대답만으로 무미건조하게 느끼게 되고 
이런 경우 Speak 노드의 Random 설정을 체크하여 해당 기능을 구현할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_speak_randomCanvas.png"  caption="랜덤 메시지 시나리오" %}

>Speak 노드의 메시지 설정에 Random 설정을 체크하면 메시지 입력창을 여러 개 추가할 수 있게 됩니다. 
유사한 답변을 등록하면 등록된 갯수 내에서 메시지를 무작위로 답변하게 됩니다. 

>{% include image.html file="chatflow/Chatflow_speak_random.png"  caption="기본 메시지 랜덤 설정" %}

### 조건별 메세지 작성
조건식에 따라 메세지를 표현하고 싶은 경우에는 하단의 **+ 조건별 메세지 추가** 버튼을 눌러 조건별 메세지를 설정할 수 있습니다. 조건식에는 사용자의 답변, 챗봇명, 현재 시간, 파라미터등 여러가지 값을 기준으로 조건을 설정 할 수 있습니다. 조건식은 **조건 추가**버튼을 통해 하나의 메세지에 여러 조건을 한번에 설정할 수 있습니다.

{% include image.html file="chatflow/Chatflow_speak_message.png"  caption="메시지 조건 설정" %}

{% include warning.html content="입력된 값이 모든 조건에 부합하지 않을 경우는 답변을 하지 않고 오류가 발생하니, 조건을 꼼꼼히 체크하시기 바랍니다." %}


<!-- 
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

{% include image.html file="chatflow/Chatflow_speak_paramTest.png"  caption="변수값 표시 테스트 결과" %} -->


{% include bottom.html %}
