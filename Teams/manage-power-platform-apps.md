---
title: 관리 센터에서 Microsoft Power Platform Microsoft Teams 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 관리 센터에서 Microsoft Power Platform을 사용하여 구축된 사용자 지정 앱에 대한 액세스를 관리하는 Microsoft Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: d3bf125415f3459913d7b23f5a496cb44eb51856
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730667"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>관리 센터에서 Microsoft Power Platform Microsoft Teams 관리

## <a name="microsoft-power-platform-apps-in-teams"></a>Microsoft Power Platform 앱의 Teams

이 문서에서는 관리 센터에서 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 앱을 관리하는 Microsoft Teams 제공합니다.

> [!NOTE]
> 이 문서는 조직 내 제작자에 의해 만들어진 사용자 지정 앱에 Power Apps 또는 Power Virtual Agents. 이러한 사용자 지정 앱은 자동으로 사용자 지정 앱에 Teams. 이 문서는 앱 페이지에서 Power Apps Power Virtual Agents 앱 설정 정책을 통해 앱에 고정된 앱 또는 Teams 앱에 적용되지 않습니다. 앱 권한 정책 및 앱 설정 정책을 [](manage-apps.md) 사용하여 앱 [](teams-app-permission-policies.md)관리 페이지에서 다른 앱에 대해와 같은 [앱을 관리합니다.](teams-app-setup-policies.md)

