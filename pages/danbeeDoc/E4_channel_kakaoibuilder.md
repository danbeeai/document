---
title: 카카오톡(카카오 i 빌더)
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 카카오톡에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_kakaoibuilder.html
folder: danbeeDoc
previous: {
    title: 텔레그램,
    url: channel_telegram.html
}
next: {
    title: 네이버톡톡,
    url: channel_navertalk.html
}
---

{% include note.html content=" [설정(Preference)] > [대화채널(Channel)]" %}

<h2><center>준비하기</center></h2>
챗봇을 카카오톡 채널에 연결하기 위해서는 아래항목들이 준비되어 있어야 합니다.
- 카카오톡 계정
- 카카오 i 오픈빌더 사용 권한: 카카오 i 오픈빌더 OBT 신청 절차가 필요합니다.
- 카카오톡 어플리케이션(App)
<hr/>

<h2><center>1.단비에서 설정하기</center></h2>
### Step1. 대화채널(Channel) 메뉴 이동
**설정(Preference) > 대화채널(Channel)** 메뉴로 이동 합니다.
### Step2. 카카오 i 오픈 빌더 채널 선택
카카오 i 오픈 빌더 타일 우측 상단에 **설정** 아이콘을 클릭합니다. 
### Step3. 채널연결에 필요한 정보 입력
단비에서 카카오 i 오픈 빌더를 이용해 카카오톡 채널에 연결하기위해서는 **액세스토큰**, **시작하기버튼명**을 두 가지를 정보를 설정해야합니다.
액세스토큰은 채널 WEBHOOK 확인용 토큰으로, 로그인시 필요한 패스워드와 같은 기능이라 이해해도 무방합니다.
시작하기버튼명은 사용자가 채팅방에 진입하고나서 챗봇과 대화를 시작하기 위한 버튼의 이름입니다.
여기서 설정한 액세스토큰,시작하기버튼명 값은 **카카오 i 오픈 빌더 설정시에 사용됩니다.** 
### Step4. 폴백 URL 복사
**폴백 URL**을 복사합니다. 폴백 URL역시 **카카오 i 오픈 빌더 설정시에 사용됩니다.**
### Step5. 채널 연결
**연결**을 눌러 단비에서의 채널 연결 설정을 마칩니다. 이제 카카오 i 오픈 빌더 설정을 해볼까요?

{% include warning.html content=" 단비에서 채널 연결을 재설정할 경우 '2.카카오 i 오픈 빌더 설정하기' 단계를 다시 수행해야 합니다." %}
<hr/>


<h2><center>2.카카오 i 오픈 빌더 설정하기</center></h2>
### Step1. 카카오 i 오픈빌더 챗봇 생성
카카오 i 오픈빌더에서 단비와 연동할 챗봇을 생성합니다.

1) 우측의 챗봇 생성 버튼을 클릭합니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-01.PNG"  caption="" %}

2) **[카카오톡 챗봇]**을 선택합니다.
{% include image.html file="channel/kakaoibuilder/kakao-02.PNG"  caption="" %}

3) 챗봇의 이름을 설정하고, 생성을 완료합니다.
{% include image.html file="channel/kakaoibuilder/kakao-03.PNG"  caption="" %}

### Step2. 봇 제네릭 메뉴(시작하기 버튼) 설정
사용자가 채팅방에 진입하고나서 챗봇과 대화를 시작하기 위한 버튼을 설정해야 합니다.
버튼설정창의 버튼기능을 메세지전송으로 변경하고, 단비에서 설정한 시작하기버튼명을 버튼명에 입력해주세요.

1) 좌측 사이드바의 **[시나리오 설정]**을 클릭합니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-04.PNG"  caption="" %}

2) **[시나리오 공통 설정]** 팝업창의 **[봇 제너릭 메뉴 설정]**을 On 설정합니다.
{% include image.html file="channel/kakaoibuilder/kakao-05.PNG"  caption="" %}

3) **[+ 버튼 추가]** 를 클릭해 버튼을 추가할 수 있습니다. **[버튼 설정]**을 클릭하여 **[버튼 기능]**을 '메시지 전송'으로 변경하고, **[버튼명]**에 단비에서 설정했던 시작하기버튼명을 입력합니다.
{% include image.html file="channel/kakaoibuilder/kakao-06.PNG"  caption="" %}

4) **[확인]**을 클릭해 봇 제너릭 메뉴 설정을 마칩니다.
{% include image.html file="channel/kakaoibuilder/kakao-07.PNG"  caption="" %}

### Step3. 스킬 생성
단비에서 만든 챗봇을 카카오톡에 연동하기 위해서는 카카오 i 오픈빌더에서 챗봇을 생성한 뒤 스킬 기능을 통해 연동하게 됩니다.

1) **[스킬]탭**의 **[생성]**버튼을 클릭합니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-08.PNG"  caption="" %}

2) 스킬을 생성하기 위한 모든값들을 입력합니다. 
- **URL** : 단비에 설정돼있는 **폴백 URL**값을 입력합니다.
- **헤더값** : 단비에서 직접 설정했던 **엑세스 토큰**값을 입력합니다.
    - Key : accessToken 
    - Value : 단비에서 직접 설정했던 **엑세스 토큰**값을 입력합니다.
{% include image.html file="channel/kakaoibuilder/kakao-09.PNG"  caption="" %}

3) **[기본 스킬로 지정]**을 선택하고, **[저장]**버튼을 클릭해 스킬 생성을 마칩니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-10.PNG"  caption="" %}

