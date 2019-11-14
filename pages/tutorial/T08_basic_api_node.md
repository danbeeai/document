---
title: API 노드 사용하기 
keywords: API 노드 사용하기
tags: [tutorial, chatflow, API, advanced]
sidebar: tutorial_sidebar
permalink: basic_api_node.html
folder: tutorial
summary: API 노드의 개념을 이해할 수 있습니다.
previous: {
    title: Split 노드 사용하기,
    url: basic_split.html
}
next: {
    title: Function 노드 사용하기,
    url: basic_function_node.html
}
---

## API 를 활용하여 외부데이터 가져오기
실제 주문을 시스템에 전달하거나 피자의 가격을 표시하기 위해서는 외부 시스템과 연동하는 것이 필요합니다. 
물론, Speak 노드에 가격을 입력해두어도 데모버전에서는 충분합니다. 그러나 가격이 바뀔 때마다 Speak 노드의 메시지를 변경해야 한다면 서비스 운영이 어렵겠죠. 디지털 서비스간 정보를 주고받는 방식으로 가장 많이 사용되는 기술은 API(Application Programing Interface)입니다.

이번 Step에서는 [Api 노드](/chatflow_api.html)를 통해 외부의 데이터를 단비의 대화흐름으로 가져와 활용하는 방법을 알아보겠습니다. <br/>

### API 등록하기

1) API 관리 메뉴에 들어갑니다.

{% include callout.html content="화면 위치 : [그룹 관리] > [그룹 챗봇] > [API 관리]" type="default" %}

2) API 추가 버튼을 눌러 API 생성화면으로 들어갑니다.

3) 화면의 진입 후 상단에 생성할 API 명을 "피자주문하기_api_피자가격 가져오기"라고 입력합니다.

4) API 메서드는 GET, Request URL은 https://channel.danbee.ai:3000/pizzaTutorial/getPrice 라고 입력합니다.
   (API 설정연습을 위해 단비에서 만들어 놓은 API입니다.)

6) API 설명에 ***피자주문 튜토리얼에서 피자메뉴에 따른 피자가격을 가지고 오는 API입니다.*** 라고 입력하세요.

7) Content Type은 [JSON](https://www.json.org/json-ko.html)을 선택합니다.

8) Query 파라미터는 외부 시스템 API 호출시 넘겨줘야할 파라미터를 정의하는 영역입니다. 이 항목은 Value가 반드시 있어야 하는 항목은 아니기에 "필수"체크박스를 해제해주세요. 단비에서 제공하는 API는 q라는 변수에 피자메뉴를 넘겨준다고 미리 정의 하였기 때문에 Name 부분에 q를 입력합니다. 그리고 [API Test] 버튼을 클릭합니다.

9) Response API Tree 부분에 외부시스템에서 JSON 형태로 받아온 결과값이 트리형태로 나타납니다. 튜토리얼에서 호출한 API 의 경우 피자메뉴와 피자값을 넘겨주는 JSON 을 반환했습니다. 예시로 입력한 URL의 경우 parameter 에 특정 값이 들어가지 않아도 기본형태를 넘겨주기 때문에 결과값이 나타났습니다. 

{% include image.html file="tutorial/using_api_node3.gif"  caption="API 만들기2" %}

10) 예상한 결과값이 잘 나타난다면 외부시스템 정보를 들고올 준비가 되었습니다. <br/>
우상단의 ***저장*** 버튼을 눌러 저장합니다. 이제 생성한 API 를 대화흐름에서 어떻게 쓰는지 알아보도록 하겠습니다.

{% include note.html content="여러분이 프로그래머가 아니라면 조금 어려울 수 있습니다. 하지만, 프로그래머들도 맨 처음에는 어려웠겠죠? 이번 기회에 API란 무엇인지 경험해보시기 바랍니다." %}

{% include warning.html content="API 설정전에 정보를 주는 외부 시스템에서 JSON 형태로 정보를 던지는지 꼭 확인이 필요합니다." %}

{% include warning.html content="호출하는 API 에 따라 기본값이 들어가야 결과값이 반환되는 경우가 있을 수 있습니다.
API 규격을 잘 보고 필요한 경우 Value 부분에 Name 에 해당하는 Value 를 기입하도록 합니다." %}


### API 노드를 대화흐름에 적용하기

1) 메뉴에서 **대화흐름**을 클릭하고, "피자주문하기" 대화흐름을 선택합니다.
{% include callout.html content="화면 위치 : [챗봇 변경 / 생성하기] > 대화흐름]" type="default" %}

2) 계속해서 만들던 피자주문 시나리오에 API를 적용해 보도록 하겠습니다.

3) Api노드를 클릭하여 추가해 주세요.

