---
title: 테스트 패널
tags: [simulation, nlu, chatflow]
keywords: Basic Conversation
summary: 챗봇이 어떻게 동작하는지 확인할 수 있는 테스트 패널 활용법입니다.
sidebar: danbee_doc_sidebar
permalink: demo_n_test_panel.html
folder: danbeeDoc
previous: {
    title: 지식 답변 관리,
    url: knowledge_answer_mgmt.html
}
next: {
    title: 단비 제공 API,
    url: predefined_api.html
}
---

## 테스트 패널

{% include image.html file="test_panel_n_demo/chatbot_1.png" caption="테스트 패널 위치" %}

테스트 패널을 통해 지금까지 등록한 내용을 테스트할 수 있습니다. 테스트 패널에는 2가지 탭이 있습니다.

(1) [챗봇 테스트](#챗봇-테스트-패널)  
(2) [대화 의도 테스트](#대화-의도-테스트-패널)

{% include image.html file="test_panel_n_demo/chatbot_2.png" caption="(좌) 챗봇 테스트/ (우) 대화 의도 테스트" %}

### 챗봇 테스트 패널

챗봇 테스트 패널에서는 현재 만들어진 대화흐름이 제대로 동작하는지 테스트할 수 있습니다.

상단에 세 개의 버튼이 존재합니다.

{% include image.html file="test_panel_n_demo/chatbot_3.png" caption="(좌) 웹에서 보기 / (중앙) 디버그 모드 / (우) 초기화" %}

- **웹에서 보기**: 클릭하시면 웹브라우저를 통해 실제 챗봇 채팅창이 실행됩니다.
- **디버그 모드**: 디버그(de-bug) 모드를 켜고 끌 수 있습니다.
- **초기화**: 대화 내용을 초기화 시킵니다. 챗봇을 변경하거나 로그아웃하시면 자동으로 대화가 초기화되지만 그외의 경우에는 모든 대화내용이 유지됩니다. 대화 내용이 길어지면 초기화 시키는 것을 권장합니다.

#### 디버그 모드

{% include image.html file="test_panel_n_demo/chatbot_4.png" caption="(좌) 일반 모드 / (우) 디버그 모드" %}

일반 모드일 때는 챗봇의 대화 흐름을 따라, 어떤 답변이 오가는지 사용량(cc: chat count) 감소 없이 확인할 수 있습니다. 

웹에서 보기를 통해 챗봇 구동을 확인하는 경우, 실사용 환경이기 때문에 비용이 발생합니다. 테스트 패널에서는 그럴 걱정 없이 검수할 수 있다는 이점이 있습니다.

일반 모드에서 답변된 말풍선을 클릭하면, 테스트 패널 하단에 정보가 나옵니다.

{% include image.html file="test_panel_n_demo/chatbot_5.png" caption="" %}

하단에 관련한 정보가 노출됩니다.

'취미'라는 대화의도와 연결된 말풍선입니다. 파란 밑줄이 그어져 있는 [대화 의도 바로가기]를 클릭하면 실제 메뉴로 즉시 이동할 수 있어 간편합니다.

이제 [디버그 모드] 버튼을 눌러 전환해보겠습니다.

{% include image.html file="test_panel_n_demo/chatbot_6.png" caption="일반 모드" %}

화면 인터페이스가 모눈종이 배경으로 전환되었습니다. 디버그 모드에 진입했음을 시각적으로 바로 알아챌 수 있습니다.

{% include image.html file="test_panel_n_demo/chatbot_7.png" caption="디버그 모드" %}

디버그모드에서는 대화흐름에서 어떤 논리적인 오류(버그)가 있는지 찾기 쉽습니다.

직접 만든 대화 흐름 이외에 기본 설정에서 세팅한 정보에 따라 출력되는 답변에 대한 추가적인 정보 역시 쉽게 확인할 수 있습니다.

| 기본 설정 답변 종류| 추가 정보 |
|------|------|
| Reconfirm | 추론 정확도 및 현재 설정되어 있는 Reconfirm 답변 범위를 보여줍니다. |
| Default Fallback | 해당 메세지가 발생한 각종 이유를 확인할 수 있습니다. |
{: .table .table-striped}

빨간색 글씨로 챗봇 메시지에 대한 가이드가 제시됩니다.

일반 모드에서는 추론 실패 메시지가 떴다는 사실만 확인할 수 있는데, 디버그모드를 켜고 보면 왜 추론에 실패했는지를 확인할 수 있습니다. 추론의 정확도가 낮아서일수도 있고, 다른 이유일 수도 있습니다.

이를 통해 챗봇을 수정할 때 도움을 받을 수 있습니다.

대화 의도 한가지만 넣어놓은 현재 예시용 챗봇으로는 이 모드의 위력을 실감할 수 없습니다. 다양한 노드를 활용한 챗봇의 화면을 가져오겠습니다.

{% include image.html file="test_panel_n_demo/chatbot_8.png" caption="(좌)일반모드 / (우) 디버그모드" %}

단비AI에 처음 가입하면 '이렇게 따라 만들어보세요'라고 제안하는 샘플챗봇입니다.

(좌)일반모드 / (우) 디버그모드 차이가 보이시나요?

일반 모드에서는 드러나지 않는 챗봇의 대화흐름을 보여주고 있습니다.

대화 말풍선만으로는 드러나지 않지만 디버그모드에서 입력한 말에 대해 어떤 노드를 타서 무슨 이유로 해당 답변이 나왔는지 확인할 수 있습니다.

먼저 각 노드 별로 다음과 같은 추가 정보를 확인 수 있습니다.

| 노드 종류 | 추가 정보 |
|------|------|
| Listen | 실행되는 대화 흐름 명을 보여줍니다. |
| Speak | 해당 메세지가 어떤 조건에 의해 발생했는지 보여줍니다. |
| Slot | 무조건 물어보기 선택 여부 및 받은 파라미터 값을 보여줍니다. |
| Split | 어떤 조건이 선택되었는지 보여줍니다. |
| Carousel | 답변 받기를 선택했다면 무조건 물어보기 선택 여부 및 받은 파라미터 값을 보여줍니다. |
| Api | API명 및 URL을 보여줍니다. |
| Function | Function 노드 내부에서 값이 변경된 파라미터를 보여줍니다. |
{: .table .table-striped}

현재 화면에서 드러나는 정보 두 가지가 보입니다. 

첫째, '슬롯노드'의 분기를 거쳐서 다음 단계로 이동하고 있다.  
둘째, '캐로셀 노드'에서 또다른 분기를 맞이했다. 입력을 기다리고 있다.

챗봇이 잘 동작하지 않을 때, 테스트 패널의 디버그 모드를 켜고 동작시켜보면 결함(bug)원인을 좀 더 쉽게 찾을 수 있다.

그리고 하나 더, 디버그모드의 가치는 복잡한 기능을 활용한 챗봇일수록 높아집니다. [API노드](chatflow_api.html)나 [Funtion노드](chatflow_function.html)같은 기능을 말합니다.

그러니 만든 챗봇이 생각대로 안 굴러갈 때는 꼭 디버그 모드를 활용하세요.

{% include image.html file="test_panel_n_demo/chatbot_9.png" caption="" %}

디버그모드를 켜고 보면, 노드마다 우측 상단에 노란 물음표가 있습니다. 클릭해보겠습니다.

{% include image.html file="test_panel_n_demo/chatbot_10.png" caption="" %}

클릭한 노드에 해당하는, 파라미터 값들을 확인할 수 있습니다. 챗봇의 상세한 데이터 내역을 확인할 수 있는 기능입니다.


### 대화 의도 테스트 패널

챗봇 이용자가 채팅창에 입력한 문장이 '어떤 대화의도로 분류되는지' 확인할 수 있습니다.

또한 명확한 대화의도로 분류되지 않는 문장일 경우, 테스트를 하며 바로바로 대화의도에 등록할 수 있는 편의 기능을 제공합니다.

{% include image.html file="test_panel_n_demo/nlu_1.png" caption="" %}

"취미가 뭐야?"라고 물어보면 "축구"라고 대답하는 챗봇에 "심심할 때 뭐해?"라고 물었습니다

핵심 키워드인 '취미', '여가시간' 등이 포함되어 있지 않기 때문에 같은 대화의도로 인식하고 있지 못합니다.

그러나 사람간의 대화라면 '취미'라는 단어가 질문에 없었어도 같은 의미의 질문으로 인식하여 대답할 수 있었을 것입니다.

그러므로 빨간 박스를 친 부분을 클릭하면 아래와 같은 화면이 나타납니다.

{% include image.html file="test_panel_n_demo/nlu_2.png" caption="" %}

대화의도가 여러개 등록되어 있는 챗봇이라면 [취미] 말고도 [특기], [최애]...등등 다양한 대화의도 목록이 나타날 것입니다.

예문을 추가하기 적절한 대화의도에 바로바로 등록할 수 있는 장치입니다.

[취미] 대화의도에 넣으려고 하고 있으므로 클릭해보겠습니다.

{% include image.html file="test_panel_n_demo/nlu_3.png" caption="" %}

예문 목록에 방금 테스트한 문장 "심심할 때 뭐해"가 추가되었습니다.

이때 자동 저장은 되지 않으므로, 작업을 마친 뒤에는 꼭 하단 [저장] 버튼을 눌러줘야 합니다.

저장을 마친 뒤, 대화의도 테스트 탭에 방금 저장한 문장의 핵심 키워드 **"심심할 때"**를 입력해보겠습니다.

{% include image.html file="test_panel_n_demo/nlu_4.png" caption="" %}

학습을 마쳤기 때문에, 33.93%의 확률로 '취미'라는 대화의도를 가르키고 있다는 결과가 나왔습니다.

100%로 만들려면 또 학습을 시켜주면 되는데요. 이번에는 우측 하단의 [+] 버튼을 클릭하는 경우를 살펴보겠습니다.

{% include image.html file="test_panel_n_demo/nlu_5.png" caption="" %}

버튼을 누르는 즉시 예문이 추가되며, 아까와 달리 [자동 저장]도 됩니다.

마지막으로, 테스트 결과의 헤더 부분을 클릭해보면

{% include image.html file="test_panel_n_demo/nlu_6.png" caption="" %}

현재 입력한 문장에 대해 파악한 결과를, '대화 의도'일 때와 '버튼명'일 때 두가지 모드로 확인하실 수 있습니다.

마지막으로 **[형태소 분석]**과 **[JSON 데이터 보기]**입니다.

#### 형태소 분석

{% include image.html file="test_panel_n_demo/nlu_7.png" caption="" %}

[형태소 분석 보기]를 클릭하면 아래와 같은 화면이 나타납니다.

{% include image.html file="test_panel_n_demo/nlu_8.png" caption="" %}

현재 입력해서 테스트 중인 문장 '심심할 때'를 국어문법에 의거하여 분석해주고 있습니다.

#### JSON 데이터 보기

{% include image.html file="test_panel_n_demo/nlu_9.png" caption="" %}

{% include image.html file="test_panel_n_demo/nlu_10.png" caption="" %}

클릭하면 JSON 형태의 정보를 제공합니다.

'제이슨'이라고 읽습니다. JavaScript Object Notation 의 앞글자를 딴 약자입니다.

챗봇 프로젝트 팀에 개발자 분이 있는 경우 참고하시면 되겠습니다.

{% include note.html content="필요에 따라 [복사] 버튼을 누르면, JSON String 형태로 복사됩니다." %}


{% include bottom.html %}
