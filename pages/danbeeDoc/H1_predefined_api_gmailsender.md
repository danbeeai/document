---
title: Gmail 메일 전송
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 Google Gmail 게정을 통해 이메일을 전송하는 API입니다.
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

danbee.Ai에서 제공하는 여러가지 API 중 Google Gmail 게정을 통해 이메일을 전송하는 API임니다. <br /> 
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

## API 사용을 위한 Gmail 설정

구글에서 제공하는 가이드에 따라서 보안수준이 낮은 앱이 계정에 액세스하도록 허용설정을 진행합니다. <br />
. 구글 계정 고객센터 : https://support.google.com/accounts/answer/6010255?hl=ko <br />
. G Suite 관리자 고객센터 : https://support.google.com/a/answer/6260879 <br />

구글에서는 이 옵션을 사용하면 다른 사람이 내 계정에 쉽게 침입할 수 있으므로 사용을 권장하지는 않고 있습니다.
하지만 이메일 전송 API 를 사용하기 위해서는 액세스 허용을 해야 합니다. 
1. <span class="link">[Google 계정의 보안 수준이 낮은 앱](https://myaccount.google.com/lesssecureapps){:target="_blank"}</span>섹션으로 이동합니다.
2. 보안 수준이 낮은 앱 허용을 사용으로 설정합니다.
3. 이 방법을 사용할때는 추가 단계를 거치도록 요청하는 "보안문자(captcha)" 사용을 비활성화 시키고 액세스 허용을 해야 합니다. <span class="link">[추가 액세스 허용](https://accounts.google.com/b/0/displayunlockcaptcha){:target="_blank"}</span>

## 2단계 인증을 사용하는 계정

2단계 인증을 사용하는 계정이라면 앱 비밀번호를 생성해서 사용해야 합니다. <br />
구글에서 제공하는 가이드에 따라서 비밀번호를 생성합니다. <br />

1. <span class="link">[앱 비밀번호로 로그인하기](https://support.google.com/mail/answer/185833?hl=ko){:target="_blank"}</span>페이지로 이동합니다.
2. 앱 비밀번호 생성 방법 섹션을 클릭하여 가이드에 따라 앱 비밀번호를 생성합니다.
3. 생성된 앱 비밀번호 16자리를 danbee.Ai 의 Gmail 메일 전송 API 의 password 에 셋팅합니다.

<br />
