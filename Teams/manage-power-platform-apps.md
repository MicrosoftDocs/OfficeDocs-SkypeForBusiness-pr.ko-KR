---
title: Microsoft Teams 관리 센터에서 Microsoft Power Platform 앱 관리
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 관리 센터에서 Microsoft Power Platform을 사용하여 구축된 사용자 지정 앱에 대한 액세스를 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831298"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 Microsoft Power Platform 앱 관리

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams의 Microsoft Power Platform 앱

이 문서에서는 Microsoft Teams 관리 센터에서 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 앱을 관리하는 방법에 대한 개요를 제공합니다.

> [!NOTE]
> 이 문서는 Power Apps 또는 Power Virtual Agent를 사용하여 조직의 제작자에서 만든 사용자 지정 앱에 적용됩니다. 이러한 사용자 지정 앱은 Teams에 자동으로 추가됩니다. 이 문서는 앱 페이지에서 설치되거나 앱 설정 정책을 통해 Teams에 고정된 Power Apps 앱 또는 Power Virtual Agents 앱에는 적용되지 않습니다. 앱 관리 페이지에서 앱 사용 권한 정책 [](manage-apps.md) 및 앱 설정 정책을 사용하여 다른 앱과 [같은](teams-app-permission-policies.md)앱을 [관리합니다.](teams-app-setup-policies.md)

