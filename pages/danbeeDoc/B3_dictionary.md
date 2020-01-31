---
title: 고유 용어 사전 
tags: [nlu, advanced]
keywords: Basic Conversation
summary: 고유 용어 사전 관리을 통하여 새로운 단어를 등록할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: dictionary.html
folder: danbeeDoc
previous: {
    title: Jump 노드,
    url: chatflow_jump.html
}
next: {
    title: 기본답변 설정,
    url: settings_personality.html
}
---

{% include callout.html content="화면 위치 : 그룹 관리 > 고유 용어 사전" type="default" %}
{% include image.html file="synonym/1.PNG" %}
**고유 용어 사전**이란, 사용자가 원하는 단어를 직접 사전에 등록하여 이용할 수 있는 서비스입니다. danbee.Ai에서 기본적으로 제공하는 시스템사전에 등록되어 있지 않은 단어를 인식하거나 복합 명사를 하나의 단어로 인식하기 위해 사용할 수 있습니다. **인명, 상품명, 신조어 등 일반적이지 않은 명사**를 등록하면 해당 단어의 인식률을 높일 수 있습니다. <br/>

해당 메뉴에서는 다음과 같은 기능을 사용할 수 있습니다.<br/> 
 - [사전 단어 관리](dictionary.html#사전-단어-관리)
 - [반영 요청](dictionary.html#반영-요청)

## 사전 단어 관리

### 단어 추가
새로운 단어를 추가하고 싶을때 **단어 추가**를 클릭하여 단어의 대표어와 유의어를 추가할 수 있습니다.

>##### 유의어
특정 단어로 인식하고 싶은 비슷한 단어의 집합 
>##### 대표어
유의어의 대표 단어. 모든 유의어는 해당 대표어로 인식.

예를 들어 '단비플랫폼, 챗봇플랫폼 단비, danbee.Ai'를 모두 '단비닷에이아이'로 인식하고 싶을 때 단어 추가 버튼을 눌러 사전을 등록할 수 있습니다. 

단어는 하나당 최대 40자까지 등록 가능하며 하나의 대표어당 최대 100개의 유의어를 가질 수 있습니다. 중복된 대표어 또는 유의어는 등록할 수 없습니다.

### 단어 삭제
등록한 단어를 삭제하고 싶을 때는 해당하는 사전 행 오른쪽의 휴지통 아이콘을 눌러 삭제합니다.
삭제버튼을 누른뒤에 해당 변경사항을 실제로 반영하기 위해서는 저장해야 합니다.

{% include image.html file="synonym/synonym_03_delete_word.png"  caption="단어 삭제 버튼" %}

단, 현재 사전에 반영되어 있는 단어는 다음 반영 전까지 실제 사전에서 삭제되지 않으므로 삭제 예정 상태가 됨을 확인할 수 있습니다. 

{% include image.html file="synonym/synonym_03_delete_word_wating.png"  caption="삭제 예정 확인" %}

'사전 반영'에 대해서는 아래의 [반영 요청](dictionary.html#반영-요청)에서 확인할 수 있습니다. 한 번 삭제를 확정하면 되돌릴 수 없으니 주의하시기 바랍니다. 

### 단어 조회
{% include image.html file="synonym/synonym_04_search.png" %}
등록한 단어에 대하여 단어 종류를 선택하여 검색할 수 있습니다.

>##### 전체
대표어와 유의어 모두 검색합니다.
>##### 대표어
대표어로만 검색합니다.
>##### 유의어
유의어로만 검색합니다.




### 반영 요청
{% include image.html file="synonym/2.PNG"  caption="반영 요청 버튼" %}
고유 용어 사전 관리 화면에서 단어를 등록했다면 반드시 우측 상단의 **반영 요청** 버튼을 클릭해야 합니다. 반영 요청이 들어온 데이터에 한에서 최종적으로 시스템 사전에 반영되게 됩니다.
{% include note.html content="해당 사전은 사용하고 있는 모든 챗봇에 동일하게 반영됩니다." %}
반영 요청 시에 반영이 최종 완료될 때까지 단어 추가/수정/삭제가 불가능해집니다.
사전의 반영은 순차적으로 처리되기 때문에 다소 시간이 걸릴 수 있습니다. 진행 상황은 대표어 옆 아이콘으로 확인할 수 있습니다.

>##### 대기중
반영 요청 후 대기 상태
>##### 진행중
반영이 진행되는 상태
>##### 완료
최종적으로 시스템 사전에 단어가 반영된 상태
>{% include image.html file="synonym/synonym_06_state.png"  caption="대기/진행/완료 상태" %}


## 고유 용어 사전 확인

고유 용어 사전에 단어를 등록하면 어떤식으로 동작하는지 [대화의도 테스트 패널](demo_n_test_panel.html#nlu-intent-테스트-패널)을 통하여 확인할 수 있습니다. 예를 들어 '단비닷에이아이'라는 단어를 사전 등록 및 반영 전후 어떻게 인식을 하는지 테스트할 수 있습니다.

### 사전 반영 전

대화의도 테스트 패널에 '단비닷에이아이가 뭐하는 데야?' 라고 입력한 뒤 **TEXT ANALYTICS** 버튼을 누르면 해당 문장이 어떻게 분석되는지 확인할 수 있습니다. 

{% include image.html file="synonym/synonym_07_test_01.png"  caption="분석 결과 - 사전 등록 전" %}

'단비닷에이아이'라는 단어는 일반적이지 않기 때문에 하나의 단어로 인식하고 싶지만 여러 단어로 쪼개진 채로 인식됨을 확인할 수 있습니다.
<br/><br/>

### 사전 반영 후

고유 용어 사전에 대표어 '단비닷에이아이', 유의어 '단비플랫폼, 챗봇플랫폼 단비, danbee.Ai'를 반영 한 후 위와 동일한 테스트를 진행합니다.

{% include image.html file="synonym/synonym_07_test_02.png"  caption="분석 결과 - 사전 등록 후 대표어 테스트" %}

원하는 대로 '단비닷에이아이'라는 단어가 하나의 단어로 인식됨을 확인할 수 있습니다. 또한 해당 단어가 고유 용어 사전에 등록된 단어임이 표시됩니다.

만약 유의어에 넣었던 'danbee.Ai'이란 단어를 이용해 'danbee.Ai가 뭐하는 데야?'라고 테스트하면 다음과 같은 분석 결과가 나옵니다.

{% include image.html file="synonym/synonym_07_test_03.png"  caption="분석 결과 - 사전 등록 후 유의어 테스트" %}

danbee.Ai라는 단어가 단비닷에이아이로 바껴서 인식됨을 확인할 수 있습니다.

이와 같이 고유 용어 사전을 활용하면 챗봇이 알아듣지 못하던 말을 더욱 잘 알아들을 수 있도록 도와줄 수 있습니다.


{% include bottom.html %}
