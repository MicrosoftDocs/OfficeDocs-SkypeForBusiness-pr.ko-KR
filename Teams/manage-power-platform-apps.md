---
title: Microsoft 팀 관리 센터에서 전원 플랫폼 앱 관리
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀 관리 센터에서 Power Platform 앱에 대 한 액세스를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 687d8df929150cdc38795a13ba06687ed7e42b2b
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650961"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터에서 전원 플랫폼 앱 관리

## <a name="power-platform-apps-in-teams"></a>팀의 파워 플랫폼 앱

이 문서에서는 Microsoft 팀 관리 센터에서 팀에 추가 된 [파워 플랫폼](https://powerplatform.microsoft.com/) 앱을 관리 하는 방법에 대해 간략하게 설명 합니다.

[Power Apps](https://powerapps.microsoft.com) 는 조직의 결정권자가 비즈니스 데이터에 연결 하는 사용자 지정 앱을 작성 하는 데 사용할 수 있는 낮은 코드/비 코드 응용 프로그램 개발 환경입니다. [파워 가상 에이전트](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 는 의사 결정권자가 강력한 인공 지능을 만들 수 있는 비 코드 봇 빌딩 환경입니다. 조직에서는 강력한 플랫폼 앱을 팀에 통합 하 여 더 많은 공동 작업을 가능 하 게 하는 비즈니스 프로세스를 간소화 하 고, 생산성을 높이고 사용자 지정 솔루션을 만들고 공유 해 보세요.  

조직에서 결정권자가 만든 플랫폼 앱이 자동으로 팀에 추가 됩니다. 결정권자는 power [Apps의 공유 기능](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 을 사용 하 여 앱에 액세스할 수 있는 사용자와 [power Virtual agent의 공유 기능](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)을 제어할 수 있습니다.

Power Platform 앱을 만들거나 공유 하는 경우, 사용자는 동료 들이 작성 한 ** *조직 이름*에 대 한 빌드**를 수행 하 여 앱 페이지에서 파일을 보고 설치할 수 있습니다  >  **Built by your colleagues**. 앱이 여기에 표시 되도록 앱을 만들거나 공유 하는 데 몇 분 정도 걸릴 수 있습니다.

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="동료의 빌드 목록에 나열 된 파워 플랫폼 앱을 보여 주는 앱 페이지 스크린샷":::

앱이 다음 조건 중 하나를 충족 하는 경우 사용자는 **동료에 의해 기본으로 제공** 되는 전원 플랫폼 앱을 볼 수 있습니다.

|Power Apps |파워 가상 에이전트  |
|---------|---------|
|<ul><li>사용자가 앱을 만들었습니다.</li><li>앱이 사용자와 직접 공유 되었습니다.</li><li>사용자가 최근에 앱을 사용 했습니다. </li></ul>| <ul><li>사용자가 봇을 만들었습니다.</li><li>봇은 사용자가 소속 된 팀에서 소유 합니다. </li></ul>        |

사용자가 다른 팀 앱을 설치 하는 것과 동일한 방식으로 전원 플랫폼 앱을 설치 합니다. 사용자는 자신이 소유한 팀, 자신이 속한 채팅, 개인 범위 등 사용 권한이 있는 컨텍스트에만 앱을 설치할 수 있다는 점에 유의 하세요.

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터의 파워 플랫폼 앱에 대 한 액세스 관리

관리자는 팀의 앱 페이지에서 **동료에 의해 기본으로 제공** 되는 플랫폼 앱이 표시 되는지 여부를 제어할 수 있습니다. Power app에서 만든 모든 앱 또는 앱 [관리](manage-apps.md) 페이지의 조직 수준에서 직접 만든 모든 앱 또는 [앱 권한 정책을](teams-app-permission-policies.md)사용 하는 특정 사용자에 대해 일괄적으로 차단 하거나 허용할 수 있습니다.

조직의 앱 스토어에 있는 **공유 Power Apps** 및 **공유 파워 가상 에이전트 앱** 앱은 해당 특정 플랫폼에서 만든 모든 앱을 나타냅니다. 조직 수준에서 이러한 앱 중 하나 또는 둘 다를 차단 하거나 특정 사용자의 경우 해당 사용자가 **동료에 의해 빌드된** 플랫폼의 앱을 볼 수 없으며 팀에 설치할 수 없습니다.  

Power Apps 및 Power Virtual Agent에서 만든 모든 앱에 대 한 액세스는 제어할 수 있지만 개별 앱을 허용 하거나 차단 하는 것은 불가능 합니다. 결정권자는 Power App 및 Power Virtual Agent 내에서 공유 기능을 통해 자신이 만든 앱에 액세스할 수 있는 사용자를 결정 합니다. 작성자가 사용자와 파워 가상 에이전트에서 만든 앱을 공유 하 고 해당 사용자에 대 한 **공유 파워 가상 에이전트 앱** 을 차단한 경우 사용자는 해당 플랫폼에서 팀으로 앱을 보거나 설치할 수 없게 됩니다.

사용자가 Power App 또는 Power Virtual Agent의 앱에 액세스할 수 있는 경우 사용자가 이러한 플랫폼 중 하나 또는 둘 다에서 앱에 액세스 하지 못하도록 차단 하면 앱 또는 앱을 차단 하기 전에 사용자가 설치한 Power 플랫폼용 앱을 계속 액세스 하 여 사용할 수 있습니다. 그러나 사용자는 동료 들이 **만든**플랫폼의 앱을 더 이상 보거나 설치할 수 없습니다.

> [!NOTE]
> [앱 관리](manage-apps.md) 페이지의 조직 전체의 **사용자 지정 앱과 상호 작용 허용** 이 설정이 조직의 모든 사용자에 게 적용 되며 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어 합니다. 조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다. 이 설정은 기본적으로 설정 되어 있습니다. 이 설정을 끄면 조직의 사용자가 파워 플랫폼 앱을 포함 하 여 사용자 지정 앱을 보거나 설치할 수 없습니다. 자세히 알아보려면 [조직 전체 앱 설정 관리](manage-apps.md#manage-org-wide-app-settings)를 참조 하세요.

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a>조직의 파워 플랫폼 앱 허용 또는 차단

기본적으로 조직의 모든 팀 사용자가 **공유 Power Apps** 및 **공유 파워 가상 에이전트 앱** 을 사용할 수 있습니다. Microsoft 팀 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직 수준에서 해당 항목을 차단 하거나 허용할 수 있습니다.  

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다. 페이지에 액세스 하려면 전역 관리자 또는 팀 서비스 관리자 여야 합니다.
2. 앱 목록에서 다음 중 하나를 수행 합니다.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="공유 전원 플랫폼 앱이 표시 된 앱 관리 페이지 스크린샷":::

    - Power Apps 또는 조직의 모든 사용자에 대해 Power Virtual Agent에서 만든 앱을 차단 하려면 **공유 Power apps** 또는 **공유 파워 가상 에이전트 앱**을 검색 하 여 선택한 다음 **block**을 클릭 합니다.
    - Power App에서 만든 앱 또는 조직의 모든 사용자에 대 한 파워 가상 에이전트를 허용 하려면 **공유 Power apps** 또는 **공유 파워 가상 에이전트 앱**을 검색 하 여 선택한 다음 **허용**을 클릭 합니다.

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a>특정 사용자에 대 한 파워 플랫폼 앱 허용 또는 차단

조직의 특정 사용자가 Power App 또는 Power Virtual Agent에서 만든 앱에 액세스 하는 것을 허용 하거나 차단 하려면 하나 이상의 사용자 지정 [앱 권한 정책을](teams-app-permission-policies.md)만들고 할당 합니다. 

예를 들어 Power Apps에서 만든 앱에 특정 사용자가 액세스 하는 것을 차단 하려면 **공유 Power 앱**을 차단 하는 사용자 지정 앱 권한 정책을 만든 다음 해당 사용자에 게 정책을 할당 합니다.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="공유 Power Apps가 차단 된 사용자 지정 앱 권한 정책 예제 스크린샷":::

### <a name="use-audit-logs-to-investigate-power-platform-installation-activity"></a>감사 로그를 사용 하 여 전원 플랫폼 설치 활동 조사

팀에 대 한 감사 로그를 사용 하 여 사용자가 팀의 앱 페이지에서 **기본으로 제공** 되는 동료 섹션의 전원 플랫폼 앱을 설치한 이벤트를 조사할 수 있습니다. 이렇게 하려면 사용자 또는 사용자 집합에 대해 설치 된 **앱** 팀 이벤트 ( **appinstalled** 작업 아래)에 대 한 [감사 로그를 검색 합니다](https://docs.microsoft.com/microsoftteams/audit-log-events) . **동료가 기본으로**설치 된 앱을 찾으려면 지정 된 레코드의 세부 정보에서 **AppDistributionMode** 속성의 **TemplatedInstance** 값을 찾습니다. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 속성의 TemplatedInstance 값 스크린샷":::

> [!NOTE]
> 감사 레코드를 CSV 형식으로 내보내 필터링을 쉽게 수행할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [Power Apps에서 캔버스 앱 공유](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [다른 사용자와 인공 지능 공유](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Microsoft 팀 관리 센터에서 앱 관리](manage-apps.md)
- [Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
- [팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시](submit-approve-custom-apps.md)
