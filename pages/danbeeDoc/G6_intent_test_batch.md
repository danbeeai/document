---
title: 대화의도 테스트
tags: [settings, nlu, advanced]
keywords: General Conversation
summary: 대량의 문장을 업로드하여 일괄적으로 테스트 할 수 있는 기능입니다.
sidebar: danbee_doc_sidebar
permalink: intent_test_batch.html
folder: danbeeDoc
previous: {
    title: 공통 변수,
    url: settings_manage_variables.html
}
next: {
    title: 특수 상황 설정,
    url: settings_personality.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 고급기능 > 대화의도 테스트" type="default" %}

{% include important.html content="Standard 요금제에서 제공되는 기능입니다. [요금제 살펴보기](https://danbee.ai/pricing.html)" type="default" %}

## 개요
대량의 문장을 업로드하여 일괄적으로 테스트 할 수 있는 기능입니다.

## 사용 절차
1. [샘플 파일 다운로드]를 클릭해 CSV파일을 다운로드 합니다.
2. 테스트 하려고 하는 예문을 CSV파일의 첫번째 컬럼(A컬럼)에 입력하고 저장합니다.
3. [테스트 데이터 업로드]버튼을 클릭해 저장한 파일을 업로드합니다.
4. [테스트 요청] 버튼을 클릭하면 파일업로드에 성공했다는 메시지가 나옵니다.
5. 업로드 성공 후에 [테스트 결과]탭을 클릭하면 등록 예문 건수, 매칭 성공건수, 매칭 실패건수가 표시됩니다.
6. 업로드한 파일명을 클릭하면 테스트 결과를 CSV로 받아볼 수 있습니다.

## 대화 의도 테스트를 사용하기에 좋은 시점
- 챗봇 서비스를 오픈하기 전에 모든 대화 의도가 제대로 동작하는지 확인하기에 좋습니다.
- 대화 의도의 종류가 많은 챗봇을 운영할 때 유용한 기능입니다. A라는 대화의도에 추가로 학습된 예문으로 인해 B라는 대화의도가 잘못 추론되는 등의 파급효과를 확인하기 위한 회기테스트 용도로 사용할 수 있습니다.

## 사용시 고려사항
- 테스트 시 예문 수만큼 사용량(CC)이 측정됩니다.
- 파일 당 최대 3MB까지 업로드 할 수 있으며, 파일명은 최대 70자까지 허용됩니다.



{% include bottom.html %}
