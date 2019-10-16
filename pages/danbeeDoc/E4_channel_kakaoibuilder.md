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

### 준비하기
챗봇을 카카오톡 채널에 연결하기 위해서는 아래항목들이 준비되어 있어야 합니다.
- 카카오톡 플러스친구 계정
- 카카오 i 오픈빌더 사용 권한: 카카오 i 오픈빌더 OBT 신청 절차가 필요합니다.
- 카카오톡 어플리케이션(App)

### 단비에서 채널 연결 설정하기
#### Step1. 대화채널(Channel) 메뉴 이동
**설정(Preference) > 대화채널(Channel)** 메뉴로 이동 합니다.
#### Step2. 카카오 i 오픈 빌더 채널 선택
카카오 i 오픈 빌더 타일 우측 상단에 **설정** 아이콘을 클릭합니다. 
#### Step3. 채널연결에 필요한 정보 입력
단비에서 카카오 i 오픈 빌더를 이용해 카카오톡 채널에 연결하기위해서는 **액세스토큰**, **시작하기버튼명**을 두 가지를 정보를 설정해야합니다.
액세스토큰은 채널 WEBHOOK 확인용 토큰으로, 로그인시 필요한 패스워드와 같은 기능이라 이해해도 무방합니다.
시작하기버튼명은 사용자가 채팅방에 진입하고나서 챗봇과 대화를 시작하기 위한 버튼의 이름입니다.
여기서 설정한 액세스토큰,시작하기버튼명 값은 **카카오 i 오픈 빌더 설정시에 사용됩니다.** 
#### Step4. 폴백 URL 복사
**폴백 URL**을 복사합니다. 폴백 URL역시 **카카오 i 오픈 빌더 설정시에 사용됩니다.**
#### Step5. 채널 연결
**연결**을 눌러 단비에서의 채널 연결 설정을 마칩니다. 이제 카카오 i 오픈 빌더 설정을 해볼까요?



### 카카오 i 오픈 빌더 설정하기
#### Step1. 카카오 i 오픈빌더 챗봇 생성
카카오 i 오픈빌더에서 단비와 연동할 챗봇을 생성합니다.

1) 우측의 챗봇 생성 버튼을 클릭합니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-01.PNG"  caption="" %}

2) **[카카오톡 챗봇]**을 선택합니다.
{% include image.html file="channel/kakaoibuilder/kakao-02.PNG"  caption="" %}

3) 챗봇의 이름을 설정하고, 생성을 완료합니다.
{% include image.html file="channel/kakaoibuilder/kakao-03.PNG"  caption="" %}

#### Step2. 봇 제네릭 메뉴(시작하기 버튼) 설정
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

#### Step3. 스킬 생성
단비에서 만든 챗봇을 카카오톡에 연동하기 위해서는 카카오 i 오픈빌더에서 챗봇을 생성한 뒤 스킬 기능을 통해 연동하게 됩니다.

1) **[스킬]**탭의 **[생성]**버튼을 클릭합니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-08.PNG"  caption="" %}

2) 스킬을 생성하기 위한 모든값들을 입력합니다. 
- **URL** : 단비에 설정돼있는 **폴백 URL**값을 입력합니다.
- **헤더값** : 단비에서 직접 설정했던 **엑세스 토큰**값을 입력합니다.
    - Key : accessToken 
    - Value : 단비에서 직접 설정했던 **엑세스 토큰**값을 입력합니다.
{% include image.html file="channel/kakaoibuilder/kakao-09.PNG"  caption="" %}

3) **[기본 스킬로 지정]**을 선택하고, **[저장]**버튼을 클릭해 스킬 생성을 마칩니다.
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-10.PNG"  caption="" %}

#### Step4. 폴백블록에 스킬 연동
카카오 i 오픈빌더에서 지정해둔 시나리오 외에 처리하지 못하는 사용자 입력을 핑퐁 빌더에서 처리하기 위해서는, 폴백 블록에 저장한 스킬을 연동해야 합니다.**[폴백 블록]** 메뉴는 **[시나리오]-[기본 시나리오]**에서 찾을 수 있습니다.<br/>
<br/>
1) 스킬을 연결하기 위해서 **[파라미터 설정]**의 우측 상단 **[스킬 선택]**에서 방금 생성한 스킬을 선택합니다. 
{% include image.html file="channel/kakaoibuilder/kakao-ibuilder-11.PNG"  caption="" %}
{% include image.html file="channel/kakaoibuilder/kakao-12.PNG"  caption="" %}

2) **[봇 응답]**을 **[스킬 데이터]**로 설정합니다.
{% include image.html file="channel/kakaoibuilder/kakao-13.PNG"  caption="" %}

3) **[스킬 데이터]**로 설정된것을 확인하고, **[저장]** 버튼을 눌러 카카오 i 오픈 빌더 설정을 마칩니다.
{% include image.html file="channel/kakaoibuilder/kakao-14.PNG"  caption="" %}


## 카카오톡 플러스 친구 만들기 
1. 브라우저에서 <span class="link">[카카오톡 플러스친구](https://center-pf.kakao.com/login){:target="_blank"}</span>에 접속하십시오.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_homepage.png" alt="카카오톡 플러스친구" style="max-width: 800px"></figure>
2. 플러스친구를 만들기 위해 카카오 계정으로 로그인을 합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_login.png" alt="카카오 로그인" style="max-width: 800px"></figure>
3. 플러스 친구 관리자 가입을 합니다. ( 휴대기기에 KakaoTalk앱에서 본인확인 절차 필요 )<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_adminsign.png" alt="플러스친구 관리자가입" style="max-width: 800px"></figure>
4. 플러스친구를 만듭니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_add1.png" alt="플러스친구 추가" style="max-width: 800px"></figure>
5. 플러스친구정보 입력<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_add2.png" alt="플러스친구 추가" style="max-width: 800px"></figure>
6. 플러스친구 개설 완료<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_add3.png" alt="플러스친구 추가" style="max-width: 800px"></figure>

## 카카오톡 플러스 친구 공개설정
* 플러스친구 관리자센터에서 관리 > 상세설정 메뉴에서 공개설정을 설정합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_public.png" alt="플러스친구 공개설정" style="max-width: 800px"></figure>
## 카카오톡 스마트채팅 앱 만들기 
1. 스마트채팅의 API형으로 앱을 등록합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_app1.png" alt="API형 추가" style="max-width: 800px"></figure>
2. API형으로 앱 정보 입력 <figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_app2.png" alt="API형 정보입력" style="max-width: 800px"></figure>
3. danbee.Ai 설정에서 복사한 앱 URL을 입력한 후 API 테스트를합니다. ( 설정한 시작 버튼명이 보입니다. 여기서 저장된 값이 카카오톡에 보여집니다. )
4. 개인정보 수집 및 이용에 동의, 전화번호 를 등록하여 알림설정을 한 후 API형을 저장합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_apisetting.png" alt="API형 정보입력" style="max-width: 800px"></figure>
5. API형 시작하기 버튼을 눌러 서비스를 시작합니다. <figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_apistart.png" alt="API형 시작하기" style="max-width: 800px"></figure>

## 카카오톡 앱 테스트
* 챗봇을 테스트하려면 KakaoTalk앱에서 플러스친구를 검색하여 테스트할수 있습니다.<figure><img class="docimage" src="images/channel/kakao/kakao_app_add_chatbot.png" alt="line app add chatbot" style="max-width: 800px"></figure>

