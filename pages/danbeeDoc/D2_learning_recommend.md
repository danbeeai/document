---
title: 학습 추천 
tags: [log, nlu, chatflow, basic]
keywords: Basic Conversation
summary: 사용자가 입력한 문장에 따라 학습을 추천합니다. 운영자를 돕는 Ai기능입니다.
sidebar: danbee_doc_sidebar
permalink: learning_recommend.html
folder: danbeeDoc
previous: {
    title: 대화 이력 관리,
    url: log.html
}
next: {
    title: 사용 현황 - 처리량/학습/대화,
    url: dashboard.html
}
---
{% include callout.html content="위치 : 챗봇 만들기 > 챗봇 운영 > 학습 추천" type="default" %}

### 챗봇을 운영하는 과정에서 학습을 돕는 기능
단비Ai에서는 챗봇이 학습해야 할 사항을 모아서 보여주는 대화이력 기반 학습추천 기능을 제공하고 있습니다. 이 기능은 사용자가 입력한 문장이 중의적인 표현이거나 낮은 신뢰도로 추론되었을 때 사용자가 최종 선택을 하도록 하고, 최종선택한 의도가 추천되는 방식입니다. 사용자의 피드백을 바탕으로 챗봇이 학습해야할 문장들이 자동으로 리스트업 되는 방식입니다. 추천 사항을 선택하여 학습하면, 사용자가 입력했던 문장이 대화 의도의 예문으로 등록됩니다.

{% include image.html file="blog/009_01_recommend.PNG" caption="사용자와 대화한 이력을 바탕으로 학습해야 할 문장 추천" %}



{% include bottom.html %}
