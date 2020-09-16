---
title: Sheet
tags: [nlu, advanced]
keywords: 지식 라이브러리, Knowledge Library, FAQ+, FAQ, 엑셀, 스프레드시트
summary: 단답형 대화컨텐츠를 엑셀형태로 쉽게 관리할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: knowledge_sheet.html
folder: danbeeDoc
previous: {
    title: FAQ,
    url: knowledge_faq.html
}
next: {
    title: API 관리,
    url: external_API_management.html
}
---

{% include callout.html content="위치 : 그룹 > 그룹 챗봇 > 지식 라이브러리" type="default" %}

## Sheet 타입의 지식
단비에서는 스프레드 시트와 같은 데이터 테이블을 제공합니다. Sheet 지식은 고객정보, 상품정보 등을 질문내용에 따라 알려줄때 사용됩니다. 고객이 물어본 답변에 따라 상품정보를 소개하거나 견적을 내주는데에 사용할 수 있습니다.

{% include image.html file="knowledge/sheet_01.png" alt="엑셀 템플릿" caption="(예시) 사용자에게 찾는 ‘상품명’을 묻고 ‘가격’를 답변으로 내보내 줄 수 있습니다." %}

### Sheet 지식 만드는 방법

1. [그룹 > 그룹 챗봇 > 지식 라이브러리] 메뉴에 들어갑니다.
2. [+지식 생성]버튼을 클릭합니다.
3. 지식 유형을 선택하는 화면에서 Sheet를 선택합니다.
4. 컨텐츠 관리에서 [직접 입력]하거나 [업로드]할 수 있습니다.
5. 직접입력은 웹화면에서 제공되는 스프레드 시트에 직접 입력하는 방식이며, 다른 스프레드시트 파일에서 여러 셀을 복사/붙여넣기를 할 수 있습니다.
6. 업로드는 엑셀파일(확장자 xls, xlsx)을 지원합니다.
7. 정보가 모두 등록되고 나면 [생성]을 클릭합니다.
8. 생성된 데이터는 언제든 수정이 가능합니다.

### Sheet 지식을 챗봇에 연결하는 방법
1. 챗봇 > 대화흐름 > 새 대화흐름 만들기 > Knowledge Node를 사용합니다. 
   자세한 설명은 [knowledge Node 설명](https://doc.danbee.ai/chatflow_knowledge.html)을 참조하세요.

{% include bottom.html %}
