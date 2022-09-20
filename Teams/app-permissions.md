---
title: Teams 앱 사용 권한 및 고려 사항
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 관리자는 Microsoft Teams 앱이 조직에서 요청하는 데이터 및 권한을 알아볼 수 있습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 42044bf8f74c99b27db724e87ee35e700491aa8e
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837198"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Teams 앱 사용 권한 및 고려 사항

Microsoft Teams 앱은 하나 이상의 기능을 설치, 업그레이드 및 제거할 수 있는 앱으로 통합할 수 있는 방법입니다. 앱의 기능은 다음과 같습니다.

* 봇
* 메시징 확장
* 탭
* 커넥터

관리자는 앱만 관리합니다. 그러나 이 문서에서는 앱의 기능이 앱의 필요한 권한 및 위험 프로필에 영향을 주기 때문에 기능 수준에서 사용 권한 및 고려 사항에 중점을 둡니다. 사용의 경우 앱은 사용자가 동의하고 정책 관점에서 IT 전문가가 관리합니다.

아래에 대문자로 나열된 사용 권한(예: `RECEIVE_MESSAGE` 및 `REPLYTO_MESSAGE` )은 설명 및 설명 목적으로만 사용됩니다. 이러한 문자열 또는 사용 권한은 [Microsoft Teams 개발자 설명서](/microsoftteams/platform/overview) 또는 [Microsoft Graph에 대한 사용 권한](/graph/permissions-reference) 어디에도 표시되지 않습니다.

## <a name="global-app-permissions-and-considerations"></a>전역 앱 사용 권한 및 고려 사항

### <a name="required-permissions"></a>필요한 사용 권한

없음

### <a name="optional-permissions"></a>선택적 사용 권한

없음

### <a name="considerations"></a>고려 사항

* 앱은 사용하는 데이터와 사용 약관 및 개인 정보 취급 방침 링크에 사용되는 데이터를 공개해야 합니다.

