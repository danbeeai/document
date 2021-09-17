---
title: 얼굴컬렉션에서 얼굴사진 삭제하기
tags: [chatflow, API, advanced]
keywords: api
summary: 단비에서 제공하는 얼굴컬렉션에서 얼굴사진 삭제하기 API 입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_collectionFaceDelete.html
folder: danbeeDoc
previous: {
    title: 얼굴컬렉션에서 얼굴사진 추가하기,
    url: predefined_api_collectionFace.html
}
next: {
    title: 얼굴찾기,
    url: predefined_api_searchFacesByImage.html
}
---

## API 설명

단비에서 제공하는 얼굴컬렉션에서 얼굴사진 삭제하기 API 입니다. <br>
요금제는 Starter 이상부터 사용가능합니다. (무료) <br>

해당 API 는 Amazon Rekognition의 [DeleteFaces](https://docs.aws.amazon.com/ko_kr/rekognition/latest/dg/API_DeleteFaces.html){:target="_blank"} 에서 제공하는 api를 활용하였습니다.

## API 주소
<pre>POST https://openapi.danbee.ai/openapis/knowledge/:knowledgeId/delete</pre>

## API 입력값 유형
JSON

## API 입력값

| KEY | TYPE | Required | VALUE | Default |
|--------|--------|--------|--------|--------|
| id | Number | Yes | 삭제할 얼굴사진 id |  |
| accessKey | String | Yes | 얼굴사진 콜렉션만든 후 자동발급된 키 |  |



예시 1)
```javascript

{
    "id" : 4
    "accessKey" : "cWuDsBp3kULam"
}

```
## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_status | String | 결과코드 ( success / error ) |
| result_message | String | 결과 메시지 내용 |
| result | Object | 결과값 |
| result.id | String | 삭제된 Id |
| result.ksId | String | 얼굴사진 컬렉션 ID |
| result.faceId | String | 얼굴사진 Id |
| result.faceName | String | 얼굴사진 이름 |
| result.faceUrl | String | 얼굴사진 업로드 주소 |
| result.areaWidth | Number(Double) | 얼굴의 가로 비율(전체이미지 가로기준) |
| result.areaHeight | Number(Double) | 얼굴의 높이 비율(전체이미지 높이기준) |
| result.areaLeft | Number(Double) | 얼굴의 왼쪽 좌표(전체이미지 가로기준) |
| result.areaTop | Number(Double) | 얼굴의 높이 좌표(전체이미지 높이기준) |
| result.description | String | 얼굴사진 설명 |
| result.createDate | Date | 생성일시 |
| result.updateDate | Date | 수정일시 |

예시)
```javascript
{
    "result_status": "success",
    "result_code": "OK",
    "result_message": "데이터가 삭제되었습니다.",
    "result": {
        "faces": [
            {
                "id": 4,
                "ksId": "ce9e9dc9-590d-4e2f-a5a3-d4",
                "faceId": "cf9d9851-9b75-4671-87d1-86e",
                "faceName": "영희",
                "faceUrl": "https://facerecognition.danbee.ai/prod/7f109179-84d2-4b/ce9e9dc9-590d-4e2f-a5a3-d4/ce9e9dc9-590d-4e2f-a5a3-d47.word",
                "areaWidth": 0.78034204,
                "areaHeight": 1.0008249,
                "areaLeft": 0.14961596,
                "areaTop": -0.033830762,
                "description": "",
                "orderFace": null,
                "deleteYn": "N",
                "creator": null,
                "createDate": "2021-09-16T03:26:26.000+0000",
                "updator": null,
                "updateDate": "2021-09-16T03:26:26.000+0000"
            }
        ]
    }
}
```



<br />

{% include bottom.html %}

