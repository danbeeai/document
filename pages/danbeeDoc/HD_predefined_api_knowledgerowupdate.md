---
title: 지식 라이브러리 데이터(행) 수정
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 지식 라이브러리를 관리하는 api입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_knowledgerowupdate.html
folder: danbeeDoc
previous: {
    title: 지식 라이브러리 데이터 추가,
    url: predefined_api_knowledgerowappend.html
}
next: {
    title: 지식 라이브러리 데이터 찾기,
    url: predefined_api_knowledgerowfind.html
}
---

## 설명

단비Ai에서 제공하는 여러가지 API 중 지식 라이브러리 데이터(행) 수정 API 입니다.
<hr/>

## Request URL
<pre>POST  https://openapi.danbee.ai/openapis/knowledge/:knowledgeId/update</pre>
##### knowledgeId
지식라이브러리 ID
<hr/>

## Input

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| accessKey | String | Yes | 액세스키 | 
| id | Integer | Yes | 지식 데이터 id | 
| data | Array\<String\> | Yes | 데이터 | 


##### accessKey
지식라이브러리 생성시 자동으로 생성된 accessKey 입니다.

##### id
지식 라이브러리 데이터 중 각 데이터가 가지고 있는 고유 id로, id는 지식 데이터 찾기 API를 통해 확인할 수 있습니다.

##### data
Array\<String\> 타입으로, 아래를 예시를 참고해주세요.

- FAQ : Array.length가 10으로, 질문과 답변은 필수<br/><br/>['질문', '답변', '버튼명1', '버튼링크1', '버튼명2', '버튼링크2', '버튼명3', '버튼링크3', '버튼명4', '버튼링크4']
<br/><br/>
- FAQ+ : Array.length가 34으로, 질문과 답변은 필수<br/><br/>['호출값', 'ID (필수)', '질문(필수)', '이미지URL', '답변액션', '답변', '버튼명1', '버튼값1', '버튼명2', '버튼값2', '버튼명3', '버튼값3', '버튼명4', '버튼값4', '퀵버튼5', '퀵버튼값5', ..., '퀵버튼14', '퀵버튼값14']

<hr/>

## Output

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_status | String | 결과상태 ( success / fail ) |
| result_message | String | 결과 메시지 내용 |
| result_code | String | 결과코드 |
| result | Object | 수정된 데이터 |



<br />

