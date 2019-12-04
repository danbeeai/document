---
title: Split 노드 사용하기 
tags: [tutorial, chatflow, basic]
keywords: Tutorial
summary: Split 노드의 개념을 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_split.html
folder: tutorial
previous: {
    title: Carousel 노드 사용하기, 
    url: basic_carousel.html
}
next: {
    title: API 노드 사용하기,
    url: basic_api_node.html
}
---

### Split 노드

Split 노드는 하나의 대화흐름 안에서 대화흐름을 여러 갈래로 나누어주는 역할을 합니다. Split 노드에 여러 개의 노드를 연결하면, 조건에 따라 연결된 여러 노드들 중 하나의 노드를 선택하여 대화를 이어가게 됩니다.
이번 Step에서는 Split 노드에 조건을 추가하여 어떤 메뉴를 선택했느냐에 따라 다른 답변을 주도록 만들어보겠습니다.


### Split 노드 생성 및 노드 연결 

1) "피자주문하기" 대화흐름 상세 페이지에서 상단의 Split 노드를 클릭하여 추가해주세요.

2) 3가지의 피자 메뉴별로 메시지를 만들기 위하여 Speak 노드 3개를 추가해주세요.

3) ***Listen 노드 > Carousel 노드 > Split 노드 > Speak 노드*** 순으로 선을 연결시켜주세요. ***Split 노드는 상세 설정을 하기 전에 다음으로 넘어갈 노드들을 먼저 연결시켜주어야 합니다.*** Speak 노드가 아닌 다른 노드들도 모두 연결이 가능합니다.

{% include image.html file="tutorial/basic06_create_split.png"  caption="Split 노드 연결된 상태" %}

4) Split 노드를 더블 클릭하여 상세 패널을 열어줍니다.

### 조건 설정
1) ***기본조건***은 구체적인 조건이 없거나 다른 조건이 맞지 않는 경우 기본적으로 연결할 노드를 선택하는 것입니다. 이번에 만들 Split 노드는 기본조건이 없으므로 ***"기본조건 사용안함”***으로 선택해주세요.

2) 하단의 ***"조건추가”*** 버튼을 클릭하여 조건을 추가해주세요.

3) 조건을 정의하기 위해서는 다음에 연결할 노드, 조건의 기준이 되는 파라미터, 조건식, 조건값이 필요합니다. 아래 이미지와 같이 #조건1에 ***"페퍼로니주문 Speak 노드, 피자메뉴 파라미터, ==, 페퍼로니"***를 입력해요. 이 조건은 ***"피자메뉴” 파라미터 값이 “페퍼로니”일 때, "페퍼로니주문" Speak 노드로 연결시킨다***는 것을 의미합니다.

4) 마찬가지로 조건을 추가하여 쉬림프와 치즈 조건을 입력해주세요.

{% include image.html file="tutorial/basic06_add_condition.png"  caption="Split 노드 조건 추가" %}

5) 우측 하단의 ***“확인”*** 버튼을 클릭하여 Split 노드 상세 화면을 닫아주세요.

6) 이제 3개의 Speak 노드 상세 화면으로 이동하여 각각 다른 메시지와 이미지를 입력해주세요.

{% include image.html file="tutorial/basic06_speak_pepperoni2.png"  caption="페퍼로니주문 Speak 노드 메시지, 다른 스피크 노드들도 유사하게 만들어 보아요." %}

7) ***“대화흐름 저장”*** 버튼을 클릭한 후 우측의 테스트 패널에서 ***"페퍼로니 피자 주문해줘”, “쉬림프 피자 주문해줘”***와 같이 다른 메뉴를 입력하면 각각 다른 메시지가 나타나는 것을 확인할 수 있습니다. 슬롯노드와 동일하게 말이죠.

{% include image.html file="tutorial/basic06_test_split2.png"  caption="Split 노드 테스트" %}


### 다음 Step에서는

지금까지 Speak 노드, Slot 노드, Carousel 노드, Split 노드의 역할과 기본적인 사용법에 대해 배워보았습니다. 이 노드만으로도 충분히 챗봇을 만들 수 있지만 프로그래밍 지식이 있다면  다양한 기능들을 추가할 수 있습니다. 다음 Step에서는 조금 더 난이도가 있는 API 노드를 사용하여 외부 서비스의 데이터를 조회하여 메시지로 보여주는 방법에 대해 배워보도록 하겠습니다.




{% include bottom.html %}