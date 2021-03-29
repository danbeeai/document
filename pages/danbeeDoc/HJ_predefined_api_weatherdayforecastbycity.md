---
title: 도시별 일자별 날씨예보 조회
tags: [chatflow, API, advanced]
keywords: api
summary: 단비에서 제공하는 도시별 일자별 날씨예보 조회 API 입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_weatherdayforecastbycity.html
folder: danbeeDoc
previous: {
    title: 도시별 현재 날씨 조회,
    url: predefined_api_weathercurrentbycity.html
}
next: {
    title: 도시별 시간별 날씨예보 조회,
    url: predefined_api_weatherhourforecastbycity.html
}
---

## API 설명

단비Ai에서 제공하는 도시별 일자별 날씨예보 조회 API 입니다. <br>
요금제는 Starter 이상부터 사용가능합니다. (무료) <br>

해당 API 는 [openweathermap](https://openweathermap.org/api/one-call-api){:target="_blank"} 에서 제공하는 데이터입니다.

### 도시 목록

| 도시명 | 위도 | 경도 | 지도 |
|--------|--------|--------|--------|
| 강원도내륙 | 37.874722 | 127.734169 | [지도로보기](https://www.google.co.kr/maps/@37.874722,127.734169,12z){:target="_blank"} |
| 강원도해양 | 38.208328 | 128.59111 | [지도로보기](https://www.google.co.kr/maps/@38.208328,128.59111,12z){:target="_blank"} |
| 광주광역시 | 35.166672 | 126.916672 | [지도로보기](https://www.google.co.kr/maps/@35.166672,126.916672,12z){:target="_blank"} |
| 경기도남부 | 37.291111 | 127.008888 | [지도로보기](https://www.google.co.kr/maps/@37.291111,127.008888,12z){:target="_blank"} |
| 경기도북부 | 37.741501 | 127.047401 | [지도로보기](https://www.google.co.kr/maps/@37.741501,127.047401,12z){:target="_blank"} |
| 경상남도 | 35.228062 | 128.681107 | [지도로보기](https://www.google.co.kr/maps/@35.228062,128.681107,12z){:target="_blank"} |
| 경상북도내륙 | 36.565559 | 128.725006 | [지도로보기](https://www.google.co.kr/maps/@36.565559,128.725006,12z){:target="_blank"} |
| 경상북도해양 | 36.032219 | 129.365005 | [지도로보기](https://www.google.co.kr/maps/@36.032219,129.365005,12z){:target="_blank"} |
| 부산광역시 | 35.133331 | 129.050003 | [지도로보기](https://www.google.co.kr/maps/@35.133331,129.050003,12z){:target="_blank"} |
| 서울특별시 | 37.583328 | 127 | [지도로보기](https://www.google.co.kr/maps/@37.583328,127,12z){:target="_blank"} |
| 세종특별자치시 | 36.4800121 | 127.2890691 | [지도로보기](https://www.google.co.kr/maps/@36.4800121,127.2890691,12z){:target="_blank"} |
| 울산광역시 | 35.566669 | 129.266663 | [지도로보기](https://www.google.co.kr/maps/@35.566669,129.266663,12z){:target="_blank"} |
| 울릉도 | 37.500499 | 130.872916 | [지도로보기](https://www.google.co.kr/maps/@37.500499,130.872916,12z){:target="_blank"} |
| 이어도 | 32.122953 | 125.182447" | [지도로보기](https://www.google.co.kr/maps/@32.122953,125.182447,12z){:target="_blank"} |
| 인천광역시 | 37.450001 | 126.416107 | [지도로보기](https://www.google.co.kr/maps/@37.450001,126.416107,12z){:target="_blank"} |
| 전라남도 | 34.989719 | 126.47139 | [지도로보기](https://www.google.co.kr/maps/@34.989719,126.47139,12z){:target="_blank"} |
| 전라북도 | 35.821941 | 127.148888 | [지도로보기](https://www.google.co.kr/maps/@35.821941,127.148888,12z){:target="_blank"} |
| 제주특별자치도 | 33.50972 | 126.521942 | [지도로보기](https://www.google.co.kr/maps/@33.50972,126.521942,10z){:target="_blank"} |
| 충청남도 | 36.5 | 127 | [지도로보기](https://www.google.co.kr/maps/@36.5,127,12z){:target="_blank"} |
| 충청북도 | 36.637218 | 127.489723 | [지도로보기](https://www.google.co.kr/maps/@36.637218,127.489723,12z){:target="_blank"} |


## API 입력값

| KEY | TYPE | Required | VALUE | Default |
|--------|--------|--------|--------|--------|
| cityName | String | Yes | 도시명 | |
| dateType | String | Yes | 일자검색유형 ( 1 : 일자 / 2 : 계산 ) | 1 |
| dateValue1 | String | Yes | 검색유형일자값 |  |
| dateValue2 | String | Yes | 검색유형계산값 |  |
| dateFormatter | String | No | 일자결과포맷 | yyyyMMdd |
| decimalPoint | Integer | No | 결과소숫점자리 | 1 |

예시)
```javascript
{
    "cityName": "서울특별시",
    "dateType": "1",
    "dateValue1": "20210329",
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
| result.cityName | String | 도시명 |
| result.dayDt | String | 날씨시간 |
| result.dayTempMorn | String | 아침온도 ( 섭씨 ) |
| result.dayTempDay | String | 낮온도 ( 섭씨 ) |
| result.dayTempEve | String | 오후온도 ( 섭씨 ) |
| result.dayTempNight | String | 밤온도 ( 섭씨 ) |
| result.dayTempMin | String | 최저온도 ( 섭씨 ) |
| result.dayTempMax | String | 최고온도 ( 섭씨 ) |
| result.dayFeelsLikeMorn | String | 아침체감온도 ( 섭씨 ) |
| result.dayFeelsLikeDay | String | 낮체감온도 ( 섭씨 ) |
| result.dayFeelsLikeEve | String | 저녁체감온도 ( 섭씨 ) |
| result.dayFeelsLikeNight | String | 밤체감온도 ( 섭씨 ) |
| result.dayPressure | String | 대기압력 ( hPa ) |
| result.dayHumidity | String | 습도 ( % ) |
| result.dayDewPoint | String | 이슬점 ( 섭씨 ) |
| result.dayWindSpeed | String | 바람세기 (m/s) |
| result.dayWindDeg | String | 바람의 각도 |
| result.dayWindDegName | String | 바람방향 |
| result.dayClouds | String | 흐림/구름낀 정도 ( % ) |
| result.dayUvi | String | 자외선지수 |
| result.dayPop | String | 강수확률 ( % ) |
| result.dayId | String | 날씨아이디 |
| result.dayMain | String | 날씨그룹 ( Rain, Snow, Extreme 등 ) |
| result.dayDesc | String | 날씨설명 |
| result.dayIcon | String | 날씨아이콘 |

예시)
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "yyyymmdd": "20210327",
        "cityName": "서울특별시",
        "dayDt": "2021년 03월 27",
        "dayTempMorn": "12.0",
        "dayTempDay": "16.8",
        "dayTempEve": "11.9",
        "dayTempNight": "12.0",
        "dayTempMin": "11.7",
        "dayTempMax": "16.8",
        "dayFeelsLikeMorn": "8.5",
        "dayFeelsLikeDay": "11.9",
        "dayFeelsLikeEve": "9.0",
        "dayFeelsLikeNight": "11.4",
        "dayPressure": "1012",
        "dayHumidity": "30",
        "dayDewPoint": "-0.9",
        "dayWindSpeed": "4.0",
        "dayWindDeg": "127",
        "dayWindDegName": "SE",
        "dayClouds": "100",
        "dayUvi": "2.2",
        "dayPop": "1.0",
        "dayId": "501",
        "dayMain": "Rain",
        "dayDesc": "보통 비",
        "dayIcon": "10d"
    }
}
```

<br />

{% include bottom.html %}

