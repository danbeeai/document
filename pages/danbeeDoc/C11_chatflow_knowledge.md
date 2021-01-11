---
title: Knowledge 노드 
tags: [chatflow, advanced]
keywords: Basic Conversation
summary: 단비 지식라이브러리에서 조건에 맞는 값을 추출해 파라미터에 담는 지식 노드를 설명합니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_knowledge.html
folder: danbeeDoc
previous: {
    title: Carousel 노드,
    url: chatflow_carousel.html
}
next: {
    title: API 노드,
    url: chatflow_api.html
}
---

{% include callout.html content="화면 위치 : 챗봇 > 챗봇 제작 > 대화흐름" type="default" %}

## 개요

Knowledge 노드는 단비의 지식라이브러리에서 [Sheet지식](knowledge_sheet.html), [FAQ지식](knowledge_faq.html), [FAQ+지식](knowledge_faq2.html) 데이터를 불러담는데에 사용됩니다. 사용자에게 받은 파라미터의 값에 따라 행을 조회하고, 해당 행 중 특정 열의 값을 파라미터에 담을 수 있습니다.

{% include image.html file="chatflow/Chatflow_knowledge_canvas.png"  caption="Knowledge 노드" %}


## Sheet 행 조회(Read)

### 사용법

<ol>
    <li>
        <p>Knowledge 노드를 Slot>Knowledge>Speak 등과 연결하여 사용하시면 됩니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist1.png" />
    </li>
    <li>
        <p>Knowolege 노드를 더블클릭하여 패널을 엽니다.</p>
    </li>
    <li>
        <p>지식을 선택합니다. Sheet 지식 중에서 선택이 가능합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist3.png" />
    </li>
    <li>
        <p>조회할 행을 찾는 방법을 먼저 선택합니다.</p>
        <table class="table table-bordered">
            <thead>
                <tr class="header">
                    <th>행 번호로 찾기</th>
                    <th>행 키워드로 찾기</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>사용자에게 직접 행 번호값을 입력받아서 찾는 방법입니다.</td>
                    <td>사용자가 입력한 값이 들어있는 행을 찾는 방법입니다.</td>
                </tr>
            </tbody>
        </table>
    </li>
    <li>
        <p>조회한 행을 특정 파라미터에 담아두는 과정을 설정해둡니다. 사용자의 입력 값에 따라 나온 행 중 특정 열의 값을 해당 파라미터에 담도록 합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist5.png" />
    </li>
    <li>
        <p>이제 Speak, Carousel, Slot 노드 등에 해당 #{파라미터명}를 입력하시면 사용자의 요청 값에 따라 지식라이브러리를 조회하여 답변을 내보낼 수 있습니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist6.png" />
    </li>
</ol>

## sheet 행 업데이트(Update)

### 사용법
<ol>
    <li>
        <p>Knowledge 노드를 Slot>Knowledge>Speak 등과 연결하여 사용하시면 됩니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist1.png" />
    </li>
    <li>
        <p>Knowolege 노드를 더블클릭하여 패널을 엽니다.</p>
    </li>
    <li>
        <p>지식을 선택합니다. Sheet 지식 중에서 선택이 가능합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist3.png" />
    </li>
    <li>
        <p>행 업데이트 탭을 클릭하고 업데이트할 행을 찾는 방법을 선택합니다.</p>
    </li>
    <li>
        <p>업데이트할 행의 대체 값을 열별로 설정할 수 있습니다.</p>
    </li>
    <li>
        <p>또한 행 데이터 업데이트 처리 결과에 대한 값을 파라미터에 넣어 전달할 수 있습니다.</p>
    </li>
</ol>

## Sheet 행 삭제(Delete)

### 사용법
<ol>
    <li>
        <p>Knowledge 노드를 Slot>Knowledge>Speak 등과 연결하여 사용하시면 됩니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist1.png" />
    </li>
    <li>
        <p>Knowolege 노드를 더블클릭하여 패널을 엽니다.</p>
    </li>
    <li>
        <p>sheet 지식 타입을 선택하고 만든 지식을 선택합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist3.png" />
    </li>
    <li>
        <p>행 삭제 탭을 클릭하고 삭제될 행을 찾는 방법을 선택합니다.</p>
    </li>
    <li>
        <p>또한 행 삭제 처리 결과에 대한 값을 파라미터에 넣어 전달할 수 있습니다.</p>
    </li>
</ol>

## Sheet 행 추가(Create)

### 사용법
<ol>
    <li>
        <p>Knowledge 노드를 Slot>Knowledge>Speak 등과 연결하여 사용하시면 됩니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist1.png" />
    </li>
    <li>
        <p>Knowledge Node를 더블클릭하여 패널을 엽니다.</p>
    </li>
    <li>
        <p>sheet 지식 타입을 선택하고 만든 지식을 선택합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist3.png" />
    </li>
    <li>
        <p>행 추가 탭을 선택하고 맨 아래 추가될 행의 값을 열별로 세팅합니다.</p>        
    </li>
    <li>
        <p>또한 행 추가 처리 결과에 대한 값을 파라미터에 넣어 전달할 수 있습니다.</p>        
    </li>
</ol>

## FAQ/ FAQ+ 지식

### 사용법
<ol>
    <li>
        <p>Knowledge 노드를 Slot>Knowledge>Speak 등과 연결하여 사용하시면 됩니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist1.png" />
    </li>
    <li>
        <p>Knowolege 노드를 더블클릭하여 패널을 엽니다.</p>
    </li>
    <li>
        <p>FAQ 또는 FAQ+ 지식 타입을 선택하고 만든 지식을 선택합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist3_faq.png" />
    </li>
    <li>
        <p>사용자에게 받을 메세지 파라미터를 설정합니다.#{파라미터명}으로 특정 파라미터를 지정해주시거나 #{@받은메세지}로 바로 전에 남긴 메세지로 값을 지정해줄 수 있습니다.</p>        
        <img src="../../images/chatflow/Chatflow_knowledge_uselist7.png" />
    </li>
    <li>
        <p>받은 메세지의 지식 추론율별로 내보낼 메세지를 설정합니다.</p>
        <img src="../../images/chatflow/Chatflow_knowledge_uselist8.png" />
    </li>
</ol>


{% include bottom.html %}
