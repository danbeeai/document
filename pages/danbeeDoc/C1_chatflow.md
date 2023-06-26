---
title: 대화 흐름 기본 설명 
tags: [chatflow, basic]
keywords: Basic Conversation
summary: 대화 흐름의 기본적인 개념을 이해합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow.html
folder: danbeeDoc
previous: {
    title: 대화 의도, 
    url: intent.html
}
next: {
    title: 파라미터,
    url: parameter.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 주요 대화 > 대화 흐름" type="default" %}

사람과 사람간의 대화에는 '흐름'이 있습니다. <br/><br/>

처음엔 인사를 하고 ➡️ 안부를 묻고 ➡️ 둘 사이 관심사 등에 대해서 이야기를 진행해 나갑니다. 대화 과정에서 '하나하나의 이야기 단위'들이 (인사, 안부, 관심사 등) 모여서, 대화의 '흐름'을 구성하게 됩니다. <br/><br/>

지금 말한 '하나하나의 이야기 단위'를 단비에서는 '대화 흐름' 라는 단위로 정의하고 있습니다. <br/><br/>

대화할 때는 상대방의 이야기를 듣고 대답하는 것이 기본일 것입니다. 흐름을 놓치지 않기 위해서입니다. 챗봇의 대화 흐름에서도 마찬가지입니다. <br/><br/>  

말귀를 알아 듣기 위한 **[Listen 노드]** + 대답을 위한 **[Speak 노드]** 라는 방식이 챗봇의 기본입니다. 중요하니까 다시 한 번 따로 정리합니다. <br/><br/>

[듣고 = Listen 노드] + [대답한다 = Speak 노드] <br/><br/>

{% include image.html file="chatflow/01_chatflow_basic.png" caption="" %}

대화를 하다보면 무슨 말인지 잘 못알아들을 수 있습니다. 이때 정확히 확인하려면 '다시 물어보는' 질문을 던지게 됩니다 <br/><br/>  

A: 이게 또 고장났네요. 저번 달에 고쳤던 건데

B: (저번 달에 고친게 두개 있는데...) 정수기? 에어컨? <br/><br/>

챗봇의 대화 흐름은 이렇게 대화 과정에서 필요한 기본적인 기능을 '노드'라는 형태로 제공합니다. 듣기, 말하기, 판단하기, 저장되어 있는 정보에서 가져오기 등등 여러가지 기능을 가진 노드를 조합해서 챗봇의 대화 흐름을 만들게 됩니다. <br/><br/>

앞으로 차근차근 각각의 대화 노드에 대해 알아보겠습니다.

## 대화 흐름 생성

좌측 메뉴 [대화 흐름] 클릭 후 나타나는 화면에서 우측 **[+대화 흐름 생성]** 버튼을 클릭하시면 대화흐름 생성 팝업이 나타납니다. <br><br>

{% include image.html file="chatflow/02_chatflow_basic.png" caption="" %} <br><br>


생성할 대화 흐름의 이름을 입력하신 후 **[대화 흐름 생성]** 버튼을 누르면 대화 흐름이 생성됩니다. <br><br>

{% include image.html file="chatflow/03_chatflow_basic.png" caption="" %}  


### 대화노드 추가

대화 흐름 캔버스 화면 상단에 있는 노드를 클릭하면 추가됩니다. <br><br>

{% include image.html file="chatflow/04_chatflow_basic.png" caption="" %} <br/><br/>


총 11가지의 노드가 있습니다. <br/><br/>

각각의 노드에 대한 한줄 설명은 아래와 같습니다. <br><br>

| 대화노드 | 설명 | 
|--------|-------|
| [Listen 노드](chatflow_listen.html#Listen 노드) | 사용자의 **의도**가 무엇인지 **파악**하고, **대화의 흐름을 시작하는** 노드입니다. |
| [Speak 노드](chatflow_speak.html#Speak 노드) | 챗봇의 **답변 메시지를 설정하는** 노드입니다. |
| [Carousel 노드](chatflow_carousel.html#Carousel 노드) | 사용자에게 **카드 형태로 선택지를 제시하는** 노드입니다. |
| [Slot 노드](chatflow_slot.html#Slot 노드) | 대화 과정에서 필요한 정보를 얻기 위해 **되묻는 질문을 설정하는** 노드입니다. |
| [Split 노드](chatflow_split.html#Split 노드) | **대화 흐름을 분기하기 위해** 정보를 설정하는 노드입니다. |
| [Jump 노드](chatflow_jump.html#Jump 노드) | 대화 흐름상 **다른 대화 흐름로 이동하고자 할 경우** 사용하는 노드입니다. |
| [Sleep 노드](chatflow_sleep.html#Sleep 노드) | 챗봇이 **받은 응답을 일정시간동안 지연**시키는 노드입니다. |
| [Knowledge 노드](chatflow_knowledge.html#Knowledge 노드) | **[지식 라이브러리] 메뉴와 연결**하여 데이터를 읽고 쓰는 노드입니다. |
| [Api 노드](chatflow_api.html#API 노드) | **다른 컨텐츠 서비스와 연계**하여 정보를 얻기 위한 노드입니다. |
| [Function 노드](chatflow_function.html#Function 노드) | **파라미터 정보를 가공 처리할 경우** 사용하는 노드입니다. |
| [Parameter 노드](chatflow_parameter.html#Parameter 노드) | **파라미터 값을 바로 설정**할 수 있는 노드입니다. |
{: .table .table-striped}  


### 이벤트 대화흐름  

대화 의도에서 시작되는 흐름이 아닌, '특정 조건'에서 시작되는 흐름을 이야기합니다. '특정 조건'을 갖추면 '이벤트'가 발생했다고 보는 것입니다. <br/><br/>  

이벤트 플로우는 이벤트 URL과 이벤트명을 가지며, 스크립트를 통해 직접 호출해야 합니다. <br/><br/>

이벤트 전환 토글 버튼을 눌러 활성/비활성 하실 수 있습니다. <br><br>

{% include image.html file="chatflow/05_chatflow_basic.png"  caption="클릭 전 (비활성 상태)" %} <br><br>  
{% include image.html file="chatflow/06_chatflow_basic.png"  caption="클릭 후 (활성 상태)" %}


## 대화 흐름 기본 조작

### 노드 선택
노드는 클릭 또는 드래그로 선택할 수 있습니다.
{% include image.html file="chatflow/07_chatflow_basic.gif"  caption="" %} <br/><br/>

### 노드 연결
노드의 연결점을 클릭, 드래그하는 방식으로 노드끼리 연결할 수 있습니다.
{% include image.html file="chatflow/08_chatflow_basic.gif"  caption="" %} <br/><br/>

### 노드 삭제
노드와 연결선을 선택한 후 [삭제] 버튼을 눌러 삭제할 수 있습니다. 단축키 [delete]키도 가능합니다. (Mac에서는 fn + delete)
{% include image.html file="chatflow/09_chatflow_basic.gif"  caption="" %}


## 노드 개별 수정
모든 노드는 더블클릭하면 상세화면을 열 수 있습니다.  
{% include image.html file="chatflow/10_chatflow_basic.gif"  caption="" %} <br/><br/>


### 노드 반영 확인/취소
모든 노드는 이름과 설명을 수정할 수 있습니다. 노드를 수정한 뒤 [적용]을 눌러 확정하거나, [취소]를 눌러 되돌릴 수 있습니다.
{% include image.html file="chatflow/11_chatflow_basic.gif"  caption="" %}  


### 이미지 추가
메세지를 출력하는 노드에는 이미지를 추가할 수 있습니다. (좌)이미지 파일을 직접 업로드 할때는 1MB 파일크기 제한이 있습니다. <br><br>  

[이미지 url 연결] 옵션을 선택하면, 이미지가 있는 인터넷상의 URL을 활용하여 이미지를 올릴 수 있습니다. 확장자(jpg, png, gif)가 있는 URL을 적용해야 정상적으로 출력됩니다. 

{% include image.html file="chatflow/12_chatflow_basic.png"  caption="" %}

{% include tip.html content="[imgur.com](https://imgur.com/){:target='_blank'}나 [giphy.com](https://giphy.com/){:target='_blank'}과 같은 간단 이미지 공유사이트를 활용하면 편리합니다. " %} <br>


### 이미지 사이즈
채널 유형에 따라 노드의 권장 사이즈입니다.

<table class="table table-bordered">
    <tr>
        <th></th>
        <th>클래식(프로그)</th>
        <th>플러스(토드)</th>
    </tr>
    <tr>
        <th>speak(스피크)</th>
        <td>330 X 230</td>
        <td>380 X 280</td>
    </tr>    
    <tr>
        <th>slot(슬롯)</th>
        <td>330 X 230</td>
        <td>380 X 280</td>
    </tr>    
    <tr>
        <th>carousel(캐로셀ㅋ)</th>
        <td>260 X 260</td>
        <td>320 X 240</td>
    </tr>
</table>
<br><br>

### 파라미터 활용
노드는 단순히 입력된 메시지만 출력할 뿐만 아니라, 사용자로부터 입력받은 파라미터 정보들을 활용하여 메시지를 표시할 수 있습니다. <br/><br/>  
 
#{파라미터명} 형태로 메세지를 작성하면 실제 대화 채널에는 해당 파라미터에 설정되어 있는 값이 치환되어 표시됩니다.
 
{% include image.html file="chatflow/13_chatflow_basic.png"  caption="" %}

파라미터에는 시스템 파라미터와 일반 파라미터가 있습니다. <br><br><br>

#### 시스템 파라미터
>단비 AI시스템에서 기본적으로 제공하는 파라미터입니다. 아래 표를 참고해 활용하실 수 있습니다.

>(사용법 예시: #{@message}) <br><br>

>| 시스템 파라미터 | 표기 | 설명 | 
|--------|-------|-------|
| 사용자 식별정보 | @userId | 사용자ID가 표시됩니다. (ex: email ) |
| 챗봇명 | @chatbotName | 챗봇 생성시 명명했던 **이름**이 표시됩니다.  |
| 채널아이디 | @channelId | **접속한 채널 아이디**가 표시됩니다. <br/>(ex : 5-facebook / 3-kakaotalk / 2-line / 7-navertalk / 6-telegram / 4-slack)  |
| 받은 메시지 | @message | 사용자로부터 받은 질문 메시지 입니다. |
| 현재년도 | @currentDateYYYY | 현재년도 정보입니다. (예:2019) |
| 현재월 | @currentDateMM | 현재월 정보입니다. (예:12) |
| 현재일 | @currentDateDD | 현재일 정보입니다. (예:31) |
| 현재년월 | @currentDateYYYYMM | 현재년월 정보입니다. (예:201912) |
| 현재년월일 | @currentDateYYYYMMDD | 현재년월일 정보입니다. (예:20191231) |
| 현재시간 | @currentTimeHH | 현재시간 정보입니다. (예:23) |
| 현재분 | @currentTimeMI | 현재분 정보입니다. (예:59) |
| 현재초 | @currentTimeSS | 현재초 정보입니다. (예:59) |
| 현재요일 | @currentDateWeek | 현재요일 정보입니다. <br/>(예: 1:일, 2:월, 3:화, 4:수, 5:목, 6:금, 7:토) |
{: .table .table-striped}

<br><br><br>


#### 일반 파라미터

>입력창에 직접 #{파라미터명} 식으로 입력할 수 있지만, 편의성 차원에서 아래와 같이 [+Parameter 추가] 버튼을 눌러서도 가능합니다. <br/><br/>

>버튼을 눌렀을 때 나오는 팝업에서 파라미터 선택시, 해당 파라미터는 #{파라미터명} 식으로 메시지에 추가됩니다. <br><br>

>{% include image.html file="chatflow/14_chatflow_basic.png"  caption="" %}  


### 버튼 추가
메세지를 출력하는 노드는 [+ 버튼 추가]를 클릭해 버튼을 추가할 수 있습니다. 

{% include image.html file="chatflow/15_chatflow_basic.png"  caption="" %} <br><br>


버튼은 단순 대답부터 전화걸기, 다른 대화 흐름으로 연결 등 다양한 기능을 지원하고 있습니다.

{% include image.html file="chatflow/16_chatflow_basic.png"  caption="" %} <br><br>


#### 버튼(선택지) 설정

>버튼 선택지의 상세 설명은 아래와 같습니다. 

>| 버튼 | 설명 | 
|--------|-------|
| 선택지 | 버튼 형태 선택지를 제공합니다. |
| 웹 링크 | 팝업으로 호출할 Link 정보를 제공합니다. |
| 내부 App실행 | <u>스마트폰에서</u> 내부 App을 실행합니다.  |
| 외부 App실행 | <u>스마트폰에서</u> 외부 App을 실행합니다.  |
| 전화걸기 | <u>스마트폰에서</u> 전화걸기로 연결합니다. |
| 대화 흐름호출 | 다른 대화 흐름을 호출합니다. 이때 현재 대화 흐름의 파라미터를 넘겨줄 수 있습니다. |
| 퀵 리플라이 | 입력창 상단에 버튼 형태의 선택지를 제공합니다. |
| 액션 | 버튼을 누르면 챗봇이 별도의 설정된 함수를 실행합니다. |
| 지식답변 호출 | [지식 라이브러리] 메뉴 FAQ+ 시트와 연결합니다. |
{: .table .table-striped}

>{% include note.html content="퀵 리플라이 타입은 facebook, 네이버톡톡에서 해당 형태로 이용 가능하며 제공되지 않는 채널에서는 선택지와 동일하게 표시됩니다." %} <br><br>  


#### 대화 흐름 호출 파라미터 연결

>대화 흐름 호출 버튼을 눌렀을때, 각 대화 흐름에서 사용되는 파라미터들끼리 연결 가능합니다. [Jump 노드](chatflow_jump.html) 기능이 버튼에 달려있다고 이해하시면 쉽습니다. <br/><br/>

>예를 들어 날씨를 물어분 후 ➡️ 사용자가 버튼을 클릭하면 ➡️ 날씨에 맞는 음식을 추천한다고 가정해보겠습니다.  

>{% include image.html file="chatflow/17_chatflow_basic.png"  caption="" %}  


>위와 같이 Speak 메세지를 설정하고 대화 흐름 호출 버튼을 추가합니다. 호출할 대화 흐름을 선택하면 [파라미터 연결] 버튼이 활성화 됩니다. <br/><br/> 

>파라미터 연결 버튼을 클릭하면 호출할 대화 흐름과 현재 대화 흐름의 파라미터 값을 연결할 수 있는 창이 뜹니다. 예시와 같이 ‘tempo’라는 파라미터를 연결하고 테스트패널에서 테스트 해보면 다음과 같은 결과를 확인할 수 있습니다.  

>{% include image.html file="chatflow/18_chatflow_basic.png"  caption="" %}  


>[디버그 모드](demo_n_test_panel.html#디버그-모드)에서 기존 날씨 대화 흐름에서 세팅되었던 tempo의 ‘폭우’라는 값이 야식 대화 흐름의 파라미터로 넘어갔음을 확인할 수 있습니다.



## 대화 흐름 저장

각 노드로 수정 후 [적용/취소]를 통해 설계를 마치셨나요? 마지막으로 대화 흐름 전체를 [저장]버튼을 눌러야만 최종적으로 반영됩니다.

{% include image.html file="chatflow/19_chatflow_basic.png"  caption="" %} <br><br>


제대로 적용됐는지 확인을 위해, 우측 [테스트] 버튼을 눌러 테스트 패널을 활용하시면 좋습니다.

{% include image.html file="chatflow/20_chatflow_basic.png"  caption="" %}


{% include warning.html content="대화 흐름 저장을 하지 않고 다른 화면으로 이동하면 입력되었던 작업은 사라지게 되니 유의하시기 바랍니다. " %}


## 대화 흐름 테스트 패널

설계한 대화 흐름이 정상적으로 흐름을 진행하는지 테스트할 수 있습니다.

{% include image.html file="chatflow/21_chatflow_basic.png"  caption="" %} <br><br>


테스트 예문을 입력하고 그에 따른 답변과 현재 진행되고 있는 상태 정보를 확인 할 수 있습니다. 사용자 선택에 따라 일반 모드, 디버그 모드로 테스트 패널을 사용하실 수 있습니다.

{% include image.html file="chatflow/22_chatflow_basic.png"  caption="테스트 패널 디버그 모드 (좌) 일반 모드 / (우) 디버그 모드" %}

최초 오픈시 일반 모드입니다. 패널 내 우측 상단 곤충 아이콘을 클릭하시면 디버그 모드로 진입합니다. <br/><br/>

- [일반 모드] : 챗봇과의 메시지를 주고 받는 상황을 일반 채팅창처럼 보여줍니다.
- [디버그 모드] : 메시지 뿐만 아니라 내부적으로 처리되는 데이터 처리 내용까지 확인이 가능합니다. 
- [파라미터 팝업] : 특정 노드에서의 처리된 파라미터 내역 확인이 가능합니다. (? 표시 클릭) <br/><br/>

{% include image.html file="chatflow/23_chatflow_basic.png"  caption="" %} <br><br>

디버그 모드에서 말풍선 우측 상단에 주황색 물음표 버튼이 나타나신 경우, 클릭하시면 파라미터 정보가 팝업으로 보입니다.

{% include image.html file="chatflow/24_chatflow_basic.gif"  caption="" %}

현재 진행 중인 대화 흐름을 확인하고 싶다면, 테스트 패널 우측 하단 [대화 흐름 바로가기] 버튼을 눌러주세요. 대화 흐름 canvas가 곧바로 펼쳐집니다.



## 용어 설명

| 용어 | 용어 설명 | 
|-------------------------|------------------------|
| 대화세션 | '대화세션아이디'의 줄임말입니다. <br>대화를 시작해서 끝날 때까지를 식별하기 위한 단위 개념입니다. |
| 인스턴스 | ‘ChatflowInstance’의 줄임말입니다. <br>‘대화 흐름’ 단위로 이야기를 진행할때 인스턴스 단위로 발급되는 식별 단위 입니다. |
| 노드 | 대화 흐름을 이어가는데 필요한 기본 기능 단위 입니다. <br>(듣기, 말하기, 판단하기, 되묻기 등등) |
| 파라미터 | 대화 흐름에서 사용되는 변수들을 말합니다. <br>Slot 노드, Carousel 노드에서 답변 정보를 저장하는 용도로 주로 사용합니다.  |
| 의도추론 | 현재 대화에 대해 NLU(자연어 이해)가 파악한 의도 정보를 나타냅니다. |
{: .table .table-striped}



{% include bottom.html %}
