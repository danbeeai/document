---
title: 대화 의도
tags: [intent, nlu, basic]
keywords: Basic Conversation
summary: 대화 의도를 통하여 입력 문장을 어떤 의도로 분류할 것인가를 설정할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: intent.html
folder: danbeeDoc
previous: {
    title: 시작 메세지,
    url: welcome.html
}
next: {
    title: 대화 흐름 기본 설명,
    url: chatflow.html
}
---

{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 대화 의도" type="default" %}
 
{% include image.html file="intent/chatbotflow.png"  caption="대화 의도와 엔티티의 관계" %}

**대화 의도**란, 입력 문장이 어떤 의도인지 분류하기 위한 기준입니다. 문장을 입력 받으면 봇은 지금까지 학습된 문장을 바탕으로 가장 적절한 대화의도를 찾고, 설정에 따라 복잡한 업무를 처리하도록 만들거나, 단순한 문장으로 대답을 할도록 만들수도 있습니다.<br/>

해당 메뉴에서는 다음과 같은 내용을 설정할 수 있습니다.<br/>
 - [사용자 입력 예문](intent.html#사용자-입력-예문)
 - [대화의도 속성](intent.html#intent-속성)

------------------------

## 대화의도 속성

대화의도에 따라 각 속성을 적절하게 설정하는 것이 중요합니다. 

- [대화의도 버튼이름](intent.html#intent-버튼명)
- [답변 유형](intent.html#답변-유형)
- [Multi 대화의도 제외 설정](intent.html#multi-intent-제외-설정)
- [채널 Fallback 설정](intent.html#채널-fallback-설정)
- [대화의도 ID](intent.html#intent-id)

------------------------------------------------------------

## 대화의도 예문

**대화의도 예문**은 대화 의도에 해당하는 문장들의 예시입니다. 단비.Ai 챗봇은 사용자가 입력한 문장을 3가지 추론단계를 거쳐 가장 적합한 의도를 찾아내도록 되어있습니다. 대화의도 예문은 **패턴매칭**과 **형태소 분석** 단계에 필요한 데이터로 **챗봇의 추론률에 가장 영향을 많이 주는 요소**입니다.

예를 들어 사용자가 '안녕'이라는 말을 했을 때 챗봇이 '인사'라는 이름의 대화의도로 알아듣길 원한다면 '인사' 대화의도를 생성하시고 '안녕'이라는 사용자 입력 예문을 추가하시면 됩니다. 더 다양한 상황에 유동적으로 대처하도록 만들고자 한다면, '안녕'외에도 다양하게 인사 상황에 쓰일만한 예문을 추가해주면 됩니다.


### 예문에서 정보 추출

사용자가 입력한 문장에서 특정 정보를 추출해야 할 때에는 등록한 예문에 [파라미터](parameter.html) 영역을 설정 하실 수 있습니다. 파라미터 영역을 지정하면 지정한 영역에 들어오는 정보를 변수로 사용할 수 있게 됩니다.

{% include image.html file="intent/Intent_sentence_parameter_00.PNG"  caption="대화의도에 맞는 예문 등록" %}

위와 같이 설정함으로써 챗봇은 **"치킨 먹고 싶어"**와 같거나 비슷한 문장을 이해하고 **야식 주문하기** 의도로 적절하게 이해할 수 있게 되었습니다. 예문에서 **치킨**부분을 드래그 하여 파라미터 영역으로 지정함으로써 **~~ 먹고 싶어**에서 **~~**에 해당하는 부분을 치킨외의 피자, 초밥, 카레등등 동적으로 추출할 수 있게 되었습니다. 이때 파라미터색은 랜덤하게 정해집니다.

정보가 정확히 어떻게 추출되는지 확인하고 싶다면 우측에 있는 [테스트 패널](demo_n_test_panel.html#테스트-패널)의 NLU TEST탭을 활용하여 자세히 알아볼 수 있습니다. [엔티티](entity.html) 설정에 따라 사용자가 입력한 정보와 대화의도에서 이해하는 값이 다를 수 있으니, 자세한 내용은 [엔티티 문서](entity.html)를 참조하시기 바랍니다.

{% include image.html file="intent/Intent_sentence_parameter_03.png" caption="예문은 하나지만 다른 단어를 동적으로 받는 모습을 확인 할 수 있습니다." %}

### 예문에 연결된 파라미터 관리
{% include image.html file="intent/Intent_parameter_03.png"  caption="대화의도에서 관리되고 있는 파라미터 목록" %}

해당 대화의도에 추가되어 있는 파라미터는 파라미터 목록에서 확인할 수 있습니다. 대화의도에서 지정된 파라미터는 해당 의도 안에서만 사용할 수 있습니다.

>##### 파라미터
파라미터명입니다. 예문에 연결된 파라미터의 이름이 바뀌면 모든 예문에서 해당 파라미터명이 일괄적으로 수정됩니다.
##### 엔티티
파라미터에 지정된 엔티티 타입입니다. 모든 파라미터는 엔티티 타입을 가지고 있어야 합니다. 엔티티값은 파라미터를 생성할 때 최초 지정한 후에는 변경이 불가능합니다. 파라미터를 효과적으로 이용하기 위해서는 [엔티티](entity.html)에 대한 이해가 필요합니다.
##### {파라미터}
파라미터 값을 불러와 사용할때의 형태입니다.
##### Default
파라미터에 따로 저장되는 값이 없을 때 기본값으로 지정되는 값입니다.
>{% include image.html file="intent/Intent_parameter_06_default_result.png"  caption="Parameter Default 값 테스트" %}
>##### 사용갯수
해당 파라미터가 사용되고 있는 예문 갯수입니다. 하나라도 사용되고 있는 곳이 있으면 삭제할 수 없습니다.




### 답변 방식 설정

대화 의도는 2가지 답변 유형 중 하나를 선택할 수 있습니다. 간편 답변으로 대답하게 되면 간단한 문장이나 버튼만 이용해 답변하게 되고, [대화 흐름](chatflow.html)에 연결하면 여러가지 복잡한 업무를 수행할 수 있게 됩니다.

>##### 간편답변
대화 흐름에 연결하지 않으면 작성된 **간편 답변** 목록에서 무작위로 선택해 답변합니다. **+ 간편 답변 추가** 버튼으로 여러개의 메세지를 추가할 수 있습니다. 간편답변에도 파라미터를 사용하여 사용자 말에 적절한 대답을 하도록 만들 수 있습니다.

>{% include image.html file="intent/intent_simple_answer_01.png"  caption="파라미터를 이용한 간편답변" %}

>간편 답변을 입력하지 않으면 아무런 답도 하지 않습니다. 테스트 패널에서는 실제 엔진이 동작했음을 보여주기 위하여 빈 말풍선을 내보내고 있지만 실제 작동시에는 아무런 말풍선도 출력되지 않습니다.
>{% include image.html file="intent/intent_simple_answer_02.png"  caption="값이 없는 간편 답변" %}

>##### 대화 흐름
대화 흐름으로 연결하면 해당 대화의도와 연결된 대화 흐름을 진행합니다. 미리 만들어둔 대화 흐름 중 하나를 연결할 수도 있고, **+ 대화 흐름 생성**버튼을 통해 바로 연결된 대화 흐름을 생성할 수도 있습니다. 대화 흐름에 관한 자세한 내용은 [대화 흐름 관리](chatflow.html) 문서를 참조하시기 바랍니다.

### 대화 의도 버튼이름

대화 의도를 버튼형식으로 보여줄때 사용되는 이름입니다. **일치하는 대화 의도가 있지만, 추론률이 낮아 확신을 가지지 못하는 경우**에 대화 의도 버튼을 보여주어 사용자가 알맞은 의도를 선택할 수 있도록 노출됩니다. 공백으로 둘 경우 대화 의도 이름이 버튼 이름으로 사용됩니다.
대화 의도 버튼이 노출되는 경우는 다음과 같습니다. 

- 입력 문장에 유효한 대화 의도를 찾았지만 추론률이 낮을 경우. 이를 **재확인**이라고 합니다. 재확인에 대한 자세한 설정은 [추론설정](settings_personality.html)에서 할 수 있습니다.

- 입력 문장에 대하여 2개 이상의 유효한 대화 의도를 찾았을 경우. 이를 **Multi Intent**라고 합니다.

{% include image.html file="intent/Intent_button_name_01.PNG"  caption="대화 의도 버튼명 결과확인" %}

### Multi Intent 제외 설정
체크하는 경우 여러 개의 의도와 함께 multi intent로 파악되더라도 제외 설정된 대화 의도는 버튼형식으로 노출되지 않습니다.

### Default Fallback으로 답변
체크하는 경우 해당 대화 의도로 파악되면 강제적으로 Default Fallback으로 넘어갑니다. 즉, 의도를 성공적으로 추론했음에도 불구하고 말을 알아듣지 못한 것처럼 반응하게 됩니다. Default Fallback시 챗봇의 응답은 [특수 상황 설정]()에서 지정할 수 있습니다.

{% include image.html file="intent/Intent_parameter_06_default_result.png"  caption="파라미터 Default 값 테스트" %}

----------------------------------

## 의도(Intent) 업로드

단비Ai는 편의 기능의 일종으로 대화 의도 업로드 기능을 제공하고 있습니다. 해당 기능은 CSV파일로 지원됩니다.

{% include warning.html content="CSV파일을 열 때에는 **메모장, UltraEdit** 등의 편집기 사용을 권장합니다. MS Excel 사용 시 한글이 깨질 수 있습니다." %}

### 업로드
{% include callout.html content="화면 위치 : 챗봇 만들기 > 챗봇 제작 > 대화 의도 > 대화 의도 생성 더보기 버튼" type="default" %}
업로드 형식에 맞추어 작성한 CSV파일을 업로드하면 자동으로 내용이 생성됩니다. 업로드 파일은 다음과 같은 제약사항이 존재합니다.

 - CSV파일만 가능합니다.
 - 파일당 최대 3MB까지 가능합니다.
 - 파일명은 최대 70자까지 허용합니다.

해당 메뉴에서 **Intent Upload Sample File 보기**를 클릭하시면 업로드 형식을 확인할 수 있으며 샘플 파일을 다운로드 받으실 수 있습니다.

#### 업로드 형식
입력하고자 하는 정보는 정의된 구분자에 의해 구분되며 반드시 START 태그와 END 태그를 한쌍으로 가집니다. 구분자의 START와 END 사이의 정보를 업로드 하게 되며 구분자에는 INTENT, NAME, SENTENCE, PARAM, ANSWER 이 존재합니다.

<table class="table-bordered table-striped">
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
            <td markdown="span">해당 업로드 정보가 대화 의도에 관한 정보임을 나타냅니다.</td>
        </tr>
        <tr>
            <td markdown="span">**NAME**</td>
            <td markdown="span">부분 필수</td>
            <td markdown="span">Intent명, 대화 의도 버튼명, 대화 의도 ID에 관한 정보임을 나타냅니다. Intent명은 필수값이나 나머지는 생략이 가능합니다. 챗봇 내에서 동일한 대화 의도 명이 존재할 경우 이름이 변경되어 올라갑니다.</td>
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

필수값에 해당하는 정보가 없거나 형식이 맞지 않으면 파일은 업로드에 실패하게 됩니다. 실제 업로드 파일은 아래와 같은 형식이 됩니다.

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

샘플 파일을 다운로드 받은 후 업로드 해서 결과를 확인해보세요.



{% include bottom.html %}
