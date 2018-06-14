---
title: LINE
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 네이버 라인에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_line.html
folder: danbeeDoc
previous: {
    title: 페이스북,
    url: channel_facebook.html
}
next: {
    title: 텔레그램,
    url: channel_telegram.html
}
---

## LINE 채널 연결 
 {% include callout.html content="화면 위치 : [설정(Preference)] > [대화채널(Channel)]" type="default" %}


### LINE 설정
LINE 채널 연계 설정을 하려면 다음이 필요합니다.

* LINE 계정
* 휴대 기기에 설치된 LINE 앱
{% include note.html content="계정 가입은 모바일 앱을 통해 완료됩니다." %}


### LINE 봇 만들기
1. LINE 모바일 앱에서 설정> 계정> 이메일 계정 등록으로 이동하여 계정을 만듭니다. (이미 E-mail이 등록되어 있다면 할필요가 없습니다.)
2. 브라우저에서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[LINE 비즈니스 센터](http://at.line.me/ko/){:target="_blank"}</span>에 접속하십시오.<figure><img class="docimage" src="images/channel/line/line_bizcenter_homepage.png" alt="LINE 비즈니스 센터" style="max-width: 800px"></figure>
3. LINE@ 계정(일반계정)을 생성 후 관리화면에 로그인 합니다. (휴대기기에 LINE앱에서 본인확인 절차 필요)
4. LINE@ MANAGER에서 계정 리스트를 확인 합니다.
5. 브라우저에서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[LINE developers](https://developers.line.me/en/){:target="_blank"}</span>에 접속하여 개발자 계정을 등록하십시오.<figure><img class="docimage" src="images/channel/line/line_developers_homepage.png" alt="LINE developers" style="max-width: 800px"></figure>
6. create provider 버튼을 이용하여 생성 후 생성된 provider을 선택합니다.
7. Messaging API 버튼으로 채널 셋팅 화면으로 이동합니다.<figure><img class="docimage" src="images/channel/line/line_messagingapi_create.png" alt="LINE channel create" style="max-width: 800px"></figure>
8. 페이지에 다음 정보를 입력하십시오.<figure><img class="docimage" src="images/channel/line/line_channel_setting.png" alt="LINE channel setting" style="max-width: 800px"></figure>
  * App name : 챗봇 이름 
  * App description : 챗봇 설명
  * plan : Developer Trial / Free 중 선택
  * Category : 챗봇 서비스 분류 
  * Subcategory : 챗봇 서비스 소분류
  * Email address : 연결 이메일
9. 정보 입력 및 확인 후 LINE@ 서비스 정책에 대한 내용을 확인체크하여 채널을 생성합니다.<figure><img class="docimage" src="images/channel/line/line_channel_setting_term.png" alt="LINE channel term" style="max-width: 800px"></figure>

### LINE 채널 연계 정보 설정
1. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[LINE developers](https://developers.line.me/en/){:target="_blank"}</span>에 계정> Providers 에 채널 목록을 확인합니다.
2. 생성한 채널의 설정 페이지로 이동합니다.
3. Messaging settings 에서 Channel access token (long-lived)을 Issue 버튼을 활용하여 생성합니다.<figure><img class="docimage" src="images/channel/line/line_channel_create_token.png" alt="LINE channel create token" style="max-width: 800px"></figure>
4. Use webhooks 를 Enabled 로 설정합니다.<figure><img class="docimage" src="images/channel/line/line_channel_use_webhook.png" alt="LINE channel use webhook" style="max-width: 800px"></figure>
5. 다음 정보를 기록하십시오.
  * Channel ID : 채널 ID
  * Channel secret : 채널 비밀번호
  * Channel access token : 채널 액세스 토큰

### danbee.Ai 채널 연결 설정
1. [고급설정(Advanced)] > [채널 연결(Connect of Channel)] 메뉴로 이동 하십시오.
2. LINE 타일 우측 상단에 설정 아이콘을 클릭하십시오.
3. 다음 필드에 관련 값을 입력하십시오.<figure><img class="docimage" src="images/channel/line/line_danbee_setting.png" alt="danbee line channel setting" style="max-width: 800px"></figure>
  * Channel ID : 채널 ID
  * Channel secret : 채널 비밀번호
  * Channel access token : 채널 액세스 토큰
4. Webhook URL 복사하십시오.
5. 연결 버튼을 클릭하십시오.

### LINE 채널 연계 정보 설정 수정 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[LINE developers](https://developers.line.me/en/){:target="_blank"}</span> 페이지로 돌아가서 
Messaging settings 의 Webhook URL로 스크롤하여 danbee.Ai에서 복사 한 URL 을 입력하십시오. 
확인 버튼을 클릭하여 테스트가 완료되면 녹색 확인 아이콘이 표시됩니다.<figure><img class="docimage" src="images/channel/line/line_channel_webhook_setting.png" alt="line channel url setting" style="max-width: 800px"></figure>

### LINE 채널 자동 대답 설정 변경 
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[LINE developers](https://developers.line.me/en/){:target="_blank"}</span> 페이지로 돌아가서 
Using LINE@ features 의 Auto-reply messages을 disabled 처리합니다.
최초 방문시 메시지인 Greeting messages 설정도 disabled 처리합니다.<figure><img class="docimage" src="images/channel/line/line_channel_features_setting.png" alt="line channel url setting" style="max-width: 800px"></figure>

### LINE 앱 테스트
챗봇을 테스트하려면 LINE 앱의 기본 화면에서 3개의 수평점을 누릅니다. 
그런 다음 친구추가 아이콘을 클릭 하여 QR 코드 아이콘을 탭하고 채널의 설정 페이지에서 QR 코드를 스캔하십시오.<figure><img class="docimage" src="images/channel/line/line_app_add_chatbot.png" alt="line app add chatbot" style="max-width: 800px"></figure>
그리고 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[LINE 비즈니스 센터](http://at.line.me/ko/){:target="_blank"}</span>에 LINE@ MANAGER 계약정보 > 등록정보에 LINE ID로 검색하여 친구추가를 합니다.<figure><img class="docimage" src="images/channel/line/line_app_add_chatbot_id.png" alt="line app add chatbot" style="max-width: 800px"></figure>
그러면 해당 앱의 관리자가 친구가 추가됩니다.


