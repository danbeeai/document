---
title: 사진 필터
tags: [chatflow, API, advanced]
keywords: api
summary: pho.to에서 제공하는 사진 필터 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_photoapi.html
folder: danbeeDoc
previous: {
    title: 얼굴찾기,
    url: predefined_api_searchFacesByImage.html
}
next: {
    title: 도시별 현재 날씨 조회,
    url: predefined_api_weathercurrentbycity.html
}
---

## API 설명

 단비Ai에서 제공하는 pho.to 사진 필터링 API입니다. <br>
해당 기능은 한시적으로 무료로 제공하고 있습니다. ( 추후 비용 발생 ) <br>

해당 API 는 [Pho.To](https://pho.to/){:target="_blank"} 에서 제공하는 api를 활용하였습니다.

## API 종류
- [캐리커쳐](predefined_api_photoapi.html#캐리커쳐 만들기) : 캐리커쳐 만들기
 

### 캐리커쳐 만들기

#### 캐리커쳐 API 입력값

| KEY | TYPE | Required | VALUE | Default |
|--------|--------|--------|--------|--------|
| imageUrl | String | Yes | 요청이미지 | |
| morphingType | String | No | 그리기유형 | 0 |
| cartoon | String | No | 그림여부 | N |

예시)
```javascript
{
    "imageUrl": "https://",
    "morphingType": "1",
    "cartoon": "Y"
}
```

#### 캐리커쳐 그리기 유형

| 유형 | 설명 |
|--------|--------|
| -1 | 변경없음 | 
| 0 | 아무거나 |
| 1 | 웃는 표정 |
| 2 | 슬픈 표정 |
| 3 | 놀란 표정 |
| 4 | 사팔뜨기 눈 |
| 5 | 트롤 |
| 6 | 윙크 |
| 7 | 시시덕거림(눈썹 하나 올리기) |
| 8 | 기분 나쁜 표정 |
| 9 | 외계인(턱이 좁고 눈이 휘둥그레짐) |
| 10 | 화성인(코가 작고 눈이 큰 외국인) |
| 11 | 구근머리(턱이 좁고 이마 넓으며 눈이 크다) |
| 12 | 터프가이(큰 턱, 구근코, 한쪽 눈썹 올리기) |
| 13 | 기괴한(기이한) 형태 |
| 14 | 뚱뚱한 체격 |

<br><br>

#### 캐리커쳐 API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| resultCode | String | 결과 코드 (success/fail) |
| resultMsg | String | 결과 메시지 |
| inputImageUrl1 | String | 요청이미지 URL |
| inputImageUrl2 | String | 사용안함 |
| outputImageUrl | String | 결과이미지 URL |

예시)
```javascript
{
    "resultCode": "success",
    "resultMsg": "",
    "inputImageUrl1": "https://",
    "inputImageUrl2": "",
    "outputImageUrl": "https://"
}
```

<br />

{% include bottom.html %}

