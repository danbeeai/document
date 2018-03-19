---
title: API 노드 사용하기
keywords: API 노드 사용하기
tags: [API Node]
sidebar: tutorial_sidebar
permalink: usingApiNode.html
folder: tutorial
next: {
    title: 간단한 챗봇 만들어보기,
    url: basic_create_chatbot.html
}
---

## API Node
단비에서 대화를 만들다 보면 외부에 있는 데이터를 가져와 대화에 넣어야 할 경우가 있습니다. 지금까지 만들었던 피자주문 시나리오를 예로들면 피자 가격을 피자 가격정보를 관리하던 기존 시스템에서 가져와 보여주는 것이 바람직 합니다. 단비의 Speak Node 나 Slot Node 에 피자가격을 직접 입력하여 사용하면 기존 시스템에서 가격이 변경 될 경우 가격을 여러번 수정해야하는 소요가 생깁니다.
또한 공공데이터 포탈과 같이 API 형태로 데이터를하는 곳에서 데이터를 가져와 대화흐름에 녹여 보고 싶을때가 있습니다. 이때 외부의 데이터를 만들고 있는 대화로 들고 오는 역할을 하는 것이 API Node 입니다.
이번 Step에서는 Api Node 를 추가하여 외부의 데이터를 단비의 대화흐름으로 가져와 대화에서 보여 주는 방법을 알아 보겠습니다.

1) 먼저 Chatflow 상단의 Api Node 를 클릭하여 추가해 주세요.

2) Carausel Node 와 Split Node 사이에 Api Node를 위치 시키고 앞뒤 노드와 연결해 주세요. 기존에 연결된 선의 경우 마우스로 선을 클릭하고 선이 붉은색으로 하이라이트된 후 키보드의 delete 키를 누르면 삭제됩니다.

3) Api Node를 더블 클릭하여 상세화면으로 이동해주세요. Api Node 의 경우