### Step4. 폴백블록에 스킬 연동
카카오 i 오픈빌더에서 지정해둔 시나리오 외에 처리하지 못하는 사용자 입력을 핑퐁 빌더에서 처리하기 위해서는, 폴백 블록에 저장한 스킬을 연동해야 합니다.**[폴백 블록]** 메뉴는 **[시나리오]-[기본 시나리오]**에서 찾을 수 있습니다.<br/>
<br/>
1) 스킬을 연결하기 위해서 **[파라미터 설정]**의 우측 상단 **[스킬 선택]**에서 방금 생성한 스킬을 선택합니다. 
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-11.PNG"  caption="" %}
{% include image.html file="channel/kakaoibuilder/kakao-12.PNG"  caption="" %}

2) **[봇 응답]**을 **[스킬 데이터]**로 설정합니다.
{% include image.html file="channel/kakaoibuilder/kakao-13.PNG"  caption="" %}

3) **[스킬 데이터]**로 설정된것을 확인하고, **[저장]** 버튼을 눌러 카카오 i 오픈 빌더 설정을 마칩니다.
{% include image.html file="channel/kakaoibuilder/kakao-14.PNG"  caption="" %}
<hr/>


<h2><center>3.카카오톡채널 설정하기(구 플친)</center></h2>
### Step1. 카카오톡채널 생성
1) **[+ 새 채널 만들기]**버튼을 클릭합니다.
{% include image.html file="channel/kakaoibuilder/kakao-channel-01.PNG"  caption="" %}

2) 채널생성에 필요한 정보들을 입력하고 **[확인]**버튼을 클릭합니다. 
{% include image.html file="channel/kakaoibuilder/kakao-channel-02.PNG"  caption="" %}

3) **[네, 입력한 정보로 개설하겠습니다.]** 버튼을 클릭하여 채널 생성을 완료합니다.
{% include image.html file="channel/kakaoibuilder/kakao-channel-03.PNG"  caption="" %}

### Step2. 카카오톡채널 설정
1) 채널 개설이 완료되었음을 확인하고, **[대시보드로 이동하기]**버튼을 클릭하여 대시보드로 이동합니다.
{% include image.html file="channel/kakaoibuilder/kakao-channel-04.PNG"  caption="" %}

2) 오른쪽 하단 프로필 설정영역의 **[홈 공개]**,**[검색 허용]**을 **On** 으로 설정합니다.
{% include image.html file="channel/kakaoibuilder/kakao-channel-05.PNG"  caption="" %}

### Step3. 카카오톡채널 연결

1) 카카오 i 오픈 빌더의 **[설정]탭**에서 **[카카오톡채널]**을 연결합니다.
{% include image.html file="channel/kakaoibuilder/kakao-channel-06.PNG"  caption="" %}
{% include image.html file="channel/kakaoibuilder/kakao-channel-07.PNG"  caption="" %}

2) 카카오톡채널 연결을 확인합니다.
{% include image.html file="channel/kakaoibuilder/kakao-channel-08.PNG"  caption="" %}
<hr/>


<h2><center>제약사항</center></h2>

카카오톡 채널의 경우 아래와 같은 제약사항이 존재합니다. 제약사항을 꼭 확인하세요.
<br/>(아래 내용은 실제 제약사항과 조금 다를 수 있습니다.)

| 컴포넌트 | 제약사항 | 상세
|--------|-------|-------|
| 버튼 | 개수 | 최대 3개 |
|     | 버튼명 길이 | 최대 8자 
|     | 지원타입 | 선택지, callFlow, 웹링크, 전화걸기, 퀵리플라이
| 퀵리플라이 | 개수 | 최대 10개 |
|     | 버튼명 길이 | 최대 14자 
| 캐로샐 | 카드 개수 | 최대 10개 |
| 한번에 내보낼 수 있는 메세지노드 | 개수 | 최대 3개<br/><img src="images/channel/kakaoibuilder/kakao-guide-01.PNG" /> <br/> 메세지노드 : Speak,Slot,Carousel 노드를 말합니다.|
| Speak,Slot노드(이미지,버튼 둘다없을때) | 메시지 길이 | 최대 1000자
| Speak,Slot노드(이미지,버튼 하나라도있을때 ) | 메시지 길이 | 최대 380자
| Carousel노드 | 카드명 길이 | 최대 2줄
{: .table .table-striped}

<hr/>

<h2><center>빌드 가이드</center></h2>
### 웰컴메시지
**[2.카카오 i 오픈 빌더 설정하기] - [Step2.봇 제네릭 메뉴 설정]** 을 기억하시나요? 챗봇의 웰컴메시지가 호출되기 위해서는 사용자가 채팅방에 진입해 카카오 i 오픈 빌더에서 설정한 제네릭 메뉴를 클릭해야합니다.
<br/>그렇다면 단비에서 어떻게 웰컴메시지를 만들 수 있을까요?
<br/><br/><br/>
1) **설정(Preference) > 기본답변(General)** 메뉴로 이동 합니다.
{% include image.html file="channel/kakaoibuilder/kakao-guide-02.PNG"  caption="" %}

2) **[Welcome Message]** 영역에 인사말을 입력해 간단하게 웰켐메시지를 만들거나, **[CHATFLOW 연결]**을 선택해 대화흐름을 이용해 텍스트뿐만아니라, 이미지와 같은 다양한 기능으로 웰켐메시지를 만들 수 있습니다.
{% include image.html file="channel/kakaoibuilder/kakao-guide-03.PNG"  caption="" %}
{% include warning.html content=" 웰컴메시지가 정상적으로 호출되기 위해서는 단비에서 설정한 '시작하기버튼명'과 카카오 i 오픈 빌더에서 설정한 봇 제네릭 메뉴의 버튼명이 일치해야합니다." %}

### 최대 제한 길이를 초과한 버튼이 있는 메시지 노드