---
title: API 노드 사용하기
keywords: API 노드 사용하기
tags: [API Node]
sidebar: tutorial_sidebar
permalink: basic_api_node.html
folder: tutorial
summary: API Node의 개념을 이해할 수 있습니다.
previous: {
    title: Split Node 사용하기,
    url: basic_split.html
}
next: {
    title: Function 노드 사용하기,
    url: basic_function_node.html
}
---

## API 를 활용하여 외부데이터 가져오기
단비에서 대화를 만들다 보면 외부에 있는 데이터를 가져와 대화에 넣어야 할 경우가 있습니다. <br/>
지금까지 만들었던 피자주문 시나리오를 예로들면 피자 가격을 피자 가격정보를 관리하던 기존 시스템에서 가져와 보여주는 것이 바람직 합니다. <br/>
단비의 Speak Node 나 Slot Node 에 피자가격을 직접 입력하여 사용하면 기존 시스템에서 가격이 변경 될 경우 가격을 여러번 수정해야하는 소요가 생깁니다. <br/>
또한 공공데이터 포탈과 같이 [Api](/external_API_management.html) 형태로 데이터를 제공하는 곳에서 데이터를 가져와 대화흐름에서 사용하고 싶을때도 있습니다. <br/>
이때 만들고 있는 대화로 외부의 데이터를 들고 오는 역할을 하는 것이 [Api Node](/chatflow_api.html) 입니다. <br/>
이번 Step에서는 [Api Node](/chatflow_api.html) 를 추가하여 외부의 데이터를 단비의 대화흐름으로 가져와 대화에서 보여 주는 방법을 알아 보겠습니다. <br/>

### API 만들기
#### API 등록하기
1) 좌측 사이드 메뉴에서 ***“API 관리”*** 눌러 해당 메뉴로 들어갑니다.
{% include callout.html content="화면 위치 : [API 관리]" type="default" %}

2) 현재 사용하고 있는 테넌트에서 만든 API 목록이 나타납니다. <br/>

{% include callout.html content="테넌트란 챗봇의 상위 범주입니다. 단비에 가입하고 계정을 만들면 자동으로 테넌트를 생성해 줍니다. <br/>
하나의 테넌트 안에서 여러개의 챗봇을 만들수 있습니다. <br/>
API 의 경우 개별 챗봇으로 관리하는 것이 아니고 개별 테넌트 단위로 관리합니다. <br/>
따라서 API는 한번 만들면 같은 테넌트내의 여러 챗봇에서 동일하게 가져와 사용할 수 있습니다." type="default" %}


3) 피자주문 튜토리얼에서는 피자가격을 가져올 API 를 생성해 보겠습니다. <br/>
우상단의 ***“API 등록”*** 버튼을 눌러 API 생성화면으로 들어갑니다. 

4) 화면의 진입 후 상단에 생성할 API 명을 입력합니다. 튜토리얼에서는 ***“피자주문하기_api_피자가격 가져오기”*** 를 입력하겠습니다.

5) ***“API 설명”***을 입력합니다.
튜토리얼에서는 ***“피자주문 튜토리얼에서 피자메뉴에 따른 피자가격을 가지고 오는 API 입니다.”*** 를 입력하겠습니다.

{% include image.html file="tutorial/using_api_node2.gif" max-width="900" caption="API 만들기1" %}

6) ***“API 메서드 / Request URL”*** 부분에 Request(호출) URL 을 입력합니다. 현재 만들고 있는 대화흐름에 외부정보를 갖다 줄 URL을 호출할 것입니다. <br/>
URL 호출방식은 GET 방식과 POST 방식 중에 선택할 수 있습니다. 튜토리얼에서는 GET 방식을 이용하도록 하겠습니다. <br/>

{% include warning.html content="호출하는 URL 이 GET 과 POST 중 어떤 방식을 지원하는지 꼭 확인하시기 바랍니다. " %}

예시로 입력하는 URL 은 튜토리얼에서 필요한 피자 가격을 들고 있는 시스템에서 제공하는 API 를 호출합니다. <br/>
***“https://channel.danbee.ai:3000/pizzaTutorial/getPrice”***

