---
title: 토드(단비 웹채팅창)
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 단비Ai에서 제공하는 새로운 웹 채팅창에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_toad.html
folder: danbeeDoc
previous: {
    title: 프로그(단비 웹채팅창) 오픈소스,
    url: channel_frogu_open.html
}
next: {
    title: API for Your App,
    url: channel_native_app.html
}

---


## 토드(Toad)


<strong>단비가 내리면, 개구리가 운다!</strong>

만든 챗봇이 바로 출동할 수 있는 더욱 새로워진 모습의 웹채팅창 서비스를 만나 보세요. 
아래 화면 위치에서 바로 채널 '토드'를 연결할 수 있습니다.
토드는 기존 프로그 채널에서 더욱 세련된 디자인으로 변화된 새로운 웹 채팅창 서비스입니다. 기능적인 면에서는 기존 프로그 채널과 동일합니다. 

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 배포 > 웹 채팅창" type="default" %}

{% include image_border.html file="channel/toad/toad_livechat.png"  caption="단비Ai 홈페이지에 적용된 쳇봇 Toad 채널 모습" %}


### 1. 채널에 연결하기

'연결 상태'를 ON으로 설정하시고, '채널 유형'을 '플러스(토드)'를 선택하시면 채널 연결하기가 완료됩니다!
채널 유형을 '클래식(프로그)'로 변경하시면, 토드와 연결이 해제되고 프로그 채널과 연결됩니다.

홈페이지에 바로 적용을 하거나 별도의 URL에서 동작하는 챗봇을 사용하실 수 있습니다.
기본적으로 접근 가능한 URL을 제공합니다. 오프라인 환경에서 챗봇을 만나게 하실 경우 QR코드를 활용하세요.

{% include image.html file="channel/toad/toad_connect.png"  caption="기본설정" %}

### 2. 홈페이지에 붙이고 싶은 경우, embedding 코드를 활용하여 적용할 수 있습니다.

모바일에서도 잘 동작하는 라이브챗 스타일로 홈페이지에서 안내, 문의응답을 고려하신다면 임베딩 코드를 홈페이지에 삽입하시기 바랍니다.
{% include image_border.html file="channel/toad/toad_embed.png"  caption="임베딩 코드로 홈페이지에 라이브챗 스타일로 적용할 수 있습니다." %}

라이브챗 스타일은 홈페이지 우측 하단에 대화를 유도하는 버튼을 달아 사용자와 실시간으로 채팅하는 스타일의 UI를 말합니다.


#### 2.1 웹페이지와 연동하기

<div class="indented">

웹페이지에서 특정 이벤트가 발생할 경우 챗봇의 특정 대화 흐름을 호출하여 말을 할 수 있습니다. <br />

사용자가 특정 웹페이지에 접속을 하였을 경우, 로그인을 하였을 경우, 제품을 장바구니에 담았을 경우 등 이벤트가 발생할 경우
챗봇이 먼저 대화를 유도한다면 더 많은 사용자들에게 접근성의 기회를 제공하게 됩니다.<br /><br />

{% include image_border.html file="channel/frogue/frogue07_pushmsg.png" caption="danbee.Ai 홈페이지에 적용된 푸쉬메시지" %}

사용하는 방법은 먼저 이벤트용 대화 흐름을 생성해야 합니다. 생성 시 이벤트명으로 데이터를 연동할 수 있습니다.<br />
웹페이지의 javascript 영역에서 제공하는 함수를 사용합니다.<br /><br />

<table class="table table-striped">
  <thead>
    <tr>
      <th>정보</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>함수명</td>
      <td>froguePushEvent</td>
    </tr>
    <tr>
      <td>파라미터1(문자열)</td>
      <td>이벤트명</td>
    </tr>
    <tr>
      <td>파라미터2(JSON)</td>
      <td>전달데이터 - 대화 흐름(대화 흐름) 파라미터로 전달</td>
    </tr>
  </tbody>
</table>
<table class="table table-striped">
  <thead>
    <tr>
      <th>사용 예시 : </th>
      <th>froguePushEvent('clickEvent', {"param1": 'value1', "param2": 'value2'});</th>
    </tr>
  </thead>
