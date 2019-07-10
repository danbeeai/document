---
title: 단비 업데이트 로그
tags: [chatbot]
keywords: 단비 플렛폼 업데이트
summary: 단비의 업데이트 내역을 볼 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: update_log.html
folder: danbeeDoc
previous: {
    title: 간단한 챗봇 만들어보기,
    url: basic_create_chatbot.html
}
next: {
    title: 파라미터 관리,
    url: parameter.html
}
---

## 7월 16일 — 세션 파라미터 기능 추가 및 파라미터 관리 기능 개선

### Features

{% include image.html file="changelog/session.gif" %}
- 이제 세션단위로 관리되는 파라미터를 생성하고 이용할 수 있습니다. 
*세션 파라미터는 사용자세션동안 그 값을 잃지않고 유지하는 파라미터입니다. 사용자 이름이나 주소와 같이 한번 입력된 뒤에는 계속 사용되어야하는 값을 저장하는데 유용하게 쓸 수 있습니다.*

{% include image.html file="changelog/param_panel.gif" %}
- 파라미터 관리 기능이 개선되었습니다.*이제 리슨노드를 통하지 않아도 챗플로우 설정을 변경하고 파라미터 목록을 조회, 추가할 수 있습니다.*

### Fix & Change
- 이제 챗플로우 상세에서 연관된 인텐트로 이동시 저장여부를 먼저 확인하고 이동합니다.

- 테스트 패널에서 파라미터가 어떻게 값이 변하는지 더 자세하게 알 수 있게 되었습니다.

- 테스트 패널에서 노드 자세히 보기(물음표 버튼)를 눌렀을 때 스크롤이 넘치던 현상이 수정되었습니다.

----------------------------------------------

## 6월 18일 — 액션기능

### Features

- 각종 노드에 액션 기능이 추가되었습니다.
*사용자가 챗봇과 인터렉션하면서 챗봇이 추가적으로 다른 행위를 할 수 있습니다.*

----------------------------------------------

## 6월 3일 — FAQ봇 위자드 기능 제공

### Features

{% include image.html file="changelog/faqBot.gif" %}
- 엑셀 업로드를 통해 쉽게 FAQ 챗봇을 만들수 있는 FAQ 위자드 기능이 제공됩니다 
*정해진 양식에 따라 FAQ 데이터를 업로드하거나, 직접입력하여 쉽게 FAQ봇을 제작할 수 있습니다.*

### Fix & Change
- 이제 대화의도에 위자드에 의해 생성된 의도인지 표시가 됩니다.

- 대시보드에서 레이아웃이 깨지던 문제를 수정했습니다.