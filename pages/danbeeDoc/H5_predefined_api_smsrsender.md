---
title: 예약문자(SMS) 전송
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 문자 메시지를 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_smsrsender.html
folder: danbeeDoc
previous: {
    title: 문자(SMS) 전송,
    url: predefined_api_smssender.html
}
next: {
    title: 문자(LMS) 전송,
    url: predefined_api_lmssender.html
}
---

## API 설명

danbee.Ai에서 제공하는 여러가지 API 중 예약문자 메시지를 전송하는 API임니다. <br>
요금제는 Standard 이상부터 사용가능합니다. <br>
SMS 문자의 경우 45자까지 전송이 가능하며 한건당 12원의 추가요금이 발생합니다. <br>
45자이상인 경우 길이가 긴 문자(LMS)로 전송되며 한건당 50원의 추가요금이 발생합니다. <br>

## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| receiver | String | Yes | 수신자 전화번호 - 컴마(,)분기 입력으로 최대 1천명 |
| msg | String | Yes | 메시지 내용(45자이상은 LMS로 자동변환) |
| rdate | String | Yes | 예약일 (현재일이상 YYYYMMDD) |
| rtime  | String | Yes | 예약시간 - 현재시간기준 10분이후(HHII) |
| test_yn | String | Yes | 테스트시 Y 적용 |

## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| resultCode | String | 결과코드 ( success / fail ) |
| resultMessage | String | 결과 메시지 내용 |
| apiResultCode | String | API 결과 코드 |
| apiResultMessage | String | API 결과 메시지 |
| apiResultMsgId | String | API 결과 ID |
| apiResultMsgType | String | API 전송 메시지 유형 ( SMS / LMS ) |

## API 사용을 위한 값

테스트 시에는 test_yn 값에 꼭 Y 로 셋팅하여 테스트하시기 바랍니다. <br />
문자 발송은 단비의 전화번호로만 발송되며 발송자 전화번호의 변경을 원하는 경우 contact@danbee.ai 로 문의바랍니다.
<br />


{% include bottom.html %}
