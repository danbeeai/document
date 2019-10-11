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

## 일단 한번, 만들어봅시다!

여러분들은 대화AI를 직접 만들기로 결심하신 분들이시군요? 정말 멋집니다. 저와 함께 차근 차근 만들어 보면, 생각하신 것보다 어렵지는 않으실 것입니다. 그럼 바로 시작하겠습니다.


<div class="videowrapper">
<iframe width="560" height="315" src="https://www.youtube.com/embed/V5p8JaK5eGE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### 회사소개봇 챗봇위자드로 생성하기
1) 회원가입 / 로그인을 진행합니다.

2) 챗봇목록에서 ***챗봇 생성하기*** 버튼을 클릭해 주세요. (최초 로그인 한 경우, 첫화면에서 할 수 있어요.)

3) ***회사소개봇***을 찾으셨나요? [생성하기]를 클릭합니다. (만약 회사가 아닌 기관을 소개하는 챗봇을 만들고 싶으시다면, 기관소개봇을 선택하셔도 됩니다. 똑같은 위자드 챗봇입니다.)

4) 마지막에 생성된 챗봇의 링크를 웹브라우저에서 확인해보세요. QR코드를 통해 스마트폰에서 이용하실 수도 있습니다.

### 챗봇 위자드?
벌써 여러분의 첫 챗봇이 생성되었네요! 이와 같이 챗봇 위자드는 챗봇이 답변해야할 콘텐츠, 연결해야할 데이터만 입력하면 미리 만들어진 챗봇템플릿과 결합되어 챗봇이 생성되는 기능입니다. 지금도 새로운 위자드를 만들어서 오픈하고 있습니다. 필요한 챗봇 위자드가 있다면 [contact@danbee.ai](mailto:contact@danbee.ai)에 자세한 내용을 적어서 알려주세요. 많은 분들이 요청해주시는 챗봇을 먼저 만들기 위해 노력하고 있습니다. 

## 챗봇과 단비Ai에 대해 차근 차근 알아봅시다!
어떤 챗봇이든 이렇게 쉽게 챗봇을 만들 수 있다면 좋겠네요. 바로 함께 일할 수 있는 훈련된 동료를 얻는 것이죠. 하지만, 더 여러가지를 할 수 있게 만들거나 더 복합적인 일을 맡기고 싶다면 챗봇에 대해 더 이해할 필요가 있습니다. 튜터리얼을 하나씩 따라해보시면, 챗봇과 단비AI의 다양한 기능을 쉽게 이해하실 수 있습니다.

<div class="videowrapper">
<iframe width="560" height="315" src="https://www.youtube.com/embed/RCfC8fqcnU0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### 챗봇목록에서 튜터리얼봇 생성하기
1) 로그인 한 상태에서 챗봇목록에서 ***챗봇 생성하기*** 버튼을 클릭해 주세요. (최초 로그인 한 경우, 첫화면에서 할 수 있어요.)

2) ***튜토리얼봇***을 찾으셨나요? [생성하기]를 클릭합니다.

3) 챗봇목록에 선택한 샘플챗봇이 추가된 것을 확인하실 수 있습니다. 

4) ***의도추론(Intent)***과 ***대화흐름 목록(Chatflow List)*** 메뉴에서 샘플챗봇의 상세 내용을 확인할 수 있습니다.

{% include image.html file="tutorial/samplebot_chatflow2.png"  caption="Chatflow 상세화면" %}

## 샘플챗봇 "튜토리얼봇" 테스트하기
샘플챗봇 "튜토리얼봇"은 ***"피자 주문해줘"***라는 사용자의 입력에 대하여 여러가지 버전으로 대답할 수 있는 예시를 제공하고 있습니다. 따라서 다음에 제공되는 튜토리얼에 따라 대화를 테스트 해보기 위해서는 아래와 같이 Chatflow를 수정해주는 작업이 필요합니다.

### "Tutorial 2. Chatflow 생성하기"의 예시를 테스트할 때
1) "피자주문하기"이라는 노드를 ***"Tutorial 2. 주문확인"***이라고 되어 있는 노드에 선을 연결해주세요.

2) ***"Chatflow 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

{% include image.html file="tutorial/samplebot_test_tutorial2.png"  caption="Tutorial 2 테스트" %}

### 다른 Tutorial의 예시를 테스트할 때
1) Tutorial 2. 주문확인과 연결된 선을 지워주세요. 선을 클릭하고 ***[Delete] 키***를 누르면 선이 삭제됩니다. (Mac에서는 function + backspace)

2) 다른 Tutorial 노드에 선을 연결해주세요. ***"Tutorial 4. 피자메뉴질문"***이라는 노드에 선을 연결해보겠습니다.

3) ***"Chatflow 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

{% include image.html file="tutorial/samplebot_test_tutorial4.png"  caption="Tutorial 4 테스트" %}

이런 식으로 튜토리얼 단계별로 노드를 연결하여 테스트를 해볼 수 있습니다.

단답형도 가능하지만, 사용자에게 버튼이나 카드형태로 선택을 유도하고, 사용자가 선택한 항목에 따라 분기할 수 있는 것을 알 수 있습니다. 또한, API연동을 통해 데이터를 가져와 대화흐름에서 활용하실 수도 있습니다. 마지막으로 간단한 데이터 변환, 계산 등을 처리할 수 있는 것도 알 수 있었습니다.

## 직접 만들어보세요!
다음 장부터 시작되는 튜토리얼를 따라하면, 지금까지 살펴본 샘플 챗봇의 모든 기능을 실제로 활용할 수 있게 됩니다. 직접 만드실 생각이시라면, 반드시 튜토리얼을 따라해보시길 추천드립니다. 만약 기획만 하시고 제작을 다른 분에게 부탁할 생각이라면, 이 튜터리얼의 링크를 꼭 공유해서 쉽게 배울 수 있도록 도와주세요. 만들다보면 챗봇을 만드는 것이 어렵지 않습니다. 다음 Step으로 넘어가서 이제 처음부터 챗봇을 만들어 보겠습니다.

## 진행중 어려움이 있다면?
진행 중에 궁금하신 사항은 Manual을 찾아보거나 단비Ai에서 일하고 있는 "파브르"에게 접수하면, Q&A게시판으로 회신받을 수 있습니다.

- <span class="link">[Manual](/index.html)</span> : 기능 별 자세한 설명을 제공하고 있습니다.
- <span class="link">[Q&A](http://doc.danbee.ai/feedback.html#qa-%EA%B2%8C%EC%8B%9C%ED%8C%90)</span> : Tutorial과 Document로 궁금증이 해소되지 않거나 danbee.Ai에 대한 의견이 있을 경우 운영자에게 문의할 수 있습니다.
