---
title: 의도 관리
tags: [intent, parameter]
keywords: Basic Conversation
summary: 사용자의 말을 어떤 의미로 파악할 것인가에 대하여 관리하고 설정하는 방법을 알 수 있습니다.
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
 {% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도 추론(Intent)]" type="default" %}
**의도(이하 Intent)**란, 사용자가 한 말에 대해 봇이 어떻게 대답할 지에 대한 **관계**를 설정한 것입니다.<br/>

해당 메뉴에서는 다음과 같은 내용을 설정할 수 있습니다.<br/> 
 - [사용자 입력 예문](intent.html#사용자-입력-예문)
 - [파라미터(Parameter)](intent.html#파라미터parameter)
 - [Intent 속성](intent.html#intent-속성)

### 사용자 입력 예문

**사용자 입력 예문**은 사용자가 입력한 말 중 해당 Intent로 구분되길 원하는 말을 의미합니다. DANBEE.AI는 사용자의 말과 동일하거나 가장 비슷한 예문을 가지고 있는 Intent를 찾게 됩니다. 예를 들어 사용자가 '안녕'이라는 말을 했을 때 봇이 '인사'로 알아듣길 원한다면 '인사' Intent에 '안녕'이라는 사용자 입력 예문을 추가하시면 됩니다.<br/>

{% include image.html file="intent/Intent_input_sentence.PNG" max-width="900" caption="사용자 입력 예문 추가" %} 

*사용자예문입력*란에 추가하길 원하는 예문을 입력한 뒤 *Enter*를 누르면 예문이 추가됩니다. 추가된 예문은 *전체 등록 예문*에서 확인이 가능하며 등록된 총 예문 개수가 표시됩니다. <br/>

#### 예문에서 정보 추출하기

{% include note.html content="본 내용은 [엔티티 관리](entity.html) 페이지를 확인하신 후 다시 본다면 이해도를 높일 수 있습니다." %}

입력된 말에서 특정 정보를 얻고자 할 때에는 등록한 예문에 [Parameter](intent.html#파라미터parameter)를 추가할 수 있습니다. 즉, 지정한 부분에 적힌 말을 변수에 담아서 사용할 수 있게 됩니다. 예를 들어 사용자가 '치킨 먹고 싶어'라는 말을 했을 때 ***'치킨'***이라는 부분에 다양한 음식 종류를 받고 활용하고 싶은 경우 해당 기능을 활용할 수 있습니다.<br/>

지금부터 어떻게 예문에서 정보를 추출할 수 있는지 알아보겠습니다.

{% include image.html file="intent/Intent_sentence_parameter_01.png" max-width="900" caption="예문에 Parameter 추가 01" %}

먼저, 입력한 예문에서 추출하고 싶은 영역을 *드래그* 하면 위 그림과 같이 Entity를 선택할 수 있는 창이 뜹니다. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[Entity](entity.html)</span>에 관한 자세한 내용은 다음 페이지에서 계속됩니다.

{% include image.html file="intent/Intent_sentence_parameter_02.png" max-width="900" caption="예문에 Parameter 추가 02" %}

특정 Entity를 선택하면 창은 닫히고 예문 아래 Parameter가 추가됩니다. Intent를 저장하면 Parameter를 지정한 영역의 색이 바뀌는 것을 확인할 수 있습니다.<br/>

이렇게 예문을 등록했을때 어떻게 정보가 추출되는지 확인하고 싶다면 우측에 있는 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[테스트 패널](demo_n_test_panel.html#테스트-패널)</span>을 활용할 수 있습니다. NLU Intent 테스트 패널에 등록한 예문과 동일한 패턴의 문장을 입력합니다.

{% include image.html file="intent/Intent_sentence_parameter_03.png" max-width="900" caption="문장에서 추출되는 정보 확인" %}

위의 테스트를 통해 '피자 먹고 싶어'라는 문장의 ***'피자'***가 지정한 Parameter인 '야식종류Entity' Parameter에 value로 담긴 것을 확인할 수 있습니다. 또한 '햄버거 먹고 싶어'라는 문장의 ***'햄버거'*** 역시 해당 Parameter의 value로 추출됩니다. 그러나 마지막 테스트인 '뭐라도 먹고 싶어'라는 문장에서 ***'뭐라도'***는 value로 뽑아내지 않고 있습니다. 이는 Parameter를 지정할 때 선택하였던 Entity인 '야식종류Entity'에 '뭐라도'라는 문구가 들어있지 않기 때문입니다. 만약 '먹고 싶어' 앞에 모든 문구를 추출하고 싶다면 Entity를 선택할 때 **sys.any** 라는 Entity를 선택하면 됩니다.


### 파라미터(Parameter)

**파라미터(이하, Parameter)**란 사용자와의 대화에서 뽑아내는 정보를 담아내는 껍데기입니다. 일종의 변수와도 같은 개념으로 대화흐름 속에서 특정 값을 전달하기위해 사용됩니다. Parameter 등록 방법으로는 크게 2가지가 있습니다.

- [예문에 직접 지정](intent.html#예문에서-정보-추출하기)
- Intent에 종류 추가

첫 번째 경우는 앞서 사용자 입력 예문에서 설명한 것과 같습니다.<br/> 
두 번째 경우는 대화 흐름 속에서 사용될 예정인 Parameter를 Intent 페이지 최하단에서 추가하는 방법입니다.

#### Parameter 추가

{% include image.html file="intent/Intent_parameter_01.png" max-width="900" caption="추출되는 Parameter" %}
추가 버튼 누름

{% include image.html file="intent/Intent_parameter_02.png" max-width="900" caption="Parameter 추가 팝업" %}
popup 설명 + 제약사항 summary

{% include image.html file="intent/Intent_parameter_03.png" max-width="900" caption="추가된 Parameter" %}
추가 완료

{% include image.html file="intent/Intent_parameter_04.png" max-width="900" caption="Parameter 이름 변경" %}
이름 변경 + 예문에 등록된 파라미터일 경우 자동으로 이름이 변경됨

참고로 위에서 변경하면 새로운 파라미터로 추가됨


자세한 활용법은 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[대화 흐름 설명 페이지](chatflow.html)</span>에서 확인하실 수 있습니다. 



### Intent 속성

특정 Intent에 대하여 다음과 같은 속성을 지정할 수 있습니다.
- [Intent 버튼명](intent.html#intent-버튼명)
- [Multi Intent 제외 설정](intent.html#multi-intent-제외-설정)
- [채널 Fallback 설정](intent.html#채널-fallback-설정)
- [Intent ID](intent.html#intent-id)

#### Intent 버튼명

사용자가 말을 입력하면 봇은 적절한 Intent를 찾게 됩니다. 하지만 다음과 같이 찾은 Intent에 대하여 확신을 가지지 못하는 경우가 발생합니다.<br/><br/>

 - Reconfirm : 사용자가 한 말에 대하여 Intent를 찾았지만 해당 Intent일 확률이 낮을 경우
 <span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [Reconfirm 자세히 보기](personality_settings)</span> 
 - Multi Intent : 사용자가 한 말에 대하여 여러개의 Intent를 찾을 경우
<span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [Multi Intent 자세히 보기](personality_settings)</span>
 


<br/>
위에 해당되는 경우 봇은 사용자의 의도를 정확하게 파악하기 위하여 버튼 형식으로 되물어보게 됩니다.
이때 버튼명은 Intent 버튼명에 설정한 값으로 보여집니다. 만약 벼튼명을 입력하지 않았을 때 기본값은 Intent 명이 됩니다.<br/>

{% include image.html file="intent/Intent_button_name_01.PNG" max-width="900" caption="Intent 버튼명 결과확인" %} 


#### Multi Intent 제외 설정
본 속성을 체크하는 경우 해당 Intent는 확률이 낮거나 여러 의도로 파악되더라도 버튼으로 되물어보지 않게 됩니다.
{% include image.html file="intent/intent_multi01.PNG" max-width="900" caption="Multi Intent 제외 설정 전" %}
{% include image.html file="intent/intent_multi02.PNG" max-width="900" caption="Multi Intent 제외 설정 후" %} 

#### 채널 Fallback 설정
본 속성을 체크하는 경우 해당 Intent로 파악되면 강제적으로 Default Fallback으로 넘어갑니다. 즉, 봇이 말을 알아듣지 못한 것처럼 반응하게 됩니다. Default Fallback 시 챗봇의 반응은 개발자가 지정할 수 있습니다.<span style="color:#f69023; font-size:13px"><i class="fa fa-external-link-square" aria-hidden="true" style="margin-left:5px"></i> [Default Fallback 자세히 보기](personality_settings)</span>

{% include image.html file="intent/intent_default_01.png" max-width="900" caption="채널 Fallback 설정 전" %}
{% include image.html file="intent/intent_default_02.png" max-width="900" caption="채널 Fallback 설정 후" %} 

#### Intent ID
챗봇 개발자는 필요에 따라 임의로 Intent ID를 지정할 수 있습니다. 단, Intent ID는 한 챗봇 내에서 유일해야 하며 공백으로 둘 경우 자동적으로 System ID가 적용됩니다.

## 의도(Intent) 업로드/다운로드

DANBEE.AI는 챗봇 개발자의 편의를 위하여 Intent 업로드/다운로드 기능을 제공하고 있습니다. 해당 기능은 CSV파일로 지원됩니다.

{% include warning.html content="CSV파일을 열 때에는 **메모장, UltraEdit** 등의 편집기 사용을 권장합니다. MS Excel 사용 시 한글이 깨질 수 있습니다." %}

### 업로드
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도 추론(Intent)] > [더보기] > [Intent업로드]" type="default" %}
업로드 형식에 맞추어 작성한 CSV파일을 올려주시면 자동으로 Intent가 생성됩니다. 업로드 파일은 다음과 같은 제약사항이 존재합니다.
 - CSV파일만 가능합니다.
 - 파일당 최대 3MB까지 가능합니다.
 - 파일명은 최대 70자까지 허용합니다.

해당 메뉴에서 <span style="color:#337ab7">**Intent Upload Sample File 보기**</span>를 클릭하시면 업로드 형식을 확인할 수 있으며 샘플 파일을 다운로드 받으실 수 있습니다.

#### 업로드 형식
입력하고자 하는 정보는 정의된 구분자에 의해 구분되며 반드시 START 태그와 END 태그를 한쌍으로 가집니다. 구분자의 START와 END 사이의 정보를 업로드 하게 되며 구분자에는 INTENT, NAME, SENTENCE, PARAM 이 존재합니다.

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
            <td markdown="span">해당 업로드 정보가 Intent에 관한 정보임을 나타냅니다.</td>
        </tr>
        <tr>
            <td markdown="span">**NAME**</td>
            <td markdown="span">부분 필수</td>
            <td markdown="span">Intent명, Intent 버튼명, Intent ID에 관한 정보임을 나타냅니다. Intent명은 필수값이나 나머지는 생략이 가능합니다. 챗봇 내에서 동일한 Intent 명이 존재할 경우 이름이 변경되어 올라갑니다.</td>
        </tr>
        <tr>
            <td markdown="span">**SENTENCE** </td>
            <td markdown="span">필수</td>
            <td markdown="span">예문에 관한 정보임을 나타냅니다. 한 줄당 하나의 예문으로 인식하며 반드시 하나 이상의 예문을 요구합니다.</td>
        </tr>
        <tr>
            <td markdown="span">**PARAM**</td>
            <td markdown="span">선택</td>
            <td markdown="span">Parameter에 관한 정보임을 나타냅니다. Parameter명과 Entity를 입력합니다. 존재하지 않는 Entity를 입력하면 업로드가 되지 않습니다. Entity명 앞에는 반드시 @를 붙여줘야 합니다. Parameter명이 중복될 시에도 업로드가 불가합니다.</td>
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
Parameter명,@Entity명
>>END_PARAM
>END_INTENT
{%endraw%}
```

{% include warning.html content="정보 구분을 위한 콤마(,)간 띄워쓰기는 불가합니다." %}

샘플 파일을 다운로드 받으셔서 해당 파일을 업로드 해서 결과를 확인해보세요.

### 다운로드
생성한 Intent를 CSV 파일로 다운로드 받으실 수 있습니다. DANBEE.AI는 챗봇 별 전체 Intent 다운로드 기능과 Intent 별 단건 다운로드 기능을 제공하고 있습니다.

#### 단건 다운로드
{% include callout.html content="버튼 위치 : [자연어이해(NLU)] > [의도 추론(Intent)] > 특정 Intent 선택 > [더보기] > [Intent다운]" type="default" %}

단건 다운로드 시 하나의 Intent에 관한 정보가 CSV 파일로 저장됩니다.



#### 다건 다운로드
{% include callout.html content="버튼 위치 : [자연어이해(NLU)] > [의도 추론(Intent)] > [더보기] > [Intent다운]" type="default" %}

다건 다운로드 시 챗봇 전체 Intent가 CSV 파일로 저장되며 zip 파일로 압축되어 제공됩니다.

{% include warning.html content="유니코드가 깨질 수 있기 때문에 압축을 풀때는 알집 8버전 이상, 혹은 다른 압축해제 프로그램 사용을 권장 합니다." %}



