---
title: Microsoft 팀 앱 사용 권한 및 고려 사항
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 조직에서 요청 하는 데이터 및 사용 권한 앱에 대해 알아봅니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a5efc1ec447d1aeda3c42841752b6fd6e1f1938
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516787"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft 팀 앱 사용 권한 및 고려 사항

Microsoft 팀 앱은 하나 이상의 기능을 설치, 업그레이드 및 제거할 수 있는 _앱 패키지로_ 집계 하는 방법입니다. 접근 권한 값은 다음과 같습니다.

- 봇
- 메시징 확장
- 탭
- 기가

앱은 사용자가 였음을 하 고 정책 관점에서 관리 합니다. 그러나 대부분의 경우 앱의 사용 권한과 위험 프로필은 앱에 포함 된 기능의 사용 권한과 위험 프로필에 의해 정의 됩니다. 따라서이 문서에서는 기능 수준에서 사용 권한과 고려 사항을 중점적으로 설명 합니다.

아래에 나열 된 사용 권한은 RECEIVE_MESSAGE 및 REPLYTO_MESSAGE와 같이 대/소문자에 관계 없이 [Microsoft 팀 개발자 문서](https://aka.ms/teamsdevdocs) 또는 [microsoft Graph에 대 한 사용 권한에](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)표시 되지 않습니다. 단지이 기사의 목적에 대해 설명 하는 간단한 방법입니다.


|    |     |
|-----------|------------|
| ![결정 지점을 가리키는 아이콘](media/audio_conferencing_image7.png) <br/>판단 요점|<ul><li>아래 표를 참조 하 여 조사 중인 앱에서 요청 하는 사용 권한을 파악 합니다.</li></ul> |
| ![다음 단계를 안내 하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>앱 또는 서비스 자체를 조사 하 여 조직 내에서 해당 사용자에 게 액세스를 허용 하려는 지 여부를 결정 합니다. 예를 들어, 봇은 사용자 로부터 메시지를 보내고 받으며 enterprise lob (기간 업무) 인공 지능을 제외 하 고는 규정 준수 경계 외부에 위치 합니다. 따라서 봇이 포함 된 앱에는 해당 권한이 필요 하며 최소한 위험 프로필을 보유 하 고 있는 것입니다. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>전역 앱 사용 권한 및 고려 사항

### <a name="required-permissions"></a>필요한 권한

없음

### <a name="optional-permissions"></a>선택 권한

없음

### <a name="considerations"></a>고려 사항

앱은 사용 약관 및 개인 정보 취급 방침 링크에서 사용 하는 데이터와 데이터를 공개 해야 합니다.</td>

## <a name="bots-and-messaging-extensions"></a>인공 지능 및 메시징 확장

### <a name="required-permissions"></a>필요한 권한

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. 봇은 사용자 로부터 메시지를 수신 하 고 회신할 수 있습니다. <sup>1</sup>

- POST_MESSAGE_USER. 사용자가 봇으로 메시지를 보낸 후에는 봇이 사용자 직접 메시지 (언제 든 지 *사전 메시지* 라고도 함)를 보낼 수 있습니다.

- GET_CHANNEL_LIST. 팀에 추가 된 bot 팀에 있는 채널의 이름 및 Id 목록을 가져올 수 있습니다.

### <a name="optional-permissions"></a>선택 권한

- 신분을. 채널에서 사용 하는 경우 앱의 봇이 팀 구성원의 기본 id 정보 (이름, 성, UPN (사용자 계정 이름), 전자 메일 주소)에 액세스할 수 있습니다. 개인 또는 그룹 채팅에 사용 되는 경우에는 봇이 해당 사용자에 대 한 동일한 정보에 액세스할 수 있습니다.

- POST_MESSAGE_TEAM. 사용자가 이전에 인공 지능으로가는 일이 없더라도 앱의 봇이 언제 든 지 팀 구성원에 게 직접 (사전) 메시지를 보낼 수 있습니다.

- 다음은 명시적 권한은 아니지만 RECEIVE_MESSAGE 및 REPLYTO_MESSAGE 및 해당 인공 지능으로 선언 되는 데 사용 될 수 있는 범위에 의해 암시 됩니다.
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> 봇이 개인 채팅에서 파일을 보내고 받을 수 있는지 여부를 제어 합니다 (아직 그룹 채팅 또는 채널에 지원 되지 않음).

### <a name="considerations"></a>고려 사항

- 봇에는 자신이 추가 된 팀 또는이를 설치한 사용자만 액세스할 수 있습니다.

- 인공 지능은 사용자가 명시적으로 언급 한 메시지만 받습니다. 이 데이터는 회사 네트워크를 벗어납니다.

- 봇에는이를 언급 한 대화에만 회신할 수 있습니다.

- 사용자가 봇 대를 conversed 후에는 해당 사용자의 ID를 저장 하면 언제 든 지 해당 사용자에 게 직접 메시지를 전송할 수 있습니다.

- 기본적으로 봇 메시지에 피싱 또는 맬웨어 사이트에 대 한 링크가 포함 될 수 있으 나 사용자, 테 넌 트 관리자 또는 Microsoft에서 전역으로 인공 지능을 차단할 수 있습니다.

- 봇은 앱이 추가 된 팀 구성원 또는 개인 또는 그룹 채팅의 개별 사용자에 대 한 매우 기본적인 id 정보를 검색 하 고 저장할 수 있습니다. 이러한 사용자에 대 한 자세한 정보를 얻으려면 봇에서 Azure Active Directory (Azure AD)에 로그인 해야 합니다.

- Bot은 팀에서 채널 목록을 검색 하 고 저장할 수 있습니다. 이 데이터는 회사 네트워크를 벗어납니다.

- 파일을 bot에 보내면 파일이 회사 네트워크를 벗어납니다. 파일을 보내고 받으려면 각 파일에 대 한 사용자 승인이 필요 합니다. 

- 기본적으로 인공 지능에서는 사용자를 대신 하 여 작업을 수행할 수 있지만 인공 지능 사용자에 게 로그인 하도록 요청할 수 있습니다. 사용자가 로그인 하자마자 추가 작업을 수행할 수 있는 액세스 토큰이 인공으로 포함 됩니다. 그 외에는 봇과 사용자 로그인 위치에 따라 달라질 수 있습니다. 봇은에 https://apps.dev.microsoft.com/ 등록 된 Azure AD 앱 이며 고유한 사용 권한 집합을 가질 수 있습니다.

- 봇에는 사용자가 팀에 추가 되거나 삭제 될 때마다 알림을 받을 수 있습니다.

- 봇에는 사용자의 IP 주소나 다른 참조 정보가 표시 되지 않습니다. 모든 정보는 Microsoft에서 제공 합니다. (한 가지 예외: 봇이 자체 로그인 환경을 구현 하는 경우 로그인 UI에는 사용자의 IP 주소 및 참조 정보가 표시 됩니다.)

- 반면에 메시징 확장에는 사용자의 IP 주소 및 참조 정보 정보가 표시 됩니다.

- 앱 지침 (및 AppSource review)을 사용 하 여 사용자에 게 개인 채팅 메시지를 게시할 때 적절 한 용도에 대해 신중 하 게 해야 합니다 (POST_MESSAGE_TEAM 권한을 통해). 불건전 한 경우 사용자가 인공 지능을 차단 하 고, 테 넌 트 관리자가 앱을 차단 하 고, 필요한 경우 Microsoft에서 인공 지능을 차단할 수 있습니다.

<sup>1</sup> 일부 봇만 메시지를 보냅니다 (POST_MESSAGE_USER). "알림 전용" 인공 지능 이라고 하는 데,이는 봇이 허용 되거나 허용 되지 않는 것을 의미 하지 않지만,이는 봇이 대화를 하는 것을 원하지 않습니다. 팀에서는이 필드를 사용 하 여 일반적으로 사용 되는 UI의 기능을 사용 하지 않도록 설정 합니다. 이 봇은 대화를 표시 하는 것과 비교 하 여 허용 되는 것으로 제한 되지 않습니다.

<sup>2</sup> 앱에 대 한 manifest.xml 파일의 bot 개체에 대 한 Supportsfiles 부울 속성에 의해 관리 됩니다.

> [!NOTE]
> 봇에 자체 로그인이 있으면 두 번째, 즉 사용자가 처음 로그인 할 때 동의 하는 환경이 제공 됩니다.
>
>현재 팀 앱 (봇, 탭, 커넥터 또는 메시징 확장) 내의 기능과 연결 된 Azure AD 권한은 여기에 나열 된 팀 권한과 완전히 별개입니다.

## <a name="tabs"></a>탭

탭은 팀 내에서 실행 되는 웹 사이트입니다.

### <a name="required-permissions"></a>필요한 권한

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>선택 권한

없음 (현재)

### <a name="considerations"></a>고려 사항

- 탭에 대 한 위험 프로필은 브라우저 탭에서 실행 되는 동일한 웹 사이트와 거의 동일 합니다. 

- 또한 탭은 현재 사용자의 로그인 이름 및 UPN, 현재 사용자의 Azure AD 개체 ID,이 계정이 있는 Office 365 그룹의 ID (팀 인 경우), 테 넌 트 ID를 포함 하 여 실행 중인 컨텍스트를 가져옵니다. 사용자의 현재 로캘입니다. 그러나 이러한 Id를 사용자 정보에 매핑하려면 탭에서 사용자가 Azure AD에 로그인 하도록 설정 해야 합니다.

## <a name="connectors"></a>기가

외부 시스템의 이벤트가 발생할 때 커넥터는 메시지를 채널에 게시 합니다.

### <a name="required-permissions"></a>필요한 권한

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>선택 권한

REPLYTO_CONNECTOR_MESSAGE. 특정 커넥터는 사용자가 GitHub 문제에 대 한 응답을 추가 하거나 Trello 카드에 날짜를 추가 하는 등 커넥터 메시지에 대 한 대상 지정 된 회신을 게시할 수 있도록 하는 실행 가능한 메시지를 지원 합니다.

### <a name="considerations"></a>고려 사항

- 커넥터 메시지를 게시 하는 시스템에서 메시지를 보내거나 받는 사람을 알 수 없는 경우 받는 사람에 대 한 정보가 공개 되지 않습니다. (Microsoft는 테 넌 트가 아닌 실제 받는 사람입니다. Microsoft는 채널의 실제 게시물을 처리 합니다.

- 커넥터 메시지가 채널에 게시 되 면 데이터가 회사 네트워크를 벗어납니다.

- 실행 가능 메시지를 지 원하는 커넥터 (REPLYTO_CONNECTOR_MESSAGE 사용 권한)에도 IP 주소 및 참조 정보가 표시 되지 않습니다. 이 정보는 Microsoft에 전송 된 후 커넥터 포털에서 이전에 Microsoft에 등록 한 HTTP 끝점으로 라우팅됩니다.

- 채널에 대해 커넥터가 구성 될 때마다 해당 커넥터 인스턴스에 대 한 고유 URL이 생성 됩니다. 해당 커넥터 인스턴스가 삭제 되 면 해당 URL을 더 이상 사용할 수 없습니다.

- 커넥터 메시지에 첨부 파일을 포함할 수 없습니다.

- 커넥터 인스턴스 URL은 전자 메일 주소와 같이 해당 URL이 있는 모든 사용자가 게시할 수 있는 비밀/비밀 우편으로 처리 되어야 합니다. 따라서 스팸 또는 피싱 또는 맬웨어 사이트에 대 한 링크에는 몇 가지 위험이 있습니다. 이런 일이 발생 하는 경우 팀 소유자는 커넥터 인스턴스를 삭제할 수 있습니다.

- 커넥터 메시지를 보내는 서비스가 손상 되 고 스팸/피싱/맬웨어 링크 보내기를 시작 하는 경우 테 넌 트 관리자가 새 커넥터 인스턴스가 만들어지지 않도록 하 고 Microsoft는 중앙에서 차단할 수 있습니다.

> [!NOTE]
> 현재 어떤 커넥터가 실행 가능한 메시지를 지원 하는지 알 수 없습니다 (REPLYTO_CONNECTOR_MESSAGE permission).

## <a name="outgoing-webhooks"></a>보내는 webhooks

테 넌 트에 대해 테스트용 로드를 사용 하는 경우 팀 소유자 또는 팀 구성원이 *보내는 webhooks* 를 즉시 만듭니다. 팀 앱의 기능을 제공 하지 않습니다. 이 정보는 완전성을 위해 포함 되어 있습니다.

### <a name="required-permissions"></a>필요한 권한

RECEIVE_MESSAGE, REPLYTO_MESSAGE. 사용자에 게 메시지를 수신 하 고 회신할 수 있습니다.

### <a name="optional-permissions"></a>선택 권한

없음

### <a name="considerations"></a>고려 사항

- 보내는 webhooks는 봇과 비슷하지만 사용 권한이 더 적습니다. 봇과 같이 명시적으로 언급 해야 합니다.

- 송신 webhook이 등록 되 면 보내는 webhook이 생성 되어 보낸 사람이 악의적인 공격자와 반대 되는 Microsoft 팀 인지 확인할 수 있습니다. 비밀은 비밀로 유지 되어야 합니다. 액세스 권한이 있는 모든 사용자가 Microsoft 팀을 가장할 수 있습니다. 비밀이 손상 되 면 송신 webhook을 삭제 하 고 다시 만들 수 있으며 새 비밀이 생성 됩니다.

- 비밀의 유효성을 검사 하지 않는 송신 webhook을 만들 수 있지만, 그에 대해 권장 합니다.

- 보내는 webhooks는 메시지를 받고 회신 하는 것 외에는 더 이상 메시지를 보낼 수 없고, 파일을 보내거나 받을 수 없으며, 다른 사용자가 메시지를 수신 하 고 회신 하는 것 외에는 할 수 없습니다.
