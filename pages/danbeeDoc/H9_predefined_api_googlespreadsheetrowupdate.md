---
title: 구글 스프레드시트 행 수정
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 슬랙의 특정 채널에 메시지를 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_googlespreadsheetrowupdate.html
folder: danbeeDoc
previous: {
    title: 구글 스프레드시트 행 조회,
    url: predefined_api_googlespreadsheetrowget.html
}
next: {
    title: 구글 스프레드시트 행 찾기,
    url: predefined_api_googlespreadsheetrowfind.html
}
---

## API 설명

danbee.Ai에서 제공하는 여러가지 API 중 구글 스프레드시트 행 수정 API임니다. <br>
요금제는 Standard 이상부터 사용가능합니다. <br>

## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| spreadsheetId | String | Yes | 스프레드시트아이디 |
| sheetTabName | String | Yes | 시트하단탭이름 |
| rowIndex | String | Yes | 수정행 |
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
| updatedRowIndex | String | 수정 행 위치 |
| updatedRange | String | 수정 범위 ( 시트내 탭이름 포함 A~Z 범위 ) |
| updatedvalues | JSON | 수정 결과 ( { A:A열값, B:B열값, .... } ) |
| updatedDate | String | 수정 일시 |

<br />


{% include bottom.html %}
