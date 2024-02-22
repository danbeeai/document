---
title: Slack 
tags: [channel]
keywords: Basic Conversation
summary: 몇가지 단계를 거치면 Slack Messenger에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_newslack.html
folder: danbeeDoc
previous: {
    title: 라인,
    url: channel_line.html
}
---

## Slack 채널 연결
 {% include callout.html content="화면 위치 : [챗봇 만들기] > [챗봇 배포] > [메신저 연결]" type="default" %} 


### Slack 설정 개요
Slack 채널 연계 설정을 하려면 기본적으로 다음이 필요합니다.

* Slack 계정
* Slack App을 추가할 Slack Workspace
{% include note.html content="사용자가 Slack App을 생성한 후 Slack Workspace에 App을 추가하면 연계된 챗봇과 대화할 수 있습니다." %}


### 1. Slack App 만들기
<span class="link">[Slack Developer Console](https://api.slack.com/apps/new){:target="_blank"}</span> 에서 내가 만든 챗봇과 연결할 Slack App을 생성합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_createApp.png" alt="Facebook for developers" style="max-width: 800px"></figure>
* App 이름과 Slack Workspace를 선택하여 Create App 버튼을 눌러 새로운 App을 생성합니다.
<hr/>

### 2. OAuth & Permissions 설정
[OAuth & Permissions] 메뉴로 이동합니다. 'Redirect URLs'에 단비Ai Slack채널 설정화면의 'OAuth URL'값을 입력하고, [Save URLs] 버튼을 클릭하여 저장합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_oauthUrl.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<br/>
아래 Scopes영역의 'Bot Token Scopes','User Token Scopes' 두 항목에 Scope를 추가할 차례입니다.
<br/>
먼저, 'Bot Token Scopes'에 아래 항목들을 추가합니다.
{% include callout.html content="추가할 Scope : channels:read, chat:write, groups:read, groups:write, im:read, im:write, team:read" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/newslack_botscopes.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<br/>
이어서, 'User Token Scopes'에도 동일한 항목들을 추가합니다.
{% include callout.html content="추가할 Scope : channels:read, chat:write, groups:read, groups:write, im:read, im:write, team:read" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/newslack_userscopes.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<hr/>


### 3. App Home
[App Home] 메뉴로 이동합니다. App Display 정보들을 입력하고, 'Always Show My Bot as Online'을 활성화합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_apphome.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<br/>
[OAuth & Permissions] 메뉴로 이동하여, [Install App to Workspace] 버튼을 클릭하여 앱 설치를 완료합니다. 
설치 후 화면에 'OAuth Access Token', 'Bot User OAuth Access Token' 두개의 토큰이 보인다면 OK.
<figure><img class="docimage" src="images/channel/newslack/newslack_installapp.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<hr/>

### 4. Event Subscriptions 설정
[Event Subscriptions] 메뉴로 이동합니다. 'Enable Events'를 활성화합니다.
Request URL에 단비Ai Slack채널 설정화면의 'Event Request URL'값을 입력합니다.
이어서 아래에 있는 Subscribe to bot events에서 [Add Bot User Event] 버튼을 클릭하여 아래 항목들을 추가하고, 저장합니다.
{% include callout.html content="추가할 event : message.channels, message.groups, message.im" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/newslack_eventSubscriptions.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<hr/>

### 5. Interactivity & Shortcuts 설정
[Interactivity & Shortcuts] 메뉴로 이동합니다. 'Interactivity'를 활성화합니다.
Request URL에 단비Ai Slack채널 설정화면의 'Action URL'값을 입력하고, 저장합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_action.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<hr/>

### 6. Incoming Webhooks
[Incoming Webhooks] 메뉴로 이동하여 'Active Incoming Webhooks'를 활성화합니다. 
<figure><img class="docimage" src="images/channel/newslack/newslack_incomingwebhooks.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<hr/>

### 7. Basic Information
[Basic Information] 메뉴로 이동합니다. 아래 항목들을 단비Ai Slack채널 설정화면의 'Client ID', 'Client Secret', 'Verification Token' 값에 각각 입력하고, [연결]버튼을 클릭하여 채널을 연결합니다.
{% include callout.html content="추가할 항목 : Client ID, Client Secret, Verification Token" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/newslack_basicInfomation.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<hr/>

### 8. Manage Distribution
[Manage Distribution] 메뉴로 이동합니다. [Add to Slack]버튼을 클릭하고, 게시할 채널에 자신 앱을 선택하고 [허용]버튼을 클릭합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_manage.png" alt="Facebook for developers" style="max-width: 800px"></figure>
<br/>
'auth success'문구가 보이면 정상적으로 완료되었음을 의미합니다. 
<hr/>

### 마무리
브라우저의 뒤로가기 버튼을 눌러 App 설정 페이지로 이동한 뒤,[Incoming Webhooks] 메뉴로 이동합니다. 
<br/>
아래 'Webhook URLs for Your Workspace'의 'Webhook URL'을 Copy합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_incomingwebhookurl.png" alt="Facebook for developers" style="max-width: 800px"></figure> 
<br/>
단비Ai Slack채널 설정화면의 [끊기]버튼을 클릭하여 입력폼을 활성화 시키고, 'Incoming Webhook URL'에 복사한 값을 붙여넣습니다. 
다시 [연결]버튼을 클릭하여 채널을 연결합니다.
<figure><img class="docimage" src="images/channel/newslack/newslack_danbee.png" alt="Facebook for developers" style="max-width: 800px"></figure> 


