---
title: 대화흐름 기본 설명 
tags: [chatflow, basic]
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

{% include callout.html content="화면 위치 : 챗봇 생성/변경 > 대화흐름" type="default" %}

사람과 사람간의 대화에는 이야기 흐름이 있습니다. 

처음에 인사를 하고 안부를 묻고 둘 사이의 관심사 등에 대해서 서로 이야기를 진행해 나가듯이 대화 과정에서 하나하나의 이야기 단위들이 (인사, 날씨문의, 취미 등) 모여 대화의 흐름을 구성하게 됩니다. 

여기에서 그 하나하나의 이야기 단위를 danbee.Ai 에서는 대화흐름 라는 이야기 단위로 명명을 하고 있습니다. 
대화할 때에는 상대방의 이야기를 듣고 대답하는 것이 기본일 것입니다. 대화흐름에서도 챗봇이 사람과 대화하는데 있어서 말귀를 알아 듣고 (Listen 노드) 대답 (Speak 노드) 하는 기본 방식으로 구성이 되어 있습니다. 

대화 과정에서 확인해야 할 사항이 있다면 되묻는 질문을 할 수 도 있겠고, 상대방의 답변에 대해 논리적으로 판단하여 대화의 흐름을 달리 이야기해야 할 경우도 있을 것입니다. 
대화흐름은 이러한 대화 과정에서 필요한 기본적인 듣고, 말하고, 판단하고 정보를 활용하는 기본적인 대화 노드들의 조합으로 대화의 흐름을 구성할 수 있는 역할을 담당하고 있습니다. 
다음 내용에서는 대화흐름에서 사용되고 있는 각각의 대화 노드들에 대해 자세히 알아보겠습니다

## 대화흐름 생성

대화흐름 목록 메뉴 우측 상단에 있는 [대화흐름 생성] 버튼을 눌러 호출된 팝업에서 대화흐름 제목을 입력하면 신규 대화흐름이 생성됩니다.

{% include image.html file="chatflow/Chatflow_create.png"  caption="대화흐름 생성" %}

### 대화노드 추가

대화흐름 캔버스 화면 상단에 있는 노드를 클릭하여 Canvas에 필요한 Node들을 추가할 수 있습니다. 
대화흐름의 대화 노드 종류에는 크게 8가지가 있습니다.

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
{: .table .table-striped}

{% include image.html file="chatflow/Chatflow_design.png"  caption="대화흐름 canvas" %}

### 이벤트 플로우

이벤트 플로우란 대화의도에서 시작되는 흐름이 아닌, 특정 조건에서 시작되는 흐름을 이야기합니다. 이벤트 플로우는 이벤트 URL과 이벤트명을 가지며 스크립트를 통해 직접 호출해야합니다.

{% include image.html file="chatflow/Chatflow_event.png"  caption="이벤트 플로우로 설정" %}

## 대화흐름 기본 조작

### 노드 선택
노드는 클릭 또는 드래그로 선택할 수 있습니다. 
{% include image.html file="chatflow/Chatflow_select.png"  caption="노드 선택" %}

### 노드 연결
노드의 연결점을 클릭, 드래그하는 방식으로 노드들을 연결할 수 있습니다.
{% include image.html file="chatflow/Chatflow_node_line.png"  caption="노드 연결" %}

### 노드 삭제
대화흐름 캔버스 상에 있는 Node와 연결 선은 선택한 후에 delete키를 눌러 삭제할 수 있습니다. (Mac에서는 fn + delete)
{% include image.html file="chatflow/Chatflow_node_delete.png"  caption="노드 삭제" %}

## 노드 개별 수정
모든 노드는 더블클릭하면 상세 화면을 열 수 있습니다. 

### 노드 반영 확인/취소
모든 노드에는 이름과 설명을 수정할 수 있습니다.
노드를 수정한 뒤에는 반영 확인을 눌러 수정을 확정하거나, 취소버튼을 눌러 수정내용을 되돌릴 수 있습니다.

{% include image.html file="chatflow/Chatflow_speak_basic.png"  caption="노드 정보 입력란과 반영 확인/취소 버튼" %}

### 이미지 추가
메세지를 출력하는 노드에는 이미지를 추가할 수 있습니다. 이미지 url 연결 옵션을 선택하면 이미지가 있는 인터넷상의 URL을 활용하여 이미지를 올릴 수 있습니다. 확장자(jpg, png, gif)가 있는 URL을 적용해야 정상적으로 출력됩니다. 이미지 파일을 직접 업로드 할때는 1MB 파일크기 제한이 있습니다.

