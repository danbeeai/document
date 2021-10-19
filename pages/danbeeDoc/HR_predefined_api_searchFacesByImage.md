---
title: 얼굴찾기
tags: [chatflow, API, advanced]
keywords: api
summary: 단비Ai에서 제공하는 Amazon Rekognition 사용하여 얼굴 컬렉션에 저장된 것과 일치하는 얼굴 찾기 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_searchFacesByImage.html
folder: danbeeDoc
previous: {
    title: 닮은 유명인 찾기,
    url: predefined_api_navercelebrity.html
}
next: {
    title: 사진 필터,
    url: predefined_api_photoapi.html
}
---

## API 설명

 단비Ai에서 제공하는 Amazon Rekognition 사용하여 얼굴 컬렉션에 저장된 사진과 일치하는 얼굴 찾기 API입니다. <br>
요금제는 Standard 이상부터 사용가능합니다. (건당 10원) <br>

해당 API 는 Amazon Rekognition의 [SearchFacesByImage](https://docs.aws.amazon.com/ko_kr/rekognition/latest/dg/API_DeleteFaces.html){:target="_blank"} 에서 제공하는 api를 활용하였습니다.


## API 입력값 유형
form_data


## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| collectionId | String | Yes | 얼굴컬렉션 ID|
| searchUrl | String | Yes | 얼굴 이미지 URL|

예시)
```javascript

    "collectionId" : ce9e9dc9-590d-4e2f-a5a3-d4
    "searchUrl" : https://doc.danbee.ai/images/danbeemon.png

```
## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_type | String | 결과 성공여부 ( Success / Fail ) |
| result_msg | String | 결과 메시지 내용 |
| result | Object | 결과값 |
| result.inputUrl | String | 입력된 URL |
| result.faceId | String | 입력된 URL 사진 얼굴과 일치하는 얼굴컬렉션에 있는 사진ID  |
| result.faceName | String | 입력된 URL 사진 얼굴과 일치하는 얼굴컬렉션에 있는 사진이름 |
| result.Float | Number(Float) | 일치하는 정도 % |
| result.findUrl | String | (얼굴컬렉션에서 찾아진 사진과 일치하는) '입력된 URL 사진'의 얼굴부분을 네모표시한 사진 URL |
| result.findAreaTop | Number(Double) | (얼굴컬렉션에서 찾아진 사진과 일치하는) '입력된 URL 사진'의 얼굴 높이 좌표(전체이미지 높이기준) |
| result.findAreaLeft | Number(Double) | (얼굴컬렉션에서 찾아진 사진과 일치하는) '입력된 URL 사진'의 얼굴 왼쪽 좌표(전체이미지 가로기준) |
| result.findAreaWidth | Number(Double) | (얼굴컬렉션에서 찾아진 사진과 일치하는) '입력된 URL 사진'의 얼굴 가로 비율(전체이미지 가로기준) |
| result.findAreaHeight | Number(Double) | (얼굴컬렉션에서 찾아진 사진과 일치하는) '입력된 URL 사진'의 얼굴 높이 비율(전체이미지 높이기준)|

예시 1) 일치하는 사진이 있는 경우
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "inputUrl": "https://doc.danbee.ai/images/danbeemon.png",
        "faceId": "1cab16f5-a788-402a-8bf3-",
        "faceName": "크리스마스 ",
        "similarity": 99.99409,
        "findUrl": "https://danbee.ai/platformfile/searchFace/ce9e9dc9-590d-4e2f-a5a3-d4/20210914190907-faceDetection.jpg",
        "findAreaTop": 0.18440682,
        "findAreaLeft": 0.35768306,
        "findAreaWidth": 0.36232817,
        "findAreaHeight": 0.7353094
    }
}
```
<br><br>

예시 2) 일치하는 사진이 없는 경우
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "inputUrl": "https://doc.danbee.ai/images/danbeemon.png",
        "faceId": "",
        "faceName": "",
        "similarity": 0.0,
        "findUrl": "https://danbee.ai/platformfile/searchFace/ce9e9dc9-590d-4e2f-a5a3-d4/2021091419-faceDetection.jpg",
        "findAreaTop": 0.16707684,
        "findAreaLeft": 0.43422425,
        "findAreaWidth": 0.14914586,
        "findAreaHeight": 0.4029974
    }
}
```
<br />

{% include bottom.html %}

