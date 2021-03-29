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