[Power Apps](https://powerapps.microsoft.com) 조직의 제작자는 비즈니스 데이터에 연결하는 사용자 지정 앱을 빌드하는 데 사용할 수 있는 코드/코드 없음 애플리케이션 개발 환경입니다. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 제작자는 강력한 봇을 만들 수 있는 코드 봇 구축 환경입니다. Microsoft Power Platform 앱의 통합을 통해 Teams 비즈니스 프로세스를 간소화하고, 변화하는 비즈니스 요구에 더 빠르게 대응하여 더 큰 공동 작업을 추진하고, 사용자 지정 솔루션을 만들고 공유하여 생산성을 향상할 수 있습니다.  

조직의 제작자에 의해 만들어진 Microsoft Power Platform 앱은 자동으로 해당 앱에 Teams. 확인자는 에서 공유 기능 및 [](/powerapps/maker/canvas-apps/share-app) Power Apps 에서 공유 기능을 사용하여 앱에 액세스할 [수](/power-virtual-agents/admin-share-bots)있는 Power Virtual Agents.

Microsoft Power Platform 앱이 만들어지거나 공유되면 사용자는 동료가 작성한 조직 **** 이름 작성으로 이동하여 앱 페이지에 해당 앱을 보고  >  **설치할 수 있습니다.** 앱이 여기에 표시될 수 있는 앱을 만들거나 공유한 후 몇 분 정도 걸릴 수 있습니다.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="동료가 기본 제공에 나열된 Microsoft Power Platform 앱을 보여주는 앱의 스크린샷":::

앱이 다음 조건 중  하나를 충족하는 경우 사용자가 동료에 의해 기본 제공된 앱을 볼 수 있습니다.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>사용자가 앱을 만들었다.</li><li>앱이 사용자와 직접 공유됩니다.</li><li>사용자가 최근에 앱을 사용했다. </li></ul>| <ul><li>사용자가 봇을 만들었다.</li><li>봇은 사용자가 구성원인 팀이 소유합니다. </li></ul>        |

사용자는 다른 모든 앱 설치와 동일한 방식으로 Microsoft Power Platform 앱을 Teams 설치합니다. 사용자가 권한이 있는 컨텍스트에 앱만 설치할 수 있습니다(예: 소유한 팀, 자신의 일부인 채팅 또는 개인 범위).

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>관리 센터에서 Microsoft Power Platform 앱에 대한 Microsoft Teams 관리

관리자는 Microsoft Power Platform 앱이 해당 앱 페이지의  동료에 의해 기본 제공에 나열되어 있는지 여부를 제어할 Teams. 앱 관리 페이지의 Power Apps 또는 앱 권한 정책을 사용하여 특정 사용자에 대해 Power Virtual Agents 수준에서 만든 모든 [](manage-apps.md) 앱을 전체적으로 차단하거나 허용할 [수 있습니다.](teams-app-permission-policies.md)

조직의  Power Apps 앱 스토어에서 공유된 공유 Power **Virtual Agent Apps 앱은** 해당 특정 플랫폼에서 만든 모든 앱을 대표합니다. 이러한 Teams 앱 중 하나 또는 둘 다를 구성 수준 또는 특정 사용자에 대해  차단하는 경우 해당 사용자는 해당 플랫폼에서 동료가 Built에서 해당 플랫폼의 앱을 볼 수 없습니다.  

사용자 및 앱에서 만든 모든 앱에 대한 액세스를 제어할 수 Power Apps Power Virtual Agents 허용하거나 차단할 수 없습니다. 제작자는 공유 기능을 통해 만든 앱에 액세스할 수 있는 Power Apps Power Virtual Agents. 제조사에서 만든 앱을 Power Virtual Agents 사용자와 공유하고 해당 사용자의 공유 Power Virtual Agents **앱을** 차단한 경우 사용자는 해당 플랫폼에서 해당 플랫폼에서 앱을 보거나 설치할 수 Teams.

사용자가 앱에서 앱에 액세스할 수 Power Apps Power Virtual Agents 이러한 플랫폼 중 하나 또는 둘 다에서 앱에 액세스하지 못하도록 차단하는 경우 사용자는 앱 또는 앱을 차단하기 전에 설치한 Microsoft Power 플랫폼 앱에 계속 액세스하고 사용할 수 있습니다. 그러나 사용자는 동료가 기본 제공 에서 해당 플랫폼에서 더 이상 앱을 보거나 **설치할 수 없습니다.**

> [!NOTE]
> 앱 **관리** 페이지에서 사용자 지정 앱과의 [](manage-apps.md) 상호 작용 허용 설정은 조직의 모든 사용자에 적용하고 사용자 지정 앱과 상호 작용할 수 있는지 여부를 관리합니다. 조직 전체 앱 설정은 모든 사용자의 동작을 관리하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 재정의합니다. 이 설정은 기본적으로 켜져 있습니다. 이 설정이 해제된 경우 조직의 사용자는 Microsoft Power Platform 앱을 비롯한 사용자 지정 앱을 보거나 설치할 수 없습니다. 자세한 내용은 전체 앱 설정 관리 [를 참조하세요.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>조직의 Microsoft Power Platform 앱 허용 또는 차단

기본적으로 **공유** Power Apps 및 공유 Power Virtual Agent **Apps는** 조직의 모든 Teams 허용됩니다. 관리 센터의 앱 관리 페이지에서 그룹 [](manage-apps.md) 수준에서 차단하거나 허용할 Microsoft Teams 있습니다.  

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다. 페이지에 액세스하려면 전역 관리자 또는 Teams 관리자 되어야 합니다.
2. 앱 목록에서 다음 중 하나를 실행합니다.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="공유된 Microsoft Power Platform 앱을 보여 주며 앱 관리 페이지의 스크린샷":::

    - 조직의 모든 Power Apps 또는 Power Virtual Agents 만든 앱을 차단하려면 공유 Power Apps 또는 공유 Power Virtual **Agent Apps를** **검색한** 다음 차단을 **클릭합니다.**
    - 조직의 모든 Power Apps 또는 Power Virtual Agents에서 만든 앱을 허용하려면 공유 Power Apps 또는 공유 Power **Virtual Agent Apps를** **검색한** 다음 허용을 **클릭합니다.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>특정 사용자에 대한 Microsoft Power Platform 앱 허용 또는 차단

조직에서 특정 사용자가 사용자 지정 앱 또는 Power Apps 액세스하지 Power Virtual Agents 허용하거나 차단하려면 하나 이상의 사용자 지정 앱 사용 권한 정책을 만들고 [할당합니다.](teams-app-permission-policies.md) 

예를 들어 특정 사용자가 만든 앱에 Power Apps 차단하려면 사용자 지정 앱 사용 권한 정책을 만들어 공유 Power Apps 차단한 다음 해당 사용자에게 정책을 할당합니다.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="공유 앱 사용이 차단된 예제 사용자 지정 앱 사용 권한 Power Apps 스크린샷입니다.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>감사 로그를 사용하여 Microsoft Power Platform 설치 활동을 조사합니다.

사용자에 대한 감사 로그를 사용하여 Teams 앱 페이지의 동료가 기본 제공  섹션에서 Microsoft Power Platform 앱을 설치한 이벤트를 조사할 Teams. 이렇게하려면 사용자 [](./audit-log-events.md) 또는 사용자 집합에 대해 설치된 앱 Teams **이벤트(AppInstalled 작업** 아래)에 대한 감사 로그를 검색합니다.  동료가 작성한 앱을 찾으시고, 주어진 레코드의 세부 정보에서 **AppDistributionMode** 속성의 **TemplatedInstance** 값을 찾으면 됩니다. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 속성의 TemplatedInstance 값 스크린샷입니다.":::

> [!NOTE]
> 더 쉽게 필터링할 수 있도록 CSV 형식으로 감사 레코드를 내보낼 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [캔버스 앱 공유 Power Apps](/powerapps/maker/canvas-apps/share-app)
- [다른 사용자와 봇 공유](/power-virtual-agents/admin-share-bots)
- [관리 센터에서 앱 Microsoft Teams 관리](manage-apps.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [앱 제출 API를 통해 제출된 사용자 Teams 게시](submit-approve-custom-apps.md)