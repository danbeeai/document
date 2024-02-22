---
title: NAVER WORKS 1.0( 지원종료 )
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 네이버웍스에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_lineworks.html
folder: danbeeDoc
previous: {
    title: 라인,
    url: channel_line.html
}
next: {
    title: 마이크로소프트 팀즈(MS TEAMS),
    url: channel_teams.html
}
---
## 네이버웍스 채널 연결 
{% include callout.html content="화면 위치 : [챗봇 만들기] > [챗봇 배포] > [메신저 연결]" type="default" %}


### 네이버웍스 설정
NAVER WORKS 채널 연계 설정을 하려면 다음이 필요합니다. (NAVER WORKS에서 명칭변경이 적용되지 않은 부분이 있어 LINE WORKS로 표기합니다.)

* LINE WORKS 계정
* LINE WORKS 관리자 권한
* LINE WORKS Developers Console 계정
{% include note.html content="Developers Console에서 생성한 Bot을 LINE WORKS에서 팀이 사용합니다." %}


### 네이버웍스 봇 만들기
1. 브라우저에서 <span class="link">[LINE WORKS Developers Console](https://developers.worksmobile.com/){:target="_blank"}</span>에 접속하십시오

2. Console의 Bot 메뉴에서 Bot을 등록합니다.<figure><img class="docimage" src="images/channel/lineworks/lineworks_add_chatbot.png" alt="line works add chatbot" style="max-width: 800px"></figure>
  * Bot 이름 : 챗봇 이름
  * Bot 설명 : 챗봇 설명
  * Bot No : Bot 등록 완료 시 자동으로 발행됩니다. (단비연결 시 사용)
  * Callback URL : 우선 Off ( 단비연결 후 설정해야함 )
  * 담당자 : 챗봇 관리자
 
### 네이버웍스 API 연결 정보 생성
1. Console의 API 메뉴에서 필요한 API ID, Server API Consumer Key, Server List를 발급 또는 등록합니다.<figure><img class="docimage" src="images/channel/lineworks/lineworks_api_create.png" alt="line works api create" style="max-width: 800px"></figure>
  * API ID : API 연결 시 사용할 ID <figure><img class="docimage" src="images/channel/lineworks/lineworks_api_id.png" alt="line works api id create" style="max-width: 800px"></figure>
  * Server API Consumer Key : API 연결 시 사용할 Consumer Key ( 카테고리 : 메시지 Bot 전체 ) <figure><img class="docimage" src="images/channel/lineworks/lineworks_api_consumer_key.png" alt="line works api consumer key create" style="max-width: 800px"></figure>
  * Server List(고정 IP 방식) : API 연결 시 인증할 서버 IP 등록 ( 3.35.70.32, 3.35.109.86 두개 등록 ) <figure><img class="docimage" src="images/channel/lineworks/lineworks_api_server_ip.png" alt="line works api server ip create" style="max-width: 800px"></figure>
  * Server List(ID 등록 방식) : API 연결 시 인증할 서버 ID 등록 ( 추후 제공 ) <figure><img class="docimage" src="images/channel/lineworks/lineworks_api_server_id.png" alt="line works api server id create" style="max-width: 800px"></figure>
  
2. 해당 정보를 복사한 후 단비Ai 채널 연결 정보를 설정한다.


### 단비Ai 채널 연결 설정
1. [챗봇 만들기] > [챗봇 배포] > [메신저 연결] 메뉴로 이동 하십시오.
2. NAVER WORKS 타일 우측 상단에 설정 아이콘을 클릭하십시오.
3. 다음 필드에 관련 값을 입력하십시오.<figure><img class="docimage" src="images/channel/lineworks/lineworks_danbee_setting.png" alt="danbee line works channel setting" style="max-width: 800px"></figure>
  * Bot ID : LINE WORKS Developers Console에서 생성한 Bot No
  * API ID : LINE WORKS Developers Console에서 생성한 API ID
  * Consumer Key : LINE WORKS Developers Console에서 생성한 Server API Consumer Key
  * 인증구분 : SERVER IP ( SERVER ID는 추후 제공 )
  * 인증 : LINE WORKS Developers Console에서 생성한 Server List의 토큰정보 <br>( IP는 3.35.70.32, 3.35.109.86 두개 등록 )
  
4. Webhook URL 복사하십시오.
5. 연결 버튼을 클릭하십시오.

### 네이버웍스 봇 Callback URL 설정만들기
1. 브라우저에서 <span class="link">[LINE WORKS Developers Console](https://developers.worksmobile.com/){:target="_blank"}</span>에 접속하십시오

2. Console의 Bot 메뉴에서 Bot을 선택한 후 수정하기 버튼을 클릭하여 설정페이지로 이동합니다.
3. Callback URL을 설정합니다.<figure><img class="docimage" src="images/channel/lineworks/lineworks_edit_chatbot_callback.png" alt="line works add chatbot" style="max-width: 800px"></figure>
  * Callback URL : On 으로 변경 ( Text 필수 체크, 위치공유, 스티커, 사진은 추후 기능제공 예정 )
4. 저장버튼을 클릭하여 설정을 마무리한다.


### 네이버웍스 서비스에 봇 추가
1. 브라우저에서 <span class="link">[LINE WORKS Admin](https://admin.worksmobile.com/){:target="_blank"}</span>에 접속하십시오
2. 상단의 서비스 메뉴를 클릭합니다.
3. 좌측의 Bot 메뉴를 클릭합니다.
4. 추가 버튼을 클릭하여 생성한 챗봇을 선택합니다.
5. Bot을 선택하여 공개설정을 공개로 변경합니다. 
6. 필요 시 사용 권한을 지정한 구성원으로 지정도 가능합니다.

### 네이버웍스 챗봇 테스트
챗봇을 테스트하려면 라인웍스 메시지에서 Bot을 초대하여 메시지방을 생성한 후 사용이 가능합니다.<figure><img class="docimage" src="images/channel/lineworks/lineworks_chatbot_test.png" alt="line works chatbot test" style="max-width: 800px"></figure>



{% include bottom.html %}
