---
title: 도시별 오늘 일출일몰 조회
tags: [chatflow, API, advanced]
keywords: api
summary: 단비에서 제공하는 도시별 오늘 일출일몰 조회 API 입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_weathertodaysunrisesetbycity.html
folder: danbeeDoc
previous: {
    title: 도시별 시간별 날씨예보 조회,
    url: predefined_api_weatherhourforecastbycity.html
}
next: {
    title: 도시별 일자별 일출일몰 조회,
    url: predefined_api_weatherdayforecastsunrisesetbycity.html
}
---

## API 설명

단비Ai에서 제공하는 도시별 오늘 일출일몰 조회 API 입니다. <br>
요금제는 Starter 이상부터 사용가능합니다. (무료) <br>

해당 API 는 https://sunrise-sunset.org/api 에서 제공하는 데이터입니다.

[일출-해동이](https://ko.wikipedia.org/wiki/%ED%95%B4%EB%8F%8B%EC%9D%B4), [일몰-해넘이](https://ko.wikipedia.org/wiki/%ED%95%B4%EB%84%98%EC%9D%B4) [박명](https://ko.wikipedia.org/wiki/%EB%B0%95%EB%AA%85)에 대한 측정값을 조회한다.

## API 입력값

| KEY | TYPE | Required | VALUE | Default |
|--------|--------|--------|--------|--------|
| cityName | String | Yes | 도시명 | |
| dateFormatter | String | No | 일자결과포맷 | yyyyMMdd |

예시)
```javascript
{
    "cityName": "서울특별시",
    "dateFormatter": "HH시 mm분"
}
```
## API 결과값

| KEY | TYPE | VALUE |
|--------|--------|--------|
| result_type | String | 결과코드 ( Success / Error ) |
| result_msg | String | 결과 메시지 내용 |
| result | Object | 결과값 |
| result.yyyymmdd | String | 기준일자 |
| result.cityName | String | 도시명 |
| result.astronomicalTwilightBegin | String | 일출 전 천문박명 : 천체(별)을 관착 시기 |
| result.nauticalTwilightBegin | String | 일출 전 항해박명 : 수평선이 명확하게 구분이 가능한 시기 |
| result.civilTwilightBegin | String | 일출 전 상용박명 (시민박명) : 모든 사물의 식별이 가능한 시기 |
| result.sunrise | String | 해돋이 일출 |
| result.solarNoon | String | 정오 |
| result.dayLength | String | 낮 길이 |
| result.sunset | String | 해넘이 일몰 |
| result.civilTwilightEnd | String | 일몰 후 상용박명 (시민박명) : 모든 사물의 식별이 가능한 시기 |
| result.nauticalTwilightEnd | String | 일출 후 항해박명 : 수평선이 명확하게 구분이 가능한 시기 |
| result.astronomicalTwilightEnd | String | 일출 후 천문박명 : 천체(별)을 관착 시기 |

예시)
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "yyyymmdd": "20210329",
        "cityName": "서울특별시",
        "astronomicalTwilightBegin": "04시 52분",
        "nauticalTwilightBegin": "05시 23분",
        "civilTwilightBegin": "05시 54분",
        "sunrise": "06시 21분",
        "solarNoon": "12시 36분",
        "dayLength": "45062",
        "sunset": "18시 52분",
        "civilTwilightEnd": "19시 18분",
        "nauticalTwilightEnd": "19시 49분",
        "astronomicalTwilightEnd": "20시 20분"
    }
}
```

<br />

{% include bottom.html %}