</table>
<br />
이렇게 호출할때 우측하단의 프로그 대화창이 닫혀있을때 말풍선으로, 대화창이 열려있을때 대화창내 챗봇이 말을 하게 됩니다.<br /> 

* 주의사항 : 이벤트 대화흐름이 호출되면 사용량 1CC 계산됩니다.
<br /><br />

</div>

#### 2.2 웹페이지에서 프로그 초기 데이터 변경하기

<div class="indented">

프로그를 웹페이지에 라이브챗 스타일로 사용할 경우 초기 데이터를 전달 할 수 있습니다. <br />
frogue-container 의 data-init-전달값 속성을 통해서 전달합니다. <br /><br />

초기데이터가 프로그를 사용하는 도중 변경이 될 경우 셋팅할 수 있는 방법을 제공합니다.<br /><br />

<table class="table table-striped">
  <thead>
    <tr>
      <th>정보</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>함수명</td>
      <td>frogueSetInitParam </td>
    </tr>
    <tr>
      <td>파라미터(JSON)</td>
      <td>전달데이터 - 대화 흐름(대화 흐름) 파라미터로 전달</td>
    </tr>
  </tbody>
</table>
<table class="table table-striped">
  <thead>
    <tr>
      <th>사용 예시 : </th>
      <th>frogueSetInitParam({"param1": 'value1', "param2": 'value2'});</th>
    </tr>
  </thead>
</table>
<br />

</div>

#### 2.3 웹페이지안에 아이프레임으로 넣기

<div class="indented">

아이프레임안에 프로그 URL을 셋팅할 경우 웹페이지 안에서 웹채팅창 서비스를 할 수 있습니다.. <br />

시작메시지가 바로 나오게 하려면 URK 뒤에 값을 &force_welcome=Y 붙여넣습니다.<br /><br />

* 주의사항 : 시작메시지가 호출되면 사용량 1CC 계산됩니다.
<br /><br />

<table class="table table-striped">
  <thead>
    <tr>
      <th>사용 예시 : </th>
      <th>https://frogue.danbee.ai/toad?chatbot_id=챗봇아이디&user_id=사용자ID&force_welcome=Y</th>
    </tr>
  </thead>
</table>
    
</div>

<br /><br />


#### 2.4 Embedding코드의 data 속성 활용하기
Embedding 코드의 div태그를 보시면 data-chatbot, data-user등의 속성들이 많이 보입니다. 이러한 값들을 입력하시면
라이브챗에서의 더욱 많은 기능을 이용하실 수 있습니다.<br /><br />


<table class="table table-striped">
  <thead>
    <tr>
      <th>속성</th>
      <th>설명</th>
      <th>값</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>data-chatbot</td>
      <td>(필수값) 챗봇 ID </td>
      <td>챗봇의 ID</td>
    </tr>
    <tr>
      <td>data-user</td>
      <td>사이트에 들어오는 유저id로, 사이트사용자관리가 가능할때 연결을 해주시면 사용자별로 사용로그를 확인할수 있습니다.</td>
      <td>사용자 ID</td>
    </tr>
    <tr>
        <td>data-init-식별키</td>
        <td>처음에 챗봇이 로딩딜때 넘길수있는값으로, 대화흐름파라미터와 연동하여 사용됩니다.보통 로그인여부나, 개인정보동의 등의 값을 사이트에서 받아서 처리합니다. (식별키는 소문자만 가능)</td>
        <td>예) data-init-loginyn="Y"</td>
    </tr>
    <tr>
        <td>data-close-use</td>
        <td>챗봇 아이콘 숨김 버튼 사용 여부</td>
        <td>사용:Y, 사용안함:N</td>
    </tr>
    <tr>
        <td>data-close-bgcolor</td>
        <td>챗봇 아이콘 숨김 버튼의 배경색</td>
        <td>예) #ffffff</td>
    </tr>
    <tr>
        <td>data-close-linecolor</td>
        <td>챗봇 아이콘 숨김 버튼의 X글자의 색상</td>
        <td>예) #000000</td>
    </tr>
    <tr>
        <td>data-move-use</td>
        <td>챗봇 아이콘 위치 이동 기능 사용 여부</td>
        <td>사용:Y, 사용안함:N</td>
    </tr>
    <tr>
        <td>data-move-bgcolor</td>
        <td>챗봇 아이콘 위치 이동 버튼의 배경색</td>
        <td>예) #ffffff</td>
    </tr>
    <tr>
        <td>data-move-linecolor</td>
        <td>챗봇 아이콘 위치 이동 버튼의 글자 색상</td>
        <td>예) #000000</td>
    </tr>
  </tbody>
