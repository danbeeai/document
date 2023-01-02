---
title: Split 노드 
tags: [chatflow, basic]
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

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 주요 대화 > 대화 흐름" type="default" %}
  
<br>
{% include image.html file="chatflow/01_chatflow_split.png" %}


## 개요 

Split 노드는 입력된 메시지 및 파라미터 조건에 따라 대화의 흐름을 분기(나누어 갈라지는 것) 시켜주는 노드입니다. 
  
Split 노드에서 분기할 노드를 추가하기 위해선 연결한 노드가 미리 추가되어있고 노드들은 연결선으로 Split 노드와 연결되어 있어야 합니다. Split 노드와 연결된 노드만 분기할 노드로 선택할 수 있습니다.
  
(*스플릿 노드는 주로 [슬롯(slot)노드](chatflow_slot.html)와 연계하여 사용합니다. 아래 예시를 참조해주세요.)

### 예시

분기라는 개념을 이해하기 위해 예를 들어보겠습니다. 영양제를 추천하는 챗봇의 경우를 가정합니다. 햇볕을 쬐는 시간이 적은 사람에게는 비타민D, 야채와 과일을 잘 먹지 않는 사람에게는 비타민C, 생선을 잘 먹지 않는 사람에게는 오메가3를 추천해주는 식입니다.
  
이렇게 되려면 사용자의 입력 결과에 따라 챗봇의 대답이 달라져야 합니다. A라고 입력한 경우 A', B라고 입력한 경우 B', C라고 입력한 경우 C'를 주는 것이지요.
  
화면과 함께 보면 이해가 쉬워질 것입니다. 슬롯 노드에서 활용할 파라미터 '영양제'를 미리 등록해 두었습니다.
  
{% include image.html file="chatflow/02_chatflow_split.png" %}
  
이제 슬롯 노드 세팅을 들여다 보겠습니다.
  
{% include image.html file="chatflow/03_chatflow_split.png" %}
  
파라미터는 '영양제'로 설정한 후, 세 개의 버튼을 제시하여 어떤 영양제를 추천하면 좋을지 값을 받으려고 합니다. 버튼명에 따라 각각의 값(영양제 이름)을 이어지는 스플릿 노드에 전송하도록 세팅하였습니다.
  
빨간색 박스가 버튼명, 파란색 박스가 전송값입니다.
  
{% include image.html file="chatflow/04_chatflow_split.png" %}
  
스플릿 노드에서는 이렇게 이어집니다. 앞의 슬롯 노드에서 보내준 값이 무엇인가에 따라 '분기'하여 대화 흐름을 다르게 이어갑니다.
  
{% include image.html file="chatflow/05_chatflow_split.png" %}
  
구조로 보면 이렇습니다.
  
{% include image.html file="chatflow/06_chatflow_split.png" %}
  
결과적으로, 사용자의 답변에 따라 챗봇은 다른 응답을 합니다.
  
{% include image.html file="chatflow/07_chatflow_split.png" %}
  
여기까지 스플릿 노드가 무엇인지, 어떤 경우에 쓰는지에 대해 알아보았습니다. 아래는 어떻게 쓰는지에 관한 추가 설명입니다.
  
  
## 분기조건 설정

분기조건 설정에 부합할 경우 이동할 노드를 선택합니다.

{% include image.html file="chatflow/08_chatflow_split.png" %}

이렇게 연결된 노드가 없는 경우, 설정 화면에는 노드와 연결해달라는 옵션만 나타납니다.

{% include image.html file="chatflow/09_chatflow_split.png" %}

스플릿 노드와 연결된 노드의 갯수만큼, 선택할 수 있는 옵션이 늘어납니다.

{% include image.html file="chatflow/10_chatflow_split.png" %}

### 조건식

조건식에 활용할 수 있는 것은 Listen 노드에서 선언하였던 변수를 활용하거나 이전에 사용자가 질문한 문장을 활용할 수도 있습니다. 
  
조건식 선택박스에 변수들이 파라미터에 나열이 되게 되며, ‘받은 메시지’는 사용자가 질문한 문장을 의미하는데 이 변수는 시스템적으로 ‘@message’ 변수명으로 표시됩니다. 
  
{% include image.html file="chatflow/11_chatflow_split.png" %}
  
각각의 꺽쇠들을 클릭하시면, 선택할 수 있는 다양한 조건식이 펼쳐집니다. 챗봇 세팅에 따라 필요한 대로 설정하여 사용하실 수 있습니다.
  
{% include image.html file="chatflow/12_chatflow_split.png" %}
  
[조건추가] 버튼을 선택하여 다중 입력이 가능합니다. 
  
{% include image.html file="chatflow/13_chatflow_split.png" %}  

이 때 조건식들은 and 조건으로 연산처리하게 됩니다.





<!-- 
### 샘플 시나리오 (분기 테스트)

#### 샘플 시나리오 설계

Split 노드에서는 Listen 노드에 선언된 단어항목(parameter)들의 값을 메시지에 표시할 수 있습니다. 
Split 노드는 분기 조건을 설정하여 해당하는 
해당 시나리오는 'name' 변수값에 이름을 입력 받고 입력 받은 값을 메시지에 표시합니다.

{% include image.html file="chatflow/Chatflow_split_sample.png"  caption="분기 테스트 시나리오" %}

#### [분기노드] Split 노드 설정

분기노드에 설정한 조건은 다음과 같이 '받은 메시지'(@message)에 '분기1' 단어가 포함될 경우에는 '1번 분기' Speak 노드로 '분기2', '분기3' 단어가 포함될 경우는 각각의 Speak 노드로 분기되도록 설정합니다. 

{% include image.html file="chatflow/Chatflow_split_sampleSplit.png"  caption="분기 설정" %}

#### [1번 분기, 2번 분기, 3번 분기] Speak 노드 설정

Speak 노드에서는 분기시 구분되는 메시지를 '기본 메시지'로 설정합니다. 

{% include image.html file="chatflow/Chatflow_split_sampleSpeak.png"  caption="Speak 노드 설정" %}

'2번 분기' 노드에도 메시지를 다음과 같이 설정합니다.

{% include image.html file="chatflow/Chatflow_split_sampleSpeak2.png"  caption="Speak 노드 설정" %}

'3번 분기' 노드에도 메시지를 다음과 같이 설정합니다.

{% include image.html file="chatflow/Chatflow_split_sampleSpeak3.png"  caption="Speak 노드 설정" %}

#### 테스트

'분기 테스트' 시나리오를 테스트해 보면 Split 노드에 부합하는 조건에 해당하는 Speak 노드가 호출되는 것을 확인할 수 있습니다. 

{% include image.html file="chatflow/Chatflow_split_sampleDemo.png"  caption="분기 테스트 결과" %}
 -->


{% include bottom.html %}
