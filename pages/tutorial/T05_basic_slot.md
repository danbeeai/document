---
title: Slot Node 사용하기
tags: [tutorial, chatflow, basic]
keywords: Tutorial
summary: Slot Node의 개념을 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_slot.html
folder: tutorial
previous: {
    title: Entity와 Parameter 이해하기, 
    url: basic_entity_parameter.html
}
next: {
    title: Carousel Node를 사용하기,
    url: basic_carousel.html
}
---

## Slot Node를 사용하여 필요한 정보 확인하기
피자를 정상적으로 주문 받기 위해서 메뉴, 사이즈, 수량 정보가 필요하다고 할 때, 주문하는 사람이 처음부터 “페퍼로니 피자 미디움 사이즈로 1판 주세요.”라고 완벽하게 말하는 경우는 많지 않습니다. 따라서 필요한 정보들이 모두 입력되었는지 체크하고, 누락된 내용들을 다시 질문하여 원하는 정보를 받아내야 합니다.

이번 단계에서는 간단하게 ***“피자메뉴”*** 정보가 들어왔는지 Slot Node를 이용해 체크하고, 질문을 통해 정보를 얻어내는 것까지 해보겠습니다.

### Slot Node
Slot Node는 Parameter를 기준으로 질문메시지를 정의할 수 있습니다. 필수로 얻어야 하는 정보를 Parameter로 정의하고 Slot Node에 Parameter 값을 얻기 위한 질문을 추가해야 합니다.필수로 얻어야하는 정보가 여러 개라면 각각 Parameter로 정의하고 질문을 만들면 됩니다.

#### Slot Node 생성 및 질문 메시지 정의
1) "피자주문하기" Chatflow 상세 페이지에서 상단의 Slot Node를 클릭하여 Slot Node를 추가해주세요. 그리고 ***Listen Node > Slot Node > Speak Node*** 순으로 배치한 후 선을 연결해주세요. 기존에 연결되어 있던 선을 삭제하려면 선을 선택한 후 ***[Delete] 키***를 누르면 됩니다.

{% include image.html file="tutorial/basic04_create_slot.png" max-width="900" caption="Slot Node 추가된 상태" %}

2) Slot Node를 더블 클릭하여 상세 화면으로 이동한 후, ***”질문 추가”*** 버튼을 클릭하여 1개의 질문 메시지를 생성해주세요.

{% include image.html file="tutorial/basic04_empty_slot.png" max-width="900" caption="질문 없는 상태" %}

3) #1의 Select Box에서 ***“피자메뉴”*** Parameter를 선택하고, 메시지 입력란에 ***“어떤 피자를 주문할까요?”***라고 입력해주세요

{% include image.html file="tutorial/basic04_slot_question.png" max-width="900" caption="질문 메시지 작성" %}

#### 선택지 버튼 추가 및 Parameter 값 정의
1) 텍스트로 답을 받을 수도 있지만 사용자로부터 정확한 답을 받기 위해서 버튼 형태로 선택지를 줄 수도 있습니다. ***"Button 추가”***를 클릭하여 ***“선택지”*** 옵션을 선택해주세요.

2) ***"피자메뉴”*** Entity의 각 메뉴 Entry를 버튼으로 입력해주세요. ***"버튼명”***은 메시지에 노출되는 텍스트이고, 우측의 입력란에는 ***"피자메뉴”*** Parameter에 담을 값을 입력해주세요.

{% include image.html file="tutorial/basic04_add_button.png" max-width="900" caption="버튼 내용 추가" %}

#### Slot Node 테스트
1) ***"Chatflow 저장"*** 버턴을 클릭한 후 우측의 테스트 패널에서 테스트를 해보세요. ***“피자 주문해줘”***라고 입력하면 Slot Node에서 정의한 질문 메시지가 나타나고, 버튼을 클릭하면 Speak Node에서 정의한 응답 메시지가 나타납니다. 

{% include image.html file="tutorial/basic04_slot_test1.png" max-width="900" caption="Step 4 테스트1" %}

3) 여기서 잠깐! ***“페퍼로니 피자 주문해줘”***라고 입력하면 어떻게 될까요? 이미 “피자메뉴”에 대한 정보가 “페퍼로니”라고 들어왔기 때문에 Slot Node를 건너뛰고, 바로 Speak Node 메시지가 나타납니다.

{% include image.html file="tutorial/basic04_slot_test2.png" max-width="900" caption="Step 4 테스트2" %}


## 다음 Step에서는
Slot Node를 이용하여 피자메뉴를 버튼으로 선택할 수 있게 만들어 보았습니다. 사용자가 메뉴 선택을 좀 더 직관적으로 할 수 있도록 사진도 함께 보여주면 더 좋을 것 같은데요. 다음 Step에서는 Carousel Node를 이용하여, 카드 형태로 메시지를 만드는 방법을 배워보겠습니다.
