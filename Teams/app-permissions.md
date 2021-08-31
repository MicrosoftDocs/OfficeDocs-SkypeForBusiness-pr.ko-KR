---
title: Microsoft Teams 앱 사용 권한 및 고려 사항
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
description: 관리자는 앱에서 조직에서 요청하는 Microsoft Teams 및 권한을 알 수 있습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15892a4eb3996923f7a0129805e2bb542cdc8d7c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731787"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Microsoft Teams 앱 사용 권한 및 고려 사항

Microsoft Teams 앱은 설치, 업그레이드 및 제거될 수  있는 하나 이상의 기능을 앱 패키지에 집계하는 방법입니다. 기능에는 다음이 포함됩니다.

- 봇
- 메시징 확장
- 탭
- 커넥터

앱은 사용자가 동의하고 정책 관점에서 IT에서 관리합니다. 그러나 대부분의 경우 앱의 사용 권한 및 위험 프로필은 앱에 포함된 기능의 사용 권한 및 위험 프로필에 의해 정의됩니다. 따라서 이 문서에서는 기능 수준에서 사용 권한 및 고려 사항을 중점적으로 다를 수 있습니다.

아래 대문자에 나열된 권한(예: RECEIVE_MESSAGE 및 REPLYTO_MESSAGE)은 개발자 설명서 또는 [](/microsoftteams/platform/overview) [Microsoft](/graph/permissions-reference)Microsoft Teams 에 대한 사용 권한에 Graph. 이 문서는 이 문서의 목적에 대한 설명적인 짧은 설명입니다.


