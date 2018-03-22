---
title: Entity와 Parameter 이해하기
tags: [entity, parameter]
keywords: Tutorial
summary: Entity와 Parameter의 개념을 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_entity_parameter.html
folder: tutorial
previous: {
    title: Chatflow 생성하기, 
    url: basic_listen_speak.html
}
next: {
    title: Slot Node 사용하기, 
    url: basic_slot.html
}
---

## 엔티티(Entity) 만들기
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [단어추출(Entity)]" type="default" %}
Entity란, 사용자의 말에서 중요하게 알아들어야 하는 정보들의 묶음 단위입니다. 예를 들어, 피자 가게의 피자 메뉴로 페퍼로니, 쉬림프, 치즈 피자가 있다면 ***“피자메뉴”***라는 Entity에 ***“페퍼로니”, “쉬림프”, “치즈”***라는 대표어를 정의할 수 있습니다. 이렇게 "피자메뉴" Entity를 정의하고 나면 사용자가 “페퍼로니”를 언급했을 때 챗봇은 피자메뉴를 말하고 있다고 인식하게 됩니다. Entity를 정의하는 것은 다양한 키워드를 그룹 단위로 정리하는 효과도 있지만 각각의 키워드를 포함시킨 예문을 하나하나 입력할 필요도 없어지고 Parameter로 이용할 수도 있습니다. 자세한 설명은 아래에서 다시 언급하도록 하겠습니다.

### Entity 생성
1) Entity 메뉴 화면에서 ***“Entity 생성”*** 버튼을 클릭하여 Entity 생성 페이지로 이동해주세요.

{% include image.html file="tutorial/basic03_empty_entity.png" max-width="900" caption="Entity 없는 상태" %}

2) 상단의 Entity명 입력란에 ***“피자메뉴”***과 같이 Entity명을 적어주세요. 하위에 정의할 키워드들의 그룹명이라고 볼 수 있습니다.

3) ***”페퍼로니”, “쉬림프”, “치즈”*** 등과 같이 각각의 피자 메뉴명을 Entry에 넣어주세요. Entry는 각 키워드의 대표어입니다. 우측의 Reference에는 Entry와 동일한 의미를 가지는 단어들을 입력해 주세요. 사용자가 Reference에 정의된 단어를 입력하더라도 Entry와 동일한 의미로 인식할 수 있습니다. Reference는 1개 이상 등록되어야 합니다.

{% include image.html file="tutorial/basic03_entity_detail.png" max-width="900" caption="Entity 상세 화면" %}

4) Entry와 Reference를 모두 입력하면 우측 상단의 ***”저장”*** 버튼을 클릭하여 데이터를 저장해주세요.

### Intent 예문에 Entity 설정하기
Entity를 만들었으니, Entity를 인식할 수 있도록 Intent의 예문에 등록해보겠습니다.

1) 이전 튜토리얼에서 만들었던 ***“피자주문하기”**** Intent 상세 페이지로 이동해 주세요.

2) ***“페퍼로니”***는 ***“피자메뉴”*** Entity의 Entry 중 하나였죠. ***"페퍼로니 피자 주문해줘"***라는 예문을 추가한 후 ***“페퍼로니”***를 마우스로 드래그해주세요.

3) ***“페퍼로니”*** 글자를 드래그하면 팝업으로 Entity 리스트가 나타납니다. ***“피자메뉴”*** Entity를 선택하면 예문에 Entity가 설정됩니다. 

{% include image.html file="tutorial/basic03_add_entity.png" max-width="900" caption="예문에 추가할 Entity 선택" %}

4) 우측 상단의 ***“저장”*** 버튼을 눌러 수정된 내용을 저장해주세요. Intent를 저장하면 Entity를 지정했던 글자가 컬러로 표시되는 것을 확인할 수 있습니다. 이렇게 Entity를 연결하면, “쉬림프 피자 주문해줘”, “치즈 피자 주문해줘”와 같이 메뉴 별로 하나하나 예문으로 등록하지 않아도 동일하게 동작하게 됩니다.

{% include image.html file="tutorial/basic03_added_entity.png" max-width="900" caption="예문에 Entity 추가된 모습" %}

## 파라미터(Parameter) 활용
예문에 Entity를 연결하면 동시에 같은 이름의 Parameter가 생성된 것을 확인할 수 있습니다.

***Parameter***란 사용자가 입력한 Entity 값을 담아내는 껍데기 입니다. 사용자가 "페퍼로니 피자 주문해줘"라고 입력하면 “페퍼로니”라는 Entity 값이 “피자메뉴” Parameter에 담겨지게 됩니다. 이후에 “피자메뉴” Parameter를 호출하면 “페퍼로니”라는 값이 조회되게 됩니다. 이렇게 Parameter에 필요한 정보를 담아 놓고 Chatflow에서 Parameter를 이용하여 그 값을 목적에 맞게 조회하여 활용할 수 있습니다. 

