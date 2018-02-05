---
title: NLU 설정
tags: [settings, nlu]
keywords: General Conversation
summary: 챗봇이 자연어를 이해하는 방법에 대하여 설정할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: settings_nlu.html
folder: danbeeDoc
previous: {
    title: 기본 답변 설정,
    url: settings_personality.html
}
next: {
    title: 대화 이력 관리,
    url: log.html
}
---

## NLU 설정(NLU Settings)
 {% include callout.html content="화면 위치 : [설정(Preference)] > [NLU 설정(NLU Settings)]" type="default" %}
**NLU 설정**이란, 챗봇의 NLU, 즉 챗봇이 입력된 문장을 이해하는 방식에 대하여 설정하는 페이지 입니다.

### NLU 추론 설정

{% include note.html content="본 내용은 [danbee.Ai NLU 추론 방법](settings_nlu.html#danbeeai-nlu-추론-방법)을 확인하신 후 본다면 이해에 도움이 될 수 있습니다." %}

NLU에 대하여 다음과 같은 설정이 가능합니다.<br/>

- [추론 순서](settings_nlu.html#추론-순서)
- [형태소 분석 추론 성공범위 설정](settings_nlu.html#형태소-분석-추론-성공범위-설정)
- [머신러닝 추론 성공범위 설정](settings_nlu.html#머신러닝-추론-성공범위-설정)

#### 추론 순서

챗봇이 입력된 문장의 의도를 파악하기 위해 어떤 순서로 추론을 해나갈 것인지 설정이 가능합니다. 총 2가지 순서 설정이 가능합니다.

- 형태소 분석 우선 추론(A-B-C)
- 머신러닝 우선 추론(A-C-B)

{% include image.html file="nlu_settings/nlu_settings_01.png" max-width="900" caption="추론 순서 설정" %}

##### 형태소 분석 우선 추론(A-B-C)
**형태소 분석 우선 추론**의 경우 [패턴 매칭(이하, A패턴)](settings_nlu.html#패턴-매칭-a패턴) 추론에서 적합한 Intent를 찾지 못할 경우 [형태소 분석 추론(이하, B패턴)](settings_nlu.html#형태소-분석-추론-b패턴) 방식으로 Intent를 재추론하게 됩니다. B패턴 추론 결과 Intent를 찾지 못한 경우, 혹은 적합한 Intent를 찾았지만 추론율이 설정한 [형태소 분석 추론 성공범위](settings_nlu.html#형태소-분석-추론-성공범위-설정)의 임계값 미만일 경우 [머신러닝 추론(이하, C패턴)](settings_nlu.html#머신러닝-추론-c패턴)으로 넘어가게 됩니다. C패턴 추론 결과 역시 설정한 [머신러닝 추론 성공범위](settings_nlu.html#머신러닝-추론-성공범위-설정)이상일 경우 찾은 Intent를 반환하지만 설정값 이하일 경우 최종적으로 Default Fallback을 반환합니다.

##### 머신러닝 우선 추론(A-C-B)
**머신러닝 우선 추론**의 경우 형태소 분석 우선 추론과 반대로 A패턴에서 Intent를 찾지 못하면 C패턴 방식으로 먼저 Intent를 추론합니다. 순서를 제외한 이하 내용은 형태소 분석 우선 추론과 동일하게 동작합니다.
<br/><br/>

{% include note.html content="일반적으로 학습데이터가 많을 경우 **머신러닝 우선 추론 방식**이 유리합니다." %}



#### 추론 성공범위 설정

danbee.Ai에서는 추론율이 낮다면 신뢰할 수 없는 데이터로 판단 가능하도록 추론 성공범위 설정 기능을 제공하고 있습니다. 추론 성공 범위는 추론된 데이터를 얼마나 신뢰할 것이냐의 문제이므로 신중하게 설정해야 합니다. B패턴과 C패턴 각각의 성공범위가 설정 가능합니다.

##### 형태소 분석 추론 성공범위 설정 

{% include image.html file="nlu_settings/nlu_settings_02.png" max-width="900" caption="형태소 분석 추론 성공범위 설정" %}

해당 영역에서 B패턴의 추론 성공 범위를 설정할 수 있습니다. 앞서 설명한 것과 같이 B패턴으로 찾은 Intent의 추론율이 설정한 임계값 이상일 때는 해당 Intent가 반환 되지만 임계값 미만일 경우 Default Fallback으로 치환됩니다.

##### 머신러닝 추론 성공범위 설정

{% include image.html file="nlu_settings/nlu_settings_03.png" max-width="900" caption="머신러닝 추론 성공범위 설정" %}

해당 영역에서 C패턴의 추론 성공 범위를 설정할 수 있습니다. 앞서 설명한 것과 같이 C패턴으로 찾은 Intent의 추론율이 설정한 임계값 이상일 때는 해당 Intent가 반환 되지만 임계값 미만일 경우 Default Fallback으로 치환됩니다.


#### NLU 설정 예시
NLU Intent 테스트 패널에서 같은 표현이 설정에 따라 어떻게 판단되는지 비교할 수 있습니다.<br/>

예시 챗봇이 "이번에 이사가서 에어컨 이전 설치 하고싶은데 어떠케 해야 하져?" 라는 문장을 받았을때 설정에 따라 어떤 결과를 내뱉는지 확인해보겠습니다.

- [가] 형태소 분석 우선 추론, 형태소 분석 성공범위 임계값 0%, 머신러닝 추론 성공범위 임계값 15%

 {% include image.html file="nlu_settings/nlu_settings_04-1.png" max-width="900" caption="[가]테스트 설정" %}
 {% include image.html file="nlu_settings/nlu_settings_04-2.png" max-width="900" caption="[가]테스트 결과" %}

 [가]와 같이 설정하였을때 B패턴으로 추론을 성공하였으며 추론율이 40.04%가 나옴을 먼저 확인하였습니다. [나]에서는 형태소 분석 성공범위 설정 동작을 확인하기 위해 해당 추론율 이상인 45%로 올려서 테스트를 진행합니다.
<br/><br/>
- [나] 형태소 분석 우선 추론, 형태소 분석 성공범위 임계값 45%, 머신러닝 추론 성공범위 임계값 15%

 {% include image.html file="nlu_settings/nlu_settings_05-1.png" max-width="900" caption="[나]테스트 설정" %}
 {% include image.html file="nlu_settings/nlu_settings_05-2.png" max-width="900" caption="[나]테스트 결과" %}

 [가]에서 확인한 기존 B패턴 추론 결과는 40.04%로 형태소 분석 성공범위의 임계값 미만이기 때문에 C패턴 테스트가 진행되었으면 확인할 수 있습니다. 또한, C패턴 추론 결과의 추론율이 15.69%로 성공범위 임계값 이상이기 때문에 추론에 성공함을 확인할 수 있습니다. [다]에서는 머신러닝 추론 성공범위 설정 동작을 확인하기 위해 해당 추론율 이상인 20%로 올려서 테스트를 진행합니다.
<br/><br/>
- [다] 형태소 분석 우선 추론, 형태소 분석 성공범위 임계값 45%, 머신러닝 추론 성공범위 임계값 20%

 {% include image.html file="nlu_settings/nlu_settings_06-1.png" max-width="900" caption="[다]]테스트 설정" %}
 {% include image.html file="nlu_settings/nlu_settings_06-2.png" max-width="900" caption="[다]테스트 결과" %}

 [나]에서 확인한 C패턴 추론 결과는 15.69%로 성공범위 임계값 미만이기 때문에 Default Fallback 처리 되었음을 확인할 수 있습니다.<br/><br/>

머신러닝 우선 추론으로 바꾸었을 때 역시 다음과 같이 테스트를 할 수 있습니다.

- 머신러닝 우선 추론, 형태소 분석 성공범위 임계값 0%, 머신러닝 추론 성공범위 임계값 15% : C패턴, 15.09%로 추론이 성공할 것임을 예측가능합니다.

- 머신러닝 우선 추론, 형태소 분석 성공범위 임계값 0%, 머신러닝 추론 성공범위 임계값 20% : B패턴, 40.04%로 추론이 성공할 것임을 예측가능합니다.

- 머신러닝 우선 추론, 형태소 분석 성공범위 임계값 45%, 머신러닝 추론 성공범위 임계값 20% : Default Fallback 처리가 될것임을 예측가능합니다.


### danbee.Ai NLU 추론 방법

NLU를 설정하기 전 danbee.Ai가 제공하고 있는 NLU에 대해 우선적으로 이해할 필요가 있습니다.<br/>
danbee.Ai는 챗봇이 입력된 문장을 이해할 수 있도록 하기 위하여 다음과 같은 방법들을 순차적으로 제공하고 있습니다.

 - [패턴 매칭 (A패턴)](settings_nlu.html#패턴-매칭a패턴-추론)
 - [형태소 분석 추론 (B패턴)](settings_nlu.html#형태소-분석b패턴-추론)
 - [머신러닝 추론 (C패턴)](settings_nlu.html#머신러닝c패턴-추론)

#### 패턴 매칭(A패턴) 추론

**패턴 매칭(A패턴)** 추론이란, Intent에 등록된 예문을 기준으로 완벽히 동일한 패턴을 가진 문장을 찾는 방법입니다. 완벽하게 동일한 문장이나 parameter 등록시 해당 parameter를 치환할 수 있는 문장을 찾게 됩니다. 또한 입력된 예문의 표준 문장을 정의하여 동일한 표준 문장이 들어왔을 때 역시 A패턴으로 인식합니다. danbee.Ai에서 제공하는 3가지 추론 패턴 중 가장 정확도가 높기 때문에 1순위로 동작하게 되어 있습니다. 
<br/><br/>
A패턴에서 입력 문장의 의도를 추론하지 찾지 못하면 다음 2가지 패턴으로 재추론을 시작합니다. 앞서 설명한 것과 같이 어떤 패턴을 우선적으로 추론할 것인지는 [추론 순서](settings_nlu.html#추론-순서)에서 설정이 가능합니다.


#### 형태소 분석(B패턴) 추론
**형태소 분석(B패턴)** 추론이란, 입력 문장의 형태소 분석 결과와 가장 유사한 형태소 분석 결과를 보이는 예문을 가진 Intent를 추론하는 방법입니다. 명사와 동사, 그리고 핵심 키워드를 중심으로 유사도를 평가합니다. 

#### 머신러닝(C패턴) 추론
**머신러닝(C패턴)** 추론이란, 말 그대로 머신러닝으로 자동 학습된 결과를 가지고 Intent를 추론하는 방법입니다. 현재 danbee.Ai에서는 예문을 기준으로 학습을 진행하고 있습니다. 