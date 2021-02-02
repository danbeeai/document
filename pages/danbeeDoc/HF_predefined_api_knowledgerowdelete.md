---
title: 지식 라이브러리 데이터(행) 삭제
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 지식 라이브러리를 관리하는 api입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_knowledgerowdelete.html
folder: danbeeDoc
previous: {
    title: 지식 라이브러리 데이터 추가,
    url: predefined_api_knowledgerowfind.html
}
next: {
    title: 닮은 유명인 찾기,
    url: predefined_api_navercelebrity.html
}
---

## 설명

단비Ai에서 제공하는 여러가지 API 중 지식 라이브러리 데이터(행) 삭제 API 입니다.<br>
<hr/>

## Request URL
<pre>POST  https://openapi.danbee.ai/openapis/knowledge/:knowledgeId/delete</pre>
##### knowledgeId
지식라이브러리 ID
<hr/>

## Input

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| accessKey | String | Yes | 액세스키 | 
| id | Integer | Yes | 지식 데이터 id | 


##### accessKey
지식라이브러리 생성시 자동으로 생성된 accessKey 입니다.

##### id
지식 라이브러리 데이터 중 각 데이터가 가지고 있는 고유 id로, id는 지식 데이터 찾기 API를 통해 확인할 수 있습니다.
<hr/>

## Output

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_status | String | 결과상태 ( success / fail ) |
| result_message | String | 결과 메시지 내용 |
| result_code | String | 결과코드 |
| result | Object | 삭제 데이터 |



<br />

