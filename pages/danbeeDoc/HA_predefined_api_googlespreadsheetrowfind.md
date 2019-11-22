---
title: 구글 스프레드시트 행 찾기
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 슬랙의 특정 채널에 메시지를 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_googlespreadsheetrowfind.html
folder: danbeeDoc
previous: {
    title: 구글 스프레드시트 행 수정,
    url: predefined_api_googlespreadsheetrowupdate.html
}
---

## API 설명

danbee.Ai에서 제공하는 여러가지 API 중 구글 스프레드시트 행 찾기 API임니다. <br>
요금제는 Standard 이상부터 사용가능합니다. <br>
결과가 여러행인 경우 첫번째 행만 찾아옵니다. <br>

## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| spreadsheetId | String | Yes | 스프레드시트아이디 |
| sheetTabName | String | Yes | 시트하단탭이름 |
| findColumn  | String | Yes | 찾을열(B,C....,Z) |
| findValue  | String | Yes | 찾을값(일치하는값) |
| findPosition  | String | No | 찾을위치(T-맨위, B-맨아래), 기본값(T) |

## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_code | String | 결과코드 ( success / fail ) |
| result_message | String | 결과 메시지 내용 |
| spreadsheetId | String | 스프레드시트아이디 |
| findRowIndex | String | 찾은 결과 모든 행 |
| getRowIndex | String | 결과 행 위치 |
| getRange | String | 결과 범위 ( 시트내 탭이름 포함 A~Z 범위 ) |
| getvalues | JSON | 결과 값 ( { A:A열값, B:B열값, .... } ) |



<br />
