---
title: 챗봇 성격 설정
tags: [personality]
keywords: Basic Conversation
summary: 챗봇의 답변을 여러 상황에 맞춰 다르게 말할 수 있도록 설정할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: personality_settings.html
folder: danbeeDoc
previous: {
    title: Function 노드,
    url: chatflow_function.html
}
next: {
    title: 유의어 관리,
    url: synonym.html
}
---

## 챗봇 성격 설정(Personality)
 {% include callout.html content="화면 위치 : [고급설정(Advanced)] > [성격(Personality)]" type="default" %}
**성격(이하 Personality)**란, 다음과 같은 상황에서 답변 내용을 설정할 수 있습니다. <br/>

- [Welcome](personality_settings.html#Welcome)
- [Reconfirm](personality_settings.html#Reconfirm)
- [Default Fallback](personality_settings.html#Default-Fallback)
- [Multi Intent](personality_settings.html#Multi-Intent)
- [Error](personality_settings.html#Error)

### Welcome
#### Default
**Welcome**은 사용자가 처음 챗봇을 만났을 때 챗봇이 사용자를 반기며 하는 말입니다.
{% include image.html file="personality/personality_welcome_01.PNG" max-width="900" caption="Default Welcome Message" %}

#### Chatflow
Chatflow를 해당 상황에서 단순한 메세지 대신 특정 챗플로우의 Listen 노드로 연결하여 다양한 인사말을 할 수 있습니다.
{% include image.html file="personality/personality_welcome_03.PNG" max-width="900" caption="Chatflow Welcome Message" %}

Welcome Message를 Chatflow로 설정하여 Welcome Chatflow의 Welcome Listen 노드로 설정하면 
{% include image.html file="personality/personality_welcome_04.PNG" max-width="900" caption="Welcome Chatflow" %}

Speak 노드에 Random으로 메세지 보내기를 체크하면 처음 인사말에 해당 Speak 노드에 설정된 인사말이 랜덤으로 나가게 됩니다.
{% include image.html file="personality/personality_welcome_05.PNG" max-width="900" caption="Speak Node" %}

### Reconfirm
**Reconfirm**은 사용자의 말과 Intent 매칭률이 NLU 답변설정 Reconfirm Percent 범위 안에 있을 때, 한번 더 어떤 의도로 말을 했는지 물어볼 때 하는 말입니다.
{% include image.html file="personality/personality_reconfirm_01.PNG" max-width="900" caption="Recofirm Percent" %}

예를 들어 다음과 같이 예문을 등록하고 '방가방가'라고 했을 경우 환영인사 Intent 매칭률은 39% 정도이며 Recofirm Percent 범위 안에 들기 때문에 다음과 같이 다시 물어보게 됩니다.
{% include image.html file="personality/personality_reconfirm_02.PNG" max-width="900" caption="Reconfirm이 호출될 경우" %}

### Default Fallback
#### Default
**Default Fallback**은 사용자가 한 말의 Intent를 파악하지 못했을 때 챗봇이 하는 말로 설정한 NLU 답변설정 Minimum Percent 보다 Intent 매칭률이 작을 때 Default Fallback 메세지가 사용자에게 나가게 됩니다. 
{% include image.html file="personality/personality_default_01.PNG" max-width="900" caption="Deafult Fallback Percent" %}

#### Chatflow
Welcome과 마찬가지로 해당 상황에서 단순한 Default Fallback 메세지 대신 특정 챗플로우의 Listen 노드로 연결하여 다양하게 메세지를 보낼 수 있습니다.
{% include image.html file="personality/personality_default_02.PNG" max-width="900" caption="Deafult Fallback Chatflow" %}

### Multi Intent
**Multi Intent**는 사용자가 한 말에 매칭되는 Intent가 2개 이상이고 해당 Intent들의 매칭률이 모두 동일할 때 해당 메세지와 함께 매칭된 Intent들을 모두 보여줍니다.
{% include image.html file="personality/personality_multi_01.PNG" max-width="900" caption="Multi Intent Message" %}

### Error
#### Default
**Error**는 사용자가 챗봇과 대화 중 챗봇 서버에서 예상치 못한 에러가 발생했을 때 사용자에게 하는 말입니다.
{% include image.html file="personality/personality_error_01.PNG" max-width="900" caption="Error Message" %}

#### Chatflow
Welcome과 마찬가지로 해당 상황에서 단순한 Error 메세지 대신 특정 챗플로우의 Listen 노드로 연결하여 다양하게 메세지를 보낼 수 있습니다.
{% include image.html file="personality/personality_error_02.PNG" max-width="900" caption="Error Chatflow" %}