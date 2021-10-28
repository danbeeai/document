---
title: 프로그(Frogue)
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 단비Ai에서 제공하는 웹채팅창에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_frogu.html
folder: danbeeDoc
previous: {
    title: 챗봇 채널 연계 설정,
    url: channel_connection_settings.html
}
next: {
    title: Frogue(챗봇전용 채팅창) 오픈소스,
    url: channel_frogu_open.html
}

---


## Frogue(프로그)


<strong>단비가 내리면, 개구리가 운다!</strong>

챗봇, 채팅창이 필요합니다. Frogue는 단비Ai로 만든 챗봇이 바로 출동할 수 있도록 만든 서비스 입니다.
아래 경로에서 ON 하면, 바로 사용하실 수 있습니다.
{% include callout.html content="화면 위치 : [챗봇 만들기] > [챗봇 제작] > [웹 채팅창]" type="default" %}

{% include image_border.html file="channel/frogue/frogue05_livechat.PNG"  caption="단비Ai 홈페이지에 적용된 Frogue의 모습" %}


### 1. Frogue by danbee.Ai 에 [ON/OFF] 버튼을 클릭하십시오.

홈페이지에 바로 적용을 하거나 별도의 URL에서 동작하는 챗봇을 사용하실 수 있습니다.
기본적으로 접근 가능한 URL을 제공합니다. 오프라인 환경에서 챗봇을 만나게 하실 경우 QR코드를 활용하세요.

{% include image.html file="channel/frogue/frogue01_basic.png"  caption="기본설정" %}

### 2. 홈페이지에 붙이고 싶은 경우, embedding 코드를 활용하여 적용할 수 있습니다.

모바일에서도 잘 동작하는 라이브챗 스타일로 홈페이지에서 안내, 문의응답을 고려하신다면 임베딩 코드를 홈페이지에 삽입하시기 바랍니다.
{% include image_border.html file="channel/frogue/frogue02_embedding.PNG"  caption="임베딩 코드로 홈페이지에 라이브챗 스타일로 적용할 수 있습니다." %}

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

<table class="table table-striped">
  <thead>
    <tr>
      <th>사용 예시 : </th>
      <th>https://frogue.danbee.ai/?chatbot_id=챗봇아이디&user_id=사용자ID&force_welcome=Y</th>
    </tr>
  </thead>
</table>
    
</div>


### 3. 디자인을 변경하실 수 있어요! 테마를 선택하거나 색상을 변경하실 수 있습니다.

홈페이지에 잘 어울리는 색상을 적용하실 수 있습니다.
브랜드에 맞는 톤앤매너로 바꿔보세요. <br/>
또한, Superior요금제를 이용하시면 헤더나 채팅창,하단 입력창 영역의 배경이미지까지 설정할 수 있습니다.

{% include image_border.html file="channel/frogue/frogue03_design.png"  caption="Frogue 디자인 설정" %}

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
```
{% include bottom.html %}
