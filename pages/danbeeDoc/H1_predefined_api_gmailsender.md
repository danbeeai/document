---
title: Gmail 메일 전송
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 Google Gmail 게정을 통해 이메일을 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_gmailsender.html
folder: danbeeDoc
previous: {
    title: 단비 제공 API,
    url: predefined_api.html
}
next: {
    title: 네이버 메일 전송,
    url: predefined_api_navermailsender.html
}
---

## API 설명

단비Ai에서 제공하는 여러가지 API 중 Google Gmail 계정을 통해 이메일을 전송하는 API임니다. <br /> 
해당 API를 사용하려면 OAuth2 를 사용하지 않는 낮은 보안설정을 셋팅해야 사용가능합니다. <br />
( Gmail을 사용 시 OAuth2 인증을 통해서 사용하는 것을 권장하고 있으며, 
  인증되지 않은 앱이나 허용되지 않는 지역에서 접속등의 경우 보안상 계정 액세스가 차단되는 경우가 있습니다.)


## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| user | String | Yes | Gmail 계정 ( 예 : danbee@gmail.com ) |
| password | String | Yes | Gmail 계정의 비밀번호 또는 앱 비밀번호 |
| fromUsername | String | Yes | 보내는 사람이름 ( 예 : 단비 ) |
| toEmail | String | Yes | 받는 사람 이메일 ( contact@danbee.ai ) |
| subject | String | Yes | 이메일 제목 |
| message | String | Yes | 이메일 내용 ( html 사용가능 ) |


## 보안관련 Gmail 로그인 정책 변경

현재 구글의 보안정책 변경으로 외부앱에서 로그인을 제한하고 있습니다.  <br />
이에 따라 구글 이메일 발송이 아이디 비밀번호로는 발송이 안됩니다. ( 보안 수준이 낮은 앱을 허용해도 안됨 ) <br />
2단계인증을 사용하여 앱 비밀번호를 사용해서 진행하시면 됩니다.  <br />


## 2단계 인증을 사용하고 앱비밀번호로 로그인

2단계 인증을 사용하는 계정이라면 앱 비밀번호를 생성해서 사용해야 합니다. <br />
구글에서 제공하는 가이드에 따라서 비밀번호를 생성합니다. <br />

1. <span class="link">[앱 비밀번호로 로그인하기](https://support.google.com/mail/answer/185833?hl=ko){:target="_blank"}</span>페이지로 이동합니다.
2. 앱 비밀번호 생성 방법 섹션을 클릭하여 가이드에 따라 앱 비밀번호를 생성합니다.
3. 앱 비밀번호를 생성 앱 및 기기에 danbeeai 로 설정하여 추후에 관리하시면 편합니다.
4. 생성된 앱 비밀번호 16자리를 단비.Ai 의 Gmail 메일 전송 API 의 password 에 셋팅합니다.

{% include image.html file="/external_API/api_gmail_setting1.png" caption="Gmail 앱비밀번호생성1" %}
{% include image.html file="/external_API/api_gmail_setting2.png" caption="Gmail 앱비밀번호생성2" %}


## Google Workspace의 Gmail 전송 한도

Google Workspace의 Gmail 전송 한도가 있습니다. <br />
고객센터 : https://support.google.com/a/answer/166852?hl=ko <br />


<br />


{% include bottom.html %}