* [리소스별 동의](resource-specific-consent.md)는 앱이 요청할 수 있는 권한 집합을 제공하며, 앱의 설치 화면에 표시됩니다. 리소스별 동의 권한에 대한 자세한 내용은 [Graph 권한 참조](/graph/permissions-reference#teams-resource-specific-consent-permissions)를 확인하세요.

* 앱에는 리소스별 동의 권한 이외의 권한이 필요할 수도 있습니다. 앱이 설치되면 앱은 동의 프롬프트를 통해 그래프 권한을 요청할 수 있습니다. 자세한 내용은 [Azure AD 애플리케이션 동의 환경 이해](/azure/active-directory/develop/application-consent-experience)를 참조하세요. Azure Portal API 권한 및 동의를 구성할 수 있습니다. 자세한 내용은 [Azure Active Directory 동의 프레임워크](/azure/active-directory/develop/consent-framework)를 참조하세요.

## <a name="bots-and-messaging-extensions"></a>봇 및 메시징 확장

### <a name="required-permissions"></a>필요한 사용 권한

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: 봇은 사용자로부터 메시지를 받고 회신할 수 있습니다. <sup>1</sup>

* POST_MESSAGE_USER: 사용자가 봇에 메시지를 보낸 후 봇은 사용자 직접 메시지(*자동 관리 메시지* 라고도 함)를 언제든지 보낼 수 있습니다.

* GET_CHANNEL_LIST: 팀에 추가된 봇은 팀의 채널 이름과 ID 목록을 가져올 수 있습니다.

### <a name="optional-permissions"></a>선택적 사용 권한

* ID: 채널에서 사용되는 경우 앱의 봇은 팀 구성원의 기본 ID 정보(이름, 성, 사용자 계정 이름 [UPN], 이메일 주소)에 액세스할 수 있습니다. 개인 또는 그룹 채팅에서 사용되는 경우 봇은 해당 사용자에 대해 동일한 정보에 액세스할 수 있습니다.

* POST_MESSAGE_TEAM: 사용자가 봇과 상호 작용한 적이 없더라도 앱의 봇이 언제든지 팀 구성원에게 직접(사전 대응) 메시지를 보낼 수 있도록 허용합니다.

* 다음은 명시적 권한이 아니지만 매니페스트에 선언된 RECEIVE_MESSAGE 및 REPLYTO_MESSAGE 및 봇을 사용할 수 있는 범위에 암시됩니다.

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* 다음은 명시적 권한이 아니지만 매니페스트에 선언된 RECEIVE_MESSAGE 및 REPLYTO_MESSAGE 및 봇을 사용할 수 있는 범위에 암시됩니다.

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES RECEIVE_FILES:<sup>2</sup> 봇이 개인 채팅에서 파일을 보내고 받을 수 있는지 여부를 제어합니다(아직 그룹 채팅 또는 채널에 지원되지 않음).

### <a name="considerations"></a>고려 사항

* 봇은 추가된 팀 또는 봇을 설치한 사용자에만 액세스할 수 있습니다.

* 봇은 사용자가 명시적으로 언급한 메시지만 받습니다. 이 데이터는 회사 네트워크를 떠납니다.

* 봇은 언급된 대화에만 회신할 수 있습니다.

* 사용자가 봇과 대화할 때 봇이 사용자의 ID를 저장하는 경우 언제든지 사용자에게 직접 메시지를 보낼 수 있습니다.

* 이론적으로는 봇 메시지에 피싱 또는 맬웨어 사이트에 대한 링크가 포함될 수 있습니다. 그러나 사용자, 테넌트 관리자 또는 전역적으로 Microsoft에서 봇을 차단할 수 있습니다. [앱 확인 및 유효성 검사](overview-of-app-validation.md) 에서는 모든 가짜 앱을 Teams 스토어에서 사용할 수 없도록 합니다.

* 봇은 앱이 추가된 팀 구성원 또는 개인 또는 그룹 채팅의 개별 사용자에 대한 기본 ID 정보를 검색(및 저장할 수 있음)할 수 있습니다. 이러한 사용자에 대한 추가 정보를 얻으려면 봇이 Azure Active Directory(Azure AD)에 로그인하도록 요구해야 합니다.

* 봇은 팀의 채널 목록을 검색(및 저장할 수 있음)할 수 있습니다. 이 데이터는 회사 네트워크를 떠납니다.

* 기본적으로 봇은 사용자를 대신하여 작업할 수 없지만 봇은 사용자에게 로그인하도록 요청할 수 있습니다. 사용자가 로그인하는 즉시 봇은 추가 작업을 수행할 수 있는 액세스 토큰을 갖게 됩니다. 봇과 사용자가 로그인하는 위치에 따라 정확히 무엇이 달라지는지 정확히 알 수 있습니다. 봇은 https://apps.dev.microsoft.com/에 등록된 Azure AD 앱이며 자체 사용 권한 집합을 가질 수 있습니다.

* 파일이 봇에 전송되면 파일은 회사 네트워크를 떠납니다. 파일을 보내고 받으려면 각 파일에 대한 사용자 승인이 필요합니다.

* 봇은 사용자가 팀에 추가되거나 팀에서 삭제될 때마다 알려줍니다.

* 봇은 사용자의 IP 주소 또는 기타 참조 정보를 볼 수 없습니다. 모든 정보는 Microsoft에서 제공됩니다. (한 가지 예외가 있습니다. 봇이 자체 로그인 환경을 구현하는 경우 로그인 UI에 사용자의 IP 주소 및 참조자 정보가 표시됩니다.)

* 반면 메시징 확장은 사용자의 IP 주소 및 참조 정보를 확인합니다.

* 앱 지침(및 AppSource 검토 프로세스)은 유효한 목적으로 개인 채팅 메시지를 사용자에게 게시할 때(POST_MESSAGE_TEAM 권한을 통해) 재량권을 요구합니다. 남용이 발생할 경우 사용자는 봇을 차단하고, 테넌트 관리자는 앱을 차단할 수 있으며, 필요한 경우 Microsoft는 중앙에서 봇을 차단할 수 있습니다.

<sup>1</sup> 일부 봇은 메시지만 보냅니다(POST_MESSAGE_USER). "알림 전용" 봇이라고 하지만 이 용어는 봇이 허용되거나 허용되지 않는 작업을 참조하지 않으며, 이는 봇이 대화형 환경을 노출하지 않으려는 것을 의미합니다. Teams는 이 필드를 사용하여 일반적으로 사용하도록 설정되는 UI의 기능을 사용하지 않도록 설정합니다. 봇은 대화형 환경을 노출하는 봇에 비해 허용되는 작업에서 제한되지 않습니다.

<sup>2</sup> 앱에 대한 `manifest.json` 파일의 봇 개체에 대한 supportsFiles Boolean 속성에 의해 관리됩니다.

> [!NOTE]
> 봇에 자체 로그인이 있는 경우 사용자가 처음 로그인할 때 다른 두 번째 동의 환경이 있습니다.
>
>현재 Teams 앱 내의 기능(봇, 탭, 커넥터 또는 메시징 확장)과 연결된 Azure AD 권한은 여기에 나열된 Teams 사용 권한과 완전히 별개입니다.

## <a name="tabs"></a>탭

탭은 Teams 내에서 실행되는 웹 사이트입니다.

### <a name="required-permissions"></a>필요한 사용 권한

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>선택적 사용 권한

없음(현재)

### <a name="considerations"></a>고려 사항

* 탭의 위험 프로필은 브라우저 탭에서 실행되는 동일한 웹 사이트와 거의 동일합니다.

* 또한 탭은 현재 사용자의 로그인 이름 및 UPN, 현재 사용자의 Azure AD 개체 ID, 상주하는 Microsoft 365 그룹의 ID(팀인 경우), 테넌트 ID 및 사용자의 현재 로캘을 포함하여 실행 중인 컨텍스트를 가져옵니다. 그러나 이러한 ID를 사용자의 정보에 매핑하려면 탭에서 사용자가 Azure AD에 로그인하도록 해야 합니다.

## <a name="connectors"></a>커넥터

커넥터는 외부 시스템의 이벤트가 발생할 때 채널에 메시지를 게시합니다.

### <a name="required-permissions"></a>필요한 사용 권한

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>선택적 사용 권한

REPLYTO_CONNECTOR_MESSAGE. 특정 커넥터는 GitHub 문제에 응답을 추가하거나 Trello 카드에 날짜를 추가하는 등 사용자가 대상 회신을 커넥터 메시지에 게시할 수 있도록 하는 실행 가능한 메시지를 지원합니다.

### <a name="considerations"></a>고려 사항

* 커넥터 메시지를 게시하는 시스템은 메시지를 게시하는 사람 또는 메시지를 받는 사람을 알지 못합니다. 받는 사람에 대한 정보는 공개되지 않습니다. (Microsoft는 테넌트가 아닌 실제 받는 사람입니다. Microsoft는 채널에 실제 게시물을 게시합니다.)

* 커넥터 메시지가 채널에 게시될 때 회사 네트워크에서 나가는 데이터가 없습니다.

* 실행 가능한 메시지(REPLYTO_CONNECTOR_MESSAGE 권한)를 지원하는 커넥터에도 IP 주소 및 참조 정보가 표시되지 않습니다. 이 정보는 Microsoft로 전송된 다음 커넥터 포털에서 이전에 Microsoft에 등록된 HTTP 엔드포인트로 라우팅됩니다.

* 채널에 대해 커넥터를 구성할 때마다 해당 커넥터 인스턴스에 대한 고유한 URL이 만들어집니다. 해당 커넥터 인스턴스가 삭제되면 URL을 더 이상 사용할 수 없습니다.

* 커넥터 메시지에는 파일 첨부 파일이 포함될 수 없습니다.

* 커넥터 인스턴스 URL은 비밀/기밀로 처리되어야 합니다. 해당 URL을 가진 모든 사용자는 전자 메일 주소와 같이 해당 URL에 게시할 수 있습니다. 따라서 스팸 또는 피싱 또는 맬웨어 사이트에 대한 링크의 위험이 있습니다. 이 경우 팀 소유자는 커넥터 인스턴스를 삭제할 수 있습니다.

* 커넥터 메시지를 보내는 서비스가 손상되어 스팸/피싱/맬웨어 링크 전송을 시작하는 경우 테넌트 관리자는 새 커넥터 인스턴스가 생성되지 않도록 방지하고 Microsoft가 중앙에서 차단할 수 있습니다.

> [!NOTE]
> 현재 실행 가능한 메시지(REPLYTO_CONNECTOR_MESSAGE 권한)를 지원하는 커넥터를 알 수 없습니다.

## <a name="outgoing-webhooks"></a>발신 웹후크

_발신 웹후크_ 는 팀 소유자 또는 팀 구성원이 만듭니다. Teams 앱의 기능은 아닙니다. 이 정보는 완전성을 위해 포함됩니다.

### <a name="required-permissions"></a>필요한 사용 권한

RECEIVE_MESSAGE, REPLYTO_MESSAGE. 사용자로부터 메시지를 받고 회신할 수 있습니다.

### <a name="optional-permissions"></a>선택적 사용 권한

없음

### <a name="considerations"></a>고려 사항

* 발신 웹후크는 봇과 비슷하지만 권한은 적습니다. 봇과 마찬가지로 명시적으로 언급해야 합니다.

* 발신 웹후크가 등록되면 비밀이 생성되므로 발신 웹후크는 보낸 사람이 악의적인 공격자가 아닌 Microsoft Teams인지 확인할 수 있습니다. 이 비밀은 비밀로 유지되어야 합니다. 액세스 권한이 있는 사람은 누구나 Microsoft Teams를 가장할 수 있습니다. 비밀이 손상된 경우 발신 웹후크를 삭제하고 다시 만들어 새 비밀을 생성합니다.

* 비밀의 유효성을 검사하지 않는 발신 웹후크를 만들 수 있지만, 이에 대해 권장합니다.

* 메시지를 받고 회신하는 것 외에 발신 웹후크는 많은 작업을 수행할 수 없습니다. 즉, 메시지를 사전에 보낼 수 없고, 파일을 보내거나 받을 수 없으며, 메시지 수신 및 회신 외에는 봇이 수행할 수 있는 다른 작업을 수행할 수 없습니다.
