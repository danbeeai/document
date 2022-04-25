---
title: 공통 변수
tags: [settings, nlu, chatflow, advanced]
keywords: General Conversation
summary: 챗봇에서 자주사용하는 값을 관리할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: settings_manage_variables.html
folder: danbeeDoc
previous: {
    title: 간편대화,
    url: nlu_faq.html
}
next: {
    title: 대화 의도 테스트,
    url: intent_test_batch.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 공통 변수" type="default" %}

{% include image.html file="manage_variables/1.PNG"  caption="기본 공통변수" %}

**공통변수**란, 챗봇에서 자주 사용되거나, 공통적으로 사용될 수 있는 정보를 말합니다.
공통변수는 대화 의도 간편답변 작성시,혹은 대화 흐름의 'SpeakNode','SlotNode','CarouselNode'등 노드설정화면에서 사용될 수 있으며, API 호출 값으로도 사용될 수 있습니다.
또한, 하나의 챗봇모델을 만들어놓고 회사명,챗봇명,오시는 길 등을 공통변수로 설정한 뒤 챗봇을 복사하면, 공통변수부분만 수정하면 유사한 챗봇을 쉽고 빠르게 만들 수 있습니다.
이 외에도 여러 상황에서 공통변수를 사용하면 더욱 효율적으로 챗봇을 만들 수 있습니다.

- [기본 공통변수](settings_manage_variables.html#기본-공통변수)
- [사용자정의 공통변수](settings_manage_variables.html#사용자정의-공통변수)
- [공통변수 검색](settings_manage_variables.html#공통변수-검색)
- [공통변수 사용](settings_manage_variables.html#공통변수-사용)


### 기본 공통변수
기본 공통변수는 '챗봇명'과 같은 챗봇의 기본적인 정보를 담고 있는 공통변수입니다. 기본적인 정보를 담고 있는 공통변수는 수정하거나 삭제할 수 없습니다.

### 사용자정의 공통변수
사용자 정의 공통변수는 챗봇의 정보를 담고있는 '기본 공통변수'와는 다르게, 사용자가 원하는 어떠한 정보도 담아 낼 수 있는 변수입니다.
'+ 변수추가' 버튼을 클릭하면, 공통변수를 추가할 수 있는 입력폼이 나타납니다.

>##### 변수명
필수 입력항목으로, 변수명을 입력하지않으면 공통변수가 추가되지 않습니다. 변수명 항목은 한글로도 입력할 수 있습니다. 이 변수를 사용할때는 **#{@변수명}** 형태로 사용할 수 있습니다.
>##### 내용
해당 변수에 실제로 담길 값입니다.
>##### 설명(선택사항)
해당 변수에 대한 자세한 설명입니다. 작성하지 않아도 변수를 생성할 수 있습니다.

공통변수의 수정시 '변수명'항목은 수정이 불가능하며, '내용', '설명'항목의 수정만 가능합니다.
'변수명'항목을 수정하고 싶다면 공통변수를 삭제 후 다시 설정해주셔야 합니다.

### 공통변수 검색
검색기능을 통해서 내가 찾고자 하는 공통변수를 빠르게 찾을 수 있습니다.

### 공통변수 사용
챗봇에 공통변수를 설정해놓으면 대화 흐름의 'Speak Node', 'Slot Node', 'Carousel Node'설정시 메세지나,버튼명,버튼값,이미지 등 여러 상황에서
'#{@공통변수명}'과 같은 표현식을 이용하여 공통변수를 호출할 수 있고 값을 설정할 수 있습니다.

또한, 공통변수는 대화 의도 간편답변 작성시에도, 'Function Node'의 변수로도 활용할 수 있습니다.

{% include image.html file="manage_variables/manage_variables_8.png" %}
{% include image.html file="manage_variables/manage_variables_7.png" %}



{% include bottom.html %}
