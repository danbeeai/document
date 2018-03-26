---
title: 대화흐름 기본 설명
tags: [chatflow]
keywords: Basic Conversation
summary: 대화흐름의 기본적인 개념을 이해합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow.html
folder: danbeeDoc
previous: {
    title: 엔티티 관리, 
    url: entity.html
}
next: {
    title: Listen 노드,
    url: chatflow_listen.html
}
---

## 대화흐름 기본 설명

사람과 사람간의 대화에는 이야기 흐름이 있습니다. 

처음에 인사를 하고 안부를 묻고 둘 사이의 관심사 등에 대해서 서로 이야기를 진행해 나가듯이 대화 과정에서 하나하나의 이야기 단위들이 (인사, 날씨문의, 취미 등) 모여 대화의 흐름을 구성하게 됩니다. 

여기에서 그 하나하나의 이야기 단위를 danbee.Ai 에서는 Chatflow 라는 이야기 단위로 명명을 하고 있습니다. 
대화할 때에는 상대방의 이야기를 듣고 대답하는 것이 기본일 것입니다. Chatflow에서도 챗봇이 사람과 대화하는데 있어서 말귀를 알아 듣고 (Listen 노드) 대답 (Speak 노드) 하는 기본 방식으로 구성이 되어 있습니다. 

대화 과정에서 확인해야 할 사항이 있다면 되묻는 질문을 할 수 도 있겠고, 상대방의 답변에 대해 논리적으로 판단하여 대화의 흐름을 달리 이야기해야 할 경우도 있을 것입니다. 
Chatflow는 이러한 대화 과정에서 필요한 기본적인 듣고, 말하고, 판단하고 정보를 활용하는 기본적인 대화 노드들의 조합으로 대화의 흐름을 구성할 수 있는 역할을 담당하고 있습니다. 
다음 내용에서는 Chatflow에서 사용되고 있는 각각의 대화 노드들에 대해 자세히 알아보겠습니다




### Chatflow list

관리되고 있는 Chatflow 목록을 확인할 수 있습니다.


{% include callout.html content="화면 위치 : [대화흐름(Chatflow)] > [대화흐름 목록(Chatflow List)]" type="default" %}


{% include image.html file="chatflow/Chatflow_list.png" max-width="900" caption="Chatflow list" %}


### Chatflow 테스트 패널

Chatflow Tester는 설계한 Chatflow 정상적으로 흐름을 진행하는지 사전에 테스트할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_tester_layout.png" max-width="900" caption="Chatflow Tester 영역" %}


테스트 예문을 입력하고 그에 따른 답변과 현재 진행되고 있는 상태 정보를 확인 할 수 있습니다.
사용자 선택에 따라 일반 모드, 디버그 모드로 테스트 패널을 사용하실 수 있습니다.

- [일반 모드] : 챗봇과의 메시지를 주고 받는 상황을 일반 채팅창처럼 보여줍니다.
- [디버그 모드] : 메시지 뿐만 아니라 내부적으로 처리되는 데이터 처리 내용까지 확인이 가능합니다. 
- [파라미터 팝업] : 특정 노드에서의 처리된 파라미터 내역 확인이 가능합니다. (? 표시 클릭)

{% include image.html file="chatflow/Chatflow_tester_module_set.png" max-width="900" caption="Chatflow Tester" %}



테스트 패널에서는 여러 Chatflow를 테스트해 볼 수 있습니다. 만약 지금 진행 중인 Chatflow를 확인하고 싶다면 패널 아래 부분의 'Chatflow 상세' 버튼을 선택하시면 됩니다. 
그러면 원하시는 챗플로우가 Chatflow canvas에 펼쳐지게 됩니다. 

{% include image.html file="chatflow/Chatflow_tester_link.png" max-width="900" caption="Chatflow 상세 링크" %}


#### 용어 설명

| 용어 | 용어 설명 | 
|-------------------------|------------------------|
| 대화세션 | '대화세션아이디'의 줄임말으로 대화를 시작해서 끝날 때까지의 대화를 식별하기 위한 단위 개념입니다. |
| 인스턴스 | 'ChatflowInstance'의 줄임말로 'Chatflow' 단위로 이야기를 진행할때 인스턴스 단위로 발급되는 식별 단위 입니다. |
| 노드 | 듣고, 말하고, 판단하고, 되묻고 하는 등, 대화 흐름을 이어가는데 필요한 기본 기능 단위 입니다. |
| 파라미터 | Chatflow 내 흐름 과정에서 사용되는 변수들을 일컫는 것으로 Slot, Carousel에서 답변 정보를 저장하는 용도로 주로 사용합니다.  |
| 의도추론 | 현재 대화에 대해 NLU가 파악한 의도 정보를 나타냅니다. |



