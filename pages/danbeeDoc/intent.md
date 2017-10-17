---
title: 의도 관리
tags: [intent, parameter]
keywords: Basic Conversation
summary: 사용자의 말을 어떤 의미로 파악할 것인가에 대하여 관리하고 설정하는 페이지입니다.
sidebar: danbee_doc_sidebar
permalink: intent.html
folder: danbeeDoc
previous: {
    title: 챗봇 생성하기, 
    url: basic_create_chatbot.html
}
next: {
    title: 엔티티 관리,
    url: entity.html
}
---

## 의도(Intent) 관리
 {% include callout.html content="위치 : [자연어이해(NLU)] - [의도 추론(Intent)]" type="default" %}
**의도(Intent)**란, 사용자가 한 말에 대해 봇이 어떻게 대답할 지에 대한 **관계**를 설정한 것입니다.<br/>

해당 메뉴에서는 다음과 같은 내용을 설정할 수 있습니다.<br/> 
 - [사용자 예문](intent.html#사용자-예문)
 - [파라미터(Parameter)](intent.html#파라미터parameter)
 - [Intent 속성](intent.html#intent-속성)

### 사용자 예문




### 파라미터(Parameter)


### Intent 속성

특정 Intent에 대하여 다음과 같은 속성을 지정할 수 있습니다.

#### Intent 버튼명

사용자가 말을 입력하면 봇은 적절한 Intent를 찾게 됩니다. 하지만 다음과 같이 찾은 Intent에 대하여 확신을 가지지 못하는 경우가 발생합니다.<br/><br/>

 - Reconfirm : 사용자가 한 말에 대하여 Intent를 찾았지만 해당 Intent일 확률이 낮을 경우
 <span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [Reconfirm 자세히 보기](personality_settings)</span> 
 - Multi Intent : 사용자가 한 말에 대하여 여러개의 Intent를 찾을 경우
<span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [Multi Intent 자세히 보기](personality_settings)</span>
 


<br/>
위에 해당되는 경우 봇은 사용자의 의도를 정확하게 파악하기 위하여 버튼 형식으로 되물어보게 됩니다.<br/>
이때 버튼명은 Intent 버튼명에 설정한 값으로 보여집니다. 만약 벼튼명을 입력하지 않았을 때 기본값은 Intent 명이 됩니다.<br/>

```yaml
설정값에 따라 바뀌는 버튼명 이미지 추가 영역(reconfirm / multi)
```


#### Multi Intent 제외 설정
본 속성을 체크하는 경우 해당 Intent는 확률이 낮거나 여러 의도로 파악되더라도 버튼으로 되물어보지 않게 됩니다.
```yaml
image 추가
```

#### 채널 Fallback 설정
본 속성을 체크하는 경우 해당 Intent로 파악되면 강제적으로 Default Fallback으로 넘어갑니다. 즉, 봇이 말을 알아듣지 못한 것처럼 반응하게 됩니다. Default Fallback 시 챗봇의 반응은 개발자가 지정할 수 있습니다.<span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [Default Fallback 자세히 보기](personality_settings)</span>

```yaml
image 추가
```

#### Intent ID
챗봇 개발자는 필요에 따라 임의로 Intent ID를 지정할 수 있습니다. 단, Intent ID는 한 챗봇 내에서 유일해야 하며 공백으로 둘 경우 자동적으로 System ID가 적용됩니다.

## 의도(Intent) 업로드/다운로드

DANBEE.AI는 챗봇 개발자의 편의를 위하여 Intent 업로드/다운로드 기능을 제공하고 있습니다. 해당 기능은 CSV파일로 지원됩니다.

{% include important.html content=" CSV파일을 열 때에는 **메모장, UltraEdit** 등의 편집기 사용을 권장합니다. MS Excel 사용 시 한글이 깨질 수 있습니다." %}

### 업로드
{% include callout.html content="위치 : [자연어이해(NLU)] - [의도 추론(Intent)] - [더보기] - [Intent업로드]" type="default" %}
업로드 형식에 맞추어 작성한 CSV파일을 올려주시면 자동으로 Intent가 생성됩니다. 업로드 파일은 다음과 같은 제약사항이 존재합니다.
 - CSV파일만 가능합니다.
 - 파일당 최대 3MB까지 가능합니다.
 - 파일명은 최대 70자까지 허용합니다.

해당 메뉴에서 <span style="color:#337ab7">**Intent Upload Sample File 보기**</span>를 클릭하시면 업로드 형식을 확인할 수 있으며 샘플 파일을 다운로드 받으실 수 있습니다.

#### 업로드 형식
```
{%raw%}
이미지와 함께 자세한 설명 필요
{%endraw%}
```

### 다운로드
#### 단건 다운로드
{% include callout.html content="위치 : [자연어이해(NLU)] - [의도 추론(Intent)] - 특정 인텐트 선택 - [더보기] - [Intent다운]" type="default" %}
#### 다건 다운로드
{% include callout.html content="위치 : [자연어이해(NLU)] - [의도 추론(Intent)] - [더보기] - [Intent다운]" type="default" %}



