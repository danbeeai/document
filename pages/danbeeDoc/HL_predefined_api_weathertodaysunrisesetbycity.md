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

[일출-해동이](https://ko.wikipedia.org/wiki/%ED%95%B4%EB%8F%8B%EC%9D%B4){:target="_blank"}, [일몰-해넘이](https://ko.wikipedia.org/wiki/%ED%95%B4%EB%84%98%EC%9D%B4){:target="_blank"}, [박명](https://ko.wikipedia.org/wiki/%EB%B0%95%EB%AA%85){:target="_blank"}에 대한 측정값을 조회한다.

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

