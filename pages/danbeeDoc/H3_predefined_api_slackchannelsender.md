---
title: 슬랙채널 메시지 전송
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 슬랙의 특정 채널에 메시지를 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_slackchannelsender.html
folder: danbeeDoc
previous: {
    title: AWS 메일 전송,
    url: predefined_api_awssessender.html
}
next: {
    title: 문자(SMS) 전송,
    url: predefined_api_smssender.html
}
---

## API 설명

단비Ai에서 제공하는 여러가지 API 중 슬랙(Slack)의 특정채널에 메시지를 전송하는 API임니다. 
슬랙(Slack)의 보내고자 하는 채널에 초대된 사용자로 Legacy token 을 생성하여 사용가능합니다.

## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| token | String | Yes | 슬랙(Slack) 채널에 초대된 사용자로 생성된 토큰 |
| channel | String | Yes | 슬랙(Slack)의 채널 아이디 |
| username | String | Yes | 보내는 사람이름 ( 예 : 단비 ) |
| text | String | Yes | 메시지 내용 |
| imageurl | String | No | 전송 이미지 |
| iconurl | String | No | 아이콘 이미지 |


## API 사용을 위한 값

### Token 생성
슬랙(Slack)의 Help Center의 가이드에 따라서 토큰을 생성합니다. <br />
. 가이드 : https://get.slack.help/hc/en-us/articles/215770388-Create-and-regenerate-API-tokens

1. 먼저 슬랙에 접속을 하여 로그인을 합니다. ( https://워크스페이스-workspace.slack.com )
2. 로그인 한 계정으로 <span class="link">[토큰 생성 페이지](https://api.slack.com/custom-integrations/legacy-tokens){:target="_blank"}</span>로 이동합니다.
3. Legacy tokens 페이지의 "Legacy information" > "Legacy token generator" 섹션으로 이동합니다.
4. 사용하고자 하는 워크스페이스(workspace) 의 사용자(User)로 "Create token" 버튼을 큭릭하여 토큰을 생성합니다.  
5. 발급된 토큰을 API 의 token 입력값에 설정합니다.

### 채널(Channel) ID 찾기
1. 먼저 슬랙에 접속을 하여 로그인을 합니다. ( https://워크스페이스-workspace.slack.com )
2. 찾고자 하는 채널을 클릭하여 접속을 합니다. ( Private 채널은 초대를 받아야 접속이 가능 )
3. 브라우저의 주소창에서 채널(Channel) ID를 찾습니다. ( https://워크스페이스-workspace.slack.com/messages/<font color="red">채널아이디</font>/details/ ) )
9. 찾은 채널(Channel) ID를 API 의 channel 입력값에 설정합니다.

<br />


{% include bottom.html %}
