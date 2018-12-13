---
title: 챗봇UX 2편, 챗봇 설계 UX 프로세스
tags: [blog, welcome, Chatbot-UX]
keywords: blog
summary:  챗봇을 설계하는 UX 프로세스를 공유합니다.
sidebar: blog_sidebar
permalink: blog_003_UX02_chatbot_ux_process.html
folder: blog
---

챗봇시대를 함께 열어가는 여러분, 안녕하세요!

이번 포스트는 원작자인 Abhishek Jain으로 부터 번역 및 배포에 대한 허락하에
UXness에 기고된 [Designing a Chatbot - UX Process](http://www.uxness.in/2017/11/designing-chatbot-ux-process.html){:target=_blank}를 번역하여 공유드립니다.

챗봇도 사용자와 인터렉션하는 도구이며, UX관점에서 바라봐야 한다고 생각합니다.
UX관점으로 가벼우면서 핵심적인 내용이 잘 정리되어 있어 공유드리게 되었습니다.
원작자인 Abhishek Jain님에게 감사드립니다.

자, 시작합니다!

**여기서 부터 번역시작**

## 꽤 오래된 챗봇의 개념

{% include image.html file="blog/003_01_chatbot_concept_illustration.jpg" max-width="700" caption="챗봇의 컨셉, image source : <a href='https://dribbble.com/shots/2886534-Chatbots-Illustration-finished'>Christos</a>" %}


이 시대의 기업들은 앱이나 웹기반의 인터페이스에서 대화기반 플랫폼, 챗봇으로 전환하고 있습니다. 챗봇은 인터넷을 통해 인간 사용자와의 대화를 시뮬레이션 하도록 설계된 컴퓨터 프로그램입니다. 챗봇은 새로운 발명품이 아닙니다. 튜링테스트와 같은 실험과 최초의 챗봇 엘리자의 발명을 통해 1950~60년대에 앨런튜링(Alan Turing)과 요제프 바이첸바움이 인간과 같이 의사소통 하는 컨셉의 컴퓨터를 고민했었다는 것을 알 수 있습니다. 


오늘날 챗봇은 전 세계적으로 영향력이 상당합니다. 페이스북, 트위터, 텔레그램 등 많은 플랫폼들이 기업 및 제품과의 상호작용에 큰 변화를 준 챗봇과 통합 연계할 수 있도록 플랫폼을 제공하고 개방하고 있습니다. 


오늘은 챗봇 설계 경험을 바탕으로 챗봇 설계 과정을 공유하려고 합니다. 이 글의 목표는 UX 디자이너 관점에서 ‘챗봇 설계 방법’, ‘챗봇 설계 시 취해야할 조치’에 대한 인식을 확대하는 것입니다. 공유드리는 이 프로세스를 개선하기 위한 아이디어나 피드백은 언제나 환영입니다!

## 챗봇 디자인 프로세스

{% include image.html file="blog/003_02_chatbot-design-process.jpg" max-width="700" caption="챗봇 디자인 프로세스" %}

각각의 단계별로 고려해야할 사항을 살펴보도록 합시다.


### 1. 범위와 요구사항

- 챗봇을 선택해야 하는 이유! 챗봇의 컨텍스트 이해
- 챗봇이 제공할 기능 및 콘텐츠 리스트업
- 기능과 콘텐츠의 제공여부를 명확히하고, 제공할 기능과 콘텐츠는 구체화 
- 챗봇을 출시할 플랫폼(메신저) 선택

### 2. 입력 (Input) 파악

챗봇과 인터렉션하는 목표는 논리적인 (대화)단계로 나누어 질 수 있습니다.
챗봇이 받게 되는 주요 입력은 아래와 같습니다.

1. 사용자로부터 (사용자가 제공하는 정보 또는 질문. 텍스트나 음성)
2. 디바이스로부터 (지리위치 등 디바이스 센서)
3. 지능형 시스템으로부터 (사용자에 대한 이력데이터를 통해 파악한 정보)


### 3. 챗봇UI요소 이해하기

페이스북, 트위터, 텔레그램, 위챗 등 챗봇을 지원하는 다수의 플랫폼들이 있습니다.아래 링크에서 다양한 템플릿을 확인해 보세요.

{% include image.html file="003_03_chatbot-ui-element.jpg" max-width="700" caption="챗봇 UI 요소" %}


### 4. 최초 인터렉션 세공작업

1. 사용자에게 제공할 핵심 서비스를 이해 시킵니다.
2. 추가대화를 위한 힌트나 가이드를 제공합니다.
3. Call-To-Action을 제공합니다.
4. 기본 액션을 제공합니다.

{% include image.html file="blog/003_04_chatbot-ux-welcome-get-started-greeting.jpg" max-width="700" caption="챗봇 UI 요소, image source : <a href='https://www.searchenginejournal.com/marketers-guide-facebook-messenger-bots/179028'>searchenginejournal.com</a>" %}

{% include note.html content="지난 포스트에서 Welcome Message의 설계 방법에 대해 공유한적이 있습니다. [여기](http://doc.danbee.ai/blog_002_UX01_welcome.html)에서 확인이 가능합니다. " %}


### 5. 대화 및 지능 구축하기

1. 사용자 관점에서, 특정한 요구사항을 챗봇에게 요구할 수 있는 방법을 생각해보십시오.
2. ‘인간’이 느껴지게
3. 챗봇의 성격
4. 누락되거나 모호한 입력사항은 어떻게 처리할지
5. 스몰톡(일상대화)
6. 사용자의 상호작용, 선택, 질의, 메시지, 인구통계학적인 정보에 대한 이력 기록

### 6. 테스팅

1. 챗봇의 사용성을 테스트하십시오.
2. 사용자가 인터렉션 하는 화면을 녹화해서 분석하세요.
3. 모바일과 웹 모두 테스트 해야합니다.

**여기 까지 번역 끝**

## 챗봇을 UX관점으로 설계 한다는 것

전체적인 흐름을 느낄 수 있었습니다. 특히 작지만 중요한 요소들을 짚어주었던 것 같습니다.
앞으로도 danbee.Ai 블로그에서는 챗봇관련 콘텐츠를 원작자의 허락하에 번역/공유할 계획입니다.
좋은 글이 있다면 추천 부탁드립니다!

{% include note.html content="danbee.Ai에서는 늘 함께 챗봇시대를 열어갈 인재와 파트너를 찾고 있습니다.
<br/> [contact@danbee.Ai](mailto:contact@danbee.ai)로 편지를 보내주세요!" %}
