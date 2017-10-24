---
title: 데모 및 테스트 패널
tags: [demo, test, analytics]
keywords: Basic Conversation
summary: 데모 및 테스트 패널을 활용하여 봇이 어떻게 동작하는지 확인할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: demo_n_test_panel.html
folder: danbeeDoc
previous: {
    title: 대화 로그 관리,
    url: log.html
}
next: {
    title: 챗봇 채널 연계 설정,
    url: channel_connection_settings.html
}
---

## 테스트 패널

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도추론(Intent)]/[단어추출(Entity)] & [대화흐름(CHATFLOW)] > [대화흐름 목록(Chatflow List)] 우측" type="default" %}

DANBEE.AI에서는 지금까지 등록한 정보가 시스템에서 어떻게 인식되는지 테스트할 수 있도록 테스트 패널을 제공하고 있습니다. 테스트 패널은 총 2가지 종류가 제공됩니다.

- [NLU Intent 테스트 패널](demo_n_test_panel.html#nlu-intent-테스트-패널)
- [Chatflow 테스트 패널](demo_n_test_panel.html#chatflow-테스트-패널)

### NLU Intent 테스트 패널

NLU Intent 테스트 패널에서는 입력 받은 문장이 어떻게 분석되어 어떤 Intent로 분류되는 지를 확인할 수 있습니다. 또한 잘못된 Intent로 분류될 때 해당 문장을 원하는 Intent로 등록하는 등의 편의 기능을 제공하고 있습니다.

#### Intent

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel01.PNG" max-width="900" caption="NLU Intent 테스트 패널 - Intent 영역" %}

**Intent 영역**은 입력 문장이 분류된 대표 Intent, 그리고 분류된 대표 Intent의 Parameter 정보를 보여줍니다. 만약 분류된 Intent가 적절하지 않게 여겨지면 분류 Intent를 변경할 수 있습니다. Intent 우측 표시된 버튼을 누르면 등록된 Intent 목록이 나옵니다. 여기서 분류되어지길 원하는 Intent를 선택하면 해당 Intent의 상세 화면으로 이동하며 입력 문장이 해당 Intent에 들어갑니다. 다만 다시 한 번 더 확인을 권장하므로 자동 저장은 되지 않습니다. 

#### Intent Candidates

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel02.PNG" max-width="900" caption="NLU Intent 테스트 패널 - Intent Candidates 영역" %}

앞서 [챗봇 성격 설정](personality_settings)에서 설명한 것과 같이 입력 문장은 여러개의 Intent로 파악될 수 있습니다. 그렇기 때문에 **Intent Candidates 영역**에서는 입력 문장이 분류될 수 있는 모든 Intent를 보여줍니다. 또한 하나의 Intent로 파악되더라도 해당 Intent로 파악된 매칭률을 확인할 수 있습니다.<br/>

Intent Candidates 영역 우측에 보면 [+] 버튼이 존재합니다. 해당 버튼을 누를 시 테스트로 입력한 문장이 자동으로 해당 인텐트에 들어가게 됩니다.<br/>

또한 Intent Candidates의 헤더를 클릭하면 파악된 Intent를 Intent명과 버튼명 2가지 모드로 확인할 수 있습니다.<br/>

이외에도 NLU Intent 테서트 패널에서는 입력 문장에 대한 추가적인 정보를 확인할 수 있습니다.

#### SHOW JSON 

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel03.PNG" max-width="900" caption="NLU Intent 테스트 패널 - SHOW JSON" %}

먼저 입력 문장에 대해 판별한 정보가 어떤 형태로 되돌아오는지 확인할 수 있습니다. NLU Intent 테스트 패널 최하단 [SHOW JSON] 버튼을 누르면 JSON 형태의 정보를 볼 수 있는 팝업이 뜹니다.

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel03_json_popup.PNG" max-width="900" caption="NLU Intent 테스트 패널 - JSON 팝업" %}

해당 팝업에서는 필요에 따라 사용할 수 있도록 복사 기능을 제공하고 있습니다. 복사를 누르면 해당 정보가 JSON String 형태로 복사됩니다.

#### TEXT ANALYTICS

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel04.PNG" max-width="900" caption="NLU Intent 테스트 패널 - TEXT ANALYTICS" %}

마지막으로 입력 문장이 어떻게 분석되는지 확인할 수 있습니다. NLU Intent 테스트 패널 최하단 [TEXT ANALYTICS] 버튼을 누르면 분석 결과를 볼 있는 팝업이 뜹니다.

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel04_text_popup.PNG" max-width="900" caption="NLU Intent 테스트 패널 - TEXT ANALYTICS 팝업" %}

### Chatflow 테스트 패널

Chatflow 테스트 패널에서는 대화를 진행하면서 현재 어떤 흐름을 타고 있는지, 오류가 난다면 무슨 이유인지 확인할 수 있습니다.

{% include image.html file="test_panel_n_demo/Chatflow_test_panel01.PNG" max-width="900" caption="Chatflow 테스트 패널" %}

Chatflow 테스트 패널 하단에 노출되는 정보는 다음과 같습니다.

| 구분 | 설명 |
|------|------|
| 세션 | 대화 세션 번호를 보여줍니다. 세션은 대화가 시작되고 끝나기까지의 단위입니다. |
| 대화흐름 | 현재 타고 있는 Chatflow명을 보여줍니다. |
| 인스턴스 | 인스턴스 번호를 보여줍니다. 인스턴스는 하나의 Chatflow가 유지되는 단위입니다. |
| 노드 | 현재 타고 있는 노드ID를 보여줍니다. |
| 파라메터 | Chatflow 내에서 현재 정보를 받고자하는 Parameter를 보여줍니다. |
| 의도추론 | 현재 Chatflow가 어떤 Intent와 연결되어 있는지 Intent명을 보여줍니다. |

이외에도 최하단에는 **디버깅 메세지**를 보여줌으로써 오류가 날 때 어디에서 문제가 생겼는지 알려줍니다.<br/> 
세 번째 이미지에서 확인할 수 있다 시피 해당 대화가 흐름는 중 오류가 발생하였습니다. 메세지를 확인해보면 '안녕'이라는 Chatflow에서 Split Node에 조건을 찾을 수 없다고 적혀있습니다. 실제로 '안녕'이라는 Chatflow를 확인해보면 다음과 같은 흐름이 구성되어 있습니다.

{% include image.html file="test_panel_n_demo/Chatflow_test_panel02.PNG" max-width="900" caption="오류 확인" %}

이와 같이 테스트 패널을 잘 활용한다면 보다 쉽게 자연스러운 대화를 만들 수 있을 것입니다.

## 데모
{% include callout.html content="화면 위치 : [DEMO]" type="default" %}

{% include image.html file="test_panel_n_demo/DEMO.PNG" max-width="900" caption="데모" %}

데모 화면에서는 웰컴 메세지부터 시작하여 실제로 챗봇이 어떻게 대답하는지 확인하실 수 있습니다.
