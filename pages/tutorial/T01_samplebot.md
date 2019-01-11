---
title: 튜토리얼 시작하기 
tags: [tutorial, basic]
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

## 개요

챗봇 서비스들이 많이 등장하면서 챗봇과의 대화가 점점 익숙해지고 있지만 나에게 필요한 챗봇을 직접 만드는 것은 아직은 생소한 일입니다. 어디서부터 어떻게 시작해야 할지 고민되는 분들을 위해 튜토리얼 및 다양한 지원을 하고 있습니다.
- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Tutorial](/samplebot.html)</span> : 챗봇을 만드는 방법을 순서대로 배우면서 기본기를 익힐 수 있습니다.
- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Document](/index.html)</span> : 기능 별 자세한 설명을 제공하고 있습니다.
- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Q&A](http://doc.danbee.ai/feedback.html#qa-%EA%B2%8C%EC%8B%9C%ED%8C%90)</span> : Tutorial과 Document로 궁금증이 해소되지 않거나 danbee.Ai에 대한 의견이 있을 경우 운영자에게 문의할 수 있습니다.

## 샘플챗봇 따라하기

danbee.Ai를 이용하여 처음 챗봇을 만들어보시는 분들을 위해 차근차근 따라하며 챗봇을 만들어보실 수 있도록 샘플챗봇을 만드는 방법을 튜토리얼로 제공하고 있습니다.

- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[튜토리얼봇](/basic_create_intent.html)</span> : danbee.Ai의 여러 가지 기능들을 쉬운 것부터 하나씩 익혀볼 수 있습니다. Tutorial 1부터 8까지가 튜토리얼봇에 대한 단계별 설명입니다.
- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[피자주문봇](/advanced_order_pizza_bot.html)</span> : 챗봇을 이용하여 서비스를 만들어보는 예시로 피자주문봇을 만들어볼 수 있습니다. 기본적인 기능들을 모두 담고 있으므로 응용하여 다른 새로운 챗봇을 만드는데 많은 도움이 될 것입니다.
- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[선택장애제거, 캡틴초이 살펴보기](/advanced_choice_bot.html)</span> : 선택을 도와주는 샘플챗봇을 살펴보고, 살짝 수정해보는 실습을 해봅시다. 챗봇 페르소나에 대해서도 한번 생각해보아요.
- <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[의사결정나무봇, 디트 살펴보기](/advanced_decision_tree_bot.html)</span> : 대화를 통해 추천하는 챗봇을 샘플로 보고, 배워보아요.


## 샘플챗봇 가져오기
튜토리얼에서 만든 샘플챗봇 완성본을 직접 확인하고 수정해보실 수 있습니다. 챗봇을 처음 만들어본다면 샘플챗봇을 참고하면서 원하는대로 내용을 조금씩 수정하는 것이 더 쉽게 챗봇을 만드는 방법일 수 있습니다. 앞으로 다양하게 활용하실 수 있도록 계속해서 샘플챗봇을 추가할 예정입니다.

### Bot List에 Sample Chatbot 추가하기
1) 먼저 로그인한 후 Bot List에서 ***"Sample Chatbot 가져오기"*** 버튼을 클릭해 주세요.

{% include image.html file="tutorial/samplebot_empty.png"  caption="첫 로그인 화면" %}

2) 원하는 샘플챗봇의 ***"가져오기"*** 버튼을 클릭해주세요.여기서는 ***"튜토리얼봇"***을 가져와 보겠습니다.

{% include image.html file="tutorial/import_samplebot.png"  caption="샘플챗봇 가져오기" %}

3) Bot List에 선택한 샘플챗봇이 추가된 것을 확인하실 수 있습니다. 챗봇을 클릭하면 챗봇이름과 설명을 수정하실 수 있습니다.

{% include image.html file="tutorial/samplebot_list.png"  caption="챗봇 생성 완료" %}

4) ***의도추론(Intent)***과 ***대화흐름 목록(Chatflow List)*** 메뉴에서 샘플챗봇의 상세 내용을 확인할 수 있습니다.

{% include image.html file="tutorial/samplebot_intent.png"  caption="Intent 상세화면" %}
{% include image.html file="tutorial/samplebot_chatflow2.png"  caption="Chatflow 상세화면" %}

## 샘플챗봇 "튜토리얼봇" 테스트하기
샘플챗봇 "튜토리얼봇"은 ***"피자 주문해줘"***라는 사용자의 입력에 대하여 여러가지 버전으로 대답할 수 있는 예시를 제공하고 있습니다. 따라서 다음에 제공되는 튜토리얼에 따라 대화를 테스트 해보기 위해서는 아래와 같이 Chatflow를 수정해주는 작업이 필요합니다.

### "Tutorial 2. Chatflow 생성하기"의 예시를 테스트할 때
1) "피자주문하기"이라는 노드를 ***"Tutorial 2. 주문확인"***이라고 되어 있는 노드에 선을 연결해주세요.

2) ***"Chatflow 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

{% include image.html file="tutorial/samplebot_test_tutorial2.png"  caption="Tutorial 2 테스트" %}

### 다른 Tutorial의 예시를 테스트할 때
1) Tutorial 2. 주문확인과 연결된 선을 지워주세요. 선을 클릭하고 ***[Delete] 키***를 누르면 선이 삭제됩니다. 

2) 다른 Tutorial 노드에 선을 연결해주세요. ***"Tutorial 4. 피자메뉴질문"***이라는 노드에 선을 연결해보겠습니다.

3) ***"Chatflow 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

{% include image.html file="tutorial/samplebot_test_tutorial4.png"  caption="Tutorial 4 테스트" %}

이런 식으로 튜토리얼 단계별로 노드를 연결하여 테스트를 해볼 수 있습니다.

### 주의! Tutorial 7,8번의 예시를 테스트할 때
API Node는 테스트 하기 전에 직접 설정이 필요한 부분이 있습니다. <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Tutorial 7. API Node 생성하기 ](/basic_api_node.html)</span>를 보면서 API Node를 수정한 후 테스트해보세요.

## 직접 만들어보세요!
튜토리얼를 따라 만들다보면 챗봇을 만드는 것이 어렵지 않습니다. 다음 Step으로 넘어가서 이제 처음부터 챗봇을 만들어 보겠습니다.
