---
title: 도시별 시간별 날씨예보 조회
tags: [chatflow, API, advanced]
keywords: api
summary: 단비에서 제공하는 도시별 시간별 날씨예보 조회 API 입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_weatherhourforecastbycity.html
folder: danbeeDoc
previous: {
    title: 도시별 일자별 날씨예보 조회,
    url: predefined_api_weatherdayforecastbycity.html
}
next: {
    title: 도시별 오늘 일출일몰 조회,
    url: predefined_api_weathertodaysunrisesetbycity.html
}
---

## API 설명

단비Ai에서 제공하는 도시별 시간별 날씨예보 조회 API 입니다. <br>
요금제는 Starter 이상부터 사용가능합니다. (무료) <br>

해당 API 는 https://openweathermap.org/api/one-call-api 에서 제공하는 데이터입니다.

## API 입력값

| KEY | TYPE | Required | VALUE | Default |
|--------|--------|--------|--------|--------|
| cityName | String | Yes | 도시명 | |
| hourType | String | Yes | 시간검색유형 ( 1 : 일자시간 / 2 : 계산 ) | 1 |
| hourValue1 | String | Yes | 검색유형시간값 |  |
| hourValue2 | String | Yes | 검색유형계산값 |  |
| dateFormatter | String | No | 일자결과포맷 | yyyyMMdd |
| decimalPoint | Integer | No | 결과소숫점자리 | 1 |

예시)
```javascript
{
    "cityName": "서울특별시",
    "hourType": "1",
    "hourValue1": "2021032909",
    "dateValue2": "",
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
| result.hourDt | String | 날씨시간 |
| result.hourTemp | String | 온도 ( 섭씨 ) |
| result.hourFeelsLike | String | 체감온도 ( 섭씨 ) |
| result.hourPressure | String | 대기압력 ( hPa ) |
| result.hourHumidity | String | 습도 ( % ) |
| result.hourDewPoint | String | 이슬점 ( 섭씨 ) |
| result.hourUvi | String | 자외선지수 |
| result.hourClouds | String | 흐림/구름낀 정도 ( % ) |
| result.hourVisibility | String | 가시성 ( 미터 ) |
| result.hourWindSpeed | String | 바람세기 (m/s) |
| result.hourWindDeg | String | 바람의 각도 |
| result.hourWindDegName | String | 바람방향 |
| result.hourPop | String | 강수확률 ( % ) |
| result.hourId | String | 날씨아이디 |
| result.hourMain | String | ( Rain, Snow, Extreme 등 ) |
| result.hourDesc | String | 날씨설명 |
| result.hourIcon | String | 날씨아이콘 |

예시)
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "yyyymmdd": "20210329",
        "hh": "09",
        "cityName": "서울특별시",
        "hourDt": "2021년 03월 29",
        "hourTemp": "9.7",
        "hourFeelsLike": "6.6",
        "hourPressure": "1009",
        "hourHumidity": "81",
        "hourDewPoint": "6.6",
        "hourUvi": "1.5",
        "hourClouds": "75",
        "hourVisibility": "10000",
        "hourWindSpeed": "3.3",
        "hourWindDeg": "285",
        "hourWindDegName": "WNW",
        "hourPop": "0.0",
        "hourId": "803",
        "hourMain": "Clouds",
        "hourDesc": "튼구름",
        "hourIcon": "04d"
    }
}
```

<br />

{% include bottom.html %}

