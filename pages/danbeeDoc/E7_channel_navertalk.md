---
title: 네이버톡톡
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 네이버톡톡에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_navertalk.html
folder: danbeeDoc
previous: {
    title: 카카오톡,
    url: channel_kakaotalk.html
}
next: {
    title: API 관리,
    url: external_API_management.html
}
---

## 네이버톡톡 채널 연결 
 {% include callout.html content="화면 위치 : [설정(Preference)] > [대화채널(Channel)]" type="default" %}

네이버톡톡 채널 연계 설정을 위해서는 다음이 필요합니다.

* 네이버 계정
* 네이버톡톡 계정

### 네이버톡톡 계정 만들기
1. 브라우저에서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[네이버톡톡 파트너센터](https://partner.talk.naver.com/){:target="_blank"}</span>에 접속하십시오.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_01_partner_center.png" alt="네이버톡톡 파트너센터" style="max-width: 800px"></figure>
2. 네이버톡톡 계정을 만들기 위해 네이버 계정으로 로그인을 합니다.

3. 약관 동의 후 톡톡 계정 만들기 버튼을 선택합니다.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_02_create_talktalk.png" alt="톡톡 계정 만들기" style="max-width: 800px"></figure>
4. 해당 팝업이 뜨면 서비스를 연결합니다. 연결할 서비스가 없다면 '서비스 연결 나중에 하기'버튼을 클릭합니다. 
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_03_create_talktalk_service.png" alt="톡톡 계정 만들기 - 서비스 연결" style="max-width: 800px"></figure>
5. 계정대표 정보 및 계정 프로필 정보 입력 후 사용을 신청합니다.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_04_create_talktalk_repInfo.png" alt="톡톡 계정 만들기 - 계정 정보 입력" style="max-width: 800px"></figure>
    {% include note.html content="프로필 정보 입력 시 프로필명 앞에 [테스트]를 삽입하면 톡톡 가맹점 찾기에서 제외 처리 됩니다. 즉, 검색으로부터 유입되는 유저 방문을 차단할 수 있습니다. (ex: [테스트]danbeeAI봇)" %}
6. 톡톡 계정 검수가 끝나면 계정관리 버튼을 통해 계정관리 홈으로 들어갈 수 있습니다. 해당 리스트에서 챗봇에 접근할 수 있는 URL이 제공됩니다. 
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_06_talktalk_complete.png" alt="톡톡 계정 검수 완료" style="max-width: 800px"></figure>
7. 계정관리 홈에서 [챗봇 API] - [API 설정]을 선택합니다. Closed Beta 서비스이므로 신청후 검수가 통과되고 나면 API설정을 할 수 있습니다.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_07_talktalk_botAPI.png" alt="플러스친구 추가" style="max-width: 800px"></figure>
8. 약관 동의 후 설정 페이지가 뜨면 보내기 API Authorization 생성을 누릅니다.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_08_talktalk_botAPI_auth_create.png" alt="보내기 API 인증키 생성" style="max-width: 800px"></figure>
9. 생성된 Authorization을 복사합니다.

### danbee.Ai 채널 연결 설정
1. [고급설정(Advanced)] > [채널 연결(Connect of Channel)] 메뉴로 이동 하십시오.
2. 네이버톡톡 타일 우측 상단에 설정 아이콘을 클릭하십시오.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_09_danbee_connect.png" alt="네이버톡톡 셋팅" style="max-width: 800px"></figure>
3. 다음 필드에 관련 값을 입력하십시오.
    * 인증키 : 네이버톡톡 파트너센터에서 만든 보내기 API Authorization
4. 콜백 URL을 복사하십시오.
5. 연결 버튼을 클릭하십시오.

### 네이버톡톡 Webhook 설정
1. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[네이버톡톡 파트너센터](https://partner.talk.naver.com/){:target="_blank"}</span> 의 [계정관리 홈] - [챗봇 API] - [API설정] 페이지로 돌아갑니다.
2. Webhook의 이벤트 받을 URL 란에 danbee.Ai에서 복사한 콜백 URL을 입력하고 등록을 클릭합니다.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_10_webhook.png" alt="네이버톡톡 Webhook설정" style="max-width: 800px"></figure>
3. 이벤트 변경 버튼을 클릭하여 send, open을 선택합니다.
    <figure><img class="docimage" src="images/channel/navertalk/navertalk_11_event_setting.png" alt="네이버톡톡 이벤트 설정" style="max-width: 800px"></figure>

## 네이버톡톡 테스트
* 연결한 챗봇은 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[네이버 톡톡 홈페이지](https://talk.naver.com/){:target="_blank"}</span>의 톡톡 가맹정 찾기 또는 URL로 직접 접속하여 테스트할 수 있습니다. 
* 직접 접속 URL은 관리 계정 리스트에서 확인할 수 있습니다. 또는 톡톡앱아이디를 확인하여 talk.naver.com/{톡톡앱아이디} 로 접속할 수 있습니다.
<figure><img class="docimage" src="images/channel/navertalk/navertalk_13_app_id.png" alt="line app add chatbot" style="max-width: 800px"></figure>