</table>

### 3. 디자인을 변경하실 수 있어요! 테마를 선택하거나 색상을 변경하실 수 있습니다.

홈페이지에 잘 어울리는 색상을 적용하실 수 있습니다.
브랜드에 맞는 톤앤매너로 바꿔보세요. <br/>
또한, Superior요금제를 이용하시면 헤더나 채팅창,하단 입력창 영역의 배경이미지까지 설정할 수 있습니다.

{% include image_border.html file="channel/toad/toad_custom.png"  caption="토드 커스텀 디자인 설정" %}

Trial(무료체험)요금제 사용자는 미리보기는 가능하지만, 실제 프로그에는 적용되지 않습니다. 


### 4. 아래 배너를 제거하실 수 있습니다. 

서비스 레벨에 따라 danbee.Ai 브랜드가 나오지 않게 설정을 변경할 수 있습니다.
{% include image_border.html file="channel/frogue/frogue04_banner.png"  caption="배너 설정" %}


### 5. 기타 

이 외에도 파일 업로드, 사용자의 말풍선 평가, 말풍선에 챗봇이미지 표시하기 등 더 다양한 기능들을 설정할 수 있습니다.

### 6. 라이브 챗 위치 및 사이즈 변경하기

라이브 챗의 위치와 사이즈를 수정하고싶을 땐
`<head>`태그 최하단에 단비 프로그 스타일 경로를 넣어주시고 그 다음 위치와 사이즈를 수정할 스타일 경로(_프로그 위치 및 사이즈 수정.css_)를 넣어 주시고 아래 주석을 참고하여
위치를 변경하시면 됩니다.

```html
<!--단비 프로그 스타일-->
<link id="frogue-embed-css" rel="stylesheet" href="https://danbee.ai/js/plugins/frogue-embed/frogue-embed.min.css">

<!-- 프로그 위치 및 사이즈 수정 스타일 -->
<link rel="stylesheet" href="프로그 위치 및 사이즈 수정.css">
```

프로그 위치 및 사이즈 수정.css 스타일 소스
```css
#frogue-container {
    right: 80px; /* 프로그 버튼 오른쪽 기준 */
    bottom: 85px; /* 프로그 버튼 아래쪽 기준 */
}
.frogue-chat {
    right: 220px; /* 채팅창 오른쪽 기준 위치 */
    bottom: 320px; /* 채팅창 아래쪽 기준 위치 */
    width: 320 !important; /* 채팅창 width */
    max-height: 720px !important; /* 채팅창 height */
}
.frogue-talkpop {
    right: 0px; /* 말풍선 오른쪽 기준 위치 */
    bottom: 20px; /* 말풍선 아래쪽 기준 위치 */
}
.frogue-btn-iframe-wrap{
    border-radius : 0;  /* 프로그버튼 사각형으로 보이게 변경 */
    -webkit-box-shadow : 0 !important;  /* 프로그버튼 그림자 없애기 */
    box-shadow : none !important;
}
```

### 7. STT(Speech To Text)

브라우저의 STT 기능을 이용하여 챗봇에게 음성 메시지를 전달합니다. <br/>
(* PC Chrome 브라우저에서만 오픈된 기능으로, 기타 브라우저나 모바일 환경에서는 '사용'으로 설정하였더라도 기능이 노출되지 않습니다.)

{% include image_border.html file="channel/frogue/frogue_stt_01.png"  caption="플랫폼에서의 설정 화면" %} <br/>
{% include image_border.html file="channel/toad/toad_stt.png"  caption="웹채팅창에 적용된 모습" %}


{% include bottom.html %}
