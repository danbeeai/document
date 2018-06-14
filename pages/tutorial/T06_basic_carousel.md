---
title: Carousel Node 사용하기
tags: [tutorial, chatflow, basic]
keywords: Tutorial
summary: Carousel Node의 개념을 이해할 수 있습니다.
sidebar: tutorial_sidebar
permalink: basic_carousel.html
folder: tutorial
previous: {
    title: Slot Node 사용하기, 
    url: basic_slot.html
}
next: {
    title: Split Node 사용하기,
    url: basic_split.html
}
---

## Carousel Node를 사용하여 카드 형태 선택지 만들기
사용자에게 버튼 형태의 선택지를 줄 때 이미지나 부가적인 설명이 필요한 경우 Carousel Node를 활용하면 좋습니다. Speak Node나 Slot Node를 대체하여 Carousel Node를 적절하게 사용하면 텍스트로 대화했을 때 발생하는 한계를 보완할 수 있습니다. (***단, Carousel Node는 Facebook, LINE에서는 지원하지만 카카오톡에서는 지원하지 않습니다.*** 챗봇과 연결할 메신저에 따라 기능 지원 여부를 꼭 확인하고 사용해야 합니다.) 
  
이번 Step에서는 Slot Node 대신 Carousel Node를 사용하여 ***“피자메뉴”*** 정보가 들어왔는지 Parameter를 체크하고, 이미지가 포함된 질문 메시지를 만드는 것을 배워보겠습니다.

### Carousel Node
Carousel Node는 버튼을 이미지나 텍스트와 함께 좌우로 넘기는 형태로 제공하는 노드입니다. 따라서 버튼을 포함하는 Speak Node나 Slot Node처럼 사용할 수 있는데, 이 두 노드의 큰 차이점은 Parameter 값 체크 유무에 있습니다. 앞에서 배운 Slot Node처럼 어떤 피자를 먹을지 물어보기 위해서는 “피자메뉴” Parameter가 필요하므로 Parameter를 설정하는 옵션을 사용하여 Carousel Node를 만들어보겠습니다.

#### Carousel Node 생성
1) 먼저 "피자주문하기" Chatflow 상세 페이지에서 기존에 만들었던 Slot Node를 클릭한 후 [Delete] 키를 눌러 삭제해 주세요.

2) 상단의 Carousel Node를 클릭하여 추가한 후 ***Listen Node > Caraousel Node > Speak Node*** 순으로 선을 연결해주세요.

{% include image.html file="tutorial/basic05_create_carousel.png" max-width="900" caption="Carousel Node 추가된 상태" %}

3) Carousel Node를 더블 클릭하여 상세 페이지로 이동해주세요.

#### 질문 Message 설정
***"질문 메시지 설정"*** 항목을 체크하여 ***”어떤 피자를 주문할까요?”*** 메시지를 추가해주세요. 질문 메시지는 아래의 카드 메시지가 나가기 전에 먼저 보여집니다.

{% include image.html file="tutorial/basic05_carousel_question.png" max-width="900" caption="질문 메시지 추가" %}

#### 선택 답변받기
Slot Node와 같은 역할을 하기 위해서는 Parameter가 필요합니다. ***”선택 답변받기”***를 체크하면 Parameter Select Box가 나타납니다.<br>
***”피자메뉴”*** Parameter를 선택해주세요. 

{% include image.html file="tutorial/basic05_add_parameter.png" max-width="900" caption="선택 답변받기" %}

#### 이미지 URL 첨부하기
이미지는 URL 형태로 첨부만 가능하고, 컴퓨터에서 파일을 직접 업로드 하는 것은 지원하지 않습니다. 즉, 온라인상에 있는 무료 이미지를 사용하거나 네이버 블로그, Pinterest, GitHub와 같은 다른 서비스에 공개 형태로 이미지를 업로드한 후 URL를 복사해오는 방법으로 이미지를 첨부할 수 있습니다.

이미지 영역을 클릭한 후 아래의 샘플이미지 URL을 복사하여 이미지를 첨부해주세요.<br> 
샘플이미지 URL :<br>
 http://doc.danbee.ai/images/tutorial/pizza_001.png<br>
 http://doc.danbee.ai/images/tutorial/pizza_002.png<br>
 http://doc.danbee.ai/images/tutorial/pizza_003.png<br>

{% include image.html file="tutorial/basic05_add_image2.png" max-width="900" caption="이미지 URL 첨부" %}

#### 버튼 및 설명 추가하기
이미지 외에 Title, Sub Title, 버튼 등을 추가할 수 있습니다. 피자 토핑에 대한 설명과 메뉴를 선택할 수 있는 버튼을 추가해보겠습니다.

1) Sub Title에 ***“토핑 정보 : 페퍼로니, 모짜렐라 치즈”***를 입력해 주세요. Sub Title은 이미지 아래에 노출됩니다. 선택지의 버튼명과 Parameter 값으로 ***“페퍼로니”***를 입력해 주세요.  

{% include image.html file="tutorial/basic05_add_button2.png" max-width="900" caption="카드 내용 입력" %}

2) 왼쪽 하단의 ***”카드추가”*** 버튼을 클릭하면 오른쪽으로 카드가 하나씩 추가됩니다. 같은 방법으로 쉬림프와 치즈 메뉴를 추가해주세요.

{% include image.html file="tutorial/basic05_add_card2.png" max-width="900" caption="카드 추가" %}

3) 우측 하단의 ***”확인”*** 버튼을 클릭하여 Carousel Node 설정 화면을 닫아주세요.

#### Carousel Node 테스트
우측 상단의 ***“Chatflow 저장”***버튼을 클릭한 후 우측의 테스트 패널에서 테스트를 해보세요. ***“피자 주문해줘”***라고 입력하면 Carousel Node에서 만든 카드 메시지가 나타나고, 버튼을 클릭하면 Speak Node에서 정의한 응답 메시지가 나타납니다.

{% include image.html file="tutorial/basic05_test_carousel2.png" max-width="900" caption="Carousel Node 테스트" %}


## 다음 Step에서는
지금까지는 한 방향으로만 흘러가는 Chatflow를 만들어 보았습니다. 하지만 여러 상황에 따라 대화흐름이 바뀔 수도 있고, 응답 메시지를 여러 개로 정의하여 챗봇을 좀 더 완성도 있게 만들 수도 있습니다. 다음 Step에서는 조건에 따라 대화흐름을 바꾸어주는 Split Node를 만들어 보겠습니다.