[Power Apps는](https://powerapps.microsoft.com) 조직의 제작자는 비즈니스 데이터에 연결하는 사용자 지정 앱을 빌드하는 데 사용할 수 있는 코드가 없는 애플리케이션 개발 환경입니다. [Power Virtual Agent는](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 제작자에서 강력한 봇을 만들 수 있는 코드 없는 봇 구축 환경입니다. Microsoft Power Platform 앱을 Teams에 통합하면 조직은 비즈니스 프로세스를 간소화하고, 변화하는 비즈니스 요구에 더 빠르게 대응하여 더 큰 공동 작업을 추진하고, 사용자 지정 솔루션을 만들고 공유하여 생산성을 향상할 수 있습니다.  

조직의 제작자에서 만든 Microsoft Power Platform 앱은 Teams에 자동으로 추가됩니다. 확인자는 [Power Apps의](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 공유 기능 및 [Power Virtual Agent의](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)공유 기능을 사용하여 앱에 액세스할 수 있는 사용자들을 제어할 수 있습니다.

Microsoft Power Platform 앱을 만들거나 공유할 때 사용자는 동료가 작성한 조직 **** 이름에 대한 작성으로 이동하여 앱 페이지에 앱을 보고  >  **설치할 수 있습니다.** (앱이 생성되거나 공유된 후 앱이 여기에 표시될 때 몇 분 정도 걸릴 수 있습니다.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="동료가 기본 제공에 나열한 Microsoft Power Platform 앱을 보여주는 앱 페이지의 스크린샷":::

앱이 다음 조건 중  하나를 충족하는 경우 사용자가 동료가 구축한 앱을 볼 수 있습니다.

|Power Apps |Power Virtual Agent  |
|---------|---------|
|<ul><li>사용자가 앱을 만들었다.</li><li>앱이 사용자와 직접 공유됩니다.</li><li>사용자가 최근에 앱을 사용했다. </li></ul>| <ul><li>사용자가 봇을 만들었다.</li><li>봇은 사용자가 멤버인 팀이 소유합니다. </li></ul>        |

사용자는 다른 Teams 앱을 설치하는 방법과 동일한 방식으로 Microsoft Power Platform 앱을 설치합니다. 사용자는 권한이 있는 컨텍스트(예: 소유한 팀, 사용자가 일부인 채팅 또는 개인 범위)에만 앱을 설치할 수 있습니다.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 Microsoft Power Platform 앱에 대한 액세스 관리

관리자는 Teams의 앱 페이지에서 동료가 Microsoft Power  Platform 앱을 기본 제공에 나열할지 여부를 제어할 수 있습니다. Power Apps에서 만든 모든 앱 또는 앱 관리 페이지의 구성 수준에서 또는 앱 사용 권한 [](manage-apps.md) 정책을 사용하는 특정 사용자에 대해 Power Virtual Agent에서 만든 모든 앱을 전체적으로 차단하거나 허용할 [수 있습니다.](teams-app-permission-policies.md)

조직의 **앱 스토어에서** 공유 Power Apps 및 공유 **Power Virtual Agent 앱** 앱은 해당 특정 플랫폼에서 만든 모든 앱을 대표합니다. 이러한 앱 중 하나 또는 둘 다를 구성 수준에서 차단하거나 특정 사용자에 대해 차단하는 경우 해당 사용자는 동료가 구축한 플랫폼의 앱을 볼 수 없습니다. Teams에는 앱을 설치할 수 없습니다.   

Power Apps 및 Power Virtual Agent에서 만든 모든 앱에 대한 액세스를 제어할 수 있지만 개별 앱을 허용하거나 차단할 수 없습니다. 제작자는 Power Apps 및 Power Virtual Agent 내에서 공유 기능을 통해 만든 앱에 액세스할 수 있는 사용자로 결정됩니다. 사용자가 Power Virtual Agents에서 만든 앱을 사용자와 공유하고 해당 사용자에 대한 공유 **Power Virtual Agents 앱을** 차단한 경우 사용자는 Teams의 해당 플랫폼에서 앱을 보거나 설치할 수 없습니다.

사용자가 Power Apps 또는 Power Virtual Agent에서 앱에 액세스할 수 있도록 허용한 다음 사용자가 이러한 플랫폼 중 하나 또는 둘 다에서 앱에 액세스하지 못하도록 차단하는 경우 사용자는 앱 또는 앱을 차단하기 전에 설치된 Microsoft Power Platforms 앱에 계속 액세스하고 사용할 수 있습니다. 그러나 사용자는 더 이상 동료가 기본 제공한 플랫폼에서 앱을 보거나 **설치할 수 없습니다.**

> [!NOTE]
> 앱 **관리 페이지의** 사용자 지정 앱 조직 [](manage-apps.md) 전체 앱 설정과의 상호 작용 허용은 조직의 모든 사용자에 적용하고 사용자 지정 앱과 상호 작용할 수 있는지 여부를 관리합니다. 전체 앱 설정은 모든 사용자에 대한 동작을 관리하고 사용자에게 할당된 다른 모든 앱 사용 권한 정책을 수정합니다. 기본적으로 이 설정은 켜져 있습니다. 이 설정을 해제하면 조직의 사용자는 Microsoft Power Platform 앱을 비롯한 사용자 지정 앱을 보거나 설치할 수 없습니다. 자세한 내용은 전체적인 앱 설정 [관리를 참조하세요.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>조직의 Microsoft Power Platform 앱 허용 또는 차단

기본적으로 공유 **Power Apps** 및 공유 Power Virtual Agent **앱은** 조직의 모든 Teams 사용자에게 허용됩니다. Microsoft Teams 관리 센터의 앱 관리 [](manage-apps.md) 페이지에서 해당 앱을 차단하거나 허용할 수 있습니다.  

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams 앱 관리**  >  **앱으로 이동하세요.** 페이지에 액세스하려면 전역 관리자 또는 Teams 서비스 관리자해야 합니다.
2. 앱 목록에서 다음 중 하나를 실행합니다.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="공유 Microsoft Power Platform 앱을 보여 주며 앱 관리 페이지의 스크린샷":::

    - 조직의 모든 사용자에 대해 Power Apps 또는 Power Virtual Agent에서 만든 앱을 차단하려면 공유 **Power Apps** 또는 공유 **Power Virtual Agent 앱을** 검색하고 선택한 다음 차단을 **클릭합니다.**
    - Power Apps 또는 Power Virtual Agent에서 만든 앱을 조직의 모든 사용자에 대해 허용하려면 공유 **Power Apps** 또는 공유 **Power Virtual Agent 앱을** 검색하고 선택한 다음 **허용을 클릭합니다.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>특정 사용자에 대한 Microsoft Power Platform 앱 허용 또는 차단

조직의 특정 사용자가 Power Apps 또는 Power Virtual Agent에서 만든 앱에 액세스할 수 있도록 허용하거나 차단하려면 하나 이상의 사용자 지정 앱 사용 권한 정책을 만들고 [할당합니다.](teams-app-permission-policies.md) 

예를 들어 특정 사용자가 Power Apps에서 만든 앱에 액세스할 수 없는 경우 공유 **Power Apps를** 차단하는 사용자 지정 앱 사용 권한 정책을 만든 다음 해당 사용자에게 정책을 할당합니다.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="공유 Power Apps가 차단된 사용자 지정 앱 사용 권한 정책 예제 스크린샷":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>감사 로그를 사용하여 Microsoft Power Platform 설치 활동 조사

Teams에 대한 감사 로그를 사용하여 사용자가 Teams의 앱 페이지의  동료에 의해 구축된 섹션에서 Microsoft Power Platform 앱을 설치한 이벤트를 조사할 수 있습니다. 이렇게하려면 사용자 [](https://docs.microsoft.com/microsoftteams/audit-log-events) 또는 사용자 집합에 대해 설치된 앱 **Teams** **이벤트(AppInstalled** 작업 아래)에 대한 감사 로그를 검색합니다. 동료가 **작성한** 앱에서 설치된 앱을 찾으면 주어진 레코드의 세부 정보에서 **AppDistributionMode** 속성의 **TemplatedInstance** 값을 찾아야 합니다. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 속성의 TemplatedInstance 값 스크린샷":::

> [!NOTE]
> 더 쉽게 필터링할 수 있도록 CSV 형식으로 감사 레코드를 내보낼 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [Power Apps에서 캔버스 앱 공유](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [다른 사용자와 봇 공유](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [Teams 앱 제출 API를 통해 제출된 사용자 지정 앱 게시](submit-approve-custom-apps.md)
