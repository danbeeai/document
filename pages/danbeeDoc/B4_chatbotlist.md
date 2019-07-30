---
title: 그룹 
tags: [nlu, advanced]
keywords: Chatbot Management
summary: 챗봇을 관리하는 단위입니다.
sidebar: danbee_doc_sidebar
permalink: chatbot_list.html.html
folder: danbeeDoc
previous: {
    title: Jump 노드,
    url: chatflow_jump.html
}
next: {
    title: 기본답변 설정,
    url: chatflow_jump.html
}
---


## 그룹(Group)

**그룹**이란 챗봇을 관리하는 관리자 단위를 의미합니다. 

하나의 그룹에는 여러개의 챗봇이 할당될 수 있으며, 계정등급(그룹 생성자의 등급)에 따라 하나의 그룹에 생성할 수 있는 챗봇의 갯수와 협업 가능 여부가 다릅니다. 자세한 내용은 요금제 페이지을 확인하시기 바랍니다. [요금제 확인하기](pricing.html) 

그룹 관리 기능은 다음과 같습니다.

 - Group 사용자 관리
 - Group 챗봇 관리

### Group 사용자 관리


{% include image.html file="image/group_usr.PNG" %}

**Group 사용자 관리**에서는 그룹에 사용자를 등록하거나 삭제할 수 있습니다.
그룹에 사용자를 등록할 때 사용자의 권한을 정하게 됩니다. 설정할 수 있는 권한은 총 3가지입니다.

 - ADMIN : 그룹 어드민 권한입니다. 요금제 변경 외에 모든 권한을 가지고 있습니다. 유일하게 챗봇을 생성할 수 있는 권한입니다.
 - DESIGNER : 그룹 디자이너 권한 입니다. 챗봇의 인텐트와 챗플로우를 생성/수정할 수 있는 권한이 있습니다.
 - TRAINER : 그룹 트레이너 권한입니다. 챗봇에 예문을 학습시킬 수 있는 권한을 가지고 있습니다.

### Group 챗봇 관리

{% include image.html file="image/group_usr.PNG" %}

**Group 챗봇 관리**에서는 그룹에 등록된 챗봇을 그룹내 사용자들에게 분배할 수 있습니다.


--------------

## 챗봇 목록

{% include image.html file="image/chatbot_list.PNG" %}

**챗봇 목록** 페이지에서는 **선택한 그룹 내**에서 수정/학습 **권한**을 가지고 있는 챗봇을 모아 볼 수 있습니다. 만일 현재 그룹내에 생성권한이 있다면 챗봇 생성도 진행할 수 있습니다.

--------------


## 챗봇 생성

{% include image.html file="image/chatbot_create.PNG" %}

**챗봇 생성** 페이지에서는 샘플 챗봇을 복사하거나, 빈 챗봇을 생성하여 직접 챗봇을 생성하기 시작할 수 있습니다. 튜토리얼봇을 통해 단비 플렛폼을 익혀나갈수도 있습니다. 챗봇 생성은 3가지 종류가 있습니다.

 - 빈 챗봇 생성
 - 위자드 챗봇 생성
 - 샘플 챗봇 생성

### 빈 챗봇 생성

아무런 정보도 없는 빈 챗봇을 생성합니다.

### 위자드 챗봇 생성

필요한 정보만 입력하면 나만의 챗봇이 만들어지는 위자드 챗봇을 생성합니다.

### 샘플 챗봇 생성

이미 만들어져있는 챗봇을 그대로 복사해옵니다.
