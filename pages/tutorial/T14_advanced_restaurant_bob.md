---
title: 식당곰, 밥 
keywords: 식당, 레스토랑, 메뉴, 매장위치, 영업시간, 프랜차이즈
tags: [tutorial, advanced]
sidebar: tutorial_sidebar
permalink: advanced_restaurant_bob.html
summary: 식당에서 일하는 식당곰, 밥입니다!
previous: {
    title: 버그채집봇, 파브르,
    url: advanced_bug_hunting_fabre.html
}
next: {
    title: 웹에이전씨봇, 스페이드컴퍼니,
    url: advanced_agency_spadecompany.html
}
---

## 샘플챗봇 살펴보기
이번에 소개하려고 하는 챗봇은 식당에서 일하는 식당곰, 밥입니다.
식당, 레스토랑, 카페에서 메뉴, 매장위치, 영업시간 등 자주 문의되는 질문에 대답하고 프랜차이즈 가입문의 접수를 받는 챗봇입니다.


<span class="link">[식당곰, 밥을 Frogue에서 만나보기](https://frogue.danbee.ai/?chatbot_id=1f517ca0-4735-4d9a-85bf-65ccdf731f21){:target="_blank"}</span><br/>

{% include image_border.html file="tutorial\sample_bob\bob_01_welcome.PNG" caption="Frogue에서 만나는 식당곰, 밥" %}

## 식당곰, 밥은?
밥은 마늘과 양파를 열심히 먹어 인간이 되려 했지만, 인간이 되는 것은 어려웠습니다. 대신 인간의 언어와 요리를 깨우치게 됩니다. 언젠가 자신을 위한 레스토랑을 열고야 말겠다는 마음으로 무작정 인간세계에 와서 식당에 취직을 했습니다.

### 식당곰, 밥의 목적!
메뉴, 영업시간, 영업점 위치와 같은 자주 묻는 문의에 대답하고, 프랜차이즈에 관심이 있는 훌륭한 사장님들의 상담접수를 담당합니다. 또한 대화 과정에서 고객으로 부터 들을 수 있는 중요한 인사이트를 얻어내는 역할도 합니다.

### 식당곰, 밥이 주목하는 Pain Point
영업점이 몇 시까지 하는지, 어떤 메뉴가 있는지 확인하는 전화는 고객유치를 위해 매우 중요한 정보입니다. 하지만 매우 바쁘게 돌아가는 식당에서 중간 중간 걸려오는 전화를 받아 대응하는 것은 쉬운 일이 아닙니다. 또한, 영업점을 확대하기 위한 프랜차이즈 모집도 중요한 요소입니다. 하지만 프랜차이즈에 가입할 마음이 생긴 사장님이 장시간 전화 대기를 타게 되면, 자신의 가입의사를 밝힐 수 있는 기회를 포기할 확률도 발생합니다. 

### 식당곰, 밥의 가치
식당곰, 밥은 디지털 채널에서 식당 브랜드에 관심있는 고객과 파트너쉽을 원하는 기업들과 소통을 대신합니다.

샘플로 제공되는 챗봇에서는 fabre@danbee.ai가 사용자로부터 받은 정보를 단비 운영팀 슬랙에 메시지를 보내고, 접수자에게는 접수완료 e-mail을 보내게 되어있습니다.
원하시는 형태로 상담전문 조직 등 관련 부서에게 전달하도록 변경하실 수 있습니다.

## 식당곰, 밥의 UX
식당홈페이지, 또는 블로그, 페이스북 메신저에 온 사용자들은 식당곰 밥과 대화하면서 브랜드, 메뉴, 매장위치를 자연스럽게 알게 됩니다.

### 메뉴 안내
식당곰, 밥이 가장 좋아하는 메뉴를 추천해줍니다. 가장 자신 있는 메뉴, 프로모션하고 있는 메뉴를 보여주고 다른 메뉴도 궁금하게 만듭니다.
모든 메뉴를 볼 수 있는 링크를 마지막에 제공해서 전체메뉴를 볼 수 있게 합니다.
{% include image_border.html file="tutorial\sample_bob\bob_02_menu.PNG" caption="식당곰 밥이 보여주는 메뉴" %}

### 영업점 안내
영업점의 위치, 영업점별 영업시간을 안내합니다. 
{% include image_border.html file="tutorial\sample_bob\bob_03_location.PNG" caption="영업점 위치" %}

영업점이름을 포함해서 물어볼 수도 있습니다. 
{% include image_border.html file="tutorial\sample_bob\bob_05_candidate_slack.PNG" caption="Slack으로 접수된 영업점 후보" %}

영업점 이름을 포함하지 않고 물어보면 어느 영업점에 대해 알고 싶냐고 되묻습니다.
{% include image_border.html file="tutorial\sample_bob\bob_03_location.PNG" caption="영업점 위치" %}

생각했던 지역에 영업점이 없을 수도 있습니다. 이런 경우, 영업점 후보를 수집할 수 있는 요소를 버튼으로 제공합니다.
{% include image_border.html file="tutorial\sample_bob\bob_04_candidate.PNG" caption="영업점 후보 수집" %}
영업점을 물어보려던 고객은 자연스럽게 영업점 후보를 제안하게 되었고,
많은 고객이 요청할 경우, 해당 지역에 식당브랜드에 대한 관심이 높다는 중요한 인사이트를 얻을 수 있게 됩니다.

### 프랜차이즈 상담접수
우연히 식당에서 식사를 하는 과정에서 식당브랜드에 대한 호감이 생긴 정모 사장님. 프랜차이즈 상담 의사가 있는 상태에서 홈페이지에 방문했다가 챗봇과 간단한 대화를 하게 됩니다. 이때, 프랜차이즈 상담접수 버튼이 있다면? 방금 든 긍정적인 생각이 휘발되기 전에 액션으로 이어집니다. 상담전에 수집해야할 몇 가지 정보와 연락처를 받으면 상담접수가 완료됩니다.
"당장" 상담을 시작하는 것이 아닌, 식당 오픈 후보에 대한 리서치후에 심도있는 상담으로 바로 넘어갈 수 있는 것이죠.

{% include image_border.html file="tutorial\sample_bob\bob_06_fran_01.PNG" caption="프랜차이즈 상담접수 흐름" %}

사장님은 채팅하듯이 자신의 생각을 식당브랜드에 보내게 됩니다.
{% include image_border.html file="tutorial\sample_bob\bob_07_fran_02.PNG" caption="상담접수 내용 최종 확인" %}

그리고 바로 접수가 잘되었다는 메일을 받게 됩니다.
{% include image_border.html file="tutorial\sample_bob\bob_09_fran_04.PNG" caption="프랜차이즈 제휴 의사가 있는 사장님에게 전달된 접수 메일" %}

한편, 프랜차이즈 상담팀은 즉시 상담신청 내용을 받아볼 수 있게 됩니다.
{% include image_border.html file="tutorial\sample_bob\bob_08_fran_03.PNG" caption="Slack으로 접수된 프랜차이즈 상담 내용" %}

식당곰, 밥은 샘플챗봇이기 때문에 danbee.Ai에서 바로 받아서 원하는 질문과 흐름으로 수정하여 홈페이지나 모바일앱, 페이스북과 같은 메신저에 연결이 가능합니다.
{% include image_border.html file="tutorial\sample_bob\bob_10_fran_05.PNG" caption="시각적으로 드러나는 대화흐름" %}


## 적용 방법

danbee.Ai에 접속하여, 챗봇 샘플 가져오기할 수 있습니다.
<span class="link">[Sample Chatbot 가져오는 방법 확인하기](/samplebot.html#%EC%83%98%ED%94%8C%EC%B1%97%EB%B4%87-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0)</span><br/>


가지고 온 챗봇을 아래와 같은 방법을 통해 출동시킬 수 있습니다.

1. danbee.Ai에서 제공하는 챗봇전용 채팅창, [프로그(Frogue)](/channel_frogu.html) <br>
2. 개발자를 위한 [Native API](/channel_native_app.html)<br>
3. 다양한 메신저 플랫폼에 [연결](/channel_connection_settings.html)<br>

가장 쉬운 방법은 프로그를 이용하는 방법입니다.

### 1. 모바일앱 적용방법 : Frogue Web URL을 모바일앱에 Embedding
가장 쉽게 적용하는 방법은 Web URL을 모바일앱의 HTML View에 적용하는 것입니다.
모바일앱으로 구현된 IT서비스를 사용하다 발생하는 제보, 문의사항을 접수받고 간단한 문의사항에 답변할 수 있습니다.

### 2. PC웹, 모바일웹 적용방법 : Frouge Web Embedding Code를 웹사이트 body내에 삽입
이미 웹사이트를 가지고 계신가요? Live Chat UI로 적용이 가능합니다.
웹페이지 우측하단에 위치한 상태로, 언제든 사용자의 제보, 문의사항을 접수받고 간단한 문의사항에 답변할 수 있습니다.


### 기능 최적화
샘플로 제공되는 파브르가 보내는 이메일 주소와 슬랙주소만 바꾸면 바로 쓰실 수 있지만
여러분들의 서비스가 무엇이냐에 따라 기능이 달라질 수 있습니다. 아래의 변경을 고려해 보세요.

#### 1. 질문 변경
접수 받고 싶은 유형이 다를 수도 있겠습니다. 다른 유형으로 바꾸어 보세요.

#### 2. 간편 답변 추가 
사용자 로그에서 문의사항 및 자동 처리가능한 접수사항을 보면서 하나씩 추가하는 방법도 있고
다량으로 업로드하여 학습시킬 수도 있습니다. [Intent 및 간단 답변 업로드](/intent.html#의도intent-업로드)

#### 3. API 설정
단비에서 미리 만들어놓은 API가 있습니다. 사용자 및 운영자에게 전달하는 용도로 사용하실 수 있습니다.
좋은 아이디어가 있다면 직접 API를 만들어 적용해보는 것도 좋을 것 같습니다.
1. [Gmail 메일 전송](/predefined_api_gmailsender.html) <br>
2. [네이버 메일 전송](/predefined_api_navermailsender.html) <br>
3. [슬랙채널 메시지 전송](/predefined_api_slackchannelsender.html) <br>
4. [AWS 메일 전송](/predefined_api_awssessender.html) <br>

### 브랜드 최적화
캐릭터가 기존 서비스와 잘 어울린다면, 정말 다행입니다!
하지만, 브랜드에 어울리지 않는다고 판단되신다면 변경하실 수 있습니다.

1. 프로필 변경 : 챗봇 설정에서 프로필 사진을 변경하세요.
2. 말투 변경 : 말투가 너무 가볍거나 너무 무겁나요? Chatflow에 있는 멘트들을 쉽게 수정하실 수 있습니다.
3. 이모티콘 추가 : 이모티콘을 활용하면 챗봇과의 대화를 더 즐겁게 바꿀 수 있습니다. 캐릭터의 이모티콘을 다양하게 만들어 제공해 보세요.

## 마치며,
챗봇은 빈번하게 발생하는 커뮤니케이션, 간단한 서비스 처리에 적합한 서비스입니다.
지금 가지고 계신 웹사이트, IT시스템, 블로그 등에 적용해보세요.
하고 계신 업무에 따라 다양한 아이디어가 떠오르실 것입니다.

## 함께해요! 챗봇시대;) 
단비아이엔씨는 함께 챗봇시대를 만들어갈 파트너, 인재를 찾고 있습니다. 

[contact@danbee.ai](mailto:contact@danbee.ai)로 연락주세요!


