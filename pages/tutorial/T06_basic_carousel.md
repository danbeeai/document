---
title: Carousel 노드 사용하기 
tags: [tutorial, chatflow, basic]
keywords: Tutorial
summary: Carousel 노드의 개념을 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_carousel.html
folder: tutorial
previous: {
    title: Slot 노드 사용하기, 
    url: basic_slot.html
}
next: {
    title: Split 노드 사용하기,
    url: basic_split.html
}
---

## Carousel 노드를 사용하여 카드 형태 선택지 만들기

사용자에게 버튼 형태의 선택지를 줄 때 이미지나 부가적인 설명이 필요한 경우 Carousel 노드를 활용하면 좋습니다. Speak 노드나 Slot 노드를 대체하여 Carousel 노드를 적절하게 사용하면 텍스트로 대화했을 때 발생하는 한계를 보완할 수 있습니다. (***단, Carousel 노드는 Facebook, LINE, 카카오톡에서 지원되는 범위가 다릅니다.*** 챗봇과 연결할 메신저에 따라 기능 지원 여부를 꼭 확인하고 사용해야 합니다.) 
  
이번 Step에서는 Slot 노드 대신 Carousel 노드를 사용하여 ***“피자메뉴”*** 정보가 들어왔는지 파라미터를 체크하고, 이미지가 포함된 질문 메시지를 만드는 것을 배워보겠습니다.

### Carousel 노드
Carousel 노드는 버튼을 이미지나 텍스트와 함께 좌우로 넘기는 형태로 제공하는 노드입니다. 따라서 버튼을 포함하는 Speak 노드나 Slot 노드처럼 사용할 수 있는데, 이 두 노드의 큰 차이점은 파라미터 값 체크 유무에 있습니다. 앞에서 배운 Slot 노드처럼 어떤 피자를 먹을지 물어보기 위해서는 “피자메뉴” 파라미터가 필요하므로 파라미터를 설정하는 옵션을 사용하여 Carousel 노드를 만들어보겠습니다.

### Carousel 노드 생성
1) 먼저 "피자주문하기" 대화흐름 상세 페이지에서 기존에 만들었던 Slot 노드를 클릭한 후 [Delete] 키를 눌러 삭제해 주세요.

2) 상단의 Carousel 노드를 클릭하여 추가한 후 ***Listen 노드 > Caraousel 노드 > Speak 노드*** 순으로 선을 연결해주세요.

{% include image.html file="tutorial/basic05_create_carousel.png"  caption="Carousel 노드 추가된 상태" %}

3) Carousel 노드를 더블 클릭하여 상세 페이지로 이동해주세요.

### 질문 Message 설정
***"질문 메시지 설정"*** 항목을 체크하여 ***”어떤 피자를 주문할까요?”*** 메시지를 추가해주세요. 질문 메시지는 아래의 카드 메시지가 나가기 전에 먼저 보여집니다.

{% include image.html file="tutorial/basic05_carousel_question.png"  caption="질문 메시지 추가" %}

### 선택 답변받기
Slot 노드와 같은 역할을 하기 위해서는 파라미터가 필요합니다. 응답저장하기를 활성화하면 파라미터 Select Box가 나타납니다.<br>
***”피자메뉴”*** 파라미터를 선택해주세요. 

{% include image.html file="tutorial/basic05_add_parameter.png"  caption="선택 답변받기" %}

### 이미지 첨부하기
이미지를 업로드하거나 URL을 등록해 연결할 수 있습니다. 아래의 샘플이미지 URL을 복사하여 이미지를 첨부해주세요. <br> 

>##### 샘플이미지 URL :<br>
http://doc.danbee.ai/images/tutorial/pizza_001.png<br>
http://doc.danbee.ai/images/tutorial/pizza_002.png<br>
http://doc.danbee.ai/images/tutorial/pizza_003.png<br>

### 버튼 및 설명 추가하기
이미지 외에 Title, Sub Title, 버튼 등을 추가할 수 있습니다. 피자 토핑에 대한 설명과 메뉴를 선택할 수 있는 버튼을 추가해보겠습니다.

1) Sub Title에 ***“토핑 정보 : 페퍼로니, 모짜렐라 치즈”***를 입력해 주세요. Sub Title은 이미지 아래에 노출됩니다. 선택지의 버튼명과 파라미터 값으로 ***“페퍼로니”***를 입력해 주세요.  

2) ***”카드추가”*** 버튼을 클릭하면 오른쪽으로 카드가 하나씩 추가됩니다. 같은 방법으로 쉬림프와 치즈 메뉴를 추가해주세요.

3) 우측 하단의 ***”확인”*** 버튼을 클릭하여 Carousel 노드 설정 화면을 닫아주세요.

### Carousel 노드 테스트
좌측 하단의 ***“변경내용 저장”***버튼을 클릭한 후 우측의 테스트 패널에서 테스트를 해보세요. ***“피자 주문해줘”***라고 입력하면 Carousel 노드에서 만든 카드 메시지가 나타나고, 버튼을 클릭하면 Speak 노드에서 정의한 응답 메시지가 나타납니다.

{% include image.html file="tutorial/basic05_test_carousel2.gif"  caption="Carousel 노드 테스트" %}


## 다음 Step에서는
지금까지는 한 방향으로만 흘러가는 대화흐름을 만들어 보았습니다. 하지만 여러 상황에 따라 대화흐름이 바뀔 수도 있고, 응답 메시지를 여러 개로 정의하여 챗봇을 좀 더 완성도 있게 만들 수도 있습니다. 다음 Step에서는 조건에 따라 대화흐름을 바꾸어주는 Split 노드를 만들어 보겠습니다.




{% include bottom.html %}