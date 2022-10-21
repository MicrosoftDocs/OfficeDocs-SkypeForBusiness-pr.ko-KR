---
title: Microsoft Teams 관리 센터에서 Microsoft Power Platform 앱 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Teams 관리 센터에서 Microsoft Power Platform을 사용하여 빌드된 사용자 지정 앱에 대한 액세스를 관리하는 방법을 알아봅니다.
ms.openlocfilehash: 3a81d1db3de7cf4fa82b80526ffdb206bfbe8da6
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656040"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Teams 관리 센터에서 Microsoft Power Platform 앱 관리

## <a name="manage-custom-apps-created-using-microsoft-power-platform-apps"></a>Microsoft Power Platform 앱을 사용하여 만든 사용자 지정 앱 관리

이 문서에서는 Microsoft Teams 관리 센터에서 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 앱을 사용하여 만든 사용자 지정 앱을 관리하는 방법에 대한 개요를 제공합니다. 사용자 지정 앱은 내부 사용자를 위해 조직 내의 개발자가 만듭니다.

> [!NOTE]
> 이 문서는 앱 페이지에서 설치했거나 앱 설정 정책을 통해 Teams에 고정된 Power Apps 앱이나 Power Virtual Agents 앱에는 적용되지 않습니다. Store 앱은 [앱 허용 정책](teams-app-permission-policies.md) 및 [앱 설정 정책](teams-app-setup-policies.md)을 이용해 관리할 수 있습니다.

