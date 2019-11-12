---
title: 의도 관리 
tags: [intent, nlu, basic]
keywords: Basic Conversation
summary: Intent를 통하여 입력 문장을 어떤 의도로 분류할 것인가를 설정할 수 있습니다.
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

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도 추론(Intent)]" type="default" %}
 
{% include image.html file="intent/chatbotflow.png"  caption="대화 의도와 엔티티의 관계" %}
**대화 의도**란, 입력 문장이 어떤 의도인지 분류하기 위한 기준입니다. 문장을 입력 받으면 봇은 지금까지 학습된 문장을 바탕으로 가장 적절한 대화의도를 찾고, 설정에 따라 복잡한 업무를 수행할수도, 단순한 대답을 할수도 있습니다.<br/>

해당 메뉴에서는 다음과 같은 내용을 설정할 수 있습니다.<br/>
 - [사용자 입력 예문](intent.html#사용자-입력-예문)
 - [대화의도 속성](intent.html#intent-속성)


------------------------

## 대화의도 속성

해당 대화의도의 목적에 따라 대화의도의 속성을 적절히 설정하는 것이 중요합니다.

대화의도에 대하여 다음과 같은 속성을 지정할 수 있습니다.

- [대화의도 버튼이름](intent.html#intent-버튼명)
- [답변 유형](intent.html#답변-유형)
- [Multi 대화의도 제외 설정](intent.html#multi-intent-제외-설정)
- [채널 Fallback 설정](intent.html#채널-fallback-설정)
- [대화의도 ID](intent.html#intent-id)

### 대화의도 버튼이름

대화의도를 버튼형식으로 보여줄때 사용되는 이름입니다. 일치하는 대화의도가 있지만, 추론률이 낮아 확신을 가지지 못하는 경우에 대화의도 버튼을 보여주어 사용자가 알맞은 의도를 선택할 수 있도록 노출됩니다. 대화의도 버튼이 노출되는 경우는 다음과 같습니다. 공백으로 둘 경우 대화의도 이름이 버튼 이름으로 사용됩니다.

 - [Reconfirm](settings_personality.html#reconfirm) : 입력 문장에 유효한 대화의도를 찾았지만 추론률이 낮을 경우
 - [Multi Intent](settings_personality.html#multi-intent) : 입력 문장에 대하여 2개 이상의 유효한 대화의도를 찾았을 경우


{% include image.html file="intent/Intent_button_name_01.PNG"  caption="대화의도 버튼명 결과확인" %}

### 대화의도 ID
필요에 따라 임의로 대화 의도 ID를 지정할 수 있습니다. 단, 대화의도 ID는 한 챗봇 내에서 유일해야 하며 공백으로 둘 경우 자동적으로 시스템 ID가 적용됩니다.

### 대화 흐름으로 연결

한가지 대화 의도에 대하여 어떻게 답변할지 2가지 유형을 선택할 수 있습니다. 대화 흐름에 연결하지 않으면 대화 의도에서 설정하는 간편답변을 통해 답변하게 되고, [대화 흐름](chatflow.html)에 연결하면 대화 흐름을 따라 여러 복잡한 업무를 수행합니다.

#### 간편답변

<div class="indented">대화 흐름에 연결하지 않으면 작성된 <strong>간편 답변</strong>목록에서 무작위로 선택해 답변합니다. <strong>+간편 답변 추가</strong> 버튼으로 여러개의 메세지를 추가할 수 있습니다.</div>
{% include image.html file="intent/intent_simple_answer_01.png"  caption="여러개의 간편 답변" %}

<div class="indented">간편 답변을 입력하지 않으면 아무런 답도 하지 않습니다. 테스트 패널에서는 실제 엔진이 동작했음을 보여주기 위하여 빈 말풍선을 내보내고 있지만 실제 작동시에는 아무런 말풍선도 출력되지 않습니다.</div>
{% include image.html file="intent/intent_simple_answer_02.png"  caption="값이 없는 간편 답변" %}

#### 대화 흐름
<div class="indented">대화 흐름으로 연결하면 해당 대화의도와 연결된 대화흐름을 진행합니다. 미리 만들어둔 대화흐름 중 하나를 연결할 수도 있고, <strong>+대화흐름 생성</strong>버튼을 통해 바로 연결된 대화 흐름을 생성할 수도 있습니다. 대화흐름에 관한 자세한 내용은 <a href="chatflow.html">대화흐름 관리</a> 문서를 참조하시기 바랍니다.</div>

### 상세 설정

상세 설정은 대화 의도 모듈 오른쪽 상단에 "상세 설정" 버튼을 통해 설정하실 수 있습니다.

#### Multi 대화의도 제외 설정
<div class="indented">체크하는 경우 여러 개의 의도와 함께 multi intent로 파악되더라도 해당 대화의도는 버튼형식으로 노출되지 않습니다.</div>

#### 채널 Fallback 설정
<div class="indented">체크하는 경우 해당 대화의도로 파악되면 강제적으로 Default Fallback으로 넘어갑니다. 즉, 봇이 말을 알아듣지 못한 것처럼 반응하게 됩니다. <a href="settings_personality.html">Default Fallback</a> 시 챗봇의 반응은 성격 화면에서 지정할 수 있습니다.</div>

------------------------------------------------------------

## 사용자 입력 예문

**사용자 입력 예문**은 대화 의도해당하는 문장들의 예시입니다. danbee.Ai는 여러 대화의도들 중에 사용자가 입력한 문장과 가장 비슷한 예문을 가지고 있는 대화의도로 분류하여 대화를 진행합니다. 예를 들어 사용자가 '안녕'이라는 말을 했을 때 챗봇이 '인사'라는 이름의 대화의도로 알아듣길 원한다면 '인사' 대화의도를 생성하시고 '안녕'이라는 사용자 입력 예문을 추가하시면 됩니다.<br/>

{% include image.html file="intent/Intent_input_sentence.PNG"  caption="사용자 입력 예문 등록" %}

사용자 예문 입력란에 추가하길 원하는 예문을 입력한 뒤 Enter나 예문등록 버튼을 누르면 예문이 추가됩니다. 추가된 예문은 전체 등록 예문에서 확인이 가능하며 예문 목록 타이틀 옆에는 등록된 총 예문 개수가 표시됩니다. danbee.Ai 플렛폼에서는 클라우드 학습을 통해 입력하지 않은 문장에 대해서도 감지가 가능하지만, 예문등록을 통해 더욱 확실한 추론률을 확보할 수 있습니다. 쉽고 빠르게 다양화 할 수 있도록 예문 추천 기능을 제공하고 있습니다.

<!-- {% include tip.html content="챗봇은 등록된 예문외에도 클라우드 학습을 통해 다양한 문장을 감지할 수 있지만, 많은 예문을 추가하면 더욱 높은 추론률을 가질 수 있습니다. danbee.Ai는 예문을 쉽고 빠르게 다양화 할 수 있도록 예문추천 기능을 제공하고 있습니다." %} -->

### 예문에서 정보 추출

<!-- {% include note.html content="본 내용은 [엔티티 관리](entity.html) 페이지를 확인하신 후 다시 본다면 이해도를 높일 수 있습니다." %} -->

사용자가 입력한 문장에서 특정 정보를 추출해야 할 때에는 등록한 예문에 [파라미터](parameter.html) 영역을 설정 하실 수 있습니다. 즉,지정한 영역에 해당하는 정보를 변수로서 사용할 수 있게 됩니다. 예문에 파라미터 영역을 설정하기 위해서는 반드시 **인텐트가 대화흐름에 연결되어있어야 합니다.**

{% include image.html file="intent/parameter_from_sentence.gif"  caption="대화의도에 맞는 예문 등록" %}

위와 같이 설정함으로써 챗봇은 **"치킨 먹고 싶어"**와 같거나 비슷한 문장을 이해하고 **야식 주문하기** 의도로 적절하게 이해할 수 있게 되었습니다. 더불어 **치킨**을 드래그 하여 파라미터 영역으로 지정함으로써 **~~ 먹고 싶어**에서 **~~**에 해당하는 부분을 정보값으로 동적으로 추출할 수 있게 되었습니다.

정보가 정확히 어떻게 추출되는지 확인하고 싶다면 우측에 있는 <span class="link">[테스트 패널](demo_n_test_panel.html#테스트-패널)</span>을 활용할 수 있습니다. [엔티티](entity.html) 설정에 따라 사용자가 입력한 정보와 대화의도에서 이해하는 값이 다를 수 있으니, 자세한 내용은 [엔티티 문서](entity.html)를 참조하시기 바랍니다.

{% include image.html file="intent/Intent_sentence_parameter_03.png"  caption="문장에서 추출되는 정보 확인" %}

### 예문에 연결된 파라미터 관리

{% include image.html file="intent/Intent_parameter_03.png"  caption="대화의도에서 관리되고 있는 파라미터 목록" %}

해당 대화의도에 추가되어 있는 전체 파라미터는 '추출되는 파라미터'에서 확인할 수 있습니다. 이때 사용개수는 해당 파라미터가 예문에서 지정되어 사용 중인 개수를 의미합니다. 예문에서 한 군데라도 사용중이라면 삭제가 불가능합니다.

#### 파라미터 수정
예문에 연결한 파라미터에 대하여 일부 정보를 수정을 할 수 있습니다.

 - **파라미터명**은 언제든지 수정할 수 있습니다. 예문에 연결된 파라미터의 이름이 바뀌면 지금까지 해당 이름으로 연결된 모든 영역이 함께 수정됩니다.
 - 생성된 파라미터의 **엔티티**는 한 번 지정한 후에는 변경이 불가합니다. Entity를 변경하기 위해서는 삭제 후 새롭게 추가를 하셔야 합니다.
 - **디폴트**값을 설정하면 파라미터에 해당하는 값이 없을 때 디폴트 값으로 대신 대화 흐름을 진행 할 수 있습니다.

{% include image.html file="intent/Intent_parameter_06_default_result.png"  caption="파라미터 Default 값 테스트" %}

----------------------------------

## 의도(Intent) 업로드

danbee.Ai는 편의 기능의 일종으로 대화의도 업로드 기능을 제공하고 있습니다. 해당 기능은 CSV파일로 지원됩니다.

{% include warning.html content="CSV파일을 열 때에는 **메모장, UltraEdit** 등의 편집기 사용을 권장합니다. MS Excel 사용 시 한글이 깨질 수 있습니다." %}

### 업로드
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도 추론(Intent)] > [더보기] > [대화의도 업로드]" type="default" %}
업로드 형식에 맞추어 작성한 CSV파일을 올려주시면 자동으로 엔티티가 생성됩니다. 업로드 파일은 다음과 같은 제약사항이 존재합니다.
 - CSV파일만 가능합니다.
 - 파일당 최대 3MB까지 가능합니다.
 - 파일명은 최대 70자까지 허용합니다.

해당 메뉴에서 <span style="color:#337ab7">**대화의도 Upload Sample File 보기**</span>를 클릭하시면 업로드 형식을 확인할 수 있으며 샘플 파일을 다운로드 받으실 수 있습니다.

#### 업로드 형식
입력하고자 하는 정보는 정의된 구분자에 의해 구분되며 반드시 START 태그와 END 태그를 한쌍으로 가집니다. 구분자의 START와 END 사이의 정보를 업로드 하게 되며 구분자에는 INTENT, NAME, SENTENCE, PARAM, ANSWER 이 존재합니다.

<table>
    <colgroup>
        <col width="15%" />
        <col width="15%" />
        <col width="70%">
    </colgroup>
    <thead>
        <tr class="header">
            <th>구분자</th>
            <th>필수여부</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td markdown="span">**INTENT**</td>
            <td markdown="span">필수</td>
            <td markdown="span">해당 업로드 정보가 대화의도에 관한 정보임을 나타냅니다.</td>
        </tr>
        <tr>
            <td markdown="span">**NAME**</td>
            <td markdown="span">부분 필수</td>
            <td markdown="span">Intent명, 대화의도 버튼명, 대화의도 ID에 관한 정보임을 나타냅니다. Intent명은 필수값이나 나머지는 생략이 가능합니다. 챗봇 내에서 동일한 대화의도 명이 존재할 경우 이름이 변경되어 올라갑니다.</td>
        </tr>
        <tr>
            <td markdown="span">**SENTENCE** </td>
            <td markdown="span">필수</td>
            <td markdown="span">예문에 관한 정보임을 나타냅니다. 한 줄당 하나의 예문으로 인식하며 반드시 하나 이상의 예문을 요구합니다.</td>
        </tr>
        <tr>
            <td markdown="span">**PARAM**</td>
            <td markdown="span">선택</td>
            <td markdown="span">파라미터에 관한 정보임을 나타냅니다. 파라미터명과 Entity를 입력합니다. 존재하지 않는 Entity를 입력하면 업로드가 되지 않습니다. Entity명 앞에는 반드시 @를 붙여줘야 합니다. 파라미터명이 중복될 시에도 업로드가 불가합니다.</td>
        </tr>
        <tr>
            <td markdown="span">**ANSWER**</td>
            <td markdown="span">선택</td>
            <td markdown="span">간편답변 리스트를 나타냅니다. 한 줄당 하나의 답변으로 인식합니다.</td>
        </tr>
    </tbody>
</table>

필수값에 해당하는 정보가 없거나 형식이 맞지 않으면 파일은 업로드에 실패하게 됩니다. 실제 업로드 파일은 다음과 같은 형식으로 쓰게 됩니다.

```
{%raw%}
>START_INTENT
>>START_NAME
Intent명,Intent별명(생략가능),IntentID(생략가능)
>>END_NAME
>>START_SENTENCE
예문입력줄
"예문에 콤마(,) 입력시 반드시 큰따옴표로 묶어주세요"
>>END_SENTENCE
>>START_PARAM
파라미터명,@Entity명
>>END_PARAM
>>START_ANSWER
간편답변입력줄
"예문과 동일하게 콤마(,) 입력시 반드시 큰따옴표로 묶어주세요"
>>END_ANSWER
>END_INTENT
{%endraw%}
```

{% include warning.html content="정보 구분을 위한 콤마(,)간 띄워쓰기는 불가합니다." %}

샘플 파일을 다운로드 받으셔서 해당 파일을 업로드 해서 결과를 확인해보세요.