4) Carausel 노드 와 Split 노드 사이에 Api 노드를 위치 시키고 앞뒤 노드와 연결해 주세요. <br/>
기존에 연결된 선의 경우 마우스로 선을 클릭하고 선이 붉은색으로 하이라이트된 후 키보드의 delete 키를 누르면 삭제됩니다. <br/>
나중에 알아보기 쉽도록 ***외부에서 피자가격 가져오기*** 와 같은 노드명을 부여하면 좋겠죠? 

{% include image.html file="tutorial/using_api_node6.gif"  caption="API 노드 생성하기1" %}

### 출력값을 담을 파라미터 추가

1) 피자가격 정보를 받아낼 파라미터를 추가해야 합니다. 좌측 하단의 파라미터 추가버튼을 이용해 "피자가격"이라는 파라미터를 sys.any 라는 엔티티로 추가합니다. 

{% include image.html file="tutorial/using_api_node8.gif"  caption="응답값을 받아낼 파라미터 미리 추가" %}

### API 노드 요청 파라미터 설정

1) Api 노드를 더블 클릭하여 상세 패널을 엽니다.

2) ***선택하세요*** 를 누르면 현재 그룹에서 사용 가능한 API 목록이 하단에 펼쳐집니다. <br/>
앞에서 만들었던 ***피자주문하기_api_피자가격 가져오기*** 를 선택하세요. 

3) ***피자주문하기_api_피자가격 가져오기*** 를 선택하고 **불러오기**를 클릭합니다. 

4) 불러온 부분의 ***Api 요청 설정***탭의 ***요청 파라미터*** 부분에 요청시 보낼 파라미터를 설정합니다. 외부시스템은 대화흐름에서 사용자가 선택한 #{피자메뉴} 정보를 받아서 Api로 보내면, 메뉴에 해당하는 가격을 응답으로 보내 줄 것입니다. 앞서서 q라는 변수에 피자메뉴를 넘겨주기로 약속했기 때문에 사용자가 선택한 피자메뉴가 담겨있는 내부 변수 #{피자메뉴}를 q에 입력 하도록 하겠습니다.

{% include image.html file="tutorial/using_api_node9.png"  caption="API 노드 요청 설정" %}

### API 노드 응답 파라미터 설정
1) API에서 응답받은 정보를 대화흐름의 파라미터에 할당 시켜야합니다. 이 작업 진행을 위해  ***Api 응답 저장*** 탭으로 이동합니다. <br/>

2) ***API 결과 Tree*** 섹션 우측의 [API 결과 Tree 보기]버튼을 클릭하면, API 결과가 표시되는 것을 볼 수 있습니다.

3) ***대화흐름 파라미터에 API 결과값 연결*** 섹션 하단에 피자가격 변수에 외부시스템 값을 설정할 박스가 나타납니다. <br/>
좌측 ***Api Tree*** 에 외부시스템에서 price 변수에 가격 정보를 넣어줬기 때문에 price를 드래그 하여 피자가격 박스 부분에서 클릭을 풀어줍니다. <br/>

[+] 버튼을 누르면 대화흐름 내부에서 정의한 변수들이 나타납니다. <br/>
피자가격을 받아오기 위해 대화흐름 내부에서 정의한 피자가격 파라미터를 선택합니다. 

{% include image.html file="tutorial/using_api_node10.gif"  caption="API 노드 응답 설정" %}

4) API 노드 생성을 완료하였습니다. 상단의 ✔반영확인 버튼을 눌러 상세화면을 닫고, 변경내용 저장버튼을 클릭하여 대화흐름을 저장합니다. <br/>


### API 노드 테스트
1) 이제는 받아온 피자가격을 사용자에게 보여주기 위해 Speak 노드 문구를 변경해 줍니다. 각각의 Speak 노드에 #{피자가격} 을 넣어 문구를 만들어 주세요. <br/>
문구 수정 후 ***확인*** 버튼을 통해 상세 패널을 닫아주세요. 상세화면 닫은 후 우상단의 ***변경내용 저장*** 버튼도 꼭 누르셔야 내용이 저장 됩니다. 

{% include image.html file="tutorial/using_api_node11.png"  caption="API 노드 테스트" %}

2) 우측의 테스트 패널에서 테스트를 해보세요. “피자 주문해줘”라고 입력 후 피자메뉴 선택 하면 <br/>
Speak 노드에 #{피자가격} 을 넣어 만든 문구를 확인하실 수 있습니다.

{% include image.html file="tutorial/using_api_node12.png"  caption="API 노드 테스트" %}

## 다음 Step 에서는 
지금까지 API 를 등록하고 API 노드 를 설정하는 방법을 알아 보았습니다.<br/>
다음 Step 에서는 Function 노드 를 활용하여 대화흐름 내부에서 사용하는 변수를 원하는대로 가공하는 방법을 알아보도록 하겠습니다.
