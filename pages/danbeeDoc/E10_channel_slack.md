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
 {% include callout.html content="화면 위치 : [설정(Preference)] > [대화채널(Channel)]" type="default" %} 


### Slack 설정 개요
Slack 채널 연계 설정을 하려면 기본적으로 다음이 필요합니다.

* Slack 계정
* Slack App을 추가할 Slack Workspace
{% include note.html content="사용자가 Slack App을 생성한 후 Slack Workspace에 App을 추가하면 연계된 챗봇과 대화할 수 있습니다." %}


### 1. Slack App 만들기
<span class="link">[Slack Developer Console](https://api.slack.com/apps/new){:target="_blank"}</span> 에서 내가 만든 챗봇과 연결할 Slack App을 생성합니다.<figure><img class="docimage" src="images/channel/newslack/1.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>
* App 이름과 Slack Workspace를 선택하여 Create App 버튼을 눌러 새로운 App을 생성합니다.


### 2. OAuth & Permissions 설정
화면 아래 Scopes영역의 'Bot Token Scopes','User Token Scopes' 두 항목 모두에 아래 Scope들을 추가합니다.
{% include callout.html content="추가할 Scope : channels:read, chat:write, groups:read, groups:write, im:read, im:write, team:read" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/3.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>

페이지 최상단의 'Install App to Workspace'가 활성화되었다면, 클릭하여 Workspace에 App을 등록합니다.

### 3. Event Subscriptions 설정
[Event Subscriptions] 메뉴의 Enable Events를 활성화합니다.
Request URL에 단비Ai 채널설정화면의 Event Request URL값을 등록합니다.
이어서 아래에 있는 Subscribe to bot events에서 [Add Bot User Event] 버튼을 클릭하여 아래 항목들을 추가하고, 저장합니다.
{% include callout.html content="추가할 event : message.channels, message.groups, message.im" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/4.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>


### 4. Interactivity & Shortcuts 설정
[Interactivity & Shortcuts] 메뉴의 Interactivity를 활성화합니다.
Request URL에 단비Ai 채널설정화면의 Action URL값을 등록하고, 저장합니다.
<figure><img class="docimage" src="images/channel/newslack/5.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>

### 5. Incoming Webhooks
[Incoming Webhooks] 메뉴의 Active Incoming Webhooks를 활성화합니다. 
<figure><img class="docimage" src="images/channel/newslack/6.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>

### 6. Install App
[Install App] 메뉴의 [Reinstall App] 버튼을 클릭하고, 앱을 게시할 채널을 선택하고 확인을 클릭합니다.
<figure><img class="docimage" src="images/channel/newslack/7.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>
<br/>
생성된 Webhook URL을 Copy하여 단비Ai 채널설정화면의 'Incoming Webhook URL'값에 붙여 넣습니다.
<figure><img class="docimage" src="images/channel/newslack/8.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>

### 7. Basic Information
[Basic Information] 메뉴의 아래 항목들을 단비Ai 채널설정화면의 'Client ID', 'Client Secret', 'Verification Token' 값에 각각 붙여넣습니다.
{% include callout.html content="추가할 항목 : Client ID, Client Secret, Verification Token" type="default" %}
<figure><img class="docimage" src="images/channel/newslack/9.PNG" alt="Facebook for developers" style="max-width: 800px"></figure>

### 8. App Home
[App Home] 메뉴의 'Always Show My Bot as Online'을 활성화합니다.
