---
title: 버튼식 대화흐름 
tags: [chatflow, tree]
keywords: Basic Conversation
summary: ARS와 같이 하위메뉴가 연속되는 버튼식 대화흐름을 손쉽게 만들 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: chatflow_tree.html
folder: danbeeDoc
previous: {
    title: 대화흐름, 
    url: chatflow.html
}
next: {
    title: 엔티티,
    url: entity.html
}
---

{% include callout.html content="화면 위치 : 챗봇 제작 > 대화흐름" type="default" %}


## 버튼식 대화흐름
단비에서는 엑셀 템플릿을 이용하여 간단하게 버튼식 챗봇을 만드실 수 있습니다. 퀵리플라이 형태로 하위메뉴가 노출됩니다.

{% include image.html file="chatflow/chatflow-tree01.png"  caption="버튼식 대화흐름 채팅창" %}
{% include image.html file="chatflow/chatflow-tree02.png"  caption="버튼식 대화흐름 템플릿" %}

### 버튼식 흐름 만드는 방법
1. [챗봇 > 대화흐름] 메뉴에 들어갑니다.
2. [버튼식 흐름 생성] 버튼을 클릭합니다.
3. 버튼식 흐름의 시작 메세지를 채웁니다. 이미지를 포함하고 싶다면 이미지 URL을 추가로 입력합니다.
4. [예시 채우기 버튼]을 눌러 작성양식을 확인하고 삭제합니다.
5. 1depth부터 5depth까지 입력하고 메세지 또는 호출값을 입력합니다.
6. 상위 depth를 마저 채워넣습니다.
7. [저장]을 눌러 값을 누락되거나 중복된 값을 확인합니다.
8. 직접입력은 웹화면에서 제공되는 스프레드 시트에 직접 입력하는 방식이며, 다른 스프레드시트 파일에서 여러 셀을 복사/붙여넣기를 할 수 있습니다.

### 버튼식 흐름 템플릿

{% include image.html file="chatflow/chatflow-tree03.png"  caption="버튼식 흐름 작성예시" %}

각 템플릿 열에 대한 정보와 작성법을 설명합니다. 1~5depth만 채우고 마지막 depth에 메세지 또는 호출값을 넣으면 기본형 버튼식 챗봇이 완성됩니다.

<table class="table table-striped">
    <tr>
        <th>ID(필수)</th>
        <td>템플릿에서 해당하는 행의 답변을 불러올때 사용합니다. ID는 자유롭게 설정하실 수 있습니다. 호출값에 넣을때는 예시대로 채워주시면 됩니다.예시) 🚩IT05D033 or #네비_IT05D033</td>
    </tr>
    <tr>
        <th>Depth 채우기</th>
        <td>맨 아랫 Depth부터 작성 후, 윗 Depth를 순서대로 작성하세요.</td>
    </tr>
    <tr>
        <th>(선택)메세지 또는 호출값</th>
        <td>
            Depth 구조 작성을 완료했다면 선택적으로 메세지를 채웁니다. 메세지를 채우지 않으면 “아래 메뉴 중 선택해주세요.”라는 메세지가 기본으로 노출됩니다.<br/><br/>            
            <b style="font-size: 2px">●</b> 하위메뉴가 있을때 퀵 버튼과 함께 메세지를 내보냅니다.<br/>
            <b style="font-size: 2px">●</b> 하위메뉴가 없을때는 메세지만 단독으로 노출합니다.<br/>
            <b style="font-size: 2px">●</b> 호출값은 하위메뉴를 노출하지 않습니다. 마지막 depth에 채우는 것을 권장드립니다.<br/><br/>
            1. 메세지<br/>클릭했을때 나타나는 메세지를 작성합니다. 빈칸일때는 ‘아래 메뉴 중 선택해주세요.’라는 기본 메세지가 함께 노출됩니다.하위 메뉴가 없을때는 메세지만 단독으로 노출됩니다.<br/><br/>            
            2. 웹 링크<br/> 버튼웹 링크 호출코드와 주소를 입력합니다.(예시) 🔗https://www.naver.com or #링크_https://www.naver.com<br/><br/>
            3. 내부 App 링크<br/>내부 App 링크 호출코드와 주소를 입력합니다.(예시) 😀https://NMXWArA or #내부앱_https://NMXWArA<br/><br/>
            4. 외부 App 링크<br/>외부 App 링크 호출코드와 주소를 입력합니다.(예시)😎https://N347ccc or #외부앱_https://N347ccc<br/><br/>
            5. 전화걸기<br/>전화걸기 호출코드와 주소를 입력합니다.(예시)📞01012345678 or #전화_01012345678<br/><br/>
            6. FAQ+ 스킬 사용<br/>FAQ+ 호출코드와 ID를 입력합니다.(예시)🗣FAQ+답변1 or #간편답변_FAQ+답변1<br/><br/>
            7. 대화의도에 연결된 답변대화의도 호출코드와 ID를 입력합니다.(예시)👂대화의도ID or #대화의도_대화의도ID
        </td>
    </tr>
</table>

| 값 종류 | 메시지 | 🔗웹, 😀내부앱, 😎외부앱 링크 | 🗣FAQ+ ID | 🦻대화의도 ID | 
|---|---|---|---|---|
| 버튼 타입 | 퀵 | 선택지 | 선택지 | 선택지 |
| 하위메뉴 있을때 노출항목 | 메시지 하위메뉴 퀵버튼처음&이전 퀵버튼 | 버튼 클릭 시 링크 바로 열기 | 호출값 | 호출값 |
| 하위메뉴 없을때 노출항목 | 메세지처음&이전 퀵버튼 | 버튼 클릭 시 링크 바로 열기 | 호출값 | 호출값 |
| 비고 |  | 하위메뉴 노출 안됨 알림 | 하위메뉴 노출 안됨 알림 | 하위메뉴 노출 안됨 알림 |
{: .table .table-striped}



{% include bottom.html %}
