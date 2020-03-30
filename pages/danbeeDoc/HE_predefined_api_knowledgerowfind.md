---
title: 지식 라이브러리 데이터(행) 찾기
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 지식 라이브러리를 관리하는 api입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_knowledgerowfind.html
folder: danbeeDoc
previous: {
    title: 지식 라이브러리 데이터 수정,
    url: predefined_api_knowledgerowupdate.html
}
next: {
    title: 지식 라이브러리 데이터 삭제,
    url: predefined_api_knowledgerowdelete.html
}
---

## 설명   

단비Ai에서 제공하는 여러가지 API 중 지식 라이브러리 데이터(행) 찾기 API 임니다.
<hr/>

## Request URL
<pre>POST  https://openapi.danbee.ai/openapis/knowledge/:knowledgeId/find</pre>
##### knowledgeId
지식라이브러리 ID

## Input

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| accessKey | String | Yes | 액세스키 | 
| columnName | String | Yes | 컬럼명 | 
| findValue | String | Yes | 검색어 |  


##### accessKey
지식라이브러리 생성시 자동으로 생성된 accessKey 입니다.
##### columnName
지식의 특정 항목으로, 지식 유형별로 찾을 수 있는 항목이 다릅니다. 아래의 예시를 참고하세요.

FAQ 지식 라이브러리 

| columnName | TYPE | VALUE |
|--------|--------|--------|
| question | String | 질문 |
| answer | String | 답변 |
| buttonName1 | String | 버튼1 이름 |
| buttonUrl1 | String | 버튼1 링크 |
| ... |  |  |
| buttonName4 | String | 버튼4 이름 |
| buttonUrl4 | String | 버튼4 링크 |

<hr/>

## Output

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_status | String | 결과상태 ( success / fail ) |
| result_message | String | 결과 메시지 내용 |
| result_code | String | 결과코드 |
| result | Array\<Object\> | 조회 데이터 |



<br />

