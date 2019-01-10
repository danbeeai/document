---
title: 연결 가능한 대화 채널
tags: [channel, basic]
keywords: Basic Conversation
summary: 원하는 채팅창, 메신저 플랫폼과 연결하는 방법을 소개합니다.
sidebar: danbee_doc_sidebar
permalink: channel_connection_settings.html
folder: danbeeDoc
previous: {
    title: 테스트 패널 및 시뮬레이션,
    url: demo_n_test_panel.html
}
next: {
    title: 프로그(단비에이아이웹채널),
    url: channel_frogu.html
}
---

danbee.Ai로 만든 대화모델, 챗봇은 어떤 대화채널이든 연결 가능합니다.

바로 사용하실 수 있는 웹 채팅창 Frogue, 음성인식/합성 기술과 연계하거나 다른 서비스와 연계할 수 있는 개발자를 위한 Native API.
그리고 국내외 많은 사람들이 이용하고 있는 메신저 플랫폼과 연계가능합니다.


## danbee.Ai 자체 채널, Frogue(프로그)

{% include image.html file="channel/c_frogue.png" max-width="200" caption="챗봇 전용 웹채팅창 Frogue by danbee.Ai" %}

danbee.Ai에서 제공하는 챗봇 전용 채팅창 frogue를 여러분의 웹사이트에 바로 적용하세요!
[프로그 자세히 보기](channel_frogu.html)

## 개발자를 위한 Native API

{% include image.html file="channel/c_danbee.png" max-width="200" caption="대화서비스와 연계할 수 있는 API by danbee.Ai" %}

API를 활용해 자유롭게 챗봇, 음성봇 등 여러분이 상상하는 어떤 대화형 서비스라도 만들 수 있습니다.
[Native App API 자세히 보기](channel_native_app.html)

## 메신저 플랫폼 연동



<div class="row" class="channel_gate">
    <div class="col-md-4 col-sm-6">
        <div class="panel panel-default text-center">
            <div class="panel-heading">
                <img src="https://danbee.Ai/platform/img/channel/c_facebook.png" />
            </div>
            <div class="panel-body">
                <h5>페이스북</h5>
                <p>Facebook 페이지에 방문한 고객에게 챗봇이 대응합니다!</p><br />
                <a href="channel_facebook.html" class="btn btn-primary">자세히</a>
            </div>
        </div>
    </div>
    <div class="col-md-4 col-sm-6">
        <div class="panel panel-default text-center">
            <div class="panel-heading">
                <img src="https://danbee.Ai/platform/img/channel/c_line.png" />
            </div>
            <div class="panel-body">
                <h5>네이버 라인</h5>
                <p>글로벌 메신저, 라인에 챗봇을 연동해보세요. </p><br />
                <a href="channel_line.html" class="btn btn-primary">자세히</a>
            </div>
        </div>
    </div>
    <div class="col-md-4 col-sm-6">
        <div class="panel panel-default text-center">
            <div class="panel-heading">
                <img src="https://danbee.Ai/platform/img/channel/c_telegram.png" />
            </div>
            <div class="panel-body">
                <h5>텔레그램</h5>
                <p>글로벌 메신저, 텔레그램에 챗봇을 연동해 보세요.</p><br />
                <a href="channel_telegram.html" class="btn btn-primary">자세히</a>
            </div>
        </div>
    </div>
    <div class="col-md-4 col-sm-6">
        <div class="panel panel-default text-center">
            <div class="panel-heading">
                <img src="https://danbee.Ai/platform/img/channel/c_kakaotalk.png" />
            </div>
            <div class="panel-body">
                <h5>카카오톡</h5>
                <p>2018년 11월 30일까지 생성된 플러스친구 계정에 연결가능합니다.</p><br />
                <a href="channel_kakaotalk.html" class="btn btn-primary">자세히</a>
            </div>
        </div>
    </div>
    <div class="col-md-4 col-sm-6">
        <div class="panel panel-default text-center">
            <div class="panel-heading">
                <img src="https://danbee.Ai/platform/img/channel/c_naver_talktalk.png" />
            </div>
            <div class="panel-body">
                <h5>네이버톡톡</h5>
                <p>네이버톡톡으로 자주 물어보는 고객에게 자동으로 답변하세요!</p><br />
                <a href="channel_navertalk.html" class="btn btn-primary">자세히</a>
            </div>
        </div>
    </div>
    <div class="col-md-4 col-sm-6">
        <div class="panel panel-default text-center">
            <div class="panel-heading">
                <img src="https://danbee.Ai/platform/img/channel/c_slack.png" />
            </div>
            <div class="panel-body">
                <h5>Slack</h5>
                <p>업무용 챗봇을 만들어 팀원들과 함께 사용해보세요.</p><br />
                <a href="channel_slack.html" class="btn btn-primary">자세히</a>
            </div>
        </div>
    </div>
</div>
<br />
## 채널 별 제약사항
채널 별로 환경이 다르기 때문에 몇 가지 제약사항이 존재합니다.

| 기능 | 설명 | 제한 채널 | 비고 |
|--------|-------|-------|------|
| 버튼 | 버튼의 모든 기능을 사용할 수 있다. | 카카오톡, 텔레그램 | 카카오톡 : 전화걸기 불가, link 버튼 1개로 제한<br/>텔레그램 : 전화걸기 버튼 사용 불가|
| 캐로셀 카드 | 카드 형태 메세지를 사용할 수 있다. | 카카오톡, 텔레그램 | 최상단 버튼 set 및 질문메세지만 제공 |
| 다건 메세지 연속 전송 | 여러 메세지를 동시에 전송할 수 있다. | 카카오톡, 라인 | 카카오톡 : 하나의 메세지로 합쳐서 제공<br/>라인 : 최대 5개 연속 전송 가능 |
| 사용자 정보 | 사용자 정보를 활용할 수 있다. | Frogue, 카카오톡, 텔레그램,<br/> 네이버톡톡  | 사용 불가 |
{: .table .table-striped}

이외에도 버튼 사용 가능 개수의 경우 채널 별로 제한이 존재합니다.

| 채널 | 버튼 제한 개수 |
|--------|-------|
| Frogue | 제한없음 |
| 라인 | 4개 | 
| 카카오톡 | 일반 버튼 제한없음. 단, Link 버튼 1개 | 
| 페이스북 | 3개 | 
| 텔레그램 | 제한없음 |
| 네이버 톡톡 | 10개 |
| Slack | 5개 |
{: .table .table-striped}

해당 제약사항은 대화채널 설정 화면에서 간결한 아이콘으로 확인할 수 있습니다.


