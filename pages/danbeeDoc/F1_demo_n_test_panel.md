---
title: 테스트 패널 및 시뮬레이션 
tags: [simulation, nlu, chatflow]
keywords: Basic Conversation
summary: 테스트 패널 및 시뮬레이션을 활용하여 봇이 어떻게 동작하는지 확인할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: demo_n_test_panel.html
folder: danbeeDoc
previous: {
    title: 대시보드,
    url: dashboard.html
}
next: {
    title: 챗봇 채널 연계 설정,
    url: channel_connection_settings.html
}
---

## 테스트 패널

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도추론(Intent)]/[단어추출(Entity)] & [대화흐름(CHATFLOW)] > [대화흐름 목록(대화흐름 List)] 우측" type="default" %}

danbee.Ai에서는 지금까지 등록한 정보가 시스템에서 어떻게 인식되는지 테스트할 수 있도록 테스트 패널을 제공하고 있습니다. 테스트 패널은 총 2가지 종류가 제공됩니다.

- [대화의도 테스트 패널](demo_n_test_panel.html#nlu-intent-테스트-패널)
- [대화흐름 테스트 패널](demo_n_test_panel.html#chatflow-테스트-패널)

### 대화의도 테스트 패널

대화의도 테스트 패널에서는 입력 받은 문장이 어떻게 분석되어 어떤 Intent로 분류되는 지를 확인할 수 있습니다. 또한 잘못된 Intent로 분류될 때 해당 문장을 원하는 Intent로 등록하는 등의 편의 기능을 제공하고 있습니다.

#### Intent

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel01.png"  caption="대화의도 테스트 패널 - 대화의도 영역" %}

**대화의도 영역**은 입력 문장이 분류된 대표 Intent, 그리고 분류된 대표 대화의도의 파라미터 정보를 보여줍니다. 만약 분류된 Intent가 적절하지 않게 여겨지면 분류 Intent를 변경할 수 있습니다. 대화의도 우측 표시된 버튼을 누르면 등록된 대화의도 목록이 나옵니다. 여기서 분류되어지길 원하는 Intent를 선택하면 해당 대화의도의 상세 화면으로 이동하며 입력 문장이 해당 대화의도에 들어갑니다. 다만 다시 한 번 더 확인을 권장하므로 자동 저장은 되지 않습니다. 

#### 대화의도 Candidates

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel02.png"  caption="대화의도 테스트 패널 - 대화의도 Candidates 영역" %}

앞서 [기본 답변 설정](settings_personality)에서 설명한 것과 같이 입력 문장은 여러개의 Intent로 파악될 수 있습니다. 그렇기 때문에 **대화의도 Candidates 영역**에서는 입력 문장이 분류될 수 있는 모든 Intent를 보여줍니다. 또한 하나의 Intent로 파악되더라도 해당 Intent로 파악된 매칭률을 확인할 수 있습니다.<br/>

대화의도 Candidates 영역 우측에 보면 [+] 버튼이 존재합니다. 해당 버튼을 누를 시 테스트로 입력한 문장이 자동으로 해당 인텐트에 들어가게 됩니다.<br/>

또한 대화의도 Candidates의 헤더를 클릭하면 파악된 Intent를 Intent명과 버튼명 2가지 모드로 확인할 수 있습니다.<br/>

이외에도 대화의도 테서트 패널에서는 입력 문장에 대한 추가적인 정보를 확인할 수 있습니다.

#### SHOW JSON 

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel03.png"  caption="대화의도 테스트 패널 - SHOW JSON" %}

먼저 입력 문장에 대해 판별한 정보가 어떤 형태로 되돌아오는지 확인할 수 있습니다. 대화의도 테스트 패널 최하단 [SHOW JSON] 버튼을 누르면 JSON 형태의 정보를 볼 수 있는 팝업이 뜹니다.

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel03_json_popup.png"  caption="대화의도 테스트 패널 - JSON 팝업" %}

해당 팝업에서는 필요에 따라 사용할 수 있도록 복사 기능을 제공하고 있습니다. 복사를 누르면 해당 정보가 JSON String 형태로 복사됩니다.

#### TEXT ANALYTICS

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel04.png"  caption="대화의도 테스트 패널 - TEXT ANALYTICS" %}

마지막으로 입력 문장이 어떻게 분석되는지 확인할 수 있습니다. 대화의도 테스트 패널 최하단 [TEXT ANALYTICS] 버튼을 누르면 분석 결과를 볼 있는 팝업이 뜹니다.

{% include image.html file="test_panel_n_demo/NLU_intent_test_panel04_text_popup.png"  caption="대화의도 테스트 패널 - TEXT ANALYTICS 팝업" %}

### 대화흐름 테스트 패널

대화흐름 테스트 패널에서는 현재 만들어진 Chatflow가 제대로 동작하는지 테스트할 수 있습니다. 

{% include image.html file="test_panel_n_demo/chatflow_testpanel_01.png"  caption="대화흐름 테스트 패널 - 구성" %}

대화흐름 테스트 패널 상단에는 모드 전환 버튼과 초기화 버튼이 존재합니다.

- **초기화 버튼** : 대화 내용을 초기화 시킵니다. 챗봇을 변경하거나 로그아웃하시면 자동으로 대화가 초기화되지만 그외의 경우에는 모든 대화내용이 유지됩니다. 대화 내용이 길어지면 초기화 시키는 것을 권장합니다.
- **모드 전환 버튼** : 테스트의 결과를 크게 일반 모드와 디버그 모드, 총 2가지 모드로 확인할 수 있습니다. 

#### 일반 모드

{% include image.html file="test_panel_n_demo/chatflow_testpanel_02.png"  caption="대화흐름 테스트 패널 - 일반모드" %}

일반 모드에서는 실제로 챗봇이 내뱉는 답변을 확인할 수 있습니다. 챗봇의 답변을 클릭하면 하단에 답변이 어떤 노드를 통하여 뱉여진 답변인지 확인할 수 있습니다. 대화흐름 테스트 패널 하단에 노출되는 정보는 다음과 같습니다.

| 구분 | 설명 |
|------|------|
| 노드명 | 마지막 답변 또는 클릭된 노드의 이름을 보여줍니다. |
| 노드ID | 마지막 답변 또는 클릭된 노드의 ID를 보여줍니다. |
| 요청 파라메터 |  마지막 답변 또는 클릭된 노드에서 정보를 받고자하는 파라미터를 보여줍니다. |
{: .table .table-striped}

우측 **[챗플로우 상세]** 버튼을 클릭하면 해당 노드가 존재하는 Chatflow의 상세 화면으로 이동합니다.

#### 디버그 모드

디버그 모드는 Chatflow의 정확성이나 논리적인 오류(버그)를 찾아내는데 용이한 모드입니다. 해당 모드에서는 입력한 말에 대하여 어떤 노드를 타서 무슨 이유로 해당 답변이 나왔는지 전체 과정을 확인할 수 있습니다.

{% include image.html file="test_panel_n_demo/chatflow_testpanel_03.png"  caption="대화흐름 테스트 패널 - 디버그 모드" %}

먼저 각 노드 별로 다음과 같은 추가 정보를 확인 수 있습니다.

| 노드 종류 | 추가 정보 |
|------|------|
| Listen | 실행되는 대화흐름 명을 보여줍니다. |
| Speak | 해당 메세지가 어떤 조건에 의해 발생했는지 보여줍니다. |
| Slot | 무조건 물어보기 선택 여부 및 받은 파라미터 값을 보여줍니다. |
| Split | 어떤 조건이 선택되었는지 보여줍니다. |
| Carousel | 답변 받기를 선택했다면 무조건 물어보기 선택 여부 및 받은 파라미터 값을 보여줍니다. |
| Api | API명 및 URL을 보여줍니다. |
| Function | Function 노드 내부에서 값이 변경된 파라미터를 보여줍니다. |
{: .table .table-striped}

{% include image.html file="test_panel_n_demo/chatflow_testpanel_04.png"  caption="대화흐름 테스트 패널 - 파라미터 값 확인" %}

각 답변을 클릭하면 **[?]**모양의 버튼이 뜨는 것을 확인할 수 있습니다. **[?]버튼**을 클릭하면 해당 노드에 들어왔을때 값이 존재하는 파라미터의 정보를 확인할 수 있습니다. 해당 노드에 들어왔을때 값이 수정된 파라미터가 있다면 표시가 되는 것 또한 확인할 수 있습니다.


{% include image.html file="test_panel_n_demo/chatflow_testpanel_05.png"  caption="대화흐름 테스트 패널 - 기본 설정 답변 확인" %}

직접 만든 대화흐름 이외에 기본 설정에서 세팅한 정보에 따라 출력되는 답변에 대한 추가적인 정보 역시 쉽게 확인할 수 있습니다.

| 기본 설정 답변 종류| 추가 정보 |
|------|------|
| Reconfirm | 추론 정확도 및 현재 설정되어 있는 Reconfirm 답변 범위를 보여줍니다. |
| Default Fallback | 해당 메세지가 발생한 각종 이유를 확인할 수 있습니다. |
{: .table .table-striped}

특히 Default Fallback 메세지가 노출되는 이유에 대하여 자세하게 확인할 수 있습니다.<br/>

{% include image.html file="test_panel_n_demo/chatflow_testpanel_06.png"  caption="대화흐름 테스트 패널 - Default Fallback Case" %}

- **CASE 01** : 추론 정확도가 낮습니다.

 [기본 설정]에서 설정한 Reconfirm 임계값보다 낮은 정확도로 찾을 경우 발생합니다. 붉은색 디버깅 메세지를 클릭하면 어떤 대화의도 몇 퍼센트의 정확도로 추론하였는지, 되묻기 임계값이 얼마인지 확인할 수 있습니다.
 <br/><br/>
- **CASE 02** : 채널 Fallback 설정된 대화의도 입니다.

 찾은 Intent가 Fallback 설정이 체크된 Intent일 경우 발생합니다. 디버깅 메세지 클릭 시 추론한 대화의도에 대한 정보를 얻을 수 있습니다.

{% include image.html file="test_panel_n_demo/chatflow_testpanel_06_01.png"  caption="채널 Fallback 설정 확인" %} 

 대화의도 목록에서 실제로 추론된 Intent가 채널 Fallback 설정이 되어 있음을 확인할 수 있습니다.
 <br/><br/>
- **CASE 03** : 대화의도에 연결된 대화흐름을 찾지 못했습니다.

 Intent는 찾았지만 해당 대화의도에 연결된 Chatflow가 없을 경우 발생합니다. 디버깅 메세지 클릭 시 추론한 대화의도에 대한 정보를 얻을 수 있습니다. 
 
 {% include image.html file="test_panel_n_demo/chatflow_testpanel_06_02.png"  caption="연결 대화흐름 확인" %} 
 
 추론된 Intent를 찾아 들어가면 실제로 연결된 Chatflow가 없음을 확인할 수 있습니다.<br/><br/>
예시 이외에도 다양한 CASE에 대하여 Default Fallback 발생 원인 파악에 용이한 정보를 제공하고 있습니다.<br/>

이와 같이 테스트 패널을 잘 활용한다면 보다 쉽게 자연스러운 대화를 만들 수 있을 것입니다.<br/>

{% include note.html content="테스트 패널은 필요에 따라 언제는지 접고 필 수 있습니다." %}

{% include image.html file="test_panel_n_demo/chatflow_testpanel_07.png"  caption="테스트 패널 여닫기" %} 
<!-- 
## 시뮬레이션
{% include callout.html content="화면 위치 : [시뮬레이션(Simulation)]" type="default" %}

{% include image.html file="test_panel_n_demo/DEMO.png"  caption="시뮬레이션" %}

시뮬레이션 화면에서는 웰컴 메세지부터 시작하여 실제로 챗봇이 어떻게 대답하는지 확인하실 수 있습니다. -->


{% include bottom.html %}
