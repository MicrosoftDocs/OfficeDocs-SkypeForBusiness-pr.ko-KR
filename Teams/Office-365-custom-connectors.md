---
title: Microsoft 365 커넥터 및 사용자 지정 커넥터 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 사용하는 서비스를 위해 Teams 채널에 콘텐츠 및 업데이트를 자주 전달하여 커넥터가 팀을 업데이트하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983686"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Microsoft 365 커넥터 및 사용자 지정 커넥터 관리

Microsoft Teams의 커넥터는 타사 서비스에서 Teams 채널로 직접 콘텐츠 및 서비스 업데이트를 제공합니다. 커넥터를 사용하여 사용자는 Trello, Wunderlist, GitHub 및 Azure DevOps Services 같은 인기 있는 서비스에서 업데이트를 받습니다. 업데이트는 채팅 스트림에 직접 게시됩니다. 이렇게 하면 모든 멤버가 동기화 상태를 유지하고 관련 정보를 빠르게 받을 수 있습니다.

Microsoft 365 커넥터는 Teams 및 Microsoft 365 그룹 모두에서 사용됩니다. Teams 및 Microsoft Exchange에서 동일한 커넥터를 사용할 수 있습니다. 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

팀 권한이 허용하는 경우 팀의 모든 구성원이 팀에 커넥터를 추가할 수 있으며 모든 팀 구성원은 해당 서비스의 활동에 대한 알림을 받습니다. 추가 또는 제거 권한이 있는 모든 팀 구성원은 다른 구성원의 커넥터 설정을 수정할 수 있습니다.

## <a name="enable-or-disable-connectors-in-teams"></a>Teams에서 커넥터 활성화 또는 비활성화

Exchange Online PowerShell v2 모듈은 최신 인증을 사용하고 MFA(다단계 인증)를 사용하여 Microsoft 365의 모든 Exchange 관련 PowerShell 환경에 연결합니다. 관리자는 Exchange Online PowerShell을 사용하여 전체 테넌트 또는 특정 그룹 사서함에 대한 커넥터를 비활성화하여 해당 테넌트 또는 사서함의 모든 사용자에게 영향을 줄 수 있습니다. 일부 특정 사용자에 대해 사용하지 않도록 설정할 수 없습니다.

테넌트 설정이 그룹 설정보다 우선합니다. 예를 들어 관리자가 그룹에 대한 커넥터를 활성화하고 테넌트에서 비활성화하는 경우 그룹의 커넥터는 비활성화됩니다. Teams에서 커넥터를 활성화하려면 MFA가 있거나 없는 최신 인증을 사용하여 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)합니다.

커넥터를 사용하거나 사용하지 않도록 설정하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

* 테넌트에 대한 커넥터를 비활성화하려면: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* 테넌트에 대해 실행 가능한 메시지를 비활성화하려면: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Teams용 커넥터를 활성화하려면 다음 명령을 실행합니다.
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

PowerShell 모듈 교환에 대한 자세한 내용은 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)를 참조하세요. Outlook 커넥터를 활성화하거나 비활성화하려면 [Microsoft Outlook에서 앱을 그룹에 연결](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)하세요.

## <a name="publish-connectors-for-your-organization"></a>조직의 커넥터 게시

조직의 사용자가 사용자 지정 커넥터를 사용할 수 있도록 하려면 조직의 앱 카탈로그에 사용자 지정 커넥터 앱을 업로드합니다. 조직 내의 최종 사용자는 팀에서 커넥터를 설치, 구성 및 사용할 수 있습니다.

> [!IMPORTANT]
> GCC(Government Community Cloud), GCCH(Government Community Cloud-High) 및 DOD(국방부) 환경에서는 사용자 지정 커넥터를 사용할 수 없습니다.

팀 또는 채널에서 커넥터를 사용하려면 채널의 오른쪽 상단에서 추가 옵션 메뉴를 엽니다. 메뉴에서 **커넥터** 를 선택한 다음 필요한 커넥터를 찾거나 검색합니다. 필요한 경우 선택한 커넥터를 구성합니다.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="채널의 오른쪽 상단에 있는 추가 옵션에서 Teams의 채널에 커넥터를 추가하세요.":::

## <a name="update-url-of-a-connector"></a>커넥터의 URL 업데이트

Teams 커넥터는 보안을 강화하기 위해 새 URL로 전환하고 있습니다. 전환하는 동안 구성된 커넥터를 업데이트한다는 알림을 받게 됩니다. 커넥터 서비스가 중단되지 않도록 최대한 빨리 커넥터를 업데이트합니다. 커넥터를 업데이트하려면 다음을 수행합니다.

1. 커넥터 구성 페이지에서 구성된 커넥터 옆에 있는 **주의 필요** 메시지를 확인합니다.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="주의 필요 메시지의 스크린샷.":::

1. 수신되는 웹후크 커넥터에 대한 연결을 다시 만들려면 **URL 업데이트** 를 선택하고 생성된 웹후크 URL을 사용합니다.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="URL 업데이트 단추의 스크린샷.":::

1. 다른 커넥터 유형의 경우 커넥터를 제거하고 커넥터 구성을 다시 만듭니다. **URL이 최신 상태입니다** 메시지가 나타납니다.

   :::image type="content" source="media/teams-url-updated.png" alt-text="URL의 스크린샷은 최신 메시지입니다.":::

## <a name="considerations-when-using-connectors-in-teams"></a>Teams에서 커넥터를 사용할 때 고려 사항

* 커넥터는 GCC(정부 클라우드 커뮤니티) 환경에서 기본적으로 비활성화되어 있습니다. 이를 활성화하려면 `SetOrganizationConfig` cmdlet을 사용하여 `ConnectorsEnabled` 또는 `ConnectorsEnabledForTeams` 매개 변수를 `$true`(으)로 설정합니다. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true)에 연결합니다.

* 팀에 커넥터를 추가한 사용자가 팀을 떠나는 경우 커넥터는 계속 작동합니다.

* 다음 커넥터는 2023년 1월 이후에 사용할 수 없습니다.

  * Aha
  * 에어브레이크 (동음이의)
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * BEANSTALK
  * BITBUCKET
  * BITBUCKETSERVER
  * 친구
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * Getresponse
  * GHOSTINSPECTOR
  * 홈
  * Heroku
  * HONEYBADGER
  * 인터 콤
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * Pingdom
  * PIVOTALTRACKER
  * 레이건 주
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * 세마포
  * 센 트리
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * Subversion
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>관련 기사

* [사용자 지정 커넥터 및 웹후크 개요](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Office 365 커넥터를 만드는 방법](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
