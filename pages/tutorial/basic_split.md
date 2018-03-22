---
title: Split Node 사용하기
tags: [split_node]
keywords: Tutorial
summary: Split Node의 개념을 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_split.html
folder: tutorial
previous: {
    title: Carousel Node 사용하기, 
    url: basic_carousel.html
}
next: {
    title: API 노드 사용하기,
    url: basic_api_node.html
}
---

## Splitl Node를 사용하여 조건별 메시지 나누기
대화를 할 때, 기계적으로 같은 대답만 하면 지루하겠죠. 같은 내용이라도 다르게 대답하거나 예외적인 상황이 있을 때를 구분하여 대답한다면 사용자가 좀 더 만족스러운 답변을 들을 수 있을 것입니다. Split Node는 조건에 따라 대화 방향을 전환시켜주는 역할을 합니다. 

이번 Step에서는 Split Node에 조건을 추가하여 어떤 메뉴를 선택했느냐에 따라 다른 답변을 주도록 만들어보겠습니다.

### Split Node
Split Node는 하나의 Chatflow 안에서 대화흐름을 여러 갈래로 나누어주는 역할을 합니다. Split Node에 여러 개의 노드를 연결하면, 조건에 따라 연결된 여러 노드들 중 하나의 노드를 선택하여 대화를 이어가게 됩니다.

#### Split Node 생성 및 노드 연결 
1) "피자주문하기" Chatflow 상세 페이지에서 상단의 Split Node를 클릭하여 추가해주세요.

2) 3가지의 피자 메뉴별로 메시지를 만들기 위하여 Speak Node 3개를 추가해주세요.

3) ***Listen Node > Carousel Node > Split Node > Speak Node*** 순으로 선을 연결시켜주세요. ***Split Node는 상세 설정을 하기 전에 다음으로 넘어갈 노드들을 먼저 연결시켜주어야 합니다.*** Speak Node가 아닌 다른 노드들도 모두 연결이 가능합니다.

{% include image.html file="tutorial/basic06_create_split.png" max-width="900" caption="Split Node 연결된 상태" %}

4) Split Node를 더블 클릭하여 상세 화면으로 이동해주세요.

#### 조건 설정
1) ***기본조건***은 구체적인 조건이 없거나 다른 조건이 맞지 않는 경우 기본적으로 연결할 Node를 선택하는 것입니다. 이번에 만들 Split Node는 기본조건이 없으므로 ***"기본조건 사용안함”***으로 선택해주세요.

{% include image.html file="tutorial/basic06_default_condition.png" max-width="900" caption="Split Node 기본조건" %}

2) 하단의 ***"조건추가”*** 버튼을 클릭하여 조건을 추가해주세요.

3) 조건을 정의하기 위해서는 다음에 연결할 노드, 조건의 기준이 되는 Parameter, 조건식, 조건값이 필요합니다. 아래 이미지와 같이 #조건1에 ***"페퍼로니주문 Speak Node, 피자메뉴 Parameter, ==, 페퍼로니"***를 입력하고 ***[+]*** 버튼을 클릭해주세요. 이 조건은 ***"피자메뉴” Parameter의 값이 “페퍼로니”일 때, "페퍼로니주문" Speak Node로 연결시킨다***는 것을 의미합니다.

4) 마찬가지로 조건을 추가하여 쉬림프와 치즈 조건을 입력해주세요.

{% include image.html file="tutorial/basic06_add_condition.png" max-width="900" caption="Split Node 조건 추가" %}

5) 우측 하단의 ***“확인”*** 버튼을 클릭하여 Split Node 상세 화면을 닫아주세요.

6) 이제 3개의 Speak Node 상세 화면으로 이동하여 각각 다른 메시지와 이미지를 입력해주세요.

{% include image.html file="tutorial/basic06_speak_pepperoni2.png" max-width="900" caption="페퍼로니주문 Speak Node 메시지" %}
{% include image.html file="tutorial/basic06_speak_shrimp2.png" max-width="900" caption="쉬림프주문 Speak Node 메시지" %}
{% include image.html file="tutorial/basic06_speak_cheese2.png" max-width="900" caption="치즈주문 Speak Node 메시지" %}

7) ***“Chatflow 저장”*** 버튼을 클릭한 후 우측의 테스트 패널에서 ***"페퍼로니 피자 주문해줘”, “쉬림프 피자 주문해줘”***와 같이 다른 메뉴를 입력하면 각각 다른 메시지가 나타나는 것을 확인할 수 있습니다.

{% include image.html file="tutorial/basic06_test_split2.png" max-width="900" caption="Split Node 테스트" %}


## 다음 Step에서는
지금까지 Speak Node, Slot Node, Carousel Node, Split Node의 역할과 기본적인 사용법에 대해 배워보았습니다. 이 노드만으로도 충분히 챗봇을 만들 수 있지만 프로그래밍 지식이 있다면  다양한 기능들을 추가할 수 있습니다. 다음 Step에서는 조금 더 난이도가 있는 API Node를 사용하여 외부 서비스의 데이터를 조회하여 메시지로 보여주는 방법에 대해 배워보도록 하겠습니다.