7) ***“Content Type”*** 부분에서는 외부 시스템과 정보를 주고 받을때 정보의 형태를 무엇으로 할지를 선택할 수 있습니다. <br/>
현재는 [JSON](https://www.json.org/json-ko.html) 형태를 지원하고 있습니다. 
{% include warning.html content="API 설정전에 정보를 주는 외부 시스템에서 JSON 형태로 정보를 던지는지 꼭 확인이 필요합니다." %}

8) ***“요청 Parameter”*** 부분에서는 외부 시스템 API 호출시 넘겨줘야할 파라미터를 정의합니다. <br/>
튜토리얼에서는 대화흐름에서 사용자가 선택한 피자메뉴를 외부시스템에 알려줘야 합니다. <br/>
외부시스템은 피자메뉴를 받아 해당하는 피자의 가격을 대화흐름에 넘겨 줄 것입니다. <br/>
q 라는 변수에 피자메뉴를 넘겨준다고 미리 정의 하였기 때문에 Name 부분에 q 를 입력합니다. 그리고 ***“실행”*** 버튼을 클릭합니다.. <br/>

9) 우하단의 ***“Response API Tree”*** 부분에 외부시스템에서 JSON 형태로 받아온 결과값이 트리형태로 나타납니다. <br/>
튜토리얼에서 호출한 API 의 경우 피자메뉴와 피자값을 넘겨주는 JSON 을 반환했습니다. <br/>
예시로 입력한 URL의 경우 parameter 에 특정 값이 들어가지 않아도 기본형태를 넘겨주기 때문에 결과값이 나타났습니다. <br/>

{% include warning.html content="호출하는 API 에 따라 기본값이 들어가야 결과값이 반환되는 경우가 있을 수 있습니다. <br/>
API 규격을 잘 보고 필요한 경우 Value 부분에 Name 에 해당하는 Value 를 기입하도록 합니다." %}

{% include image.html file="tutorial/using_api_node3.gif" max-width="900" caption="API 만들기2" %}

10) 예상한 결과값이 잘 나타난다면 외부시스템 정보를 들고올 준비가 되었습니다. <br/>
우상단의 ***“저장”*** 버튼을 눌러 저장합니다. 이제 생성한 API 를 대화흐름에서 어떻게 쓰는지 알아보도록 하겠습니다.


### API Node 만들기
#### API Node 를 Chatflow 창에서 설정하기
1) 좌측 사이드 메뉴에서 ***“대화흐름 목록 (Chatflow List)”*** 눌러 해당 메뉴로 들어갑니다.
{% include callout.html content="화면 위치 : [대화흐름 (Chatflow)] > 대화흐름 목록 (Chatflow List)]" type="default" %}

2) 계속해서 만들던 피자주문 시나리오에 API 를 적용해 보도록 하겠습니다.

3) Chatflow 상단의 Api Node 를 클릭하여 추가해 주세요.

4) Carausel Node 와 Split Node 사이에 Api Node를 위치 시키고 앞뒤 노드와 연결해 주세요. <br/>
기존에 연결된 선의 경우 마우스로 선을 클릭하고 선이 붉은색으로 하이라이트된 후 키보드의 delete 키를 누르면 삭제됩니다. <br/>
기왕이면 알아보기 쉽도록 ***“외부에서 피자가격 가져오기”*** 와 같은 노드명을 부여하면 좋겠죠? <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Node명 수정하기](/basic_listen_speak.html#node-%EB%AA%85-%EC%88%98%EC%A0%95)</span>

{% include image.html file="tutorial/using_api_node6.gif" max-width="900" caption="API Node 생성하기1" %}

#### API Node 상세정보 설정하기(요청 Parameter)
1) Api Node를 더블 클릭하여 상세화면으로 이동해주세요. 상세화면의 ***“API 설정”*** 탭이 열립니다. 

2) ***“사용 API”*** 부분에 ***“선택하세요”*** 를 누르면 현재 테넌트에서 사용 가능한 API 목록이 하단에 펼쳐집니다. <br/>
앞에서 만들었던 ***“피자주문하기_api_피자가격 가져오기”*** 가 보일것 입니다. 

3) ***“피자주문하기_api_피자가격 가져오기”*** 를 선택해 주세요. 선택 후 적용을 누르면 앞에서 설정한 내역을 불러 옵니다.

