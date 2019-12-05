---
title: 대시보드 
tags: [dashboard, nlu, chatflow, basic]
keywords: 대화 이력 시각화
summary: 챗봇의 동작한 이력을 시각화 하여 대쉬보드로 보여드립니다.
sidebar: danbee_doc_sidebar
permalink: dashboard.html
folder: danbeeDoc
previous: {
    title: 대화 이력 관리 ,
    url: log.html
}
next: {
    title: 테스트 패널 및 시뮬레이션,
    url: demo_n_test_panel.html
}
---

danbee.Ai에서는 실 챗봇 사용 통계를 애널리틱스 메뉴에서 시각화된 자료로 확인할 수 있습니다. 

- [처리량 통계](dashboard.html#Transaction)
- [학습 통계](dashboard.html#Learning)
- [대화 통계](dashboard.html#Dialog)
- [행동 분석](dashboard.html#Dialog)
- [리포트 다운로드](dashboard.html#Dialog)



## 처리량 통계

{% include image.html file="dashboard/dashboard_transaction.PNG"  %}

챗봇의 사용량을 모니터링하는 화면입니다.
세션수는 session_id를 기준으로 산정되며, 매일 새벽 3시 ~ 4시 사이에 전일 생성된 session은 Reset 됩니다.
전체사용량은 테스트 패널과 시뮬레이션의 사용량이 포함되며, Chat Count는 테스트 패널과 시뮬레이션의 사용량이 제외됩니다.

{% include note.html content="의도추론, 대화흐름 사용순위의 추이를 보면, 주간/월간 사용자들의 질의사항이 어떻게 달라지는지 추적할 수 있습니다.  Welcome Message에 노출되는 버튼을 시즌, 요일에 따라 다르게 표시하면 사용자 만족도는 더 높아질 것입니다." %}


## 학습 통계

{% include image.html file="dashboard/dashboard_learning.PNG" %}

의도추론의 학습 현황을 모니터링하는 화면입니다.
학습추천 화면에서 추천된 학습을 수행하면 NLU 학습율이 올라갑니다.
학습의 결과는 의도추론 신뢰도와 Default Fallback 비율로 평가할 수 있습니다.
감성평가는 "장대비"와 "함께맞는비" 등급만 제공되는 기능으로 의도추론 시 대화 내용의 긍정/중립/부정률을 측정하여 확률적 수치로 제공합니다.

{% include note.html content="의도추론의 평균신뢰도를 높일 수 있도록 매일 아침에 학습 추천 메뉴에 올라온 학습 추천 사항을 학습시키기를 권장합니다." %}


## 대화 통계

{% include image.html file="dashboard/dashboard_dialog.PNG" %}
어떤 핵심 단어들이 오고 갔는지 한 눈에 확인할 수 있는 워드클라우드(Word Cloud)와 키워드별 빈도 순위를 보여주는 메뉴입니다.
사람들이 어떤 대화를 나누었는지에 대한 Insight를 얻으실 수 있습니다.

## 행동 분석

사용자들이 어떻게 챗봇과 대화하고, 어떤 과정을 통해 챗봇을 이용했는지 모니터링하는 화면입니다. Session ID를 따로 설정하지 않으면 단비에서 자동으로 생성한 Session ID를 바탕으로 분석이 이루어집니다. 사용하시는 요금제에 따라 이용이 불가능할 수도 있습니다.

## 리포트 다운로드

통계를 다운로드 받아 가공하고 보관할 수 있습니다. 사용하시는 요금제에 따라 이용이 불가능할 수도 있습니다.



{% include bottom.html %}
