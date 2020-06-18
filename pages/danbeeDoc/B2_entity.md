---
title: 엔티티
tags: [nlu, basic]
keywords: Basic Conversation
summary: Entity를 통하여 입력 문장에서 필요한 정보를 뽑아낼 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: entity.html
folder: danbeeDoc
previous: {
    title: JUMP 노드,
    url: chatflow_jump.html
}
next: {
    title: 공통 변수,
    url: settings_manage_variables.html
}
---

{% include callout.html content="화면 위치 : 챗봇 > 챗봇 제작 > 엔티티" type="default" %}


{% include image.html file="entity/chatbotflow.png"  caption="대화의도와 엔티티의 관계" %}

**엔티티**란, 사용자의 말이나 문장 속에서 원하는 정보를 추출하여 적절하게 대화를 이끌어 나갈 수 있도록 설정하는 단어군입니다. 
엔티티는 [대화의도의 파라미터](intent.html#파라미터parameter)가 실제로 어떤 종류의 값을 가지게 될지 결정해 주는 역할을 합니다.
엔티티에 대해 자세히 알아보며 어떻게 사용해야 할지 알아보도록 하겠습니다.

엔티티에는 2가지 종류가 있습니다.<br/>

<!-- 앞서 <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[대화의도의 파라미터](intent.html#파라미터parameter)</span>에서 설명한 것과 같이 파라미터라는 껍데기가 어떤 정보를 담을 수 있을지 결정해주는 역할을 합니다.<br/>Entity의 종류에는 크게 2가지가 있습니다. -->

- [시스템 엔티티](entity.html#시스템-entity)
- [사용자정의 엔티티](entity.html#사용자정의-entity)

--------------------------------------------------

## 사용자 정의 엔티티

**사용자 정의 엔티티**는 사용자의 필요에 의해 직접 정의하여 사용하는 엔티티입니다. 단비.Ai에서 기본적으로 지원하는 시스템 엔티티로 처리할 수 없는 경우는 사용자 정의 엔티티를 이용해 처리할 수 있습니다.

### 사용자 정의 엔티티 등록하기

{% include image.html file="entity/entity_create.PNG"  caption="사용자정의 엔티티 등록" %}

엔티티 등록은 **챗봇 생성/관리 > 엔티티 > 엔티티 생성** 버튼을 통해 할 수 있습니다. 추출 항목과 레퍼런스를 등록하게 됩니다. **추출 항목**이란 사용자 입력 문장에서 추출하고자하는 정보의 대표어를 의미합니다. **레퍼런스**로 등록된 단어는 해당되는 추출 항목으로 인식되게 됩니다. 챗봇이 실제로 대화를 진행하면서 파라메터에 담게 되는 값은 **추출 항목**입니다.<br/>

>##### 엔티티 이름
추출 해내고자 하는 단어 모음의 총칭입니다.
##### 추출 항목
실제로 챗봇에 전달되는 추출명입니다.
##### 레퍼런스
사용자의 단어를 실제로 찾아볼 단어목록입니다. 

{% include image.html file="entity/Entitiy_user_define01.png"  caption="사용자정의 엔티티 등록" %}

예를 들어 위와 같이 **'치킨'**이라는 추출 항목에는 **'통닭,Chicken,치느님'** 등의 레퍼런스를 등록할 수 있습니다. 이렇게 엔티티를 설정하면 챗봇은 '통닭','Chicken','치느님'이라는 문장을 입력받았을 때 **'치킨'으로 인식하게 됩니다.**

사용하고자 하는 정보에 따라서 추출 항목에 치킨, 일식, 중식과 같은 큰 범주나, 짜장면, 짬뽕 볶음밥과 같은 작은 범주로 적절하게 설정하여 사용해야합니다. 

{% include image.html file="entity/Entitiy_user_define02.png"  caption="사용자정의 엔티티 테스트" %}


엔티티 등록/수정에는 다음과 같은 제약사항이 존재합니다.

- 엔티티는 반드시 하나 이상의 추출 항목을 가져야 한다.
- 추출 항목은 반드시 하나 이상의 레퍼런스를 가져야 한다.
- 추출 항목과 레퍼런스는 최대 각 40자로 제한한다.
- 하나의 추출항목에 레퍼런스는 최대 100개까지 등록이 가능하다.


### 고유 용어 사전 등록 추천 단어

사용자정의 엔티티를 저장하게되면 고유 용어 사전에 등록하면 좋을 단어들을 추천합니다. 해당 단어는 인식률이 떨어질 수 있는 단어들이기 때문에 고유 용어 사전 등록을 권장합니다. 고유 용어 사전에 관하여 더 자세한 내용은 [고유 용어 사전 관리](dictionary.html) 메뉴에서 확인할 수 있습니다.

{% include image.html file="entity/Entity_user_define03_recommend.png"  caption="사전 등록 추천어 확인" %}

### 고유 용어 사전 불러오기

{% include image.html file="entity/Entity_user_define04_userdic01.png"  caption="사용자사전 불러오기" %}

위 버튼을 클릭하면 사용자정의 엔티티로 사용자사전에 등록해놓은 단어를 불러와서 사용할 수 있습니다. 원하는 단어를 체크한 뒤 불러오기 버튼을 클릭하면 고유 용어 사전의 대표어는 추출 항목으로, 고유 용어 사전의 유의어는 레퍼런스로 추가되는 것을 확인할 수 있습니다.

{% include image.html file="entity/Entity_user_define04_userdic02.png"  caption="사용자사전 불러오기 - 결과" %}

---------------------

## 시스템 엔티티
**시스템 엔티티**는 단비Ai에서 기본적으로 제공하는 엔티티들을 의미합니다. 단비Ai에서는 기본적으로 다음과 같은 시스템 Entity를 제공합니다.
- [날짜 엔티티 : sys.year, sys.month, sys.date](entity.html#날짜-entity)
- [확인 엔티티 : sys.confirm](entity.html#확인-entity)
- [숫자 엔티티 : sys.number](entity.html#숫자-entity)
- [일반 엔티티 : sys.any](entity.html#일반-entity)

### 날짜 엔티티

| 엔티티명 | 레퍼런스 | 값 |
|--------|-------|-------|
| sys.date | 오늘, 내일, 모레, 어제, 그제, 3일 전, 3일 후 등 | ..., -2, -1, 0, 1, ...|
| sys.month | 당월, 익월, 전월, 익익월, 전전월 등 | ..., -2, -1, 0, 1, ... |
| sys.year | 올해, 내년, 작년, 내후년, 재작년 등 | ..., -2, -1, 0, 1, ... |
{: .table .table-striped}

**날짜 엔티티**는 날짜를 가리키는 단어를 추출합니다. 일, 월, 년에 대해 각각의 시스템 엔티티를 제공합니다. 위 대표어 이외에 당일, 이번달, 금년 등 일반적으로 사용하는 날짜 지칭 단어를 구분할 수 있도록 제공되고 있습니다. 날짜 엔티티는 자체적으로 현재시점으로부터 사용자 지칭 날짜까지의 차이를 값으로 제공합니다.<br>
예) 오늘 날씨 어때 => 0, 어제 날씨 어때 => -1

{% include image.html file="entity/Entitiy_system_date01.png"  caption="대화의도에서 파라미터 추가 - sys.date 설정" %}

{% include image.html file="entity/Entitiy_system_date02.png"  caption="sys.date 결과값 확인" %}

대화의도에 날짜 엔티티타입의 파라메터를 추가하고 날짜 지칭 단어가 들어가는 문장을 입력하면 파라메터값(Value)이 숫자로 입력되고 있는 것을 확인 할 수 있습니다. 오늘, 당월, 올해를 기준으로 떨어진 날짜수를 계산하여 반환합니다.

>##### 날짜 엔티티의 값을 상대값에서 절대값으로 변환하는 방법
sys.date에서는 0이 오늘(today)을 의미하고,
sys.month는 0이 이번달(this month)를 의미합니다.
하지만 필요에 따라 2019-01-29와 같이 날짜 포멧에 맞추어 표현을 바꾸고 싶을 수 있습니다.
자바스크립트를 잘 다룰 수 있는 개발자라면, Function노드를 활용해 형변환을 할 수 있겠지만, 개발 경험이 없는 분들은 아래와 같은 형태의 수식을 통해 날짜포멧을 만들 수 있습니다.

>{% include sampleCode.html content="#{fn_date(\'yyyy-MM-dd\', \'day\', #{변수명})} /* fn_date(포맷, 일자계산유형, 계산값) */" %}

>fn_date함수의 첫번째 파라미터의 포멧에서 지원하는 항목은 아래와 같습니다.

>| 포멧   |   내용 |
|--------|-------|
| yyyy | 네자리 년도  |
| yy   | 두자리 년도  |
| MM   | 월          |
| dd   | 일          |
| E    | 요일         |
| HH   | 24 시간     |
| hh   | 12 시간     |
| mm   | 분          |
| ss   | 초          |
| a/p  | 오전/오후    |
{: .table .table-striped}

>fn_date함수의 두번째 파라미터의 포멧에서 지원하는 일자계산유형은 아래와 같습니다.
유형에 따라 세번째 파라미터인 계산값의 기준이 됩니다. 유형을 day로 하고, 계산값을 -1로 하면 '어제'가 되지만 유형을 month로 설정하고 계산값을 -1을 입력하면 '지난달'이 나오게 되고 year로 설정하면 작년에 해당하는 숫자가 나오게 됩니다.

>| 유형   |   내용 |
|--------|-------|
| day    | 일자계산 |
| month  | 월계산 |
| year   | 년계산 |
{: .table .table-striped}

>fn_date함수의 세번째 파라미터인 계산값은 #{파라미터명} 또는 0, 1, -1과 같은 상대적인 숫자값을 넣어주시면 됩니다.
##### 확인 엔티티

>| 엔티티명 | 레퍼런스 | 값 |
|--------|-------|-------|
| sys.confirm | 예, 아니오, 대답회피 | Y, N, C |
{: .table .table-striped}


>**확인 엔티티**는 긍정,부정,중립을 구분합니다.
>{% include image.html file="entity/Entitiy_system_confirm.png"  caption="sys.confirm 결과값 확인" %}
>위 예시와 같이 좋고 싫음 혹은 예, 아니요를 요구하는 질문에 대하여 돌아오는 대답에 따라 다른 반응을 보일 수 있도록 지정하는데 유용하게 활용할 수 있습니다.
##### 숫자 엔티티

>| 엔티티명 | 레퍼런스 | 값 |
|--------|-------|-------|
| sys.number | 일(1),이(2), ..., 백(100), 천(1000) 등 | 0,1,2,3,4.. |
{: .table .table-striped}

>**숫자 엔티티**는 숫자 표현을 구분합니다.
>{% include image.html file="entity/Entitiy_system_number01.png"  caption="파라미터 추가 - sys.number Entity" %}
>{% include image.html file="entity/Entitiy_system_number02.png"  caption="sys.number 결과값 확인" %}
>대화 의도에 숫자 엔티티 타입의 파라메터를 추가하고 숫자를 지칭 단어가 들어가는 문장을 입력하면 단어가 실제 숫자값으로 변환되어 들어오는 것을 확인할 수 있습니다. 단비Ai는 1,2,3과 같은 숫자 형태와 일,이,삼 또는 하나,둘,셋과 같은 한글 형태의 서수 및 기수 표현을 sys.number로 지원하고 있습니다. 두번째 표현과 같이 숫자와 한글을 섞은 표현 역시 지원됩니다. 다만, 현재 한글 형태의 경우 자연수만 지원하고 있습니다.
##### 일반 엔티티

>| 엔티티명 | 레퍼런스 | 값 |
|--------|-------|-------|
| sys.any | N/A | (사용자입력단어) |
{: .table .table-striped}

>**일반 엔티티**는 모든 단어 또는 어구를 담을수 있는 타입이며 그렇기 때문에 가장 다양하게 활용할 수 있는 시스템 엔티티 입니다. 주로 후보군을 특정하기 힘든 지명, 이름같은 고유명사나 어떤 단어가 들어올지 예상하기 힘든 영역에 활용하게 됩니다.
>{% include image.html file="entity/Entitiy_system_any_01.png"  caption="파라미터 추가 - sys.any Entity" %}
>{% include image.html file="entity/Entitiy_system_any_02.png"  caption="sys.any 결과값 확인" %}
>대화 의도에서 예문에 sys.any 타입의 파라미터를 추가하면 를 해당 위치에 들어가는 모든 단어 또는 어구가 그대로 파라메터에 담기는 것을 확인할 수 있습니다.<br/>
다만, 세 번째 테스트에서는 **'라파엘'**이라는 글자만 얻고자 했지만 문장 패턴이 **'내 이름은 ~야'**로 지정되어 있기 때문에 **'라파엘이'** 라는 정보를 가져오게 됩니다. 이와 같이 sys.any는 모든 말이 담기기 때문에 예문에 특정 패턴으로 지정해서 사용 시에는 예외가 있지는 않은지 점검하면서 사용해야 합니다.

---------------------------------------
## 엔티티(Entity) 업로드

단비Ai는 편의 기능의 일종으로 사용자정의 엔티티 업로드기능을 제공하고 있습니다. 해당 기능은 CSV파일로 지원됩니다.

{% include warning.html content="CSV파일을 열 때에는 **메모장, UltraEdit** 등의 편집기 사용을 권장합니다. MS Excel 사용 시 한글이 깨질 수 있습니다." %}

### 업로드
{% include callout.html content="화면 위치 : 챗봇 생성/변경 > 대화의도 > 대화의도 생성 옆 더보기 > 대화의도 업로드" type="default" %}
업로드 형식에 맞추어 작성한 CSV파일을 올려주시면 자동으로 Entity가 생성됩니다. 업로드 파일은 다음과 같은 제약사항이 존재합니다.
 - CSV파일만 가능합니다.
 - 파일당 최대 3MB까지 가능합니다.
 - 파일명은 최대 70자까지 허용합니다.

해당 메뉴에서 **Entity Upload Sample File 보기**를 클릭하시면 업로드 형식을 확인할 수 있으며 샘플 파일을 다운로드 받으실 수 있습니다.

>##### 업로드 형식
입력하고자 하는 정보는 정의된 구분자에 의해 구분되며 반드시 START 태그와 END 태그를 한쌍으로 가집니다. 구분자의 START와 END 사이의 정보를 업로드 하게 되며 구분자에는 ENTITY, NAME, ENTRY 가 존재합니다.
><table>
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
            <td markdown="span">**ENTITY**</td>
            <td markdown="span">필수</td>
            <td markdown="span">해당 업로드 정보가 Entity에 관한 정보임을 나타냅니다.</td>
        </tr>
        <tr>
            <td markdown="span">**NAME**</td>
            <td markdown="span">필수</td>
            <td markdown="span">Entity명 관한 정보임을 나타냅니다. 챗봇 내에서 동일한 Entity명이 존재할 경우 이름이 변경되어 올라갑니다.</td>
        </tr>
        <tr>
            <td markdown="span">**ENTRY** </td>
            <td markdown="span">필수</td>
            <td markdown="span">Entry명과 Reference 정보임을 나타냅니다. 한 줄당 하나의 Entry로 인식하며 반드시 하나 이상의 Entry를 요구합니다. 또한 Entry와 Reference는 콤마(,)로 구분되며 Reference는 큰따옴표("")로 묶여야만 합니다. 여러개의 Reference는 큰따옴표 내에서 콤마로 구분됩니다.</td>
        </tr>
    </tbody>

>필수값에 해당하는 정보가 없거나 형식이 맞지 않으면 파일은 업로드에 실패하게 됩니다. 실제 업로드 파일은 다음과 같은 형식으로 쓰게 됩니다.

```
{%raw%}
>START_ENTITY
>>START_NAME
Entity명
>>END_NAME
>>START_ENTRY
Entry1,"ref1_1,ref1_2,ref1_3"
Entry2,"ref2_1,ref2_2"
>>END_ENTRY
>END_ENTITY
{%endraw%}
```

{% include warning.html content="정보 구분을 위한 콤마(,)간 띄워쓰기는 불가합니다." %}

샘플 파일을 다운로드 받으셔서 해당 파일을 업로드 해서 결과를 확인해보세요.



{% include bottom.html %}