{% include tip.html content="[imgur.com](https://imgur.com/){:target='_blank'}나 [giphy.com](https://giphy.com/){:target='_blank'}과 같은 간단 이미지 공유사이트를 활용하면 편리합니다. " %}

{% include image.html file="chatflow/chatflow_common_image.png"  caption="노드에 이미지 추가" %}


### 파라미터 활용
노드는 단순히 입력된 메시지만 출력할 뿐만 아니라, 사용자로부터 입력받은 파라미터 정보들을 활용하여 메시지를 표시할 수 있습니다. 
#{파라미터명} 형태로 메세지를 작성하면 실제 대화 채널에는 해당 파라미터에 설정되어 있는 값이 치환되어 표시됩니다. 

{% include image.html file="chatflow/Chatflow_speak_parameter.png"  caption="파라미터 활용 사례" %}

>##### 시스템 파라미터
대화 흐름을 설계하다 보면 챗봇명을 표시해야할 경우도 있고, 사용자가 한 말에 대한 패턴 및 채널별로 달리 처리해 주어야 하는 경우도 있을 것입니다. 
Danbee.Ai에서는 그러한 처리를 위해 몇가지 시스템 변수를 아래와 같이 제공합니다. ( 예 : #{@message} )

>| 시스템 파라미터 | 표기 | 설명 | 
|--------|-------|-------|
| 사용자 식별정보 | @userId | 사용자ID가 표시됩니다. (ex: email ) |
| 챗봇명 | @chatbotName | 챗봇 생성시 명명했던 이름이 표시됩니다.  |
| 채널아이디 | @channelId | 접속한 채널 아이디가 표시됩니다. <br/>(ex : 5-facebook / 3-kakaotalk / 2-line / 7-navertalk / 6-telegram / 4-slack)  |
| 받은 메시지 | @message | 사용자로부터 받은 질문 메시지 입니다. |
| 현재년도 | @currentDateYYYY | 현재년도 정보입니다. (예:2019) |
| 현재월 | @currentDateMM | 현재월 정보입니다. (예:12) |
| 현재일 | @currentDateDD | 현재일 정보입니다. (예:31) |
| 현재년월 | @currentDateYYYYMM | 현재년월 정보입니다. (예:201912) |
| 현재년월일 | @currentDateYYYYMMDD | 현재년월일 정보입니다. (예:20191231) |
| 현재시간 | @currentTimeHH | 현재시간 정보입니다. (예:23) |
| 현재분 | @currentTimeMI | 현재분 정보입니다. (예:59) |
| 현재초 | @currentTimeSS | 현재초 정보입니다. (예:59) |
| 현재요일 | @currentDateWeek | 현재요일 정보입니다. (예: 1:일, 2:월, 3:화, 4:수, 5:목, 6:금, 7:토) |
{: .table .table-striped}

>##### 일반 파라미터
등록된 파라미터들의 값은 메시지나 조건절 경우에 따라 활용하실 수 있습니다. 
직접 #{파라미터명} 식으로 입력할 수도 있겠지만, 편의성 차원에서 아래와 같이 파라미터를 추가하실 수 있습니다.
팝업에서 파라미터 선택시 해당 파라미터는 #{파라미터명} 식으로 메시지에 추가됩니다.
>{% include image.html file="chatflow/Chatflow_parameter_add.png"  caption="일반 변수 추가" %}


### 버튼 추가
메세지를 출력하는 노드는 **+ 버튼 추가**를 클릭해 버튼을 추가할 수 있습니다. 버튼은 단순 대답부터 전화연결, 다른 대화흐름으로 연결까지 다양한 기능을 지원하고 있습니다.


>##### 버튼(선택지) 설정
Speak 노드는 답변 메시지와 함께 사용자에게 다음 버튼을 제공함으로써 사용자 편의성을 제공할 수 있습니다.
버튼은 일부 '단비' 엔진에서 처리하는 버튼과 채널(Web, 스마트폰, IoT디바이스)에서 옵션정보를 활용하여 처리해야하는 항목들로 구성되어 있고
그 항목들은 다음과 같습니다. 

>| 버튼 | 설명 | 
|--------|-------|
| 선택지 | 버튼 형태 선택지를 제공합니다. |
| 웹 링크 | 팝업으로 호출할 Link 정보를 제공합니다. |
| 내부 App실행 | 스마트폰에서 내부 App을 실행합니다.  |
| 외부 App실행 | 스마트폰에서 외부 App을 실행합니다.  |
| 전화걸기 | 스마트폰에서 전화걸기로 연결합니다. |
| [대화흐름호출](chatflow_speak.html#chatflow-호출-파라미터-연결) | 다른 대화흐름을 호출합니다. 이때 현재 대화흐름의 파라미터를 넘겨줄 수 있습니다. |
| 퀵 리플라이 | 입력창 상단에 버튼 형태의 선택지를 제공합니다. |
| 액션 | 버튼을 누르면 챗봇이 별도의 설정된 함수를 실행합니다 |
{: .table .table-striped}

>{% include note.html content="퀵 리플라이 타입은 facebook, 네이버톡톡에서 해당 형태로 이용 가능하며 제공되지 않는 채널에서는 선택지와 동일하게 표시됩니다." %}




>##### 대화흐름 호출 파라미터 연결
대화흐름 호출 버튼을 눌렀을때 각 대화흐름에서 사용되는 파라미터들끼리 연결이 가능합니다. 버튼형 [Jump 노드](chatflow_jump.html) 기능으로 볼 수 있습니다.


>예를 들어 날씨를 물은 뒤 사용자가 버튼을 클릭하면 날씨에 따라 음식을 추천한다고 가정해보겠습니다.

>{% include image.html file="chatflow/Chatflow_callflow_param_01.png"  caption="대화흐름 호출 파라미터 연결" %}

>위와 같이 Speak 메세지를 설정하고 대화흐름 호출 버튼을 추가합니다. 호출할 대화흐름을 선택하면 [파라미터 연결] 버튼이 활성화 됩니다.


>파라미터 연결 버튼을 클릭하면 호출할 대화흐름과 현재 대화흐름의 파라미터 값을 연결할 수 있는 창이 뜹니다. 예시와 같이 *'tempo'*라는 파라미터를 연결하고 테스트패널에서 테스트 해보면 다음과 같은 결과를 확인할 수 있습니다.

>{% include image.html file="chatflow/Chatflow_callflow_param_03.png"  caption="대화흐름 호출 파라미터 연결 테스트" %}

>[디버그 모드](demo_n_test_panel.html#디버그-모드)에서 기존 날씨 대화흐름에서 세팅되었던 tempo의 '폭우'라는 값이 야식 대화흐름의 파라미터로 넘어갔음을 확인할 수 있습니다.



## 대화흐름 저장

대화흐름 설계하고 나서 [대화흐름 저장] 버튼을 클릭을 하면 해당 내용이 서버에 반영됩니다. 
대화흐름은 서버에 반영되고 나서야 Tester 혹은 시뮬레이션(Simulation) 에서 테스트해 볼 수 있습니다.

{% include image.html file="chatflow/Chatflow_save.png"  caption="대화흐름 저장" %}

{% include warning.html content="대화흐름 저장을 하지 않고 다른 화면으로 이동하면 입력되었던 작업은 사라지게 되니 유의하시기 바랍니다. " %}


## 대화흐름 테스트 패널

테스트 패널은 설계한 대화흐름이 정상적으로 흐름을 진행하는지 사전에 테스트할 수 있는 기능을 제공합니다.

{% include image.html file="chatflow/Chatflow_tester_layout.png"  caption="대화흐름 Tester 영역" %}


테스트 예문을 입력하고 그에 따른 답변과 현재 진행되고 있는 상태 정보를 확인 할 수 있습니다.
사용자 선택에 따라 일반 모드, 디버그 모드로 테스트 패널을 사용하실 수 있습니다.

- [일반 모드] : 챗봇과의 메시지를 주고 받는 상황을 일반 채팅창처럼 보여줍니다.
- [디버그 모드] : 메시지 뿐만 아니라 내부적으로 처리되는 데이터 처리 내용까지 확인이 가능합니다. 
- [파라미터 팝업] : 특정 노드에서의 처리된 파라미터 내역 확인이 가능합니다. (? 표시 클릭)

{% include image.html file="chatflow/Chatflow_tester_module_set.png"  caption="테스트 패널" %}



테스트 패널에서는 여러 대화흐름을 테스트해 볼 수 있습니다. 만약 지금 진행 중인 대화흐름을 확인하고 싶다면 패널 아래 부분의 '대화흐름 상세' 버튼을 선택하시면 됩니다. 
그러면 원하시는 챗플로우가 대화흐름 canvas에 펼쳐지게 됩니다. 

{% include image.html file="chatflow/Chatflow_tester_link.png"  caption="대화흐름 상세 링크" %}


## 용어 설명

| 용어 | 용어 설명 | 
|-------------------------|------------------------|
| 대화세션 | '대화세션아이디'의 줄임말으로 대화를 시작해서 끝날 때까지의 대화를 식별하기 위한 단위 개념입니다. |
| 인스턴스 | 'ChatflowInstance'의 줄임말로 '대화흐름' 단위로 이야기를 진행할때 인스턴스 단위로 발급되는 식별 단위 입니다. |
| 노드 | 듣고, 말하고, 판단하고, 되묻고 하는 등, 대화 흐름을 이어가는데 필요한 기본 기능 단위 입니다. |
| 파라미터 | 대화흐름 내 흐름 과정에서 사용되는 변수들을 일컫는 것으로 Slot, Carousel에서 답변 정보를 저장하는 용도로 주로 사용합니다.  |
| 의도추론 | 현재 대화에 대해 NLU가 파악한 의도 정보를 나타냅니다. |
{: .table .table-striped}



## 샘플 시나리오 (튜토리얼봇)

단비.AI는 이해를 돕기 위한 다양한 샘플과 튜토리얼을 준비해놓고 있습니다. [튜토리얼 확인하기]()


<!-- 
대화노드를 설명하는데 있어 "야식 주문" 시나리오 샘플로 대화흐름 노드를 배치해 보겠습니다.
먼저 Listen Node를 통해 "야식배달"이라는 의도를 파악(Listen 노드)하고 Slot Node를 통해서 주문할 야식의 종류를 되묻고(Slot 노드) 입력된 답변에 따라서 질문이 분기(Split 노드)된 후 치킨의 종류 혹은 피자사이즈를 되물은(Slot 노드) 뒤 종류나 사이즈에 따라 확인 답변(Speak 노드)을 하는 흐름으로 구성되어 있습니다.

대화노드를 설명하는데 있어 "야식 주문" 시나리오 샘플로 대화흐름 노드를 배치해 보겠습니다.
먼저 Listen 노드를 통해 "야식배달"이라는 의도를 파악(Listen 노드)하고 Slot 노드를 통해서 주문할 야식의 종류를 되묻고(Slot 노드) 입력된 답변에 따라서 질문이 분기(Split 노드)된 후 치킨의 종류 혹은 피자사이즈를 되물은(Slot 노드) 뒤 종류나 사이즈에 따라 확인 답변(Speak 노드)을 하는 흐름으로 구성되어 있습니다.


{% include image.html file="chatflow/Chatflow_sample.png"  caption="샘플 시나리오(야식주문)" %}


#### [야식 주문] Listen 설정 화면

야식 주문에 사용할 파라미터들을 설정 합니다. 

- [야식 종류] : type
- [피자 크기] : size
- [양념,후라이드] : cook_type

{% include image.html file="chatflow/Chatflow_sample_listen.png"  caption="'야식주문' 설정 화면" %}


#### [야식종류] Slot 설정 화면

피자와 치킨 중에 어떤 야식을 선택할 것인지 묻는 질문과 파라미터를 설정합니다. 

{% include image.html file="chatflow/Chatflow_sample_slot1.png"  caption="'야식종류' 설정 화면" %}


#### [피자, 치킨?] Split 설정 화면

야식 종류 기준으로 피자주문 대화 흐름을 진행할 것인지, 치킨 주문 대화 흐름을 진행할 것인지 판단합니다. 

{% include image.html file="chatflow/Chatflow_sample_split.png"  caption="'피자, 치킨?' 설정 화면" %}


#### [피자 사이즈는?] Slot 설정 화면

피자 크기를 묻는 질문과 파라미터를 설정합니다. 

{% include image.html file="chatflow/Chatflow_sample_slot_pizza.png"  caption="'피자 사이즈는?' 설정 화면" %}


#### [양념/후라이드?] Slot 설정 화면

양념, 후라이드 선택을 묻는 질문과 파라미터를 설정합니다. 

{% include image.html file="chatflow/Chatflow_sample_slot_chicken.png"  caption="'양념/후라이드?' 설정 화면" %}


#### [역시 피자는~] Speak 설정 화면

선택한 피자와 크기에 대한 답변을 조건별로 설정합니다. 

{% include image.html file="chatflow/Chatflow_sample_speak_pizza.png"  caption="'역시 피자는~' 설정 화면" %}


#### [역시 피자는~] Speak 설정 화면

선택한 치킨에 대한 답변을 조건별로 설정합니다. 

{% include image.html file="chatflow/Chatflow_sample_speak_chicken.png"  caption="'역시 피자는~' 설정 화면" %}


야식주문 시나리오는 '야식 먹고 싶다'라는 이야기에 챗봇이 야식 종류(치킨, 피자)와 그에 따른 선택지(치킨종류, 피자크기)를 묻는 대화가 진행됩니다.

{% include image.html file="chatflow/Chatflow_sample_test.png"  caption="야식주문 치킨 선택 결과" %}

{% include image.html file="chatflow/Chatflow_sample_test2.png"  caption="야식주문 피자 선택 결과" %}
  -->

{% include bottom.html %}
