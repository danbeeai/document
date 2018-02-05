---
title: 유의어 관리
tags: []
keywords: Basic Conversation
summary: 유의어 관리
sidebar: danbee_doc_sidebar
permalink: synonym.html
folder: danbeeDoc
previous: {
    title: Function 노드,
    url: chatflow_function.html
}
next: {
    title: 기본답변 설정,
    url: settings_personality.html
}
---

## 유의어 관리
 {% include callout.html content="화면 위치 : [유의어(Synonym)]" type="default" %}
**유의어(이하 Synonym)**란, 입력 단어가 포함된 대표어를 검색하는 기능을 합니다.<br/>

해당 메뉴에서는 다음과 같은 내용을 설정할 수 있습니다.<br/> 
 - [유의어 추가](synonym.html#유의어-추가)
 - [유의어 검증](synonym.html#유의어-검증)
 - [유의어 조회](synonym.html#유의어-조회)

### 유의어 추가

**유의어 추가**는 입력 단어가 해당 대표어로 검색되길 원하는 단어를 의미합니다. danbee.Ai는 입력 단어가 의미하는 대표어를 찾습니다. 예를 들어 사용자가 입력한 문장 중 '스벅' 이라는 단어를 입력하였을때 '스타벅스' 라는 대표어를 검색하게 됩니다.<br/>

{% include image.html file="synonym/synonym_add_01.png" max-width="900" caption="유의어 추가" %} 
{% include image.html file="synonym/synonym_add_02.png" max-width="900" caption="유의어 저장" %} 

*+ 유의어 추가* 버튼을 클릭 하면 대표어와 조건메시지를 추가하는 항목이 생성됩니다. *대표어를 입력해주세요* 란 에 대표어를 입력합니다. *조건 메시지를 추가해주세요*항목은 대표어에 포함된 유의어를 입력하는 항목으로 유의어를 입력후 Enter key를 누르면 유의어가 입력됩니다. 대표어 와 유의어 입력이 완료 되면 *V* 버튼을 클릭 해 대표어 와 유의어를 저장합니다.<br/>

{% include warning.html content="유의어를 입력 추가 할때 **대표어, 유의어(조건 메시지)** 를 함께 입력해야 합니다. 하나의 대표어는 복수의 유의어(조건 메시지)를 포함 할 수 있습니다. 입력한 유의어는 배치작업 이후 다음날 사용 가능합니다." %}

### 유의어 검증

**유의어 검증**은 입력 단어가 해당 대표어로 검색 여부를 확인 합니다. 입력된 단어가 유의어와 일치하면 해당 대표어를 반환 합니다.<br/>

{% include image.html file="synonym/synonym_test_01.png" max-width="900" caption="유의어 검증" %}

*① 유의어 입력* 에 유의어를 입력 합니다. *② TEXT_ANALYTICS*를 클릭 하여 형태소 분석 결과를 조회 합니다. *분석결과 목록에 ③분석결과* 유의어의 대표어가 검색 됩니다.<br/>

### 유의어 조회

**유의어 조회**는 입력된 유의어 를 조회, 결과를 목록에 보여줍니다.<br/>

{% include image.html file="synonym/synonym_search_01.png" max-width="900" caption="전체 조회" %}
{% include image.html file="synonym/synonym_search_02.png" max-width="900" caption="대표어 조회" %}
{% include image.html file="synonym/synonym_search_03.png" max-width="900" caption="유의어 조회" %}

조회 조건의 종류 *전체, 대표어, 유의어* 에 따라 대표어, 유의어 검색이 가능 합니다.