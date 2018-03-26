---
title: Speak 노드
tags: [chatflow]
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
- [기본정보](Chatflow_speak.html#기본정보)
- [메시지 설정](Chatflow_speak.html#메시지 설정)

{% include image.html file="chatflow/Chatflow_speak_canvas.png" max-width="900" caption="Speak 노드" %}

### 기본정보

Speak 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_speak_basic.png" max-width="900" caption="Speak노드 기본정보" %}


### 메시지 설정

Speak 노드는 챗봇이 대답할 메시지를 입력하는 노드입니다. 
Speak 노드는 초기 '기본 메시지'로 설정이 되어 있고 사용자 선택에 따라 조건식을 활용하여 메시지를 다르게 표현할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_speak_basicMessage.png" max-width="900" caption="메시지 기본 설정" %}

조건식을 활용하여 메시지를 표현하고 싶을 경우에는 아래와 같이 조건식을 설정할 수 있습니다. 
조건식에 활용할 수 있는 것은 Listen 노드에서 선언하였던 변수를 활용하거나 이전에 사용자가 질문한 문장을 활용할 수도 있습니다. 
조건식 선택박스에 변수들이 Parameter에 나열이 되게 되며, '받은 메시지'는 사용자가 질문한 문장을 의미하는데 이 변수는 시스템적으로 '@message' 변수명으로 표시됩니다.
조건식은 [+] 버튼을 선택하여 다중 입력이 가능하며, 이 때 조건식을은 and 조건으로 연산처리하게 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_message.png" max-width="900" caption="메시지 조건 설정" %}


{% include warning.html content="입력된 값이 모든 조건에 부합하지 않을 경우는 답변을 하지 않고 오류가 발생하니, 조건을 꼼꼼히 체크하시기 바랍니다." %}


Speak 노드는 답변 메시지와 함께 사용자에게 다음 선택지 옵션을 제공함으로써 사용자 편의성을 제공할 수 있습니다.
선택지 옵션은 일부 '단비' 엔진에서 처리하는 선택지 옵션과 채널(Web, 스마트폰, IoT디바이스)에서 옵션정보를 활용하여 처리해야하는 항목들로 구성되어 있고
그 항목들은 다음과 같습니다. 


| 선택지 옵션 | 설명 | 
|--------|-------|
| 선택지(버튼) | 버튼 형태 선택지를 제공합니다. |
| Web Link | 팝업으로 호출할 Link 정보를 제공합니다. |
| 내부 App실행 | 스마트폰에서 내부 App을 실행합니다.  |
| 외부 App실행 | 스마트폰에서 외부 App을 실행합니다.  |
| 전화걸기 | 스마트폰에서 전화걸기로 연결합니다. |
| Chatflow호출 | 다른 Chatflow를 호출합니다. |
| Quick Reply | 입력창 상단에 버튼 형태의 선택지를 제공합니다. |

{% include note.html content="Quick Reply 타입은 facebook, 네이버톡톡에서 해당 형태로 이용 가능하며 제공되지 않는 채널에서는 선택지와 동일하게 표시됩니다." %}

{% include image.html file="chatflow/Chatflow_speak_option.png" max-width="900" caption="Speak 선택지 설정" %}


### 파라미터 활용

Speak 노드에서는 단순히 입력된 메시지만 출력할 뿐만 아니라, 사용자로부터 입력받은 파라미터 정보들을 활용하여 메시지를 표시할 수 있습니다. 

Speak 노드에서 #{변수명} 형태로 표시하면 채널에는 '변수명'에 가지고 있는 값이 치환되어 표시됩니다. 

{% include image.html file="chatflow/Chatflow_speak_parameter.png" max-width="900" caption="메시지 조건 설정" %}



### 샘플 시나리오 (랜덤 메시지)

사람과의 대화정에서 하나의 의도에 여러가지 유사한 메시지를 무작위로 답변할 수도 있을 것입니다. 
한가지 대답만으로 무미건조하게 느끼게 되고 
이런 경우 Speak 노드의 Random 설정을 체크하여 해당 기능을 구현할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_speak_randomCanvas.png" max-width="900" caption="랜덤 메시지 시나리오" %}

Speak 노드의 메시지 설정에 Random 설정을 체크하면 메시지 입력창을 여러 개 추가할 수 있게 됩니다. 
유사한 답변을 등록하면 등록된 갯수 내에서 메시지를 무작위로 답변하게 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_random.png" max-width="900" caption="기본 메시지 랜덤 설정" %}

### 샘플 시나리오 (변수값 표시)

Speak 노드에서는 Listen 노드에 선언된 단어항목(parameter)들의 값을 메시지에 표시할 수 있습니다. 
해당 시나리오는 'name' 변수값에 이름을 입력 받고 입력 받은 값을 메시지에 표시합니다.

{% include image.html file="chatflow/Chatflow_speak_paramCanvas.png" max-width="900" caption="변수값 표시 시나리오" %}

Listen 노드에 'name' 변수를 다음과 같이 선언합니다.

{% include image.html file="chatflow/Chatflow_speak_paramListen.png" max-width="900" caption="Listen 노드 설정" %}

Slot 노드에서는 'name' 값을 입력 받기 위해 다음과 변수를 지정하고 질문 메시지를 등록합니다. 

{% include image.html file="chatflow/Chatflow_speak_paramSlot.png" max-width="900" caption="Slot 노드 설정" %}

Speak 노드에서는 답변 메시지를 입력할때 변수 값을 표시하고 싶은 경우 #{변수명} 과 같이 표시하면 됩니다. 
해당 시나리오 실행시에는 #{변수명} 은 변수값으로 치환되어 보여지게 됩니다.

{% include image.html file="chatflow/Chatflow_speak_paramSpeak.png" max-width="900" caption="Speak 노드 설정" %}

'변수값 표시' 시나리오를 테스트해 보면 Speak 노드에 입력된 메시시 중에 변수처리 된 부분은 #{name} 은 입력 받은 값이 치환되어 다음과 같은 결과가 나오게 됩니다. 

{% include image.html file="chatflow/Chatflow_speak_paramTest.png" max-width="900" caption="변수값 표시 테스트 결과" %}