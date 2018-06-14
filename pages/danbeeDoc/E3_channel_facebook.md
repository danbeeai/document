---
title: Facebook
tags: [channel]
keywords: Basic Conversation
summary: 간단한 설정으로 Facebook Messenger에 연결할 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_facebook.html
folder: danbeeDoc
previous: {
    title: Native App(API),
    url: channel_native_app.html
}
next: {
    title: 라인,
    url: channel_line.html
}
---

## Facebook 채널 연결 
 {% include callout.html content="화면 위치 : [설정(Preference)] > [대화채널(Channel)]" type="default" %}


### Facebook 설정
Facebook 채널 연계 설정을 하려면 다음이 필요합니다.

* Facebook 계정
* 챗봇을 추가 할 페이스북 페이지
{% include note.html content="사용자가 페이스북 페이지에 방문하여 메시지를 보내면 챗봇과 대화하게 됩니다." %}


### Facebook 앱 만들기
1. 브라우저에서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Facebook for developers](https://developers.facebook.com/){:target="_blank"}</span>에 접속하십시오.<figure><img class="docimage" src="images/channel/facebook/facebook_dev_homepage.png" alt="Facebook for developers" style="max-width: 800px"></figure>
2. Facebook 계정으로 로그인 후 우측 상단의 내앱 > ***새앱 추가***를 클릭합니다.
3. 표시이름과 연락처 이메일을 입력 후 앱ID를 만듭니다.<figure><img class="docimage" src="images/channel/facebook/facebook_dev_appadd.png" alt="Facebook App Add" style="max-width: 800px"></figure>
4. 제품중 Messenger의 버튼을 클릭 하여 설정 페이지로 이동한다.<figure><img class="docimage" src="images/channel/facebook/facebook_dev_messenger_setting.png" alt="Facebook Messenger Set" style="max-width: 800px"></figure>
5. 토큰 생성 영역의 페이지 선택을 클릭하여 챗봇을 추가할 페이스북 페이지를 선택합니다.<figure><img class="docimage" src="images/channel/facebook/facebook_dev_page_setting.png" alt="Facebook Page Set" style="max-width: 800px"></figure>
6. 생성된 페이지 액세스 토큰은 danbee.Ai 설정에 사용하므로 미리 기록해놓으십시오.

### danbee.Ai 채널 연결 설정
1. [고급설정(Advanced)] > [채널 연결(Connect of Channel)] 메뉴로 이동 하십시오.
2. Facebook 타일 우측 상단에 설정 아이콘을 클릭하십시오.
3. 다음 필드에 관련 값을 입력하십시오. 이전에 기록한 페이지 엑세스 토큰도 함께 입력하십시오.<figure><img class="docimage" src="images/channel/facebook/facebook_danbee_setting.png" alt="danbee facebook channel setting" style="max-width: 800px"></figure>
  * 콜백 URL : 채널 WEBHOOK URL ( 자동생성 )
  * 확인 토큰 : 채널 WEBHOOK 확인 토큰 - 사용자 임의 생성
  * 페이지 엑세스 토큰 : 채널 액세스 토큰 
4. 확인 토큰과 콜백 URL 복사하십시오. ( 확인토큰은 입력한 값을 함께 기록해놓으십시오 )
5. 연결 버튼을 클릭하십시오.
{% include note.html content="WEBHOOK URL은 자동생성 되므로 확인 토큰만 유지 관리하십시오." %}

### Facebook Webhook 설정 
1. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Facebook for developers](https://developers.facebook.com/){:target="_blank"}</span> 페이지로 돌아갑니다. 
2. Webhooks 영역의 Webhooks 설정 버튼을 클릭하여 설정을 합니다. 
3. 다음 필드에 관련 값을 입력하십시오. 입력 후 확인 및 저장버튼을 클릭합니다.<figure><img class="docimage" src="images/channel/facebook/facebook_channel_webhook_setting.png" alt="facebook channel url setting" style="max-width: 800px"></figure>
  * 콜백 URL : danbee.Ai에서 자동생성된 URL
  * 확인 토큰 : danbee.Ai에 입력한 확인 토큰 
  * 받아보기 필드 : messages, messaging_postbacks, messaging_option 체크 
4. 설정 페이지로 다시 들어오면 Webhooks가 "완료"상태 여야합니다. 그리고 이벤트를 받아볼 페이지를 선택 후 받아보기를 선택하십시오.<figure><img class="docimage" src="images/channel/facebook/facebook_channel_webhook_setting1.png" alt="facebook channel url setting" style="max-width: 800px"></figure>

### Facebook Messenger 테스트

앱 테스트는 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Facebook Messenger](https://www.messenger.com){:target="_blank"}</span>에서 진행할 수 있습니다. 연결한 페이지 이름을 검색하여 테스트하십시오.

{% include warning.html content="앱이 비공개일 경우 해당 앱에 역할이 부여된 계정만 해당 페이지를 검색할 수 있습니다." %}


### Facebook 앱 공개

모든 사람이 해당 챗봇을 사용할 수 있도록 만들기 위해서는 앱을 공개해야 합니다. 앱 공개를 위해서는 다음과 같은 과정이 선행되어야 합니다. 앱 공개를 위해서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Facebook for developers](https://developers.facebook.com/){:target="_blank"}</span> 페이지로 이동합니다.

1. 기본 설정 세팅<br/>
  : Facebook 앱 관리 페이지의 **[설정] - [기본설정]**에서 다음 정보를 반드시 입력해야 합니다.
  - 개인정보처리방침 URL
  - 앱아이콘 : Facebook Messenger에서 대화시 노출되는 프로필 사진으로 1024x1024 해상도의 이미지만 등록할 수 있습니다.
  - 카테고리 설정

2. 페이지 사용자 이름 설정<br/>
  : 챗봇 사용할 때 사용자가 채팅 할 챗봇 이름입니다. 챗봇 이름을 설정하려면 연결한 Facebook 페이지로 접속하여 프로필 사진과 제목 아래에있는 **페이지@사용자 이름 만들기** 링크를 클릭하십시오.

3. 메신저 사용을 위한 검수 사항 제출<br/>
  : 기본 설정 항목을 모두 입력하셨다면 메신저 앱 사용을 위한 검수 사항을 제출하여야 합니다.<br/>
  Facebook 앱 관리 페이지의 **[Messenger] - [설정]**에 들어가서 하단으로 내려보시면 [Messenger의 앱 검수] 블럭이 존재합니다. 해당 블럭에서 **pages_messaging** 우측 [제출에 추가] 버튼을 클릭하시면 해당 사항에 대하여 검수를 받으실 수 있습니다.

3. 앱 공개<br/>
  : [앱 검수]메뉴에서 앱 공개를 '예'로 변경합니다. 검수가 완료되면 모드 사용자가 해당 앱을 사용할 수 있습니다. 


## Facebook 고정메뉴
{% include callout.html content="화면 위치 : [고급설정(Advanced)] > [채널 연결(Connect of Channel)]" type="default" %}

danbee.Ai에서는 Facebook Messenger 하단 입력창 옆에 위치한 Facebook 고정메뉴 설정 기능을 제공하고 있습니다.

### Facebook 고정메뉴 설정

고정메뉴는 채널 연결시 뜨는 팝업 하단 사용자 고정 메뉴 설정 블락에서 설정하실 수 있습니다.

#### 메인 메뉴
**메인 메뉴**는 **최대 3개**까지 설정이 가능하나 **'시작하기'** 및 **'danbee.Ai로 만든 봇'** 메뉴는 변경할 수 없습니다.<br/>

{% include image.html file="channel/facebook/facebook_menu_setting_01.png" max-width="900" caption="Facebook 메인 메뉴 설정" %} 

메인 메뉴에서 설정 가능한 메뉴 종류는 선택지, Web Link, 챗플로우 호출, 서브메뉴가 존재합니다.

| 메뉴 옵션 | 설명 | 
|--------|-------|
| 선택지 | 입력값을 호출합니다. |
| Web Link | 팝업으로 호출할 Link 정보를 제공합니다. |
| Chatflow호출 | 다른 Chatflow를 호출합니다. |
| 서브메뉴 | 하위 메뉴를 설정합니다. |

#### 서브 메뉴

{% include image.html file="channel/facebook/facebook_menu_setting_02.png" max-width="900" caption="Facebook 서브 메뉴 설정" %} 

메뉴 옵션에서 서브메뉴를 선택 시 'Edit Submenu'를 클릭하면 하위 메뉴를 설정할 수 있습니다. 서브 메뉴는 최대 2레벨, 각 레벨당 최대 5개의 메뉴를 지원합니다. 1레벨 서브 메뉴는 메인 메뉴와 동일한 옵션을 제공하며 2레벨 서브 메뉴는 서브메뉴 옵션을 제외한 나머지 옵션을 지원합니다.<br/>

메뉴를 설정한 뒤 [연결]버튼을 누르면 해당 메뉴가 자동으로 Facebook Messanger에 세팅됩니다.

{% include image.html file="channel/facebook/facebook_menu_setting_03.png" max-width="900" caption="Facebook Messenger 고정 메뉴 확인" %}

{% include warning.html content="메뉴 적용 여부 확인 시 Facebook Messanger 대화창이 켜져있다면 나갔다 다시 접속해야 변경 사항을 확인할 수 있습니다." %}



