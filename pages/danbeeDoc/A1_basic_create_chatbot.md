---
title: 간단한 챗봇 만들어보기 
tags: [chatbot]
keywords: 챗봇 생성, 챗봇 만들기
summary: 대화 주체의 단위인 챗봇을 생성하는 법을 알아봅니다.
sidebar: danbee_doc_sidebar
permalink: basic_create_chatbot.html
folder: danbeeDoc
previous: {
    title: 챗봇 위자드로 5분만에 챗봇 만들기,
    url: chatbot_wizard.html
}
next: {
    title: 업데이트 로그,
    url: update_log.html
}
---

## 챗봇 생성하기

챗봇은 danbee.Ai에서 대화를 하는 주체의 단위입니다. 챗봇단위로 사용자가 발화하는 내용을 이해하고, 답변하는 것이 달라집니다.
온라인 게임에서 캐릭터 하나 만든다고 생각하고 쉽게 시작할 수 있습니다.

### 챗봇 생성

최초 로그인을 하게 되면, 아래와 같이 챗봇이 하나도 없는 상태입니다.
이 곳에서 단비에서 제공하는 샘플챗봇을 가져오거나, 사용자가 직접 챗봇을 생성할 수도 있습니다.

{% include image.html file="chatbot_create\no_chatbot_01.png"  caption="챗봇이 없는 상태" %}

1) 해당 영역에서는 단비에서 제공하는 샘플챗봇들 중 **가장 인기있는 샘플챗봇**들이 보여집니다. 

{% include image.html file="chatbot_create\no_chatbot_02.png"  caption="인기 샘플챗봇" %}
2) 인기샘플챗봇영역 하단에 위치한 **"샘플 더보기"**을 클릭하여, 단비에서 제공하는 모든 샘플챗봇들을 볼 수 있습니다.

{% include image.html file="chatbot_create\sample_chatbot_03.png"  caption="모든 샘플챗봇" %}
3) 샘플챗봇을 가져오지 않고, 챗봇을 바닥부터 직접 만들고 싶을때에는 화면의 하단 '처음부터 만들기'영역의 **"Chatbot 생성"**을 클릭하여 챗봇을 생성할 수 있는 화면으로 이동할 수 있습니다.
이 곳에서 챗봇의 이름과 챗봇을 설명하는 텍스트를 입력하여 간단히 챗봇을 생성하고, 곧 바로 바닥부터 챗봇 빌드를 시작할 수 있습니다.  


{% include image.html file="chatbot_create\chatbot_create_04.png"  caption="챗봇 직접생성" %}

4) 최초로 챗봇을 생성하게되면 화면과 같은 단비 플랫폼의 **'기능 알림 튜토리얼'**이 진행됩니다. 
튜토리얼에서는 **테스트패널의 사용법**부터, **추가 챗봇생성**, **전체적인 메뉴안내**까지 챗봇을 만드는데 필요한 기본적인 기능들을 간략히 설명합니다.  

{% include image.html file="chatbot_create\tutorial_05.png"  caption="기능알림 튜토리얼 진행화면" %}

5) 튜토리얼이 끝나면 생성된 챗봇을 확인할 수 있으며, **챗봇별로 관리되는 데이터**가 보입니다.
{% include image.html file="chatbot_create\chatbot_created_06.png"  caption="챗봇이 생성된 모습" %}

 - [의도](intent.html) : 챗봇이 추론할 수 있는 **의도(Intent)**의 개수를 나타냅니다.
 - [핵심단어](entity.html): 챗봇이 추출할 수 있는 **핵심단어(Entity)**의 개수를 나타냅니다.
 - [대화흐름](chatflow.html) : 답변 가능하도록 설정된 **챗플로우**의 개수를 나타냅니다.
 - [의도분류 이력조회](log.html) 사람들이 어떤 말을 걸었는지, Chatbot은 어떻게 이해했는지 확인해보세요. Default Fallback으로 처리된 대화 내용을 다른 Intent로 업데이트하면 Chatbot의 이해도가 더욱 향상됩니다.
 - [대화흐름 이력조회](log.html) 사람들이 어떤 말을 걸었는지, Chatbot은 어떻게 이해했는지 확인할 수 있습니다.

Intents, Entities, Chatflows를 클릭하면, 챗봇을 설정할 수 있는 각각의 메뉴로 이동합니다.

**"설정"** 버튼을 클릭하여 챗봇의 기본정보를 변경하거나 삭제할 수 있습니다.<br/>
**"복제"** 버튼을 클릭하여 해당 챗봇을 복사한 새로운 챗봇이 생성됩니다.

### 챗봇 기본정보 변경
챗봇명 우측의 ***"설정"*** 버튼을 클릭하면, 아래와 같은 화면이 나타납니다.
{% include image.html file="chatbot_create\04_chatbot_edit.PNG"  caption="챗봇 기본정보 변경 화면" %}
***"사진변경"*** 버튼을 눌러 프로필사진을 변경하거나 설명을 수정하고 우측 상단의 ***"저장"*** 버튼을 클릭하면 변경사항이 반영됩니다.


### 챗봇 삭제
챗봇 설정 화면의 하단에 있는 ***"Chatbot 삭제"*** 기능은 매우 조심해야 하는 기능입니다. 등록되어 있는 모든 학습데이터와 대응되는 답변 시나리오가 삭제됩니다. ***매우 매우 조심하셔야 합니다!***


## 대화 서비스 만들기
우선 간단하게 인사를 하는 챗봇을 한번 만들어보겠습니다.
"안녕?" 이라고 입력하면 "안녕~" 이라고 대답하게 말이죠. 대화는 크게 2가지 단계로 나뉘어집니다.
"상대방의 의도를 인식하는 단계"와 "인식한 의도에 따라 답변하는 단계"입니다.

