---
title: NPS설문봇, 벼리 
keywords: 고객만족, 설문, NPS, 설문조사
tags: [tutorial, advanced]
sidebar: tutorial_sidebar
permalink: advanced_nps.html
summary: 만족도 조사 챗봇 템플릿입니다.
previous: {
    title: 웹에이전씨봇, 스페이드컴퍼니,
    url: advanced_agency_spadecompany.html
}
---

## “측정할 수 없으면 개선할 수 없다.” – 피터 드러커

어떠한 사업을 하든 고객에게 제공한 제품이나 서비스가 얼마나 만족스러운지 측정을 해야 개선이 가능합니다. 많은 기업에서 다양한 채널을 이용해 만족도 조사를 실시합니다. 웹사이트, 이메일, 전화, 그리고 고객과 대면해서 만족도를 물어보기도 합니다. 

## 챗봇으로 설문을 한다면?
효율적인 방법 중 하나로 챗봇을 이용한 만족도조사가 있습니다.
만족도 조사를 전담하는 만족도 조사 챗봇은 다른 온라인 만족도 조사 기법과 다른 점이 있습니다. 

1. 높은 활용성
한번 만들어 놓은 만족도 조사 챗봇은 고유한 URL을 갖게 됩니다. 웹사이트, 소셜미디어, 알림톡, SMS에 링크를 제공해 수시로 만족도를 조사할 수 있습니다. 챗봇을 복제하여 다른 질문을 추가할 수 있습니다.

2. 높은 행동유발성
온라인 설문의 가장 큰 난제는 고객의 설문 진행중 이탈입니다. 하지만 챗봇은 고객의 응답에 따라 반응할 수 있다는 점이 다릅니다. 고객이 만족했다고 한다면 감사와 기쁜 마음을 전달하고, 고객이 만족하지 못했다고 하면 고객이 느꼈을 괴로움을 공감하는 표현을 합니다. 설문을 끝까지 할 수 있도록 돕는 동시에 마음속에 있는 이야기를 끌어냅니다.

## danbee.Ai의 설문챗봇 템플릿
danbee.Ai에서는 브랜드, 회사명, 제품이나 서비스명만 입력하면 바로 완성되는 NPS 만족도 조사 템플릿을 제공합니다. [데모링크](https://frogue.danbee.ai/?chatbot_id=0ccf95e6-8ae9-4b2f-8960-fde4bed2ba3a){:target="_blank"} 설문 챗봇 템플릿은 danbee.Ai에 접속하신 후, **챗봇목록 > 챗봇가져오기**에서 활용하실 수 있습니다.

NPS(순수고객추천지수, Net Promoter Score)란 만족도 지표 중 가장 가장 궁극적인 지표입니다.
만족여부를 파악하고 핵심적인 이슈를 파악하는 용도로 많이 사용되고 있습니다.

{% include image_border.html file="tutorial/samplebot_nps.PNG"  caption="Level 1. Answering Machine" %}

**“당신은 (제품이나 서비스)를 친구나 동료에게 추천할 의사가 있습니까?”**
여기서 좀더 나아간다면 그렇게 선택한 원인을 파악하는 질문을 던집니다.

**“감사합니다! 저희 (제품이나 서비스)을 추천하시는 이유는 무엇입니까?”**
또는 “그렇군요. 만족스럽지 않았다면 어떤 이유인지 여쭤봐도 될까요?”

수집된 만족도 조사 내용은 Google Spread Sheet에 차례로 모이게 됩니다.


## 챗봇이 받은 데이터를 구글스프레드 시트에 로그 남기는 법!

{% include note.html content="구글 스프레드 시트 API는 standard 버전부터 이용가능한 기능입니다." %}
{% include tip.html content="2019년 11월 11일 부터 [구글스프레드시트 행추가](/predefined_api_googlespreadsheetrowappend.html)를 이용해서 만드실 수 있습니다." %}

### 1. 구글스프레드시트 생성
구글 스프레드 시트를 하나 만듭니다. 그리고 danbee.Ai에서 만든 API가 접근할 수 있게 권한을 부여합니다. 
(구글스프레드시트 우측상단에 [공유설정]에서 “초대할 사용자”에 sheets-api01@danbee-ai.iam.gserviceaccount.com를 추가하고, 수정권한을 부여)
참고로, 구글 스프레드시트는 MS오피스의 엑셀과 유사한 서비스입니다. [여기](https://docs.google.com/spreadsheets/){:target="_blank"}에서 만드실 수 있습니다.

### 2. 스프레드시트ID 복사해두기
spreadsheetId는 구글 스프레드시트가 열려있는 URL상에서 “https://docs.google.com/spreadsheets/d/” 이하에 있는 44자리 글자입니다. 44자리 글자 부분을 복사해서 API관리 > API설정 탭에 Body부분, spreadsheetId의 JSON 값을 바꿔주면, 해당 id의 스프레드시트에 데이터가 쌓이게 됩니다. (또는 Chatflow의 API노드에서 ID부분만 수정하셔도 됩니다.)

### 3. range 부분은 만지지 않기
range는 스프레드시트 Head에 해당하는 부분입니다. (그냥 두시는 것이 좋겠어요.)

### 4. 아래 values부분에 배열로 정의된 항목들이 실제 쌓이게 됩니다. #{변수명}을 넣으면 사용자가 입력했거나 Function노드에서 처리한 변수에 담긴 값이 들어갑니다.

        {
            "spreadsheetId":"1SFXKRAzCtLCmRNQnnSE1WxarUe5UzjLRRKlWNSJce2I",
            "range":"A1",
            "values":[
                ["#{fn_date('yyyy-MM-dd HH:mm:ss', 'day', 0)}", "테스트Y/N","테스트_만족사유","테스트_불만족_사유","테스트_연락처"]
            ]
        }

회사의 규모와 종류에 관계 없이 반드시 필요한 만족도 조사! danbee.Ai에서 제공하는 템플릿으로 빠르게 시도해보면 어떨까요? 



## 함께해요! 챗봇시대;) 
단비아이엔씨는 함께 챗봇시대를 만들어갈 파트너, 인재를 찾고 있습니다. 

[contact@danbee.ai](mailto:contact@danbee.ai)로 연락주세요!


