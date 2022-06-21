---
title: Microsoft 365 및 사용자 지정 커넥터 관리
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 커넥터가 사용하는 서비스에 대한 Teams 채널에 콘텐츠 및 업데이트를 자주 전달하여 팀을 업데이트하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: de0c0398d511aca05a69220e0e35a28268535c59
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190448"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Microsoft 365 및 사용자 지정 커넥터 관리

팀을 계속 업데이트하기 위해 커넥터는 자주 사용하는 콘텐츠 및 서비스 업데이트를 Teams 채널에 직접 제공합니다. 커넥터를 사용하면 Teams 사용자가 Trello, Wunderlist, GitHub 및 Azure DevOps Services 같은 인기 있는 서비스에서 업데이트를 받을 수 있습니다. 업데이트는 팀의 채팅 스트림에 직접 게시됩니다.

Microsoft 365 커넥터는 Microsoft Teams 및 Microsoft 365 그룹에서 모두 사용되므로 모든 구성원이 동기화 상태를 유지하고 관련 정보를 빠르게 받을 수 있습니다. Microsoft Teams 및 Exchange 모두 동일한 커넥터 모델을 사용하므로 두 플랫폼 내에서 동일한 커넥터를 사용할 수 있습니다. 그러나 Microsoft 365 그룹에 대해 구성된 커넥터를 사용하지 않도록 설정하면 Microsoft 365 그룹에서 커넥터를 만드는 기능도 비활성화됩니다.

팀 권한이 허용되고 모든 팀 구성원에게 해당 서비스의 활동에 대한 알림을 받으면 팀의 모든 구성원이 커넥터를 사용하여 인기 있는 클라우드 서비스에 팀을 연결할 수 있습니다. 커넥터를 처음 설정한 멤버가 나간 후에도 커넥터는 계속 작동합니다. 추가 또는 제거할 수 있는 권한이 있는 모든 팀 구성원은 다른 멤버가 커넥터 설정을 수정할 수 있습니다.

## <a name="enable-or-disable-connectors-in-teams"></a>Teams 커넥터 사용 또는 사용 안 함

Exchange Online PowerShell V2 모듈은 최신 인증을 사용하며 MFA라는 다단계 인증을 사용하여 Microsoft 365 모든 Exchange 관련된 PowerShell 환경에 연결합니다. 관리자는 Exchange Online PowerShell을 사용하여 전체 테넌트 또는 특정 그룹 사서함에 대한 커넥터를 사용하지 않도록 설정하여 해당 테넌트 또는 사서함의 모든 사용자에게 영향을 미칠 수 있습니다. 몇 가지 특정 사용자에 대해 사용하지 않도록 설정할 수 없습니다. 또한 커넥터는 GCC 테넌트라고 하는 정부 커뮤니티 클라우드 대해 기본적으로 사용하지 않도록 설정됩니다.

테넌트 설정은 그룹 설정을 재정의합니다. 예를 들어 관리자가 그룹에 대한 커넥터를 사용하도록 설정하고 테넌트에서 사용하지 않도록 설정하면 그룹에 대한 커넥터가 비활성화됩니다. Teams 커넥터를 사용하도록 설정하려면 MFA 사용 여부에 관계없이 최신 인증[을 사용하여 Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true)합니다.

커넥터를 사용하거나 사용하지 않도록 설정하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.

* 테넌트에 대한 커넥터를 사용하지 않도록 설정하려면 : `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* 테넌트에 대해 실행 가능한 메시지를 사용하지 않도록 설정하려면 : `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Teams 커넥터를 사용하도록 설정하려면 다음 명령을 실행합니다.
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

PowerShell 모듈 교환에 대한 자세한 내용은 [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true)를 참조하세요. Outlook 커넥터를 사용하거나 사용하지 않도록 설정하려면 [Outlook 그룹에 앱을 연결합니다](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>조직에 대한 커넥터 게시

사용자 지정 커넥터를 조직의 사용자만 사용할 수 있도록 하려면 조직의 앱 카탈로그에 사용자 지정 커넥터 앱을 업로드할 수 있습니다. 앱 패키지를 업로드한 후 최종 사용자는 조직의 앱 카탈로그에서 커넥터를 설치하고 팀에서 커넥터를 구성하고 사용할 수 있습니다.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> 사용자 지정 커넥터는 정부 커뮤니티 클라우드(GCC), GCC 높음 및 국방부(DOD)에서 사용할 수 없습니다.

팀 또는 채널에서 커넥터를 사용하려면 채널의 오른쪽 위 모서리에서 기타 옵션 메뉴를 엽니다. 메뉴에서 **커넥터를** 선택한 다음 필요한 커넥터 앱을 찾거나 검색합니다. 필요한 경우 선택한 커넥터를 구성합니다.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="채널의 오른쪽 위 모서리에 있는 기타 옵션에서 Teams 채널에 커넥터를 추가합니다.":::

## <a name="update-url-of-a-connector"></a>커넥터의 URL 업데이트

Teams 커넥터는 보안을 강화하기 위해 새 URL로 전환되고 있습니다. 전환하는 동안 구성된 커넥터를 업데이트하는 알림을 받게 됩니다. 커넥터 서비스의 중단을 방지하기 위해 커넥터를 가장 일찍 업데이트합니다. 커넥터를 업데이트하려면 다음을 수행합니다.

1. 커넥터 구성 페이지에서 구성된 커넥터 옆에 **있는 주의 필요** 메시지를 확인합니다.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="주의 필요 메시지의 스크린샷.":::

1. 들어오는 웹후크 커넥터에 대한 연결을 다시 만들려면 **URL 업데이트를** 선택하고 생성된 웹후크 URL을 사용합니다.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="URL 업데이트 단추의 스크린샷.":::

1. 다른 커넥터 유형의 경우 커넥터를 제거하고 커넥터 구성을 다시 만듭니다. **URL이 최신** 메시지인 경우 메시지가 나타납니다.

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="URL의 스크린샷은 최신 메시지입니다.":::

## <a name="see-also"></a>참고 항목

* [사용자 지정 커넥터 및 웹후크 개요](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Office 365 커넥터 만들기](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
