---
title: 닮은 유명인 찾기
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 네이버 CFR(Clova Face Recognition)의 닮은 유명인 찾기 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_navercelebrity.html
folder: danbeeDoc
previous: {
    title: 지식 라이브러리 데이터(행) 삭제,
    url: predefined_api_knowledgerowdelete.html
}
---

## API 설명

단비Ai에서 제공하는 여러가지 API 중 네이버 CFR(Clova Face Recognition)의 닮은 유명인 찾기 API입니다. <br>
요금제는 Standard 이상부터 사용가능합니다. (건당 10원) <br>
    
## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| imageUrl | String | Yes | 이미지 URL|

예시)
```javascript
{
    "imageUrl" : "https://doc.danbee.ai/images/danbeemon.png"
}
```
## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| statusCode | Number | 결과코드 ( 200 / 500 ) |
| resultMsg | String | 결과 메시지 내용 |
| body | Object | 결과값 |
| body.name1 | String | 이름(1순위) |
| body.name2 | String | 이름(2순위) |
| body.name3 | String | 이름(3순위) |
| body.score1 | Number | 점수(0부터1까지) |
| body.score2 | Number | 점수(0부터1까지) |
| body.score3 | Number | 점수(0부터1까지) |

예시)
```javascript
{
    "body": {
        "name1": "유재석"
        "score1": 1,
        "name2": "박명수",
        "score2": 0.4,
        "name3": "정준하",
        "score3": 0.1,
    },
    "statusCode": 200,
    "resultMsg": "success"
}
```

<br />

{% include bottom.html %}

