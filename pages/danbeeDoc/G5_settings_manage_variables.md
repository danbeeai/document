---
title: 공통 변수 관리
tags: [settings, nlu, chatflow, advanced]
keywords: General Conversation
summary: 챗봇에서 자주사용하는 값을 관리할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: settings_manage_variables.html
folder: danbeeDoc
previous: {
    title: NLU 설정,
    url: settings_nlu.html
}
next: {
    title: 대화 이력 관리,
    url: log.html
}
---

## 공통 변수 관리 (Manage Variable)
 {% include callout.html content="화면 위치 : [설정(Preference)] > [공통 변수 관리]" type="default" %}
**공통변수**란, 챗봇에서 자주 사용되거나, 공통적으로 사용될 수 있는 변수를 말합니다.<br/>
공통변수는 인텐트 간편답변 작성시,혹은 챗플로우의 'SpeakNode','SlotNode','CarouselNode'등 노드설정화면에서 사용될 수 있으며, API 호출 값으로도 사용될 수 있습니다. <br/><br/>
또한, 하나의 챗봇모델을 만들어놓고 회사명,챗봇명,오시는 길 등을 공통변수로 설정한 뒤 챗봇을 복사하면, 공통변수부분만 수정하면 유사한 챗봇을 쉽고 빠르게 만들 수 있습니다. <br/>
이 외에도 여러 상황에서 공통변수를 사용하면 더욱 효율적으로 챗봇을 만들 수 있습니다.

- [기본 공통변수](settings_manage_variables.html#기본-공통변수)
- [사용자정의 공통변수](settings_manage_variables.html#사용자정의-공통변수)
- [공통변수 검색](settings_manage_variables.html#공통변수-검색)
- [공통변수 사용](settings_manage_variables.html#공통변수-사용)

### 기본 공통변수
기본 공통변수는 '챗봇명'과 같은 챗봇의 기본적인 정보를 담고 있는 공통변수입니다. <br/>
기본 공통변수는 공통변수관리페이지에서는 사용자가 임의로 수정 할 수 없습니다.  
<br/>
{% include image.html file="manage_variables/manage_variables_1.png"  caption="기본 공통변수" %}
<br/>

### 사용자정의 공통변수
사용자 정의 공통변수는 챗봇의 정보를 담고있는 '기본 공통변수'와는 다르게, 사용자가 원하는 어떠한 정보도 담아 낼 수 있는 변수입니다. <br/>
'+변수추가' 버튼을 클릭하면, 공통변수를 추가할 수 있는 입력폼이 나타납니다.
<br/>
{% include image.html file="manage_variables/manage_variables_2.png"  caption="사용자정의 공통변수 - 변수 추가" %}
<br/>

'변수명'항목은 필수 입력항목으로, 변수명을 입력하지않으면 공통변수가 추가되지 않습니다.<br/>
'변수명'항목은 한글입력도 가능합니다.<br/>

<br/>
{% include image.html file="manage_variables/manage_variables_3.png"  caption="사용자정의 공통변수 - 목록" %}
<br/>
공통변수가 저장되면, 공통변수 목록에 추가된 공통변수가 나타납니다. <br/> 
추가된 공통변수들은, Chatflow의 SpeakNode 등에서 '#{@변수명}'으로 값을 불러올 수 있습니다.

<br/>
{% include image.html file="manage_variables/manage_variables_4.png"  caption="사용자정의 공통변수 - 수정" %}
<br/>
공통변수의 수정시 '변수명'항목은 수정이 불가능하며, '내용','설명'항목의 수정만 가능합니다.<br/>
'변수명'항목을 수정하고 싶다면 공통변수를 삭제 후 다시 설정해주셔야 합니다.


<br/>

### 공통변수 검색
챗봇에 설정한 공통변수의 개수가 많아지면 수정,삭제 작업시 공통변수를 찾기 불편합니다.<br/>
검색기능을 통해서 내가 찾고자 하는 공통변수를 빠르게 찾을 수 있습니다.<br/>
<br/>
{% include image.html file="manage_variables/manage_variables_5.png"  caption="공통변수검색 - '전체'로 검색" %}
<br/>
'전체'옵션 선택 후 검색키워드를 입력하면 모든 항목에서 키워드와 일치하는 공통변수들을 찾습니다.<br/>
<br/>
{% include image.html file="manage_variables/manage_variables_6.png"  caption="공통변수검색 - '변수내용'으로 검색" %}
<br/>
'변수내용'옵션 선택 후 검색키워드를 입력하면 '변수내용'항목에서 키워드와 일치하는 공통변수들을 찾습니다.

<br/>

### 공통변수 사용
<!-- 챗봇에 등록한 공통변수를 사용하는 간단한 예제 화면입니다. <br/> -->
챗봇에 공통변수를 설정해놓으면 챗플로우의 'SpeakkNode','SlotNode','CarouselNode'설정시 메세지나,버튼명,버튼값,이미지 등 여러 상황에서
'#{@공통변수명}'과 같은 표현식을 이용하여 공통변수를 호출할 수 있고 값을 설정할 수 있습니다.<br/><br/>

또한, 공통변수는 인텐트 간편답변 작성시에도, 'FunctionNode'의 변수로도 활용되어집니다.<br/><br/>

{% include image.html file="manage_variables/manage_variables_8.png"  caption="공통변수사용 - SpeakNode 메세지 설정" %}

{% include image.html file="manage_variables/manage_variables_7.png"  caption="공통변수사용 - 결과" %}
<br/>
<br/>

