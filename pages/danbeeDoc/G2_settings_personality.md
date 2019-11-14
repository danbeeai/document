---
title: 챗봇 추론 설정
tags: [settings, basic]
keywords: General Conversation
summary: 챗봇의 답변을 여러 상황에 맞춰 다르게 말할 수 있도록 설정할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: settings_personality.html
folder: danbeeDoc
previous: {
    title: 사용자사전 관리,
    url: dictionary.html
}
next: {
    title: NLU 설정,
    url: settings_nlu.html
}
---

{% include callout.html content="화면 위치 : 챗봇 생성/변경 > 챗봇 특수 상황 설정" type="default" %}

챗봇이 예상치 못한 상황을 어떻게 처리할지 자세하게 설정합니다.

- [예외상황 설정](settings_personality.html#정확도별-기본답변-설정)
- [파일전송시 응답 설정](settings_personality.html#예외상황-설정)
- [이전 대화 복귀 설정](settings_personality.html#이전-대화-복귀-설정)


## 예외상황 설정
{% include image.html file="unusual/0_0.PNG" %}
챗봇이 의도를 추론한 결과 단순하게 추론 성공으로 판단할 수 없거나 오류가 출력되었을 경우 설정을 합니다.

### 중의적인 의도 처리
의도를 추론한 결과 2개 이상의 의도가 동시에 추론 성공으로 판단될 경우 어떤 의도가 사용자의 의도인지 되묻습니다.

### 에러 메세지
내부적인 이유로 챗봇이 대화를 진행하는 도중 오류가 발생했을 때 메세지입니다.
>##### 간단한 상황설명
간단한 문장으로 오류가 발생했음을 알립니다.
##### 대화흐름 연결
오류가 발생했을 때 대화흐름을 실행합니다.

## 파일전송시 응답 설정
사용자가 챗봇에 이미지나 파일을 업로드 했을 때, 해당 파일을 어떻게 처리하고 알릴지 설정합니다.

### 업로드시 메세지
{% include image.html file="unusual/1.PNG" %}
>##### 간단 답변
간단한 문장으로 업로드가 이루어졌음을 알립니다.
##### 대화흐름 연결
업로드가 완료되면 대화흐름을 실행하여 업로드를 처리합니다.
##### 파라미터명
사용자가 업로드한 파일이 저장된 파라미터 이름입니다. 대화흐름에서 해당 파라미터를 이용해 업로드 받은 파일을 바로 이용할 수 있습니다.
##### 파라미터 타입
사용자가 업로드한 파일이 저장된 파라미터의 타입입니다.

## 이전 대화 복귀 설정
{% include image.html file="unusual/2.PNG" %}
사용자가 슬롯 노드에 답변할 단계에서 적절한 답변을 하지 않고 다른 말을 했을 때, 챗봇이 어떻게 반응할지 결정합니다. 이전 대화 복귀 설정을 켜면 사용자가 중간에 입력한 다른 의도를 처리한 뒤 답변하지 않은 슬롯 노드로 돌아갈지 물어봅니다. 이전 대화 복귀 설정을 사용하지 않으면 다른 의도를 실행한 뒤 원래 진행하고 있던 흐름으로 복귀하지 않습니다.

### 복귀 의사 확인
사용자의 복귀의사를 물어볼 메세지를 설정합니다. 메세지와 함께 복귀 의사 긍정/부정 버튼을 함께 설정 할 수 있습니다.
### 복귀 거부시 메세지
사용자가 슬롯노드로 복귀를 거부했을 시 챗봇의 메세지를 설정합니다.
>##### 간단 답변
간단한 문장으로 이전 대화흐름으로 복귀하지 않음을 알립니다.
##### 대화흐름 연결
복귀 거부에 따른 대화흐름을 진행합니다.

<!-- 
## 기본 답변 설정(General)
**기본 답변(이하 General)**이란, 다음과 같은 상황에서 답변 내용을 설정할 수 있습니다. <br/>

- [Welcome Message](settings_personality.html#welcome-message) : Welcome
- [정확도별 기본답변 설정](settings_personality.html#정확도별-기본답변-설정) : Default Fallback, Reconfirm
- [예외상황 설정](settings_personality.html#예외상황-설정) : Multi Intent, Error
- [이전 대화 복귀 설정](settings_personality.html#이전-대화-복귀-설정) : 복귀 확인 메시지, No 답변 메시지


### Welcome Message
Welcome Message는 사용자가 처음 챗봇을 만났을 때 행동할 수 있는 사항에 대하여 설정하는 파트입니다.

#### Welcome
**Welcome**은 사용자가 처음 챗봇을 만났을 때 챗봇이 사용자를 반기며 하는 말입니다. 단순 답변과 대화흐름 활용, 2가지 버전을 선택할 수 있습니다.

 - Default
{% include image.html file="personality/personality_welcome01.png"  caption="Welcome Message - Default" %}

 - Chatflow

해당 상황에서 단순한 메시지 대신 특정 챗플로우의 Listen 노드로 연결하여 다양한 인사말을 할 수 있습니다. 예를 들어 다음과 같이 Welcome Message를 대화흐름으로 설정하여 Welcome 대화흐름을 선택합니다.

{% include image.html file="personality/personality_welcome02.png"  caption="Welcome Message - Chatflow" %}

 Speak 노드에 Random으로 메세지 보내기를 체크하면 처음 인사말에 해당 Speak 노드에 설정된 인사말이 랜덤으로 나가도록 만들 수 있습니다.
{% include image.html file="personality/personality_welcome03.png"  caption="Welcome Message - 대화흐름 랜덤 답변 예시" %}

### 정확도별 기본답변 설정
정확도별 기본답변 설정은 챗봇이 해당 의도를 어느 정도로 정확하게 이해했는가에 따라 다르게 반응하도록 설정할 수 있습니다. 챗봇이 반응하는 구간과 해당 구간의 메시지를 설정할 수 있습니다.

#### Default Fallback
**Default Fallback**은 챗봇이 사용자가 한 말의 Intent를 파악하지 못했을 때 기본적으로 하는 말입니다. 답변이 나가는 최소 확률보다 대화의도 매칭률이 작을 때, 또는 찾은 Intent가 <span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [채널 Fallback 설정](intent.html#채널-fallback-설정)</span>이 되어 있을 때 등 다양한 경우에 Default Fallback 메시지가 나가게 됩니다. Default Fallback의 다양한 케이스는 우측 <span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [테스트 패널의 디버그 모드](demo_n_test_panel.html#디버그-모드)</span>에서 자세하게 확인할 수 있습니다.

{% include image.html file="personality/personality_default01.png"  caption="Deafult Fallback Percent" %}

#### Default Fallback (대화흐름 방식)
Welcome과 마찬가지로 해당 상황에서 단순 답변 대신 특정 챗플로우의 Listen 노드로 연결하여 다양하게 메세지를 보낼 수 있습니다. API를 통해 데이터베이스에 있는 정보를 제공하거나 챗봇이 되물어보고 사용자가 답하는 시나리오를 만들 수 있습니다. 또는 상황에 따라 특정 대화흐름으로 전환(JUMP)할 수도 있습니다. 원래 목적으로 되돌리기 위해서는 대화흐름을 잘 활용하는 것이 중요합니다. 

{% include image.html file="personality/personality_default02.png"  caption="Deafult Fallback - Chatflow" %}

#### Default Fallback (일상대화 연결, 핑퐁)
사용자가 말하는 대화 맥락에 맞게 적절히 대응할 수 있다면, "잘 못알아 들었습니다."와 같은 변명보다 더 똑똑한 상대와 대화한다는 느낌을 주겠죠? 단비AI는 핑퐁의 일상대화에 바로 연결해서 쓸 수 있도록 되어 있습니다. <br> 
<a href="https://builder.pingpong.us" target="_blank">핑퐁(Beta)</a>은 어떠한 질문이나 말에도 센스있게 대답하는 일상대화 인공지능 친구입니다. 무료기간 동안에는 브랜드를 소개하는 문구가 같이 표시됩니다. 
{% include image.html file="personality/personality_default03.png"  caption="Deafult Fallback - 자동답변" %}
{% include note.html content="핑퐁은 베타서비스로 유료고객에 한해 무료로 제공되고 있습니다. 무료고객은 브랜드 메시지가 포함됩니다." %}





#### Reconfirm
**Reconfirm**은 사용자의 말과 대화의도 매칭률이 설정한 Reconfirm Percent 범위 안에 있을 때, 한번 더 어떤 의도로 말을 했는지 물어볼 때 하는 말입니다.
{% include image.html file="personality/personality_reconfirm01.png"  caption="Recofirm Message" %}

예를 들어 '배고파배고파배고파'라고 했을 경우 야식주문 대화의도 매칭률은 25% 입니다. 해당 매칭률은 설정해둔 Recofirm Percent 범위 20~60% 안에 들게 되기 때문에 우측과 같이 다시 물어보게 됩니다.

### 예외상황 설정
예외상황 설정에서는 다양한 예외 상황에 대해 대응하기 위한 답변을 설정할 수 있습니다.

#### Multi Intent
**Multi Intent**는 사용자가 한 말에 매칭되는 Intent가 2개 이상이고 해당 Intent들의 매칭률이 모두 동일할 때 해당 메세지와 함께 매칭된 Intent들을 모두 보여줍니다.
{% include image.html file="personality/personality_multi01.png"  caption="Multi 대화의도 Message" %}

예를 들어 '배고파'라는 말이 야식주문 Intent와 나가서먹자 대화의도에 같은 확률로 매칭될 경우 우측과 같이 Multi 대화의도 Message를 이용하여 되묻게 됩니다.

#### Error
**Error**는 사용자가 챗봇과 대화 중 챗봇 서버에서 예상치 못한 에러가 발생했을 때 사용자에게 하는 말입니다. 해당 메시지가 발송될 경우 danbee.Ai에 문의하시는 것을 권장합니다.

{% include image.html file="personality/personality_error01.png"  caption="Error Message" %}

Welcome과 마찬가지로 해당 상황에서 단순한 Error 메세지 대신 특정 챗플로우의 Listen 노드로 연결하여 다양하게 메시지를 보낼 수 있습니다.

### 이전 대화 복귀 설정
**이전 대화 복귀**란, 사용자가 챗봇의 질문에 대답하지 않고 다른 대화로 넘어갔을 때 이전 대화를 기억해두었다가 다시 이야기를 이어가는 기능입니다. 즉, 이전 대화 복귀는 실질적으로 사용자에게 질문에 대한 답을 받을 수 있는 Slot 노드와 Carousel 노드에 연관된 기능입니다.

{% include note.html content="Carousel 노드의 경우 '선택지값을 파라미터에 저장하기'가 설정된 Carousel 노드만을 의미합니다." %}
{% include image.html file="personality/personality_goback00.png"  caption="이전 대화 복귀가 가능한 Carousel 노드 설정" %}

해당 기능에 대하여 다음과 같은 다양한 설정들이 가능합니다.

{% include image.html file="personality/personality_goback01.png"  caption="이전 대화 복귀 설정" %}

#### 사용 여부
이전 대화 복귀 기능의 사용 여부를 설정할 수 있습니다. 우측 상단 Toggle 버튼을 이용해 간단하게 설정이 가능합니다.

#### 복귀 확인 메시지
이전 대화 복귀 기능 사용 시 챗봇이 되물어보는 말과 버튼명을 설정할 수 있습니다. 첫번째 버튼은 긍정의 의미, 두번째 버튼은 부정의 의미로 이용됩니다. 이때 danbee.Ai에서는 **slotMsg**라는 파라미터를 제공함니다.

 - slotMsg : 이전에 대화가 끊겼던 질문 메시지를 담고 있는 파라미터

이미지와 같이 #{slotMsg}라고 입력하면 이전 메시지를 가져와 되물을 수 있습니다.

{% include warning.html content="**slotMsg**는 오직 **복귀 확인 메시지** 영역에서만 사용할 수 있는 시스템 파라미터입니다. 버튼명, No 답변 메시지 등 다른 영역에서는 제공되지 않습니다." %}

#### No 답변 메시지
사용자가 두번째 버튼을 눌렀을 때 나가는 메시지 입니다. Welcome과 마찬가지로 단순 답변 외에도 Chatflow의 Listen 노드를 연결하여 다양한 답변을 설정할 수 있습니다.

#### 샘플 시나리오
이전 대화 복귀 설정에 대한 이해를 돕기 위한 샘플 시나리오입니다. 이전 대화 복귀 설정을 상단 이미지와 동일하게 하고 이야기를 진행합니다. 예를 들어 어떤 야식을 먹고 싶은지에 대해 이야기 하다가 날씨 이야기로 빠집니다. 만약 이전 대화 복귀가 설정되어 있다면 챗봇은 날씨 이야기가 끝난 뒤 다시 야식에 대해 물어보게 됩니다. 실 대화는 다음과 같이 이루어집니다.

{% include image.html file="personality/personality_goback02.png"  caption="이전 대화 복귀 예시" %}





 -->
