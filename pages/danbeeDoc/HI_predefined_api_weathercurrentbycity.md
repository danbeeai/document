---
title: 도시별 현재 날씨 조회
tags: [chatflow, API, advanced]
keywords: api
summary: 단비에서 제공하는 도시별 현재 날씨조회 API 입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_weathercurrentbycity.html
folder: danbeeDoc
previous: {
    title: 닮은 유명인 찾기,
    url: predefined_api_navercelebrity.html
}
next: {
    title: 도시별 일자별 날씨예보 조회,
    url: predefined_api_weatherdayforecastbycity.html
}
---

## API 설명

단비Ai에서 제공하는 도시별 현재 날씨조회 API 입니다. <br>
요금제는 Starter 이상부터 사용가능합니다. (무료) <br>

해당 API 는 https://openweathermap.org/api/one-call-api 에서 제공하는 데이터입니다.

## API 입력값

| KEY | TYPE | Required | VALUE | Default |
|--------|--------|--------|--------|--------|
| cityName | String | Yes | 도시명 | |
| dateFormatter | String | No | 일자결과포맷 | yyyyMMdd |
| decimalPoint | Integer | No | 결과소숫점자리 | 1 |

예시)
```javascript
{
    "cityName": "서울특별시",
    "dateFormatter": "yyyyMMdd",
    "decimalPoint": 1
}
```
## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_type | String | 결과코드 ( Success / Error ) |
| result_msg | String | 결과 메시지 내용 |
| result | Object | 결과값 |
| result.yyyymmdd | String | 기준일자 |
| result.hh | String | 기준시간 |
| result.cityName | String | 도시명 |
| result.currentDt | String | 현재날씨시간 |
| result.currentTemp | String | 현재온도 ( 섭씨 ) |
| result.currentFeelsLike | String | 체감온도 ( 섭씨 )  |
| result.currentPressure | String | 대기압력 ( hPa ) |
| result.currentHumidity | String | 습도 ( % ) |
| result.currentDewPoint | String | 이슬점 ( 섭씨 ) |
| result.currentClouds | String | 흐림/구름낀 정도 ( % ) |
| result.currentUvi | String | 자외선지수 |
| result.currentVisibility | String | 가시성 ( 미터 ) |
| result.currentWindSpeed | String | 바람세기 (m/s) |
| result.currentWindDeg | String | 바람의 각도 |
| result.currentWindDegName | String | 바람방향 |
| result.currentId | String | 날씨아이디 |
| result.currentMain | String | 날씨그룹 ( Rain, Snow, Extreme 등 ) |
| result.currentDesc | String | 날씨설명 |
| result.currentIcon | String | 날씨아이콘 |
| result.todayTempMorn | String | 오늘아침온도 ( 섭씨 ) |
| result.todayTempDay | String | 오늘낮온도 ( 섭씨 ) |
| result.todayTempEve | String | 오늘오후온도 ( 섭씨 ) |
| result.todayTempNight | String | 오늘밤온도 ( 섭씨 ) |
| result.todayTempMin | String | 오늘최저온도 ( 섭씨 ) |
| result.todayTempMax | String | 오늘최고온도 ( 섭씨 ) |
| result.todayFeelsLikeMorn | String | 오늘아침체감온도 ( 섭씨 ) |
| result.todayFeelsLikeDay | String | 오늘낮체감온도 ( 섭씨 ) |
| result.todayFeelsLikeEve | String | 오늘오후체감온도 ( 섭씨 ) |
| result.todayFeelsLikeNight | String | 오늘밤체감온도 ( 섭씨 ) |

예시)
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "yyyymmdd": "20210329",
        "hh": "11",
        "cityName": "서울특별시",
        "currentDt": "11시기준 ",
        "currentTemp": "12.7",
        "currentFeelsLike": "10.0",
        "currentPressure": "1009",
        "currentHumidity": "50",
        "currentDewPoint": "2.5",
        "currentClouds": "1",
        "currentUvi": "4.3",
        "currentVisibility": "4800",
        "currentWindSpeed": "1.5",
        "currentWindDeg": "280",
        "currentWindDegName": "W",
        "currentId": "721",
        "currentMain": "Haze",
        "currentDesc": "연무",
        "currentIcon": "50d",
        "todayTempMorn": "8.0",
        "todayTempDay": "13.5",
        "todayTempEve": "12.0",
        "todayTempNight": "9.5",
        "todayTempMin": "8.0",
        "todayTempMax": "14.0",
        "todayFeelsLikeMorn": "5.8",
        "todayFeelsLikeDay": "7.2",
        "todayFeelsLikeEve": "5.4",
        "todayFeelsLikeNight": "5.7"
    }
}
```

<br />

{% include bottom.html %}