### 사용자의 의도를 포함한 표현을 등록하라!
의도를 인식하기 위해서는 의도 추론(Intent)메뉴에서 사용자의 의도가 담겨있는 다양한 표현을 등록해야 합니다.
좌측 내비게이션에서 아래 메뉴를 클릭합니다.

{% include callout.html content="화면 위치 : [자연어이해(NLU)] > [의도 추론(Intent)]" type="default" %}

Intent란 챗봇이 인식하는 사용자의 의도입니다. ***"대화의도 생성"*** 버튼을 클릭합니다.
챗봇이 인식할 인텐트명을 입력하고, 해당 인텐트로 해석될 수 있는 표현을 입력하고 엔터키를 누릅니다.
"만남 인사"로 해석될 수 있는 표현은, "안녕" "반가워" "방가방가" "하이" 등이 될 수 있겠네요.




{% include image.html file="chatbot_create\06_sample_sentence.gif"  caption="인텐트별 예문 등록" %}

예문을 등록하고 나서는 우측 상단의 "저장" 버튼을 클릭하여 저장합니다.
저장하고 나면, 바로 오른쪽 테스트 패널에서 테스트가 가능합니다.

{% include image.html file="chatbot_create\07_intent_test.gif"  caption="인텐트 분류 테스트" %}

"안녕" 이라고 테스트 해보면, 대화의도 Candidate에 "만남 인사"로 100% 신뢰도로 추론된다는 결과가 나옵니다.
예문에 "안녕"이라는 학습데이터가 100% 일치하기 때문입니다.

"안녕안녕" 이라고 테스트 해보면, 71.25% 정도의 신뢰도로 "만남 인사"인것 같다는 추론결과가 나옵니다.
danbee.Ai의 NLU엔진에서 유사한 표현으로 인식한 경우 입니다.

만남 인사로 해석될 수 있는 표현은 다양합니다. 다양한 예문을 등록할 수록 더 똑똑하게 의도를 분류해 낼 수 있습니다.

상대방의 의도를 파악할 수 있게 되었으니, 이제 답변을 만들어 보겠습니다!

### 의도에 맞는 대화흐름을 만들어 보자!
반갑게 인사하는 상대에게는 당연히 반갑게 인사로 대응을 해야 예의바른 챗봇이겠죠?
좌측 내비게이션에서 아래 메뉴를 클릭합니다.
{% include callout.html content="화면 위치 : [대화흐름 ] > [대화흐름 목록]" type="default" %}

메뉴를 클릭하면, 아래와 같은 화면이 나타납니다.

{% include image.html file="chatbot_create\08_chatflow_create.png"  caption="챗플로우 생성" %}
화면 중앙, 또는 우측상단에 있는 "대화흐름 생성" 버튼을 클릭합니다.

{% include image.html file="chatbot_create\09_chatflow_name.PNG"  caption="챗플로우 생성" %}
챗플로우의 이름은 자유롭게 설정이 가능하지만, Intent명과 동일하게 작성하는 것이 나중에 다시 찾을때 편리합니다.
"만남 인사"로 정하도록 하겠습니다.

생성된 "만남 인사"라는 챗플로우를 클릭하면, 캔버스 화면이 나타납니다.
만남인사로 인식되면, 답인사를 하는 간단한 흐름을 만들어 보겠습니다.
아래와 같이 "Listen노드"와 "Speak노드"를 클릭하고 양쪽을 선으로 연결합니다.

{% include image.html file="chatbot_create\10_listen_speak.gif"  caption="노드 생성 및 연결" %}

노드는 대화상에서의 단계를 의미합니다. Listen노드는 대화상대의 의도를 인식하는 단계이고, Speak노드는 챗봇이 말하는 단계입니다.
두 가지 노드가 가장 자주 사용되는 노드이며, 다른 노드들에 대한 설명은 <span class="link">[여기](/chatflow.html)</span> 에서 더 자세히 설명해 놓았습니다.
Listen노드를 더블클릭하여 대화흐름의 출발점이 되는 Intent를 정해줍니다.

{% include image.html file="chatbot_create\11_listen_setup.gif"  caption="Listen노드 설정" %}

인텐트가 설정되면, 추론을 위해 학습한 예문이 표시됩니다.

이번에는 답변에 해당하는 Speak노드를 더블클릭하여 답변을 입력해보겠습니다.
{% include image.html file="chatbot_create\12_speak_setup.gif"  caption="Speak노드 설정" %}

Listen노드와 Speak노드가 만들어졌다면, 우측 상단의 저장버튼을 클릭하면 대화모델 하나가 완성된 것입니다.

화면 우측의 대화흐름 테스트 패널에서 테스트를 해볼 수 있습니다.

{% include image.html file="chatbot_create\13_chatflow_test.gif"  caption="챗플로우 테스트" %}


### 다음으로 할 일

위에서 나온 챗봇관련 개념에 익숙해지셨고, 자신감이 생기셨다면! 지금 바로 챗봇을 만들러 GOGO!
<span class="link">[danbee.Ai 시작하기](https://danbee.ai/platform/#/loginPrivateStep)</span>


조금더 공부를 해보고 싶다면, 인텐트(의도)를 등록하는 것을 시작할 수 있겠습니다.


<span class="link">[의도관리](/intent.html)</span>

아니면 바로 메신저에 연결해 볼 수도 있습니다.

<span class="link">[챗봇 채널 연계 설정](/channel_connection_settings.html)</span>
