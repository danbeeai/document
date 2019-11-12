---
title: AWS 메일 전송
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 AWS SES 서비스를 통해 이메일을 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_awssessender.html
folder: danbeeDoc
previous: {
    title: 네이버 메일 전송,
    url: predefined_api_navermailsender.html
}
next: {
    title: 슬랙채널 메시지 전송,
    url: predefined_api_slackchannelsender.html
}
---

## API 설명

danbee.Ai에서 제공하는 여러가지 API 중 AWS의 SES( Simple Email Service )을 통해 이메일을 전송하는 API입니다.  <br />
보내는 이메일 주소가 확인된 사용자만 사용가능하며 QnA 게시판 또는 우측하단의 피드백 버튼을 통해 
보내는 이메일에 대해 확인요청 후 사용하시면 됩니다. <br />
danbee.Ai 의 가랑비 등급 이상부터 이메일 확인요청을 진행하며, 대량메일 발송 시 사전 연락을 주셔야 합니다. <br />
 
## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| fromEmail | String | Yes | 보내는 이메일 ( 예 : danbee@abcd.com ) |
| toEmail | String | Yes | 받는 사람 이메일 ( contact@danbee.ai ) |
| subject | String | Yes | 이메일 제목 |
| message | String | Yes | 이메일 내용 ( html 사용가능 ) |

## API 사용을 위한 보내는 이메일 검증

AWS SES 이메일 전송 API 를 사용하기 위해서는 먼저 danbee.Ai 서비스 담당자에게 보내는 이메일을 검증받아야 합니다.

1. danbee.Ai의 플램폼 로그인 후 QnA 게시판 또는 우측하단의 피드백 버튼을 통해 보내는 이메일에 대해 검증요청을 합니다.
2. 1일 이내에 요청한 메일로 검증요청 메일이 발송됩니다.
3. 메일의 내용을 확인 후 검증 확인버튼을 클릭하여 검증을 완료합니다.
4. 검증확인된 이메일을 API 의 fromEmail 입력값에 설정합니다.

<br />
