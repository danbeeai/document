---
title: Split 노드
tags: []
keywords: Basic Conversation
summary: Split 노드에 대한 이해와 설정하는 방법을 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_split.html
folder: danbeeDoc
previous: {
    title: Slot 노드,
    url: chatflow_slot.html
}
next: {
    title: Carousel 노드,
    url: chatflow_carousel.html
}
---

## Split 노드

Split 노드는 입력된 메시지 및 파라미터 조건에 따라 대화의 흐름을 분기 시켜주는 노드입니다. Split 노드에서 분기할 노드를 추가하기 위해선 연결한 노드가 미리 추가되어있고 노드들은 연결선으로 Split 노드와 연결되어 있어야 합니다. Split 노드와 연결된 노드만 분기할 노드로 선택할 수 있습니다.


Split 노드는 2개의 상세 화면으로 구성됩니다.
- [기본정보](Chatflow_split.html#기본정보)
- [분리조건 설정](Chatflow_split.html#분리조건 설정)

{% include image.html file="chatflow/Chatflow_split_cavas.png" max-width="900" caption="Split 노드" %}


### 기본정보

Split 노드에 표시될 기본적인 노드명과 노드에 대한 내용을 입력합니다.

{% include image.html file="chatflow/Chatflow_split_basic.png" max-width="900" caption="Split노드 기본정보" %}

### 분리조건 설정 

분기조건 설정에 부합할 경우 이동할 노드를 선택합니다. 

{% include image.html file="chatflow/Chatflow_split_select.png" max-width="900" caption="분기 선택" %}

조건식을 활용하여 이동할 노드를 설정하고 싶을 경우에는 아래와 같이 조건식을 설정할 수 있습니다. 
조건식에 활용할 수 있는 것은 Listen 노드에서 선언하였던 변수를 활용하거나 이전에 사용자가 질문한 문장을 활용할 수도 있습니다. 
조건식 선택박스에 변수들이 Parameter에 나열이 되게 되며, '받은 메시지'는 사용자가 질문한 문장을 의미하는데 이 변수는 시스템적으로 '@message' 변수명으로 표시됩니다.
조건식은 [+] 버튼을 선택하여 다중 입력이 가능하며, 이 때 조건식을은 and 조건으로 연산처리하게 됩니다. 

{% include image.html file="chatflow/Chatflow_split_condition.png" max-width="900" caption="분기조건 설정" %}

Split 노드는 다른 노드와 연결이 되어야 있어야 분기조건 설정이 가능합니다. 만약 설정이 안되어 있으면 아래와 같이 다른 노드를 연결해 달라는 메시지가 표시됩니다.

{% include image.html file="chatflow/Chatflow_split_NoConnect.png" max-width="900" caption="Split 노드 미연결시 설정화면" %}

다른 노드와 연결 되어 있는 경우 연결된 노드를 선택할 수 있는 선택지가 나열됩니다. 

{% include image.html file="chatflow/Chatflow_split_Connect.png" max-width="900" caption="Split 노드 연결시 설정화면" %}

### 샘플 시나리오 (분기 테스트)

Split 노드에서는 Listen 노드에 선언된 단어항목(parameter)들의 값을 메시지에 표시할 수 있습니다. 
Split 노드는 분기 조건을 설정하여 해당하는 
해당 시나리오는 'name' 변수값에 이름을 입력 받고 입력 받은 값을 메시지에 표시합니다.

{% include image.html file="chatflow/Chatflow_split_sample.png" max-width="900" caption="분기 테스트 시나리오" %}

{% include image.html file="chatflow/Chatflow_split_sampleSplit.png" max-width="900" caption="분기 설정" %}

'분기 테스트' 시나리오를 테스트해 보면 Split 노드에 부합하는 조건에 해당하는 Speak 노드가 호출되는 것을 확인할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_split_sampleDemo.png" max-width="900" caption="분기 테스트 결과" %}

