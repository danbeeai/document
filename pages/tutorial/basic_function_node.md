---
title: Function 노드 사용하기
keywords: Function 노드 사용하기
tags: [Function Node]
sidebar: tutorial_sidebar
permalink: basic_function_node.html
folder: tutorial
summary: Function Node의 개념을 이해할 수 있습니다.
next: {
    title: 간단한 챗봇 만들어보기,
    url: basic_function_node.html
}
---

## Function Node
대화흐름에서 사용하기 위해 만든 내부변수의 경우 Slot Node에서 사용자가 입력한 값이나 API Node 에서 받아온 값 그대로 밖에 사용할 수 없습니다. <br/>
하지만 대화를 하다보면 내부변수를 가공하여 사용해야 할 필요가 생길 때도 있습니다. <br/>
피자주문하는 시나리오에서 피자가격을 주는 외부시스템의 경우 가격을 정수값의 형태로 보내줍니다. <br/>
그러나 