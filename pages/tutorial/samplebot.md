---
title: 샘플챗봇 만들기
tags: [sample]
keywords: Tutorial
summary: 튜토리얼과 샘플챗봇을 활용하여 누구나 쉽게 챗봇을 만들 수 있습니다.
sidebar: tutorial_sidebar
permalink: samplebot.html
folder: tutorial
next: {
    title: Intent 생성하기,
    url: basic_create_intent.html
}
---

## 샘플챗봇 따라하기

danbee.Ai를 이용하여 처음 챗봇을 만들어보시는 분들을 위해 차근차근 따라하며 챗봇을 만들어보실 수 있도록 튜토리얼을 제공하고 있습니다.

danbee.Ai의 여러 가지 기능들을 익혀볼 수 있는 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[튜토리얼봇](/basic_create_intent.html)</span>과 챗봇을 이용하여 서비스를 만들어보는 예시로 제공되는 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[피자주문봇](/basic_create_intent.html)</span>을 따라서 만들어 보시면 다른 새로운 챗봇을 만드는데 많은 도움이 될 것입니다.

## 샘플챗봇 가져오기
튜토리얼의 이해를 돕고 새로운 챗봇을 만드는데 유용하도록 튜토리얼에서 만든 챗봇을 샘플로 받아서 직접 수정해보실 수 있습니다.

### Bot List에 Sample Chatbot 추가하기
danbee.Ai에 신규 챗봇을 추가할 때 아무 내용이 없는 빈 챗봇을 생성하거나 이미 어느 정도 만들어져있는 샘플챗봇을 추가하는 방법 두 가지가 있습니다.챗봇을 처음 만들어본다면 샘플챗봇을 참고하면서 원하는대로 내용을 조금씩 수정하는 것이 더 쉽게 챗봇을 만드는 방법일 수 있습니다. 앞으로 다양하게 활용하실 수 있도록 계속해서 샘플챗봇을 추가할 예정입니다.

1) 먼저 로그인한 후 Bot List에서 ***"Sample Chatbot 가져오기"*** 버튼을 클릭해 주세요.

{% include image.html file="tutorial/samplebot_empty.png" max-width="900" caption="첫 로그인 화면" %}

2) 원하는 샘플챗봇의 ***"가져오기"*** 버튼을 클릭해주세요.여기서는 ***"튜토리얼봇"***을 가져와 보겠습니다.

{% include image.html file="tutorial/import_samplebot.png" max-width="900" caption="샘플챗봇 가져오기" %}

3) Bot List에 선택한 샘플챗봇이 추가된 것을 확인하실 수 있습니다. 챗봇을 클릭하면 챗봇이름과 설명을 수정하실 수 있습니다.

{% include image.html file="tutorial/samplebot_list.png" max-width="900" caption="챗봇 생성 완료" %}

4) ***의도추론(Intent)***과 ***대화흐름 목록(Chatflow List)*** 메뉴에서 샘플챗봇의 상세 내용을 확인할 수 있습니다.

{% include image.html file="tutorial/samplebot_intent.png" max-width="900" caption="Intent 상세화면" %}
{% include image.html file="tutorial/samplebot_chatflow.png" max-width="900" caption="Chatflow 상세화면" %}

## 샘플챗봇 "튜토리얼봇" 테스트하기
샘플챗봇 "튜토리얼봇"은 ***"피자 주문해줘"***라는 사용자의 입력에 대하여 여러가지 버전으로 대답할 수 있는 예시를 제공하고 있습니다. 따라서 다음에 제공되는 튜토리얼에 따라 대화를 테스트 해보기 위해서는 아래와 같이 Chatflow를 수정해주는 작업이 필요합니다.

### Step1의 예시를 테스트할 때
1) "피자주문하기"이라는 노드를 "Step1"이라고 되어 있는 노드에 선을 연결해주세요.

{% include image.html file="tutorial/basic01_empty_intent.png" max-width="900" caption="이미지 교체필요" %}

2) ***"Chatflow 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

### 다른 Step의 예시를 테스트할 때
1) Step1과 연결된 선을 지우고, 다른 Step의 노드에 선을 연결해주세요.

{% include image.html file="tutorial/basic01_empty_intent.png" max-width="900" caption="이미지 교체필요" %}

2) ***"Chatflow 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

챗봇이 생성되었으면, 이제 기본적인 것부터 차근차근 챗봇을 만들어 보겠습니다.
이해를 돕기 위해 피자가게의 사업자가 피자를 주문 받을 수 있는 챗봇을 만든다고 가정하여 진행하겠습니다.

## 직접 만들어보세요!
튜토리얼를 따라 만들다보면 챗봇을 만드는 것이 어렵지 않습니다. 이해가 되지 않는 부분이 있다면 Document에서 더 자세한 설명을 참고하거나 Q&A로 단비에 문의해주세요.