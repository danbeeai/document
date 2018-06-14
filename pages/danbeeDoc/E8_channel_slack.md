---
title: Slack
tags: [channel]
keywords: Basic Conversation
summary: 몇가지 단계를 거치면 Slack Messenger에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_slack.html
folder: danbeeDoc
previous: {
    title: 라인,
    url: channel_line.html
}
---

## Slack 채널 연결
 {% include callout.html content="화면 위치 : [설정(Preference)] > [대화채널(Channel)]" type="default" %} 


### Slack 설정 개요
Slack 채널 연계 설정을 하려면 기본적으로 다음이 필요합니다.

* Slack 계정
* Slack App을 추가할 Slack Workspace
{% include note.html content="사용자가 Slack App을 생성한 후 Slack Workspace에 App을 추가하면 연계된 챗봇과 대화할 수 있습니다." %}


### 1. Slack App 만들기
<span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Slack Developer Console](https://api.slack.com/apps/new){:target="_blank"}</span> 에서 내가 만든 챗봇과 연결할 Slack App을 생성합니다.<figure><img class="docimage" src="images/channel/slack/slack_01_create_app.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* App 이름과 Slack Workspace를 선택하여 Create App 버튼을 눌러 새로운 App을 생성합니다.



### 2. Bot User 추가하기
생성한 Slack App에서 대화할 Bot User를 생성합니다.
<figure><img class="docimage" src="images/channel/slack/slack_02_add_bot_user.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* Bot User 섹션에서 Add Bot User 버튼을 클릭합니다.
* Always Show My Bot as Online을 On 상태로 바꿉니다.
* Add Bot User 버튼을 클릭하여 Bot User를 추가합니다.



### 3. Slack App 기본정보 Danbee.Ai 에 입력 및 연결하기
대화 채널 연결을 위해 Slack App의 기본정보를 Danbee.ai 입력하고 연결합니다.
<figure><img class="docimage" src="images/channel/slack/slack_03_basic_info.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* Basic Information 섹션에서 Client ID, Client Secret 그리고 Verification Token 을 복사합니다.
<figure><img class="docimage" src="images/channel/slack/slack_03_basic_info_d.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* 복사한 값을 대화채널 메뉴의 Slack 채널 설정 팝업창에 각각 입력한 후 연결 버튼을 클릭합니다.



### 4. Slack 채널 연결 정보 입력하기
대화 채널 연결을 위해 Danbee.ai에서 제공하는 url 정보를 Slack App 설정에 입력하고 연결합니다.

<figure><img class="docimage" src="images/channel/slack/slack_04_url.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* Slack 채널 설정 팝업창의 oAuth URL 값을 복사하고 Slack App 설정의 OAuth & Permission 섹션으로 이동합니다.

<figure><img class="docimage" src="images/channel/slack/slack_04_url_auth.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* 복사한 oAuth URL 값을 Redirect URLs 에 추가합니다.

* 이어서 바로 아래에 있는 Scopes 에 다음 10개 항목들을 검색하여 추가하고 저장합니다.
{% include callout.html content="추가할 Scope : bot, channels:read, channels:write, chat:write:bot, chat:write:user, groups:read, groups:write, im:read, im:write, team:read" type="default" %}
  
  
<figure><img class="docimage" src="images/channel/slack/slack_04_url_auth2.png" alt="Facebook for developers" style="max-width: 800px"></figure>

* 이번엔 Slack 채널 설정 팝업창의 Event Request URL 값을 복사하고 Slack App 설정의 Event Subscriptions 섹션으로 이동합니다.

<figure><img class="docimage" src="images/channel/slack/slack_04_url_requestUrl.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* Enable Events 를 On 상태로 만들어 복사해둔 URL을 Request URL에 입력합니다.
(입력시 자동으로 URL을 체크합니다.)

* 이어서 아래에 있는 Subscribe to Bot Events 에서 Add Bot User Event 버튼을 클릭하여 다음 4가지 항목을 추가하고 저장합니다.
{% include callout.html content="추가할 Bot Event : message.im, message.group, message.channel, im_created" type="default" %}
    
<figure><img class="docimage" src="images/channel/slack/slack_04_url_requestUrl2.png" alt="Facebook for developers" style="max-width: 800px"></figure>

* 마지막으로 Slack 채널 설정 팝업창의 Action URL 값을 복사하여 Slack App 설정의 Interactive Components 섹션으로 이동합니다.

<figure><img class="docimage" src="images/channel/slack/slack_04_url_requestUrl3.png" alt="Facebook for developers" style="max-width: 800px"></figure>

* Enable Interactive Components 버튼을 한번 클릭하여 입력창을 생성한 뒤 Request URL에 복사한 Action URL 값을 입력한 뒤 저장합니다.



### 5. App Install 하기, Slack에 App 추가하기
대화 채널 연계 마무리 단계입니다. 내가 만든 챗봇과 연결된 Slack App을 설치하고 내가 속한 Workspace 추가합니다.

<figure><img class="docimage" src="images/channel/slack/slack_05_install_app.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* Install App 섹션으로 이동하여 Install App to Workspace를 클릭하여 설치합니다.

* Manage Distribution 섹션으로 이동합니다.

* Add to Slack 버튼을 클릭하여 App을 Slack Workspace에 추가합니다. 
<figure><img class="docimage" src="images/channel/slack/slack_05_install_app2.png" alt="Facebook for developers" style="max-width: 800px"></figure>


Slack 채널 연계가 완료되었습니다. 이제 Slack에서도 내가 만든 챗봇과 대화할 수 있습니다.



### 제약사항
Slack 채널의 경우 아래와 같은 제약사항이 존재합니다. 제약사항을 꼭 확인하세요.

| 제약사항 | 상세 |
|--------|-------|
| 버튼 | 최대 5개 |
| 이미지 | image url만 가능 | 
| 캐로샐 | 최대 20개 | 
| 메시지 전송 제한 | <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Access Tier별 확인](https://api.slack.com/docs/rate-limits#tiers){:target="_blank"}</span> |

{% include warning.html content=" Danbee.Ai에서 채널 연결을 재설정할 경우 '5. App Install 하기, Slack에 App 추가하기' 단계를 다시 수행해야 합니다." %}
