---
title: 지식 라이브러리 데이터(행) 추가
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 지식 라이브러리를 관리하는 api입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_knowledgerowappend.html
folder: danbeeDoc
previous: {
    title: 구글 스프레드시트 행 찾기,
    url: predefined_api_googlespreadsheetrowfind.html
}
next: {
    title: 지식 라이브러리 데이터 조회,
    url: predefined_api_knowledgerowupdate.html
}
---

## API 설명

단비Ai에서 제공하는 여러가지 API 중 지식 라이브러리 데이터(행) 추가 API 입니다. <br >

## API Request URL
<pre>POST  https://openapi.danbee.ai/openapis/knowledge/:knowledgeId/create</pre>
##### knowledgeId
지식라이브러리 ID

## API 입력값

| KEY | TYPE | Required | VALUE | VALUE_EXAMPLE |
|--------|--------|--------|--------|--------| 
| accessKey | String | Yes | 액세스키 | dojfdo2Dfosk2@!dk
| data | Array\<String\> | Yes | 데이터 | 하단 예시 참고


##### accessKey
지식라이브러리 생성시 자동으로 생성된 accessKey 입니다.
##### data
Array\<String\> 타입으로, 아래를 예시를 참고해주세요.

- FAQ : Array.length가 10으로, 질문과 답변은 필수<br/><br/>['질문', '답변', '버튼명1', '버튼링크1', '버튼명2', '버튼링크2', '버튼명3', '버튼링크3', '버튼명4', '버튼링크4']


## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_status | String | 결과상태 ( success / fail ) |
| result_message | String | 결과 메시지 내용 |
| result_code | String | 결과코드 |
| result | Object | 생성된 데이터 |


<br />

