---
title: 도시별 시간별 공기현황 조회
tags: [chatflow, API, advanced]
keywords: api
summary: 단비에서 제공하는 도시별 시간별 공기현황 조회 API 입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_weatherhourforecastairbycity.html
folder: danbeeDoc
previous: {
    title: 도시별 현재 공기현황 조회,
    url: predefined_api_weathercurrentairbycity.html
}
---

## API 설명

단비Ai에서 제공하는 도시별 시간별 공기현황 조회 API 입니다. <br>
요금제는 Starter 이상부터 사용가능합니다. (무료) <br>

해당 API 는 https://openweathermap.org/api/air-pollution 에서 제공하는 데이터입니다.

[대기오염물질](https://www.airkorea.or.kr/web/airMatter?pMENU_NO=130){:target="_blank"}에 대한 측정값을 조회한다.

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
    "hourValue2": "",
    "dateFormatter": "HH기준",
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
| result.airDt | String | 공기현황 조회시간 |
| result.airMainAqi | String | 공기질 ( 1:좋음, 2:약간 좋음, 3:보통, 4:나쁨, 5:매우 나쁨 ) |
| result.airCo | String | CO 일산화탄소 ( μg/m3 ) |
| result.airNo | String | NO 일산화질소 ( μg/m3 ) |
| result.airNo2 | String | NO2 이산화질소 ( μg/m3 ) |
| result.airO3 | String | O3 오존 ( μg/m3 ) |
| result.airSo2 | String | SO2 아황산가스-이산화황 ( μg/m3 ) |
| result.airPm2Dot5 | String | PM2.5 초미세먼지 ( μg/m3 ) |
| result.airPm10 | String | PM10 미세먼지 ( μg/m3 ) |
| result.airNh3 | String | NH3 암모니아 ( μg/m3 ) |

예시)
```javascript
{
    "result_type": "Success",
    "result_msg": "",
    "result": {
        "yyyymmdd": "20210329",
        "hh": "09",
        "cityName": "서울특별시",
        "airDt": "09기준",
        "airMainAqi": "5",
        "airCo": "1295.1",
        "airNo": "87.6",
        "airNo2": "102.8",
        "airO3": "8.8",
        "airSo2": "52.0",
        "airPm2Dot5": "206.4",
        "airPm10": "242.6",
        "airNh3": "4.1"
    }
}
```

### 미세먼지 기준

| 구분 | 좋음 | 보통 | 나쁨 | 매우 나쁨 |
|--------|--------|--------|--------|--------|
| PM2.5 초미세먼지 | 0~15 | 16~35 | 36~75 | 76~ |
| PM10 미세먼지 | 0~30 | 31~80 | 81~150 | 151~ |

<br />

{% include bottom.html %}