### Chatflow 생성


Chatflow 목록 메뉴 우측 상단에 있는 [Chatflow 생성] 버튼을 눌러 호출된 팝업에서 Chatflow 제목을 입력하면 신규 Chatflow가 생성됩니다.

{% include image.html file="chatflow/Chatflow_create.png" max-width="900" caption="Create chatflow" %}


### 대화노드 추가

Chatflow 캔버스 화면 상단에 있는 Node를 클릭하여 Canvas에 필요한 Node들을 추가할 수 있습니다. 

Chatflow의 대화 노드 종류에는 크게 8가지가 있습니다.

| 대화노드 | 설명 | 
|--------|-------|
| [Listen 노드](chatflow_listen.html#Listen 노드) | 사용자의 의도가 무엇인지 가장 먼저 파악하고 대화의 흐름을 시작하는 노드입니다. |
| [Speak 노드](chatflow_speak.html#Speak 노드) | 챗봇의 답변 메시지를 설정하는 노드입니다. |
| [Slot 노드](chatflow_slot.html#Slot 노드) | 대화 과정에서 필요한 정보를 얻기 위해 되묻는 질문을 설정하는 노드입니다. |
| [Split 노드](chatflow_split.html#Split 노드) | 대화 흐름을 분기하기 위해 정보를 설정하는 노드입니다. |
| [Carousel 노드](chatflow_carousel.html#Corousel 노드) | 사용자에게 카드 형태로 선택지를 제시하는 노드입니다. |
| [Api 노드](chatflow_api.html#API 노드) | 다른 컨텐츠 서비스와 연계하여 정보를 얻기 위한 노드입니다. |
| [Function 노드](chatflow_function.html#Function 노드) | 파라미터 정보를 가공 처리할 경우 사용하는 노드입니다. |
| [Jump 노드](chatflow_jump.html#Jump 노드) | 대화 흐름상 다른 챗플로우로 이동하고자 할 경우 사용하는 노드입니다. |


{% include image.html file="chatflow/Chatflow_design.png" max-width="900" caption="Chatflow canvas" %}

### 대화노드 삭제

Chatflow 캔버스 상에 있는 Node와 연결 선은 선택한 후에 delete키를 눌러 삭제할 수 있습니다. (Mac에서는 fn + delete)

{% include image.html file="chatflow/Chatflow_node_delete.png" max-width="900" caption="Create chatflow" %}


### Chatflow 저장

Chatflow 설계하고 나서 [Chatflow 저장] 버튼을 클릭을 하면 해당 내용이 서버에 반영됩니다. 
Chatflow는 서버에 반영되고 나서야 Tester 혹은 시뮬레이션(Simulation) 에서 테스트해 볼 수 있습니다.

{% include image.html file="chatflow/Chatflow_save.png" max-width="900" caption="Chatflow 저장" %}




{% include warning.html content="Chatflow 저장을 하지 않고 다른 화면으로 이동하면 입력되었던 작업은 사라지게 되니 유의하시기 바랍니다. " %}

### 샘플 시나리오 (야식주문)

대화노드를 설명하는데 있어 "야식 주문" 시나리오 샘플로 Chatflow 노드를 배치해 보겠습니다.
먼저 Listen Node를 통해 "야식배달"이라는 의도를 파악(Listen 노드)하고 Slot Node를 통해서 주문할 야식의 종류를 되묻고(Slot 노드) 입력된 답변에 따라서 질문이 분기(Split 노드)된 후 치킨의 종류 혹은 피자사이즈를 되물은(Slot 노드) 뒤 종류나 사이즈에 따라 확인 답변(Speak 노드)을 하는 흐름으로 구성되어 있습니다.

{% include image.html file="chatflow/Chatflow_sample.png" max-width="900" caption="샘플 시나리오(야식주문)" %}

야식주문 시나리오는 '야식 먹고 싶다'라는 이야기에 챗봇이 야식 종류(치킨, 피자)와 그에 따른 선택지(치킨종류, 피자크기)를 묻는 대화가 진행됩니다.

{% include image.html file="chatflow/Chatflow_sample_test.png" max-width="900" caption="야식주문 치킨 선택 결과" %}

{% include image.html file="chatflow/Chatflow_sample_test2.png" max-width="900" caption="야식주문 피자 선택 결과" %}
 
