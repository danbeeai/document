---
title: 구글 스프레드시트 행 추가
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 구글 스프레드시트 행추가 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_googlespreadsheetrowappend.html
folder: danbeeDoc
previous: {
    title: 예약문자(LMS) 전송,
    url: predefined_api_lmsrsender.html
}
next: {
    title: 구글 스프레드시트 행 조회,
    url: predefined_api_googlespreadsheetrowget.html
}
---

## API 설명

단비Ai에서 제공하는 여러가지 API 중 구글 스프레드시트 행 추가 API임니다. <br>
요금제는 Standard 이상부터 사용가능합니다. <br>

### 구글스프레드시트 권한을 부여해야 됩니다.
구글스프레드시트에서 [공유] > 사용자 목록에 아래 이메일을 등록하고 [수정가능]권한을 부여합니다. 

    sheets-api01@danbee-ai.iam.gserviceaccount.com
 
## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| spreadsheetId | String | Yes | 스프레드시트아이디 |
| sheetTabName | String | Yes | 시트하단탭이름 |
| B | String | No | B열 |
| C | String | No | C열 |
| D | String | No | D열 |
| E | String | No | E열(Z열까지가능) |

## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_code | String | 결과코드 ( success / fail ) |
| result_message | String | 결과 메시지 내용 |
| spreadsheetId | String | 스프레드시트아이디 |
| updatedRowIndex | String | 등록 행 위치 |
| updatedRange | String | 등록 범위 ( 시트내 탭이름 포함 A~Z 범위 ) |
| updatedvalues | JSON | 등록 결과 ( { A:A열값, B:B열값, .... } ) |
| updatedDate | String | 추가 일시 |


<br />


{% include bottom.html %}

