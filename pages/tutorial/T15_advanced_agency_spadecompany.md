---
title: 에이전씨봇, 스페이드컴퍼니 
keywords: 디자인에이전씨, UX, BX, 그래픽디자인, 템플릿챗봇, 샘플챗봇
tags: [tutorial, advanced]
sidebar: tutorial_sidebar
permalink: advanced_agency_spadecompany.html
summary: Creative Agency 스페이드컴퍼니의 샘플챗봇입니다.
previous: {
    title: 식당곰, 밥,
    url: advanced_restaurant_bob.html
}
---

## 샘플챗봇 살펴보기
이번에 소개하려고 하는 챗봇은 UX, BX, 그래픽디자인에 대한 프로젝트를 전문적으로 수행하는 에이전씨를 위한 챗봇입니다.
뛰어난 감각과 축적된 경험을 가진 크리에이티브 에이전씨인 스페이드컴퍼니(http://spadecompany.kr)와 함께 진행한 샘플챗봇 프로젝트입니다.

스페이드 컴퍼니의 웹사이트에 실제로 적용되어 있으니 많이 방문해주시기 바랍니다.
에이전씨 챗봇은 크리에이티브 프로젝트을 맡기기 위해 홈페이지에 방문한 고객들에게 회사의 주요 정보를 전달하고, 프로젝트 의뢰를 접수받을 수 있게 되어 있습니다.

혹시 디자인 프로젝트와 같이 의뢰를 받아서 사업을 진행하고 계신다면, 스페이드컴퍼니 챗봇을 가져와서 회사에 맞게 수정하여 활용하시기 바랍니다. 

{% include image_border.html file="tutorial\sample_spadecompany\spade_01_demo.gif" caption="회사를 소개하고, 프로젝트 의뢰상담을 접수받는 챗봇" %}

## 직접입력한 문장에 대해 답변!
버튼을 클릭해서 넘어가는 형태를 기본적인 UX로 가져가지만, 직접 입력하는 문의사항에도 답변할 수 있습니다.
현재는 7가지 유형의 의도에 대해서 답변할 수 있게 되어 있습니다.

{% include image_border.html file="tutorial\sample_spadecompany\spade_02_demo_nlp.gif" caption="고객이 입력한 문장을 이해하고 답변하는 챗봇" %}

고객이 많이 문의하는 것이 무엇인지 이미 알고 있다면 미리 등록해두면 자동으로 응답을 합니다. 의도추론 이력을 보면 어떤 문의가 들어왔는지 확인할 수 있습니다.



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

여러분들의 서비스가 무엇이냐에 따라 기능이 달라질 수 있습니다. 아래의 변경을 고려해 보세요.

#### 1. 회사정보 변경
회사에 대한 기본적인 정보를 공통변수 메뉴에서 수정하여 테스트 해보실 수 있습니다.
{% include image_border.html file="tutorial\sample_spadecompany\spade_03_common_prameter.PNG" caption="공통변수를 수정하면 답변내용이 달라집니다." %}

[공통 변수 관리에 대해 더 알아보기](/settings_manage_variables.html)

#### 2. 접수 세부내용 변경
Chatflow에서 접수받고 싶은 세부사항을 수정하실 수 있습니다.

#### 3. 간편 답변 추가 
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

1. Frogue의 디자인 변경기능을 통해 회사의 브랜드를 더욱 강조할 수 있습니다.
{% include image_border.html file="tutorial\sample_spadecompany\spade_04_frogue_customize.PNG" caption="Frogue의 디자인 변경기능" %}
2. 프로필 변경 : 챗봇 설정에서 프로필 사진을 변경하세요.
3. 말투 변경 : 말투가 너무 가볍거나 너무 무겁나요? Chatflow에 있는 멘트들을 쉽게 수정하실 수 있습니다.
4. 이모티콘 추가 : 이모티콘을 활용하면 챗봇과의 대화를 더 즐겁게 바꿀 수 있습니다. 캐릭터의 이모티콘을 다양하게 만들어 제공해 보세요.

## 마치며,
챗봇은 빈번하게 발생하는 커뮤니케이션, 간단한 서비스 처리에 적합한 서비스입니다.
지금 가지고 계신 웹사이트, IT시스템, 블로그 등에 적용해보세요.
하고 계신 업무에 따라 다양한 아이디어가 떠오르실 것입니다.

## 함께해요! 챗봇시대;) 
단비아이엔씨는 함께 챗봇시대를 만들어갈 파트너, 인재를 찾고 있습니다. 

[contact@danbee.ai](mailto:contact@danbee.ai)로 연락주세요!