| 제목   | 설명    |
|-----------|------------|
| ![결정 지점을 표시하는 아이콘입니다.](media/audio_conferencing_image7.png) <br/>결정 지점|<ul><li>아래 표를 가이드로 사용하여 조사하는 앱이 요청하는 권한을 이해합니다.</li></ul> |
| ![다음 단계를 표시하는 아이콘입니다.](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>앱 또는 서비스 자체를 조사하여 조직 내에서 액세스 권한을 허용할지 여부를 결정합니다. 예를 들어 봇은 사용자로부터 메시지를 보내고 수신하며 엔터프라이즈 사용자 지정 봇을 제외하고는 규정 준수 경계 외부에 있습니다. 따라서 봇을 포함하는 모든 앱에는 이러한 권한이 필요하며 최소한 위험 프로필이 있습니다. </li></ul>|

탭에 대한 디바이스 [사용 권한 Microsoft Teams 참조하세요.](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)

## <a name="global-app-permissions-and-considerations"></a>글로벌 앱 사용 권한 및 고려 사항

### <a name="required-permissions"></a>필수 사용 권한

없음

### <a name="optional-permissions"></a>선택적 사용 권한

없음

### <a name="considerations"></a>고려 사항

- 앱은 사용하는 데이터와 해당 사용 약관 및 개인 정보 취급 방침 링크에 사용되는 데이터를 공개해야 합니다.

- [리소스별 동의는](resource-specific-consent.md) 앱의 설치 화면에 나타나는 앱에 요청할 수 있는 사용 권한 집합을 제공합니다. 리소스별 동의 권한에 대한 자세한 내용은 사용 [권한 Graph 참조를 참조합니다.](/graph/permissions-reference#teams-resource-specific-consent-permissions)

- 앱에 리소스별 동의 권한 외의 사용 권한이 필요할 수도 있습니다. 앱이 설치되면 앱에서 동의 프롬프트를 통해 Graph 권한을 요청할 수 있습니다. 자세한 내용은 Azure AD 애플리케이션 [동의 환경 이해 를 참조하세요.](/azure/active-directory/develop/application-consent-experience) Azure Portal에서 API 사용 권한 및 동의를 구성할 수 있습니다. 자세한 내용은 동의 [Azure Active Directory 참조합니다.](/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>봇 및 메시징 확장

### <a name="required-permissions"></a>필수 사용 권한

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. 봇은 사용자로부터 메시지를 받고 회신할 수 있습니다. <sup>1</sup>

- POST_MESSAGE_USER. 사용자가 봇에 메시지를 보낸 후 봇은 사용자 직접 메시지(사전 메시지라고도도)를 보낼 *수* 있습니다.

- GET_CHANNEL_LIST. 팀에 추가된 봇은 팀의 채널 이름 및 아이디 목록을 얻을 수 있습니다.

### <a name="optional-permissions"></a>선택적 사용 권한

- ID. 채널에서 사용되는 경우 앱의 봇은 팀 구성원의 기본 ID 정보(이름, 성, 사용자 주체 이름 [UPN], 전자 메일 주소)에 액세스할 수 있습니다. 개인 채팅 또는 그룹 채팅에 사용되는 경우 봇은 해당 사용자에 대해 동일한 정보에 액세스할 수 있습니다.

- POST_MESSAGE_TEAM. 사용자가 전에 봇과 대화한 적이 없는 경우에도 앱의 봇이 팀 구성원에게 직접(사전 예방) 메시지를 보낼 수 있습니다.

- 다음은 명시적 사용 권한이 아니라 매니페스트에서 선언된 RECEIVE_MESSAGE REPLYTO_MESSAGE 및 봇을 사용할 수 있는 범위에 의해 암시됩니다.
 
    - RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM

- SEND_FILES RECEIVE_FILES. <sup>2</sup> 봇이 개인 채팅에서 파일을 보내고 받을 수 있는지 여부를 제어합니다(그룹 채팅 또는 채널에 대해 아직 지원되지 않습니다).

### <a name="considerations"></a>고려 사항

- 봇은 추가된 팀 또는 설치한 사용자에게만 액세스할 수 있습니다.

- 봇은 사용자가 명시적으로 언급한 메시지만 수신합니다. 이 데이터는 회사 네트워크를 떠날 수 있습니다.

- 봇은 언급된 대화에만 회신할 수 있습니다.

- 사용자가 봇과 대화한 후 봇이 해당 사용자의 ID를 저장하는 경우 해당 사용자 직접 메시지를 보낼 수 있습니다.

- 이론적으로 봇 메시지에 피싱 또는 맬웨어 사이트에 대한 링크가 포함될 수 있지만 사용자, 테넌트 관리자 또는 Microsoft에서 전역적으로 봇을 차단할 수 있습니다.

- 봇은 앱이 추가된 팀 구성원 또는 개인 또는 그룹 채팅의 개별 사용자에 대한 매우 기본적인 ID 정보를 검색(저장)할 수 있습니다. 이러한 사용자에 대한 자세한 정보를 얻게하려면 봇이 Azure AD(Azure AD)에 로그인해야 Azure Active Directory 합니다.

- 봇은 팀의 채널 목록을 검색(저장)할 수 있습니다. 이 데이터는 회사 네트워크를 떠날 수 있습니다.

- 파일이 봇에 전송된 경우 파일이 회사 네트워크를 떠날 수 있습니다. 파일을 보내고 받는 경우 각 파일에 대한 사용자 승인이 필요합니다. 

- 기본적으로 봇은 사용자를 대신하여 행동할 수 없지만 봇은 사용자에게 로그인을 요청할 수 있습니다. 사용자가 로그인하면 봇에 추가 작업을 할 수 있는 액세스 토큰이 있습니다. 이러한 추가 작업의 정확한 구성은 봇에 따라 달라지며 사용자가 로그인하는 위치는 봇이 등록된 Azure AD 앱으로, 자체 사용 권한 집합을 사용할 https://apps.dev.microsoft.com/ 수 있습니다.

- 봇은 사용자가 팀에 추가되거나 삭제될 때마다 통보됩니다.

- 봇은 사용자의 IP 주소 또는 기타 참조 정보를 볼 수 없습니다. 모든 정보는 Microsoft에서 제공됩니다. (한 가지 예외가 있습니다. 봇이 자체 로그인 환경을 구현하는 경우 로그인 UI에서 사용자의 IP 주소 및 참조 정보를 볼 수 있습니다.)

- 반면 메시징 확장은 사용자의 IP 주소 및 참조 정보를 참조하세요.

- 앱 지침(및 AppSource 검토 프로세스)은 유효한 목적으로 사용자에게 개인 채팅 메시지를 게시하는 데 POST_MESSAGE_TEAM 재량이 필요합니다. 남용이 발생하면 사용자가 봇을 차단할 수 있으며, 테넌트 관리자는 앱을 차단할 수 있으며, 필요한 경우 Microsoft는 봇을 중앙에서 차단할 수 있습니다.

<sup>1</sup> 일부 봇은 메시지만 전송합니다(POST_MESSAGE_USER. "알림 전용" 봇이라고 하지만 용어는 봇이 허용하거나 허용하지 않는 것을 의미하지 않습니다. 이는 봇이 대화 환경을 노출하지 않을 것을 의미합니다. Teams 이 필드를 사용하여 기본적으로 사용하도록 설정되는 UI의 기능을 사용하지 않도록 설정합니다. 봇은 대화 환경을 노출하는 봇과 비교하여 허용되는 작업을 제한하지 않습니다.

<sup>2</sup> 지원에 의해 관리되는 봇 개체의 manifest.js파일의 부울 속성입니다.

> [!NOTE]
> 봇에 자체 로그인이 있는 경우 사용자가 처음 로그인할 때 동의 경험이 다른 두 번째가 있습니다.
>
>현재 앱 내 기능(Teams 봇, 탭, 커넥터 또는 메시징 확장)에 연결된 Azure AD 사용 권한은 Teams 권한과 완전히 구분됩니다.

## <a name="tabs"></a>탭

탭은 웹 사이트 내에서 실행되는 Teams.

### <a name="required-permissions"></a>필수 사용 권한

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>선택적 사용 권한

없음(현재)

### <a name="considerations"></a>고려 사항

- 탭의 위험 프로필은 브라우저 탭에서 실행되는 동일한 웹 사이트와 거의 동일합니다. 

- 또한 탭은 현재 사용자의 로그인 이름 및 UPN, 현재 사용자의 Azure AD 개체 ID, 현재 사용자가 상주하는 Microsoft 365 그룹의 ID, 테넌트 ID 및 사용자의 현재 로일을 포함하여 실행 중인 컨텍스트를 제공합니다. 그러나 이러한 ID를 사용자의 정보에 매핑하기 위해 탭에서 사용자가 Azure AD에 로그인하도록 설정해야 합니다.

## <a name="connectors"></a>커넥터

커넥터는 외부 시스템의 이벤트가 발생할 때 채널에 메시지를 게시합니다.

### <a name="required-permissions"></a>필수 사용 권한

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>선택적 사용 권한

REPLYTO_CONNECTOR_MESSAGE. 특정 커넥터는 사용자가 연결선 메시지에 대한 대상 응답을 게시할 수 있도록 하는 실행 가능한 메시지를 지원합니다(예: GitHub 메시지에 대한 응답을 추가하거나 Trello 카드에 날짜를 추가합니다.

### <a name="considerations"></a>고려 사항

- 커넥터 메시지를 게시하는 시스템은 받는 사람에 대한 정보가 공개되지 않습니다. (Microsoft는 테넌트가 아닌 실제 받는 사람입니다. Microsoft는 채널에 대한 실제 게시물을 합니다.)

- 커넥터 메시지가 채널에 게시되는 경우 데이터가 회사 네트워크를 떠날 수 없습니다.

- 실행 가능한 메시지(REPLYTO_CONNECTOR_MESSAGE 권한)를 지원하는 커넥터도 IP 주소 및 참조 정보를 볼 수 없습니다. 이 정보는 Microsoft로 전송된 다음 커넥터 포털에서 이전에 Microsoft에 등록된 HTTP 엔드포인트로 라우팅됩니다.

- 채널에 대해 커넥터를 구성할 때마다 해당 커넥터 인스턴스에 대한 고유한 URL이 만들어집니다. 해당 커넥터 인스턴스가 삭제되면 URL을 더 이상 사용할 수 없습니다.

- 커넥터 메시지에는 파일 첨부 파일이 포함될 수 없습니다.

- 커넥터 인스턴스 URL은 비밀/기밀로 처리해야 합니다. 해당 URL이 있는 모든 사용자가 전자 메일 주소와 같이 해당 URL에 게시할 수 있습니다. 따라서 스팸 또는 피싱 또는 맬웨어 사이트에 대한 링크의 위험이 있습니다. 이 경우 팀 소유자는 커넥터 인스턴스를 삭제할 수 있습니다.

- 커넥터 메시지를 보내는 서비스가 손상되고 스팸/피싱/맬웨어 링크를 보내기 시작하는 경우 테넌트 관리자가 새 커넥터 인스턴스를 만들지 못하게 할 수 있으며 Microsoft는 이를 중앙에서 차단할 수 있습니다.

> [!NOTE]
> 현재 실행 가능한 메시지(사용 권한)를 지원하는 커넥터를 알 수 REPLYTO_CONNECTOR_MESSAGE 없습니다.

## <a name="outgoing-webhooks"></a>진행하는 웹후크

*팀 소유자 또는* 팀 구성원이 진행하는 웹후크가 생성됩니다. 앱의 기능이 Teams 없습니다. 이 정보는 완전성을 위해 포함되어 있습니다.

### <a name="required-permissions"></a>필수 사용 권한

RECEIVE_MESSAGE, REPLYTO_MESSAGE. 사용자로부터 메시지를 받고 회신할 수 있습니다.

### <a name="optional-permissions"></a>선택적 사용 권한

없음

### <a name="considerations"></a>고려 사항

- 진행하는 웹후크는 봇과 비슷하지만 권한이 적습니다. 봇과 마찬가지로 명시적으로 언급해야 합니다.

- 발신 웹후크가 등록될 때 비밀이 생성되어 발신 웹후크가 악성 공격자가 Microsoft Teams 있는지 확인할 수 있습니다. 이 비밀은 비밀로 유지됩니다. 액세스 권한이 있는 모든 사용자에 대해 가장할 Microsoft Teams. 비밀이 손상되면 발신 웹후크를 삭제하고 다시 만들 수 있으며 새 비밀이 생성됩니다.

- 비밀의 유효성을 검사하지 않는 진행하는 웹후크를 만들 수 있습니다.

- 메시지 수신 및 회신 외에, 발신 웹후크는 많은 작업을 할 수 없습니다. 즉, 메시지를 사전적으로 보낼 수 없습니다. 파일을 보내거나 받을 수 없습니다. 봇은 메시지 수신 및 회신 외에 할 수 있는 다른 작업을 할 수 없습니다.