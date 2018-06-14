---
title: Telegram
tags: [channel]
keywords: Basic Conversation
summary: danbee.Ai의 Telegram 채널 연계 후 danbee.Ai의 자연어 이해(NLU)와 챗플로우 기능을 활용하여 Telegram 챗봇을 쉽게 만들 수 있습니다.
sidebar: danbee_doc_sidebar
permalink: channel_telegram.html
folder: danbeeDoc
previous: {
    title: 라인,
    url: channel_line.html
}
next: {
    title: 카카오톡,
    url: channel_kakaotalk.html
}
---

## Telegram 채널 연결 
 {% include callout.html content="화면 위치 : [설정(Preference)] > [대화채널(Channel)]" type="default" %}


### Telegram 설정
Telegram 채널 연계 설정을 하려면 다음이 필요합니다.

* Telegram 계정

### Telegram 봇 만들기
1. 브라우저에서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Telegram Web-version](https://web.telegram.org){:target="_blank"}</span>에 접속한 후 로그인 합니다.<figure><img class="docimage" src="images/channel/telegram/telegram_web_login.png" alt="telegram 웹 앱" style="max-width: 800px"></figure>
2. <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Telegram 봇 아버지](https://telegram.me/botfather){:target="_blank"}</span>로 이동하십시오.
3. 웹 인터페이스에서 시작 단추를 클릭 하거나 ***/start***를 입력하십시오.<figure><img class="docimage" src="images/channel/telegram/telegram_web_start.png" alt="telegram 봇 시작하기" style="max-width: 800px"></figure>
4. 봇을 생성하기 위해  ***/newbot***을 입력하십시오.
5. 봇이름을 입력합니다. 봇이름은 bot로 끝나야 합니다.(예:Namebot)
6. BotFather(봇 아버지)가 생성해준 액세스 토큰을 기록해 놓습니다.<figure><img class="docimage" src="images/channel/telegram/telegram_web_newbot.png" alt="telegram 봇 만들기" style="max-width: 800px"></figure>

### danbee.Ai 채널 연결 설정
1. [고급설정(Advanced)] > [채널 연결(Connect of Channel)] 메뉴로 이동 하십시오.
2. Telegram 타일 우측 상단에 설정 아이콘을 클릭하십시오.
3. 다음 필드에 관련 값을 입력하십시오.<figure><img class="docimage" src="images/channel/telegram/telegram_danbee_setting.png" alt="danbee line channel setting" style="max-width: 800px"></figure>
  * 텔레그램 엑세스 토큰 : BotFather 가 생성해준 액세스 토큰
5. 연결 버튼을 클릭하십시오.

### Telegram 봇 테스트
1. 브라우저에서 <span style="color:#f69023;"><i class="fa fa-external-link-square" aria-hidden="true" style="margin: 0px 5px"></i>[Telegram Web-version](https://web.telegram.org){:target="_blank"}</span>에 접속한 후 로그인 합니다.
2. 생성한 봇 이름으로 검색 후 /start를 입력하여 챗봇과 대화를 시작합니다.<figure><img class="docimage" src="images/channel/telegram/telegram_app_add_chatbot.png" alt="line app add chatbot" style="max-width: 800px"></figure>
3. 또는 https://web.telegram.org/#/im?p=@봇이름 으로 접속해서 대화를 시작합니다.