{% include image.html file="tutorial/using_api_node4.gif" max-width="900" caption="API Node 생성하기2" %}

4) 불러온 부분의 ***“요청 Parameter”*** 탭의 ***“요청 Parameter”*** 부분에 요청시 보낼 Parameter 를 설정합니다. <br/>
외부시스템은 대화흐름에서 사용자가 선택한 #{피자메뉴} 변수를 받아 해당 메뉴에 해당하는 가격을 보내 줄 것입니다. <br/>
앞서서 q 라는 변수에 피자메뉴를 넘겨주기로 약속했기 때문에 사용자가 선택한 피자메뉴가 담겨있는 내부 변수 #{피자메뉴}를 q 에 입력 하도록 하겠습니다.


#### API Node 상세정보 설정하기(출력 Parameters)
1) 외부시스템에서 받아온 값을 대화흐름에서 사용하기 위해서는 외부시스템에서 받은 결과를 대화흐름 내부의 변수에 Mapping 시켜줘야 합니다. <br/>
이 작업 진행을 위해  ***“출력 Parameters”*** 탭으로 이동합니다. <br/>

2) ***“출력 Parameters”*** 섹션 우측의 + 버튼을 누르면 대화흐름 내부에서 정의한 변수들이 나타납니다. <br/>
피자가격을 받아오기 위해 대화흐름 내부에서 정의한 피자가격 변수를 선택합니다. 피자가격 변수가 보이지 않을 경우 <br/>
피자가격 변수를 만들어 주세요. 만드는 방법은 이전 챕터에서 설명한 내용을 보시기 바랍니다.
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Parameter 추가하기](/basic_entity_parameter.html#parameter-%EC%B6%94%EA%B0%80)</span>

3) ***“출력 Parameters”*** 섹션 하단에 피자가격 변수에 외부시스템 값을 설정할 박스가 나타납니다. <br/>
좌측 ***“Api Tree”*** 에 외부시스템에서 Price 변수에 가격 정보를 넣어줬기 때문에 Price 를 클릭한 상태로 드래그 하여 피자가격 박스 부분에서 클릭을 풀어줍니다. <br/>

4) API Node 생성을 완료하였습니다. 우 하단의 ***“확인”*** 버튼을 눌러 상세화면을 닫아 주세요. <br/>

{% include warning.html content="***“확인”*** 누르지 않으면 작업한 내용이 저장되지 않으니 꼭 ***“확인”*** 버튼을 통하여 창을 닫아야 합니다. <br/>
상세화면 닫은 후 우상단의 ***“Chatflow 저장”*** 버튼도 꼭 누르셔야 내용이 저장 됩니다." %}

{% include image.html file="tutorial/using_api_node5.gif" max-width="900" caption="API Node 생성하기3" %}

#### API Node 테스트
1) API Node 에서 외부에서 피자가격을 가져와 피자가격 변수에 값을 넣는 방법을 알아 보았습니다.<br/>
이제는 받아온 피자가격을 사용자에게 보여주기 위해 Speak Node 문구를 변경해 줍니다. 각각의 Speak 노드에 #{피자가격} 을 넣어 문구를 만들어 주세요. <br/>
다시한번 말씀드리지만 문구 수정 후 ***“확인”*** 버튼을 통해 상세창을 닫아주세요. 상세화면 닫은 후 우상단의 ***“Chatflow 저장”*** 버튼도 꼭 누르셔야 내용이 저장 됩니다. 

{% include image.html file="tutorial/using_api_node7.gif" max-width="900" caption="API Node test1" %}

2) 우측의 테스트 패널에서 테스트를 해보세요. “피자 주문해줘”라고 입력 후 피자메뉴 선택 하면 <br/>
Speak 노드에 #{피자가격} 을 넣어 만든 문구를 확인하실 수 있습니다.

{% include image.html file="tutorial/using_api_node_test.png" max-width="900" caption="API Node test2" %}

## 다음 Step 에서는 
지금까지 API 를 등록하고 API Node 를 설정하는 방법을 알아 보았습니다.<br/>
다음 Step 에서는 Function Node 를 활용하여 대화흐름 내부에서 사용하는 변수를 원하는대로 가공하는 방법을 알아보도록 하겠습니다.