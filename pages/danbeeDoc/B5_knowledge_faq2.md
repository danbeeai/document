---
title: FAQ+
tags: [nlu, advanced]
keywords: 지식 라이브러리, Knowledge Library, FAQ+, FAQ, 엑셀, 스프레드시트
summary: 단답형 대화컨텐츠를 엑셀형태로 쉽게 관리할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: knowledge_faq2.html
folder: danbeeDoc
previous: {
    title: 그룹이란,
    url: chatbot_list.html
}
next: {
    title: FAQ,
    url: knowledge_faq.html
}
---

{% include callout.html content="위치 : 그룹 관리 > 그룹 챗봇 > 지식 라이브러리" type="default" %}

## FAQ+ 타입의 지식
단비에서는 질문/답변을 쉽게 관리할 수 있는 기존 FAQ지식에서 업그레이드해, 답변을 좀 더 풍성하게 할 수 있도록 FAQ+(플러스)기능을 내놓았습니다. 샘플파일을 받아 해당하는 값을 채워넣고 업로드를 하시면 간단하게 FAQ+ 을 제작하실 수 있습니다.

{% include image.html file="knowledge/faqplus-chatbot.png" alt="답변 채팅창 화면" caption="답변 채팅창 화면" %}
{% include image.html file="knowledge/faqplus-excel.png" alt="엑셀 템플릿" caption="엑셀 템플릿" %}


### FAQ+ 지식 만드는 방법
1. [그룹 > 그룹 챗봇 > 지식 라이브러리] 메뉴에 들어갑니다.
2. [+지식 생성]버튼을 클릭합니다.
3. 지식 유형을 선택하는 화면에서 FAQ+를 선택합니다. 
4. 컨텐츠 관리에서 [직접 입력]하거나 [업로드]할 수 있습니다.
5. 직접입력은 웹화면에서 제공되는 스프레드 시트에 직접 입력하는 방식이며, 다른 스프레드시트 파일에서 여러 셀을 복사/붙여넣기를 할 수 있습니다.
6. 업로드는 엑셀파일(확장자 xls, xlsx)을 지원합니다.
7. 정보가 모두 등록되고 나면 [생성]을 클릭합니다.
8. 생성된 데이터는 언제든 수정이 가능합니다.

### FAQ+ 지식을 챗봇에 연결하는 방법
1. 연결하고자 하는 챗봇이 선택된 상태에서, [챗봇 > 고급기능 > 지식 답변 관리] 메뉴로 이동합니다.
2. 지식 답변 관리의 FAQ+유형탭에 지식 라이브러리 연결관리의 [사용안함] 버튼을 클릭하여 [사용함]으로 변환합니다.
3. [사용함]으로 활성화된 버튼 아래 [FAQ+지식을 선택해주세요]를 클릭합니다.
4. 앞서 FAQ+ 지식 만드는 방법을 통해 등록한 지식을 선택합니다.
5. [변경내용 저장]을 클릭하여 연결을 마칩니다.
6. 연결을 마치고 나면 [대화의도]로 추론되지 않은 경우, 지식 라이브러리의 FAQ+지식에 있는 정보에서 응답할 수 있는 정보를 확인하고 답변하게 됩니다.

## FAQ+ 템플릿
{% include image.html file="knowledge/faqplus-excel.png" alt="엑셀 템플릿" caption="엑셀 템플릿" %}
  
  
단비에서는 FAQ+ 챗봇을 쉽게 만들 수 있는 엑셀 템플릿을 제공합니다. 각각 열에 알맞은 값을 넣어주세요.
  
<table class="table table-bordered">
    <colgroup>
        <col width="15%" />
        <col width="85%" />
    </colgroup>
    <tr>
        <th>ID<span style="color:red">(필수)</span></th>
        <td>추후 지원예정<br>다른 지식에서 해당하는 열의 답변을 불러올때 쓰는 호출값입니다. 자유롭게 변경가능합니다.<br>(예시) ID가 간편답변1일 때 → 🗣답변01 or #간편답변_캐로셀1</td>
    </tr>
    <tr>
        <th>이미지 URL</th>
        <td>답변과 함께 이미지를 내보냅니다. URL 형태로만 넣을 수 있습니다.</td>
    </tr>
    <tr>
        <th>답변 액션</th>
        <td>답변과 함께 액션을 수행합니다. 액션 스크립트(Javascript)를 적어주세요.</td>
    </tr>
    <tr>
        <th>버튼 타입</th>
        <td>
            선택지로 형태로 버튼을 사용하려면 버튼타입에 📜 or #선택지_ 를 넣어주세요. 선택지 버튼 최대 갯수는 4개 추천합니다.<br>
            퀵리플라이 형태로 버튼을 사용하려면 버튼타입에 ⚡️ or #퀵_ 을 넣어주세요. 퀵리플라이 버튼 최대 갯수는 10개를 추천합니다.|
        </td>
    </tr>
    <tr>    
        <th>버튼 값</th>
        <td>
            ▶ 버튼값 작성법 <br><br>
            1. 웹 링크: 버튼웹 링크 호출코드와 주소를 입력합니다.(예시) 🔗https://www.naver.com or #링크_https://www.naver.com <br><br>
            2. 내부 App 링크: 내부 App 링크 호출코드와 주소를 입력합니다.(예시) 😀https://NMXWArA or #내부앱_https://NMXWArA <br><br>
            3. 외부 App 링크: 외부 App 링크 호출코드와 주소를 입력합니다.(예시)😎https://N347ccc or #외부앱_https://N347ccc <br><br>
            4. 전화걸기: 전화걸기 호출코드와 주소를 입력합니다.(예시)📞01012345678 or #전화_01012345678
        </td>
    </tr>
</table>


{% include bottom.html %}