[Power Apps](https://powerapps.microsoft.com)란 조직의 앱 제작자가 사용자의 비즈니스 데이터에 연결하는 사용자 지정 앱을 빌드할 때 사용할 수 있는 로우코드나 노코드 애플리케이션 개발 환경입니다. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)란 앱 개발자가 강력한 봇을 만들수 있도록 하는 노코드 봇 빌드 환경입니다. Microsoft Power Platform 앱을 Teams에 통합함으로써 조직은 비즈니스 프로세스를 간소화하고 변화하는 비즈니스 요구 사항에 보다 신속하게 대응하여 공동 작업을 강화하고 사용자 지정 솔루션을 생성 및 공유하여 생산성을 높일 수 있습니다.  

조직의 개발자가 만든 Microsoft Power Platform 앱은 자동으로 Teams에 추가됩니다. 개발자는 [Power Apps의 공유 기능](/powerapps/maker/canvas-apps/share-app) 및 [Power Virtual Agents의 공유 기능](/power-virtual-agents/admin-share-bots)을 사용하여 앱에 액세스할 수 있는 사용자를 제어할 수 있습니다.

Microsoft Power Platform 앱을 만들거나 공유하면 사용자는 **Power Platform로 빌드** 로 이동해 이 앱을 확인해 앱 페이지에 설치할 수 있습니다. (앱이 완성되거나 공유되어 여기에 나타나기까지 몇 분 정도 걸릴 수 있습니다.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Power Platform으로 빌드함에 나열된 Microsoft Power Platform 앱을 보여 주는 Apps 페이지의 스크린샷":::

앱이 다음 조건 중 하나를 충족하는 경우 **Power Platform으로 빌드함** 에서 최종 사용자가 앱을 볼 수 있게 됩니다.

|Power Apps |파워 가상 에이전트  |
|---------|---------|
|<ul><li>사용자가 앱을 만들었습니다.</li><li>앱이 사용자와 직접 공유되었습니다.</li><li>사용자가 최근에 앱을 사용했습니다. </li></ul>| <ul><li>사용자가 봇을 만들었습니다.</li><li>봇은 사용자가 구성원인 팀의 소유입니다. </li></ul>        |

사용자는 다른 Teams 앱을 설치하는 것과 동일한 방식으로 Microsoft Power Platform 앱을 설치합니다. 사용자는 권한이 있는 컨텍스트에만 앱을 설치할 수 있습니다. 예를 들면 사용자가 보유한 팀, 사용자가 속한 채팅 또는 개인적인 범위 등입니다.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Teams 관리 센터에서 Microsoft Power Platform 앱에 대한 액세스 관리

관리자는 Microsoft Power Platform 앱을 Teams의 앱 페이지에 있는 **Power Platform으로 빌드함** 에 나열할지를 제어할 수 있습니다. Power Apps에서 만든 모든 앱이나 Power Virtual Agents에서 만든 모든 앱을 조직 전체를 대상으로 [앱 관리](manage-apps.md) 페이지에 한꺼번에 차단 또는 허용하거나 [앱 허용 정책](teams-app-permission-policies.md)을 통해 개별 사용자에게 차단 또는 허용할 수 있습니다.

조직의 앱 스토어에 있는 **공유된 Power Apps** 및 **공유된 Power Virtual Agent 앱** 은 해당 특정 플랫폼에서 만든 모든 앱을 나타냅니다. 전체 조직 또는 특정 사용자에 대해 이러한 앱을 하나 또는 둘 다 차단하는 경우 사용자는 Teams에 설치할 수 없습니다. 사용자는 앱을 허용하도록 관리자 승인을 요청할 수 없습니다.

Power Apps와 Power Virtual Agents에서 만든 모든 앱에 대한 액세스를 제어할 수는 있지만 개별 앱을 허용하거나 차단할 수는 없습니다. 앱 작성자는 Power Apps와 Power Virtual Agents 내부에 있는 공유 기능을 통해 자신이 만든 앱에 누가 액세스할 지를 정합니다. 작성자가 어떤 사용자와 함께 Power Virtual Agents에서 만든 앱을 공유한 상태에서 해당 사용자가 **공유된 Power Virtual Agents 앱** 을 차단당하면 해당 사용자는 Teams의 해당 플랫폼에서 어떤 앱도 확인하거나 설치할 수 없습니다.

Power Apps나 Power Virtual Agents의 앱에 대한 액세스 권한이 있는 사용자를 이들 플랫폼 가운데 하나 또는 전부에 있는 앱에 액세스하지 못하게 차단하면 해당 사용자는 대상 앱에 대해 차단당하기 전까지는 자신이 설치한 Microsoft Power Platforms 앱에 액세스하거나 사용할 수 있습니다. 하지만, 해당 사용자는 더 이상 **Power Platform으로 빌드함** 에 있는 해당 플랫폼에서 앱을 설치할 수 없습니다.

> [!NOTE]
> [앱 관리](manage-apps.md) 페이지의 **사용자 지정 앱과의 상호작용 허용** 조직 전체 앱 설정은 조직의 모든 사용자에 적용되며 이들이 사용자 지정 앱과 상호작용할 수 있는지 제어합니다. 조직 전체 앱 설정은 모든 사용자의 동작을 관리하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 재정의합니다. 이 설정을 해제하면 조직 내의 사용자들은 Microsoft Power Platform 앱을 비롯한 사용자 지정 앱을 아무것도 설치할 수 없습니다. 자세한 내용은 [조직 전체 앱 설정](manage-apps.md#manage-org-wide-app-settings)을 참조하세요.

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>조직의 Microsoft Power Platform 앱 허용 또는 차단

기본적으로 **공유한 Power Apps** 및 **공유한 Power Virtual Agent 앱** 은 조직 내의 모든 Teams 사용자에게 허용됩니다. 이러한 사용자들은 Microsoft Teams 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직 전체적으로 차단하거나 허용할 수 있습니다.  

1. Teams 관리 센터에 로그인하고 **Teams 앱****[관리 앱](https://admin.teams.microsoft.com/policies/manage-apps)** > 에 액세스하려면 전역 관리자 또는 Teams 서비스 관리자여야 페이지에 액세스할 수 있습니다.
1. 앱 목록에서 다음 중 하나를 실행합니다.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="공유한 Microsoft Power Platform 앱이 표시된 앱 관리 페이지의 스크린샷":::

    * 조직의 모든 사용자에게 Power Apps나 Power Virtual Agents에서 만든 앱을 차단하려면 **공유한 Power Apps** 또는 **공유한 Power Virtual Agent 앱** 을 검색해 선택한 다음 **차단** 을 선택합니다.
    * 조직의 모든 사용자에게 Power Apps나 Power Virtual Agents에서 만든 앱을 허용하려면 **공유한 Power Apps** 또는 **공유한 Power Virtual Agent 앱** 을 검색해 선택한 다음 **허용** 을 선택합니다.

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>특정 사용자에 대해 Microsoft Power Platform 앱 허용

조직의 특정 사용자가 Power Apps 또는 Power Virtual Agents에서 만든 앱에 액세스하도록 허용하거나 차단하려면 하나 이상의 사용자 지정 [app 권한 정책](teams-app-permission-policies.md)을 만들어 할당합니다.

예를 들어 특정 사용자가 Power Apps에서 만든 앱에 액세스하지 못하도록 차단하려면 앱 권한에 대한 사용자 지정 정책을 만들어 **공유 Power Apps** 를 차단한 다음 해당 사용자에게 정책을 할당합니다.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="공유 Power Apps가 차단된 앱 권한에 대한 사용자 지정 정책 예제 스크린샷":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Microsoft Power Platform 설치 작업 조사를 위해 감사 로그 사용

Teams의 감사 로그를 사용해 사용자가 Teams의 앱 페이지 내 **Power Platform으로 빌드함** 섹션에서 Microsoft Power Platform 앱을 설치한 이벤트를 조사할 수 있습니다. 이를 위해서는 대상 사용자나 사용자 그룹에 대해 **설치된 앱** Teams 이벤트(**AppInstalled** 작업에 위치)에서 [감사 로그를 검색](./audit-log-events.md)합니다. **Power Platform으로 빌드함** 에서 설치한 앱을 찾으려면 대상 레코드 세부 정보의 **AppDistributionMode** 속성에서 **TemplatedInstance** 값을 찾습니다.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 속성의 TemplatedInstance 값 스크린샷" lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> 필터링을 용이하게 할 수 있게 감사 레코드는 CSV 형식으로 내보낼 수 있습니다.

## <a name="related-articles"></a>관련 기사

* [Power Apps에서 캔버스 앱 공유](/powerapps/maker/canvas-apps/share-app)
* [다른 사용자와 봇 공유](/power-virtual-agents/admin-share-bots)
* [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
* [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
* [Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시](submit-approve-custom-apps.md)
