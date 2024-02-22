---
title: NAVER WORKS 
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 네이버웍스에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_naverworks.html
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
Naver WORKS 채널 연계 설정을 하려면 다음이 필요합니다.

* Naver Works 계정
* Naver Works 관리자 권한
* Naver Works Developers Console 계정
{% include note.html content="Developers Console에서 생성한 Bot을 Naver Works에서 팀이 사용합니다." %}


### 네이버웍스 봇 만들기
1. 브라우저에서 <span class="link">[Naver Works Developers Console](https://developers.worksmobile.com/){:target="_blank"}</span>에 접속하십시오

2. Console의 Bot 메뉴에서 Bot을 등록합니다.<figure><img class="docimage" src="images/channel/naverworks/naverworks_add_chatbot.png" alt="naver works add chatbot" style="max-width: 800px"></figure>
  * Bot 이름 : 챗봇 이름
  * Bot 설명 : 챗봇 설명
  * Bot ID : Bot 등록 완료 시 자동으로 발행됩니다. (단비연결 시 사용)
  * API Interface : 2.0
  * Callback URL : 우선 Off ( 단비연결 후 설정해야함 )
  * 담당자 : 챗봇 관리자
 
### 네이버웍스 API 연결 앱 생성
1. Console의 API 2.0 메뉴에서 앱을 추가합니다.<figure><img class="docimage" src="images/channel/naverworks/naverworks_add_app.png" alt="naver works add app" style="max-width: 800px"></figure>
   * Client ID : 클라이언트(앱) 아이디
   * Client Secret : 클라이언트(앱) 비밀
   * OAuth Scopes : bot, bot.message, bot.read, user.profile.read 를 선택합니다.

2. 생성된 앱의 Service Account와 Private Key를 발급합니다.<figure><img class="docimage" src="images/channel/naverworks/naverworks_create_key.png" alt="naver works create key" style="max-width: 800px"></figure>
   * Service Account : "serviceaccount"로 끝남
   * Private Key : 발행 후 안에 내용을 복사하여 사용

3. 해당 정보를 복사한 후 단비Ai 채널 연결 정보를 설정한다.
   * Client ID : 클라이언트(앱) 아이디
   * Client Secret : 클라이언트(앱) 비밀
   * Service Account : "serviceaccount"로 끝남
   * Private Key : 발행 후 안에 내용을 복사하여 사용

### 단비Ai 채널 연결 설정
1. [챗봇 만들기] > [챗봇 배포] > [메신저 연결] 메뉴로 이동 하십시오.
2. NAVER WORKS 타일 우측 상단에 설정 아이콘을 클릭하십시오.
3. 다음 필드에 관련 값을 입력하십시오.<figure><img class="docimage" src="images/channel/naverworks/naverworks_danbee_setting.png" alt="danbee naver works channel setting" style="max-width: 800px"></figure>
  * Bot ID : Naver Works Developers Console에서 생성한 Bot ID
  * Client ID : Naver Works Developers Console에서 생성한 Client ID
  * Client Secret : Naver Works Developers Console에서 생성한 Client Secret
  * Service Account  : Naver Works Developers Console에서 생성한 Service Account
  * Private Key : Naver Works Developers Console에서 생성한 Private Key ( 파일 내용 복사 )
  
4. Webhook URL 복사하십시오.
5. 연결 버튼을 클릭하십시오.

### 네이버웍스 봇 Callback URL 설정만들기
1. 브라우저에서 <span class="link">[Naver Works Developers Console](https://developers.worksmobile.com/){:target="_blank"}</span>에 접속하십시오

2. Console의 Bot 메뉴에서 Bot을 선택한 후 수정하기 버튼을 클릭하여 설정페이지로 이동합니다.
3. Callback URL을 설정합니다.<figure><img class="docimage" src="images/channel/naverworks/naverworks_add_chatbot.png" alt="naver works add chatbot" style="max-width: 800px"></figure>
  * Callback URL : On 으로 변경 ( Text 필수 체크, 위치공유, 스티커, 사진은 추후 기능제공 예정 )
4. 저장버튼을 클릭하여 설정을 마무리합니다.


### 네이버웍스 서비스에 봇 추가
1. 브라우저에서 <span class="link">[Naver Works Admin](https://admin.worksmobile.com/){:target="_blank"}</span>에 접속하십시오
2. 상단의 서비스 메뉴를 클릭합니다.
3. 좌측의 Bot 메뉴를 클릭합니다.
4. 추가 버튼을 클릭하여 생성한 챗봇을 선택합니다.
5. Bot을 선택하여 공개설정을 공개로 변경합니다. 
6. 필요 시 사용 권한을 지정한 구성원으로 지정도 가능합니다.

### 네이버웍스 챗봇 테스트
챗봇을 테스트하려면 네이버웍스 메시지에서 Bot을 초대하여 메시지방을 생성한 후 사용이 가능합니다.<figure><img class="docimage" src="images/channel/naverworks/naverworks_chatbot_test.png" alt="naver works chatbot test" style="max-width: 800px"></figure>


### 네이버웍스 인증키 연동
1. [챗봇 만들기] > [챗봇 배포] > [메신저 연결] 메뉴로 이동 하십시오.
2. NAVER WORKS 2 타일 우측 상단에 설정 아이콘을 클릭하십시오.
3. 다음 필드에 관련 값을 입력하십시오.<figure><img class="docimage" src="images/channel/naverworks/naverworks_danbee_setting_auth.png" alt="danbee naver works channel setting auth" style="max-width: 800px"></figure>
  * Auth Header : 네이버웍스 인증정보를 가져오기 위한 헤더 정보 ( 인증정보를 조회할때 체크를 위한 값 )
4. 저장버튼을 클릭하여 설정을 마무리합니다.
5. Http Client를 활용하여 Auth Url을 호출(GET방식) 시 헤더(DANBEE-NAVERWORKS-AUTH)값에 설정된 정보를 포함하면 인증정보를 조회할 수 있습니다. 
6. Http Client를 활용하여 Auth Refesh Url을 호출(POST방식) 시 헤더(DANBEE-NAVERWORKS-AUTH)값에 설정된 정보를 포함하면 인증정보를 재생성 할 수 있습니다.

{% include bottom.html %}
