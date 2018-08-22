---
title: 엔티티 관리
tags: [nlu, basic]
keywords: Basic Conversation
summary: Entity를 통하여 입력 문장에서 필요한 정보를 뽑아낼 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: entity.html
folder: danbeeDoc
previous: {
    title: 의도 관리,
    url: intent.html
}
next: {
    title: 대화흐름 기본 설명,
    url: chatflow.html
}
---

## 엔티티(Entity)

**엔티티(이하 Entity)**란, 사용자의 말 속에서 원하는 정보를 뽑아내기 위해 설정하는 값입니다. 앞서 <span class="link"><i class="fa fa-external-link-square" aria-hidden="true" style="margin:0px 5px"></i>[Intent의 Parameter](intent.html#파라미터parameter)</span>에서 설명한 것과 같이 Parameter라는 껍데기가 어떤 정보를 담을 수 있을지 결정해주는 역할을 합니다.<br/>

Entity의 종류에는 크게 2가지가 있습니다.
- [시스템 Entity](entity.html#시스템-entity)
- [사용자정의 Entity](entity.html#사용자정의-entity)

### 시스템 Entity
**시스템 Entity**는 danbee.Ai에서 기본적으로 제공하는 Entity를 의미합니다. danbee.Ai에서는 기본적으로 다음과 같은 시스템 Entity를 제공합니다.
- [날짜 Entity : sys.year, sys.month, sys.date](entity.html#날짜-entity)
- [확인 Entity : sys.confirm](entity.html#확인-entity)
- [숫자 Entity : sys.number](entity.html#숫자-entity)
- [일반 Entity : sys.any](entity.html#일반-entity)

#### 날짜 Entity

| Entity | 대표어 |
|--------|-------|
| sys.date | 오늘, 내일, 모레, 어제, 그제, 3일 전, 3일 후 등 |
| sys.month | 당월, 익월, 전월, 익익월, 전전월 등 |
| sys.year | 올해, 내년, 작년, 내후년, 재작년 등 |

**날짜 Entity**는 날짜를 가리키는 단어를 구분합니다. 일, 월, 년에 대해 각각의 시스템 Entity를 제공합니다. 위 대표어 이외에 당일, 이번달, 금년 등 일반적으로 사용하는 날짜 지칭 단어를 구분할 수 있도록 제공되고 있습니다.

{% include image.html file="entity/Entitiy_system_date01.png" max-width="900" caption="Parameter 추가 - sys.date Entity" %}

{% include image.html file="entity/Entitiy_system_date02.png" max-width="900" caption="sys.date 결과값 확인" %}

Intent에 날짜 Entity 타입의 Parameter를 추가하고 날짜 지칭 단어가 들어가는 문장을 입력하면 단어가 숫자값으로 변환되어 들어오는 것을 확인할 수 있습니다. '오늘', '당월', '올해'를 0으로 잡고 기준으로 부터 떨어진 날짜수를 계산하여 반환하게 됩니다.  

#### 확인 Entity

| Entity | 대표어(값) |
|--------|-------|
| sys.confirm | 예(Y), 아니오(N), 대답회피(C) |

**확인 Entity**는 긍정,부정,중립을 구분합니다.

{% include image.html file="entity/Entitiy_system_confirm.png" max-width="900" caption="sys.confirm 결과값 확인" %}

위 예시와 같이 좋고 싫음 혹은 예, 아니요를 요구하는 질문에 대하여 돌아오는 대답에 따라 다른 반응을 보일 수 있도록 지정하는데 유용하게 활용할 수 있습니다.

#### 숫자 Entity

| Entity | 대표어(값) |
|--------|-------|
| sys.number | 일(1),이(2), ..., 백(100), 천(1000) 등 |

**숫자 Entity**는 숫자 표현을 구분합니다.

{% include image.html file="entity/Entitiy_system_number01.png" max-width="900" caption="Parameter 추가 - sys.number Entity" %}

{% include image.html file="entity/Entitiy_system_number02.png" max-width="900" caption="sys.number 결과값 확인" %}

Intent에 숫자 Entity 타입의 Parameter를 추가하고 숫자를 지칭 단어가 들어가는 문장을 입력하면 단어가 실제 숫자값으로 변환되어 들어오는 것을 확인할 수 있습니다. danbee.Ai는 1,2,3과 같은 숫자 형태와 일,이,삼 또는 하나,둘,셋과 같은 한글 형태의 서수 및 기수 표현을 sys.number로 지원하고 있습니다. 두번째 표현과 같이 숫자와 한글을 섞은 표현 역시 지원됩니다. 다만, 현재 한글 형태의 경우 자연수만 지원하고 있습니다.

#### 일반 Entity

| Entity | 대표어 |
|--------|-------|
| sys.any | N/A |

**일반 Entity**는 모든 단어 또는 어구를 담을수 있는 타입이며 그렇기 때문에 가장 다양하게 활용할 수 있는 시스템 Entity 입니다. 주로 특정하기 힘든 단어 또는 어구를 찾기 위해 사용할 수 있습니다.

{% include image.html file="entity/Entitiy_system_any_01.png" max-width="900" caption="Parameter 추가 - sys.any Entity" %}

{% include image.html file="entity/Entitiy_system_any_02.png" max-width="900" caption="sys.any 결과값 확인" %}

Intent에 일반 Entity 타입의 Parameter를 추가하고 예문의 특정 위치를 지정하면 해당 위치에 들어가는 모든 단어 또는 어구가 Parameter에 담기는 것을 확인할 수 있습니다.<br/>
다만, 세 번째 테스트에서는 *'라파엘'*이라는 글자만 얻고자 했지만 문장 패턴이 '내 이름은 ~야'로 지정되어 있기 때문에 *'라파엘이'* 라는 정보를 가져오게 됩니다. 이와 같이 sys.any는 모든 말이 담기기 때문에 예문에 특정 패턴으로 지정해서 사용 시에는 주의해서 사용해야 합니다.

### 사용자정의 Entity

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [단어 추출(Entity)]" type="default" %}

**사용자정의 Entity**는 직접 정의하여 사용하는 Entity 입니다. 즉, Parameter를 해당 Entity로 지정할 경우 담길 수 있는 정보를 직접 정의할 수 있습니다.<br/>

#### 사용자정의 Entity 등록하기

해당 메뉴에서는 Entry와 Reference를 등록하게 됩니다. **Entry**란 뽑아내고자 하는 정보의 대표어를 의미합니다. 그리고 **Reference**란 Entry로 인식되는 참조어를 의미합니다.<br/>

{% include image.html file="entity/Entitiy_user_define01.png" max-width="900" caption="사용자정의 Entity 등록" %}

{% include image.html file="entity/Entitiy_user_define02.png" max-width="900" caption="사용자정의 Entity 테스트" %}

예를 들어 위와 같이 *'치킨'*이라는 Entry에는 *'통닭,Chicken,치느님'* 등의 Reference를 등록할 수 있습니다. 이렇게 등록하게 통닭,Chicken,치느님 등의 정보를 입력받았을 때 봇은 '치킨'으로 인식하게 됩니다.<br/>

Entity 등록/수정에는 다음과 같은 제약사항이 존재합니다.

- Entity는 반드시 하나 이상의 Entry를 가져야 한다.
- Entry는 반드시 하나 이상의 Reference를 가져야 한다.
- Entry와 Reference는 최대 각 40자로 제한한다.
- 하나의 Entry에 Reference는 최대 100개까지 등록이 가능하다.


#### 사용자사전 등록 추천 단어

사용자정의 Entity를 저장하면 사전에 등록하면 좋을 단어들을 추천합니다. 해당 단어는 인식률이 떨어질 수 있는 단어들이기 때문에 사용자사전 등록을 권장합니다. 사용자사전에 관하여 더 자세한 내용은 **[사용자사전 관리](dictionary.html)** 메뉴에서 확인할 수 있습니다.

{% include image.html file="entity/Entity_user_define03_recommend.png" max-width="900" caption="사전 등록 추천어 확인" %}

#### 사용자사전 불러오기

{% include image.html file="entity/Entity_user_define04_userdic01.png" max-width="900" caption="사용자사전 불러오기" %}

위 버튼을 클릭하면 사용자정의 Entity에서 사용자사전에 등록해놓은 단어를 불러와서 사용할 수 있습니다. 원하는 단어를 체크한 뒤 불러오기 버튼을 클릭하면 해당 Entity의 Entry와 Reference로 추가되는 것을 확인할 수 있습니다.

{% include image.html file="entity/Entity_user_define04_userdic02.png" max-width="900" caption="사용자사전 불러오기 - 결과" %}

## 엔티티(Entity) 업로드/다운로드

danbee.Ai는 편의 기능의 일종으로 사용자정의Entity 업로드/다운로드 기능을 제공하고 있습니다. 해당 기능은 CSV파일로 지원됩니다.

{% include warning.html content="CSV파일을 열 때에는 **메모장, UltraEdit** 등의 편집기 사용을 권장합니다. MS Excel 사용 시 한글이 깨질 수 있습니다." %}

### 업로드
{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [단어추출(Entity)] > [더보기] > [Entity 업로드]" type="default" %}
업로드 형식에 맞추어 작성한 CSV파일을 올려주시면 자동으로 Entity가 생성됩니다. 업로드 파일은 다음과 같은 제약사항이 존재합니다.
 - CSV파일만 가능합니다.
 - 파일당 최대 3MB까지 가능합니다.
 - 파일명은 최대 70자까지 허용합니다.

해당 메뉴에서 <span style="color:#337ab7">**Entity Upload Sample File 보기**</span>를 클릭하시면 업로드 형식을 확인할 수 있으며 샘플 파일을 다운로드 받으실 수 있습니다.

#### 업로드 형식
입력하고자 하는 정보는 정의된 구분자에 의해 구분되며 반드시 START 태그와 END 태그를 한쌍으로 가집니다. 구분자의 START와 END 사이의 정보를 업로드 하게 되며 구분자에는 ENTITY, NAME, ENTRY 가 존재합니다.

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
</table>

필수값에 해당하는 정보가 없거나 형식이 맞지 않으면 파일은 업로드에 실패하게 됩니다. 실제 업로드 파일은 다음과 같은 형식으로 쓰게 됩니다.

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

### 다운로드
생성한 Entity를 CSV 파일로 다운로드 받으실 수 있습니다. danbee.Ai는 챗봇 별 전체 Entity 다운로드 기능과 Entity 별 단건 다운로드 기능을 제공하고 있습니다.

#### 단건 다운로드
{% include callout.html content="버튼 위치 : [자연어이해(NLU)] > [단어추출(Entity)] > 특정 Entity 선택 > [더보기] > [Entity 다운]" type="default" %}

단건 다운로드 시 하나의 Entity에 관한 정보가 CSV 파일로 저장됩니다.



#### 다건 다운로드
{% include callout.html content="버튼 위치 : [자연어이해(NLU)] > [단어추출(Entity)] > [더보기] > [Entity 다운]" type="default" %}

다건 다운로드 시 챗봇 전체 Entity가 CSV 파일로 저장되며 zip 파일로 압축되어 제공됩니다.

{% include warning.html content="유니코드가 깨질 수 있기 때문에 압축을 풀때는 알집 8버전 이상, 혹은 다른 압축해제 프로그램 사용을 권장 합니다." %}