{% include image.html file="tutorial/basic03_create_parameter.png" max-width="900" caption="Parameter 생성된 모습" %}

### Parameter 추가
예문에 Entity를 등록하지 않고 직접 Parameter를 추가할 수도 있습니다. 피자가격 정보를 담을 Parameter를 추가해 보겠습니다.

1) Intent 상세 페이지에서 ***추출되는 Parameter*** 영역 우측에 있는 ***"+ Parameter"*** 버튼을 클릭해주세요.

{% include image.html file="tutorial/basic03_add_parameter_button.png" max-width="900" caption="Parameter 추가 버튼" %}

2) Parameter 명을 ***"피자가격"***, Entity를 ***"sys.any"***로 입력해주세요. ***sys.any***는 danbee.Ai에서 기본적으로 제공하는 Entity 중 하나로 어떤 값이든 모두 Parameter로 받을 수 있는 Entity 입니다. 피자메뉴 Entity처럼 대표어를 별도로 관리할 필요가 없습니다.
- sys.any와 같이 danbee.Ai에서 기본적으로 제공하는 Entity에 대한 자세한 설명은 document의 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[시스템 Entity](/entity.html#%EC%8B%9C%EC%8A%A4%ED%85%9C-entity)</span>에서 확인할 수 있습니다.

{% include image.html file="tutorial/basic03_new_parameter.png" max-width="900" caption="신규 Parameter 내용 입력" %}

3) ***"추가"*** 버튼을 클릭하여 팝업을 닫으면 Parameter가 추가된 것을 확인할 수 있습니다. 우측 상단의 ***"저장"*** 버튼을 클릭하여 수정한 내용을 저장해주세요.

{% include image.html file="tutorial/basic03_parameter_list.png" max-width="900" caption="Parameter 목록" %}

### Parameter를 이용하여 메시지 만들기
Entity와 Parameter를 이용하여 Chatflow를 만들어보겠습니다.

1) “피자주문” Intent 상세페이지에서 우측 상단에 ***연관 Chatflow***로 Step2에서 이미 만들었던 “피자주문하기” Chatflow가 연결되어 있는 것을 확인할 수 있습니다. “피자주문하기” Chatflow를 클릭하여 Chatflow 상세화면으로 이동해주세요.

{% include image.html file="tutorial/basic03_linked_chatflow.png" max-width="900" caption="연관 Chatflow" %}

2) Speak Node를 클릭하여 상세 페이지를 열어주세요.

3) 우측의 ***"Parameter 추가”*** 버튼을 클릭하면 Intent에서 설정했던 Entity가 조회됩니다. ***"피자메뉴”***를 클릭하여 Parameter를 추가해주세요.

{% include image.html file="tutorial/basic03_add_parameter.png" max-width="900" caption="Speak Node 내 Parameter 추가 레이어" %}

4) Parameter를 추가하면 Message 입력란에 ***"#{피자메뉴}”***가 입력된 것을 볼 수 있습니다. ***#{ParameterName}***은 Parameter를 지정하도록 약속된 특수기호이므로 알아두는 것이 좋습니다. 

5) ***"#{피자메뉴} 피자를 주문할게요”***와 같이 Parameter를 포함한 메시지를 작성하고 ***"확인”*** 버튼을 클릭한 후 Chatflow를 저장해주세요.

{% include image.html file="tutorial/basic03_parameter_message.png" max-width="900" caption="Parameter를 포함한 메시지 작성" %}

6) ***"Chatflow 저장"*** 버튼을 클릭한 후 우측의 테스트 패널에서 ***“치즈 피자 주문해줘”***를 입력해보세요. ***"치즈”***라는 단어를 사용하여 예문이나 메시지를 정의한 적이 없지만, 피자메뉴 Entity로 정의되어 있기 때문에 Parameter로 값을 받아 메시지로 보여주는 것을 확인할 수 있습니다. 

{% include image.html file="tutorial/basic03_test_parameter.png" max-width="900" caption="파라미터 테스트" %}


## 다음 Step에서는
“페퍼로니 피자 주문해줘”와 같이 피자메뉴를 정확히 입력한 경우에 대하여 Chatflow를 만들어보았습니다. 실제 피자를 주문할 때 구매자가 “피자 주문해줘”라고만 입력한다면 어떤 피자인지 메뉴를 알지 못해 주문을 해줄 수가 없습니다. 사용자가 입력한 말에서 필요한 정보를 모두 입력받지 못한 경우 다시 질문하여 답을 얻을 수 있는 Slot Node에 대하여 알아보겠습니다.

