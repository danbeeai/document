---
title: Intent 생성하기
tags: [intent, chatflow]
keywords: Tutorial
summary: danbee.Ai의 기본 구조를 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_create_intent.html
folder: tutorial
previous: {
    title: 튜토리얼 시작하기,
    url: samplebot.html
}
next: {
    title: Chatflow 생성하기,
    url: basic_listen_speak.html
}
---

<iframe width="854" height="480" src="https://www.youtube.com/embed/nuaRRwKoAYA" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
영상으로 danbee.Ai 사용법을 배울 수 있습니다. 위 영상은 튜토리얼의 ***1. Intent 생성하기***와 ***2. Chatflow 생성하기***의 내용을 포함합니다. 

## danbee.Ai의 기본 구조

챗봇의 기본 동작원리를 생각해보면 사람들이 대화할 때 일어나는 의식의 흐름과 크게 다르지 않습니다. 사용자가 챗봇에게 어떤 말을 걸면 챗봇이 그 말을 듣고 사용자의 의도를 파악하여 적절한 답변을 하게 됩니다. 원활한 대화가 되기 위해서는 말을 잘 이해하고, 원하는 대답을 해주는 것이 중요합니다.
이를 위해 danbee.Ai의 기본 구조는 크게 사용자의 의도(Intent)를 파악할 수 있는 ***자연어 이해(NLU)***와 여러 상황에 따라 적절하게 답변을 할 수 있도록 대화를 설계하는 ***대화흐름(Chatflow)***으로 구성되어 있습니다. 
어떤 말을 알아들을 것인지와 어떻게 대답할 것인지를 정의하면 하나의 대화를 완성할 수 있습니다.

## 챗봇 생성
danbee.Ai를 이용하려면 먼저 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[로그인](https://danbee.ai/platform/#/danbeelogin)</span>을 해주셔야 합니다.

처음 로그인을 하시면, 먼저 챗봇을 만들어주세요.
챗봇 생성방법은 document의 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[간단한 챗봇 만들어보기](/basic_create_chatbot.html)</span>를 참고하시면 됩니다.

챗봇이 생성되었으면, 이제 기본적인 것부터 차근차근 챗봇을 만들어 보겠습니다.
이해를 돕기 위해 피자가게의 사업자가 피자를 주문 받을 수 있는 챗봇을 만든다고 가정하여 진행하겠습니다.


## 의도추론(Intent) 만들기
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도추론(Intent)]" type="default" %}
피자를 주문 받으려면 “피자 주문해줘”와 같은 사용자의 말이 입력되었을 때 “피자를 주문하고 싶다”는 사용자의 의도를 파악할 수 있어야 합니다. 그 의도를 정의할 수 있는 메뉴가 “의도추론 (Intent)” 입니다.

### Intent 생성
1) ***”Intent 생성”*** 버튼을 클릭하여 Intent 생성 페이지로 이동해주세요.

{% include image.html file="tutorial/basic01_empty_intent.png" max-width="900" caption="Intent 없는 상태" %}

2) 상단의 Intent명 입력란에 ***”피자주문하기”***과 같이 Intent명을 적어주세요. 챗봇의 완성도가 높아질수록 Intent 수가 많아지므로 명확히 구분할 수 있고, 검색하기 쉽게 정의하는 것이 좋습니다.

3) ***“피자 주문해줘”***와 같이 피자주문 Intent로 연결될 수 있는 예문을 1개 이상 필수로 등록해야 합니다. 예문은 여러 Intent들과 중복되지 않으면서 구체적으로 적어주는 것이 좋습니다. 사용자가 입력한 말과 예문을 비교하여 가장 비슷한 Intent로 연결하기 때문에 응답의 정확도를 높이기 위해서는 예문을 적절하게 정의하는 것이 매우 중요합니다.

{% include image.html file="tutorial/basic01_create_intent.png" max-width="900" caption="Intent명과 예문 입력된 모습" %}

4) Intent 명과 예문을 입력하였으면 ***“저장”*** 버튼을 클릭하여 Intent를 생성합니다. 그 외의 Intent 설정 항목에 관해서는 document의 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[의도관리](/intent.html)</span>를 보시면 더욱 자세히 알 수 있습니다.


## Intent 테스트
우측의 테스트 패널에서 저장한 Intent가 제대로 동작하는지 테스트 해볼 수 있습니다.
NLU Intent 탭에서 “피자 주문해줘” 예문을 입력해보면 Intent가 “피자주문하기”으로 조회되는 것을 확인할 수 있습니다.

{% include image.html file="tutorial/basic01_test_intent.png" max-width="900" caption="테스트패널에서 Intent 테스트" %}


## 다음 Step에서는
사용자의 “피자주문하기” 의도를 파악할 수 있게 되었으니 이제 어떻게 응답할지 정의해야겠죠?
대화흐름(Chatflow) 메뉴에서 챗봇이 대답할 메시지를 정의해보도록 하겠습니다.

