---
title: 튜토리얼봇 살펴보기 (영상)
tags: [tutorial, basic]
keywords: Tutorial
summary: 튜토리얼봇이 어떻게 생겼는지 살펴볼 수 있는 영상콘텐츠 입니다.
sidebar: tutorial_sidebar
permalink: samplebot.html
folder: tutorial
next: {
    title: 의도 생성하기,
    url: basic_create_intent.html
}
---

## 챗봇의 원리를 이해하기에 좋은 튜토리얼

실습할 시간이 많지 않은데, 대략적인 동작원리를 알고 싶은 당신. 잘오셨습니다. 
튜토리얼 샘플을 살펴보거나 차근 차근 따라하면 챗봇을 만들어보고 동작원리를 파악하실 수 있습니다. 
<br />

## 잠깐! 질문과 답. 단답형 챗봇을 만들 계획이시라면?
질문과 답을 엑셀로 정리하기만 하면 챗봇이 생성되어 동작하는 기능이 있습니다. 복합적인 기능이 아닌 단답형 답변처리를 원하신다면, 아래 링크를 참고하여 FAQ챗봇을 만드시기 바랍니다.
<br/>
{% include button_cta.html value="FAQ챗봇 만들기 튜토리얼" title="FAQ챗봇 만들기 튜토리얼 바로가기" url="/tutorial_faq.html" %}


## 튜토리얼봇을 살펴보며 원리 이해하기

동영상으로 기본원리를 알고 넘어가면 툴을 다루는데 더 많은 도움이 될 것입니다. 차례대로 보시면 챗봇을 만드는 과정과 동작원리를 알 수 있습니다.

### 단비챗봇 만들기 튜토리얼 1편 : 인텐트와 엔티티
상대방의 말을 알아듣는 다는 것은 상대방의 의도(인텐트, Intent)와 의도속에 있는 핵심어(엔티티, Entity)를 추출한다는 것입니다. 예를 들어 '페퍼로니 피자 주문할래'라고 했을 때, 의도는 '피자주문'이고 엔티티는 '페퍼로니'인 것이죠. 자세한 것은 영상을 통해 살펴보아요.

<div class="videowrapper">
<iframe width="560" height="315" src="https://www.youtube.com/embed/-VOXXVMwYsc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### 단비챗봇 만들기 튜토리얼 2편 : 대화흐름의 기본
상대방의 말을 이해했다면, 그에 맞는 반응을 하게 됩니다. 바로 대답이 가능하면 대답을 하는 것이고, 대답을 위해 추가로 물어볼 것이 있다면 다시 물어보는 과정을 거칩니다. 단비Ai에서는 드래그앤드롭으로 흐름을 만들 수 있게 되어 있습니다. 영상으로 살펴보아요.

<div class="videowrapper">
<iframe width="560" height="315" src="https://www.youtube.com/embed/Syf54rG-2Os" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

### 단비챗봇 만들기 튜토리얼 3편 : 대화흐름 고급과정
사용자가 뭔가 골라야 하는 상황에는 카드를 펼쳐서 보여주고, 상대방이 이야기한 키워드에 따라 대답이 달라질 수 있습니다. 이러한 과정을 위한 심화 기능을 영상으로 소개합니다.

<div class="videowrapper">
<iframe width="560" height="315" src="https://www.youtube.com/embed/7PIc8IBe6gs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


### 단비챗봇 만들기 튜토리얼 4편 : 시스템 데이터 연동
챗봇이 대답해야 하는 정보가 늘 변화하는 정보 또는 따로 관리되는 정보라면 시스템 연동이 필요합니다. API라는 기술을 이용해 단비Ai와 연동할 수 있습니다. 개발자가 아니라면, 이 부분은 어려우실 수 있습니다. 하지만 튜토리얼을 통해 동작원리를 이해하고, 동료 개발자분에게 도움을 요청하실 때 활용하시기 바랍니다.

<div class="videowrapper">
<iframe width="560" height="315" src="https://www.youtube.com/embed/SZ4Dvovbyqk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## 직접 튜토리얼봇 살펴보기

영상에서 본 튜토리얼봇의 구조를 직접 살펴보시려면 아래 과정을 따라해보시기 바랍니다.

1) 로그인 한 상태에서 [챗봇 생성/관리]에서 ***챗봇 생성하기*** 버튼을 클릭해 주세요. 

2) ***튜토리얼봇***을 찾으셨나요? [생성하기]를 클릭합니다.

3) 챗봇목록에 선택한 샘플챗봇이 추가된 것을 확인하실 수 있습니다. 

4) ***의도추론 관리***과 ***대화흐름 빌더*** 메뉴에서 샘플챗봇의 상세 내용을 확인할 수 있습니다.

{% include image.html file="tutorial/samplebot_chatflow2.png"  caption="대화흐름 상세화면" %}

## 튜토리얼봇 테스트하기
샘플챗봇 "튜토리얼봇"은 ***"피자 주문해줘"***라는 사용자의 입력에 대하여 여러가지 버전으로 대답할 수 있는 예시를 제공하고 있습니다. 따라서 다음에 제공되는 튜토리얼에 따라 대화를 테스트 해보기 위해서는 아래와 같이 대화흐름을 수정해주는 작업이 필요합니다.

### "Tutorial 2. 대화흐름 생성하기"의 예시를 테스트할 때
1) "피자주문하기"이라는 노드를 ***"Tutorial 2. 주문확인"***이라고 되어 있는 노드에 선을 연결해주세요.
   - 기존에 있는 노드와 노드를 연결한 선을 지우고, 노드 끝에 달려 있는 동그라미를 드래그 하여 선을 연결합니다.

2) ***"변경내용 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

{% include image.html file="tutorial/samplebot_test_tutorial2.png"  caption="Tutorial 2 테스트" %}

### 다른 Tutorial의 예시를 테스트할 때
1) Tutorial 2. 주문확인과 연결된 선을 지워주세요. 선을 클릭하고 ***[Delete] 키***를 누르면 선이 삭제됩니다. (Mac에서는 function + backspace)

2) 다른 Tutorial 노드에 선을 연결해주세요. ***"Tutorial 4. 피자메뉴질문"***이라는 노드에 선을 연결해보겠습니다.

3) ***"변경내용 저장"*** 후 우측의 테스트 패널에서 ***"피자 주문해줘"***를 입력해보세요.

{% include image.html file="tutorial/samplebot_test_tutorial4.png"  caption="Tutorial 4 테스트" %}

이런 식으로 튜토리얼 단계별로 노드를 연결하여 테스트를 해볼 수 있습니다.

단답형도 가능하지만, 사용자에게 버튼이나 카드형태로 선택을 유도하고, 사용자가 선택한 항목에 따라 분기할 수 있는 것을 알 수 있습니다. 또한, API연동을 통해 데이터를 가져와 대화흐름에서 활용하실 수도 있습니다. 마지막으로 간단한 데이터 변환, 계산 등을 처리할 수 있는 것도 알 수 있었습니다.

## 직접 만들어보세요!
다음 장부터 시작되는 튜토리얼은 지금까지 살펴본 샘플 챗봇의 모든 기능을 실제로 활용할 수 있게 됩니다. 

1) 직접 만드실 생각이시라면, 튜토리얼을 따라해보시길 추천드립니다. 
2) 서비스 기획만 하시고 제작을 다른 분에게 부탁할 생각이라면, 이 튜토리얼의 링크를 꼭 공유해서 쉽게 배울 수 있도록 도와주세요. 

마음을 정하셨나요? 다음 Step으로 넘어가서 처음부터 챗봇을 만들어 보시죠!



{% include bottom.html %}