---
title: 구글 번역
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 구글 번역 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_googletranslation.html
folder: danbeeDoc
previous: {
    title: 구글 스프레드시트 행 찾기,
    url: predefined_api_googlespreadsheetrowfind.html
}
next: {
    title: 지식 라이브러리 데이터 추가,
    url: predefined_api_knowledgerowappend.html
}
---

## API 설명

단비Ai에서 제공하는 여러가지 API 중 구글 번역 API입니다. <br>
요금제는 Standard 이상부터 사용가능합니다. (100글자당 10원)<br>
    
## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| sourceLanguage | String | Yes | 문자열 언어(ko,en,...) |
| sourceText  | String | Yes | 번역할 문자열 |
| targetLanguage   | String | Yes | 번역 언어(ko,en,...) |

예시)
```javascript
{
    "sourceLanguage" : "ko",
    "sourceText" : "나 배고파",
    "targetLanguage" : "en"
}
```

지원 언어는 [여기](https://cloud.google.com/translate/docs/languages?hl=ko){:target="_blank"}에서 확인할 수 있습니다.

## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_code | String | 결과코드 ( 200, ... ) |
| result_message | String | 결과 메시지 내용  ( success / fail ) |
| sourceLanguage | String | 문자열 언어(ko, en, ...) |
| targetLanguage | String | 번역 언어(ko, en, ...) |
| sourceText | String | 번역할 문자열 |
| targetText | String | 번역된 문자열|

예시)
```javascript
{
    "result_code" : "200",
    "result_message" : "success",
    "sourceLanguage" : "ko",
    "targetLanguage" : "en",
    "sourceText" : "나 배고파",
    "targetText" : "i'm hungry"
}
```

<br />

{% include bottom.html %}

