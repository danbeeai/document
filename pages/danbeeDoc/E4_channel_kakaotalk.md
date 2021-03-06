---
title: 카카오톡 
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 카카오톡에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_kakaotalk.html
folder: danbeeDoc
previous: {
    title: 텔레그램,
    url: channel_telegram.html
}
next: {
    title: 네이버톡톡,
    url: channel_navertalk.html
}
---

{% include important.html content="<br/>카카오톡의 서비스 정책 변화로 인해, 카카오톡 챗봇 연동 서비스는<br/>11월30까지 등록된 스마트채팅 플러스친구 계정만 지원합니다.<br/>기존에 연동을 해놓은 챗봇은 2019년 12월 2일까지만 서비스 됩니다.<br/> [카카오톡 공지사항 확인하기](https://github.com/plusfriend/auto_reply){:target='_blank'} " %}


## KakaoTalk 채널 연결 
 {% include callout.html content="화면 위치 : [챗봇] > [챗봇 제작] > [채널 연결]" type="default" %}

## danbee.Ai 채널 연결 설정
1. [고급설정(Advanced)] > [채널 연결(Connect of Channel)] 메뉴로 이동 하십시오.
2. Kakao Talk 타일 우측 상단에 설정 아이콘을 클릭하십시오.<figure><img class="docimage" src="images/channel/kakao/kakao_danbee_setting.png" alt="카카오 셋팅" style="max-width: 800px"></figure>
3. 앱 URL 복사하십시오.
4. 카카오톡에서 처음시작되는 버튼명을 설정하십시오. ( 추후 변경할때 아래 API 테스트에서 테스트 후 저장해야 실제 반영됩니다. )
5. 연결 버튼을 클릭하십시오.

## KakaoTalk 설정
KakaoTalk 채널 연계 설정을 하려면 다음이 필요합니다.

* Kakao 계정
* KakaoTalk 플러스친구 
* 휴대 기기에 설치된 KakaoTalk 앱
{% include note.html content="계정 가입은 모바일 앱을 통해 완료됩니다." %}

## KakaoTalk 플러스 친구 만들기 
1. 브라우저에서 <span class="link">[카카오톡 플러스친구](https://center-pf.kakao.com/login){:target="_blank"}</span>에 접속하십시오.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_homepage.png" alt="카카오톡 플러스친구" style="max-width: 800px"></figure>
2. 플러스친구를 만들기 위해 카카오 계정으로 로그인을 합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_login.png" alt="카카오 로그인" style="max-width: 800px"></figure>
3. 플러스 친구 관리자 가입을 합니다. ( 휴대기기에 KakaoTalk앱에서 본인확인 절차 필요 )<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_adminsign.png" alt="플러스친구 관리자가입" style="max-width: 800px"></figure>
4. 플러스친구를 만듭니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_add1.png" alt="플러스친구 추가" style="max-width: 800px"></figure>
5. 플러스친구정보 입력<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_add2.png" alt="플러스친구 추가" style="max-width: 800px"></figure>
6. 플러스친구 개설 완료<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_add3.png" alt="플러스친구 추가" style="max-width: 800px"></figure>

## KakaoTalk 플러스 친구 공개설정
* 플러스친구 관리자센터에서 관리 > 상세설정 메뉴에서 공개설정을 설정합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_public.png" alt="플러스친구 공개설정" style="max-width: 800px"></figure>
## KakaoTalk 스마트채팅 앱 만들기 
1. 스마트채팅의 API형으로 앱을 등록합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_app1.png" alt="API형 추가" style="max-width: 800px"></figure>
2. API형으로 앱 정보 입력 <figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_app2.png" alt="API형 정보입력" style="max-width: 800px"></figure>
3. danbee.Ai 설정에서 복사한 앱 URL을 입력한 후 API 테스트를합니다. ( 설정한 시작 버튼명이 보입니다. 여기서 저장된 값이 카카오톡에 보여집니다. )
4. 개인정보 수집 및 이용에 동의, 전화번호 를 등록하여 알림설정을 한 후 API형을 저장합니다.<figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_apisetting.png" alt="API형 정보입력" style="max-width: 800px"></figure>
5. API형 시작하기 버튼을 눌러 서비스를 시작합니다. <figure><img class="docimage" src="images/channel/kakao/kakao_pfcenter_apistart.png" alt="API형 시작하기" style="max-width: 800px"></figure>

## KakaoTalk 앱 테스트
* 챗봇을 테스트하려면 KakaoTalk앱에서 플러스친구를 검색하여 테스트할수 있습니다.<figure><img class="docimage" src="images/channel/kakao/kakao_app_add_chatbot.png" alt="line app add chatbot" style="max-width: 800px"></figure>


{% include bottom.html %}
