---
title: 챗봇 생성 및 기본정보 변경
tags: [create_chatbot]
keywords: 챗봇 생성, 챗봇 만들기
summary: 대화 주체의 단위인 챗봇을 생성하는 법을 알아보겠습니다.
sidebar: danbee_doc_sidebar
permalink: basic_create_chatbot.html
folder: danbeeDoc
previous: {
    title: 챗봇을 만들기 위해 알아야할 기본, 
    url: index.html
}
next: {
    title: 의도관리,
    url: intent.html
}
---

## 챗봇 생성하기

챗봇은 danbee.Ai에서 대화를 하는 주체의 단위입니다. 챗봇단위로 사용자가 발화하는 내용을 이해하고, 답변하는 것이 달라집니다.
온라인 게임에서 캐릭터 하나 만든다고 생각하고 쉽게 시작할 수 있습니다.

### 챗봇 생성

최초 로그인을 하게 되면, 아래와 같이 챗봇이 하나도 없는 상태입니다.

{% include image.html file="chatbot_create\01_no_chatbot.PNG" max-width="900" caption="챗봇이 없는 상태" %}

1) 안내화면 가운데 또는 좌측 메뉴에 있는 ***"Chatbot 생성"*** 버튼을 클릭하여 아래와 같은 화면을 열어주세요.

{% include image.html file="chatbot_create\02_chatbot_create.PNG" max-width="900" caption="챗봇 생성 화면" %}
2) Chatbot의 이름을 정하고 ***"저장"***버튼을 클릭합니다. 설명은 입력하지 않아도 저장이 가능합니다.

{% include image.html file="chatbot_create\03_chatbot_created.PNG" max-width="900" caption="챗봇이 생성된 모습" %}
3) 챗봇의 프로필이미지가 자동으로 생성되고 챗봇별로 관리되는 데이터가 보입니다.
 - [Intents](intent.html) : 챗봇이 추론할 수 있는 의도(Intent)의 개수
 - [Entities](entity.html): 챗봇이 추출할 수 있는 Entity종류 수
 - [Chatflows](chatflow.html) : 답변 가능하도록 설정된 챗플로우의 개수
 - Bot id : [대화채널 연결](channel_connection_settings.html)시 활용할 수 있는 챗봇별로 부여되는 ID입니다.
 - Token : [대화채널 연결](channel_connection_settings.html)시 활용할 수 있는 챗봇별로 부여되는 Token값입니다. 

Intents, Entities, Chatflows를 클릭하면, 챗봇을 설정할 수 있는 각각의 메뉴로 이동합니다.

챗봇명 우측의 ***"설정"***버튼을 클릭하여 챗봇의 기본정보를 변경하거나 삭제할 수 있습니다.

### 챗봇 기본정보 변경
챗봇명 우측의 ***"설정"***버튼을 클릭하면, 아래와 같은 화면이 나타납니다.
{% include image.html file="chatbot_create\04_chatbot_edit.PNG" max-width="900" caption="챗봇 기본정보 변경 화면" %}
***"사진변경"***버튼을 눌러 프로필사진을 변경하거나 설명을 수정하고 우측 상단의 ***"저장"***버튼을 클릭하면 변경사항이 반영됩니다.


### 챗봇 삭제
챗봇 설정 화면의 하단에 있는 ***"Chatbot 삭제"***기능은 매우 조심해야 하는 기능입니다. 등록되어 있는 모든 학습데이터와 대응되는 답변 시나리오가 삭제됩니다.


### 다음으로 할 일
위에서 나온 챗봇관련 개념에 익숙해지셨다면, 본격적으로 챗봇이 파악할 수 있는 인텐트(의도)를 등록하는 것을 시작할 수 있겠습니다.

<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[의도관리](/intent.html)</span>



