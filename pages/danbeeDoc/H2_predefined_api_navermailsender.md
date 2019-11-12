---
title: 네이버 메일 전송
tags: [chatflow, API, advanced]
keywords: api
summary: danbee.Ai에서 제공하는 Naver 게정을 통해 이메일을 전송하는 API입니다.
sidebar: danbee_doc_sidebar
permalink: predefined_api_navermailsender.html
folder: danbeeDoc
previous: {
    title: Gmail 메일 전송,
    url: predefined_api_gmailsender.html
}
next: {
    title: AWS 메일 전송,
    url: predefined_api_awssessender.html
}
---

## API 설명

danbee.Ai에서 제공하는 여러가지 API 중 Naver 게정을 통해 이메일을 전송하는 API임니다.  <br />
Naver의 이메일 서비스를 통해서 이메일을 사용하려면 추가적인 설정이 필요합니다.  <br />


## API 입력값

| KEY | TYPE | Required | VALUE |
|--------|--------|--------|--------|
| user | String | Yes | Naver 계정 ( 예 : danbee ) |
| password | String | Yes | Naver 계정의 비밀번호 또는 앱 비밀번호 |
| fromUsername | String | Yes | 보내는 사람이름 ( 예 : 단비 ) |
| toEmail | String | Yes | 받는 사람 이메일 ( contact@danbee.ai ) |
| subject | String | Yes | 이메일 제목 |
| message | String | Yes | 이메일 내용 ( html 사용가능 ) |

## API 사용을 위한 Naver 설정

Naver의 이메일 서비스의 환경 설정에서 SMTP 사용설정을 합니다. <br />
1. <span class="link">[Naver](https://naver.com){:target="_blank"}</span>로 이동합니다.
2. 네이버 <span class="link">[메일](http://mail.naver.com){:target="_blank"}</span>로 이동합니다.
3. 맨 하단에 이메일 사용량 옆 "환경설정" 버튼을 큭릭하여 환경 설정 페이지로 이동합니다.
4. 상단에 "POP3/IMAP 설정" 글자를 클릭하여 설정 페이지로 이동합니다.
5. POP3/SMTP 설정 탭에 POP3/SMTP 사용을 "사용합" 으로 설정합니다.
6. 원본 저장에 대한 옵션을 설정합니다. ( 보통 네이버 메일에 원본 저장을 선택함 )
7. "확인" 버튼을 클릭하여 저장합니다.
8. 해당페이지의 하단에 "메일 프로그램 환경 설정 안내"를 보면 SMTP 설정정보를 확인가능합니다.
9. 아이디와 비밀번호를 API 의 user, password 입력값에 설정합니다.

## 2단계 인증을 사용하는 계정

2단계 인증을 사용하는 계정이라면 앱 비밀번호를 생성해서 사용해야 합니다. 아래의 두가지 가이드를 확인합니다. <br />
POP3/SMTP가 설정되지 않을 경우에 대한 설명을 Naver 고객센터에서 확인 가능합니다. <br />
. Naver 고객센터 : https://help.naver.com/support/contents/contents.help?serviceNo=2342&categoryNo=2317 <br />
어플리케이션 비밀번호 사용에 대한 사용방법에 대한 가이드는 Naver 고객센터에서 확인 가능합니다. <br />
. Naver 고객센터 : https://help.naver.com/support/contents/contents.help?serviceNo=532&categoryNo=11047 <br />

1. 메뉴 (위치 : 내정보 > 보안설정 > 2단계 인증 > 관리하기) 로 이동합니다. 
2. 네이버 로그인 비밀번호 재확인 후 "애플리케이션 비밀번호 관리" 기능 확인합니다.
3. 사용하려는 애플리케이션 종류 직접 입력(Danbee API) 선택 후 '생성하기' 버튼 클릭합니다.
4. 생성된 애플리케이션 비밀번호 12자리를 danbee.Ai 의 Naver 메일 전송 API 의 password 에 셋팅합니다.

<br />
