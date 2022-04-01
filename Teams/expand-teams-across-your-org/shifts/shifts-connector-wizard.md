---
title: Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Shifts 커넥터 마법사를 사용하여 Blue Yonder Workforce Management와 Teams Shifts를 통합하는 방법에 대해 알아보고자 합니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593699"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결

## <a name="overview"></a>개요

작업의 Shifts 커넥터 마법사를 Microsoft 365 관리 센터 WFM(인력 관리) 시스템과 Microsoft Teams Shifts 앱을 통합할 수 있습니다. 연결을 설정한 후 프런트라인 작업자는 Shifts 내에서 WFM 시스템에서 일정을 원활하게 보고 관리할 수 있습니다.

마법사는 Shifts 커넥터를 구성하고, WFM 시스템에 대한 연결을 만들고, 선택한 동기화 설정 및 팀 매핑을 적용합니다. 동기화 설정은 WFM 시스템과 Shifts 간에 동기화되는 일정 정보를 확인합니다. 팀 매핑은 WFM 사이트와 팀 간의 동기화 관계를 Teams. 기존 팀 및 새 팀에 매핑할 수 있습니다.

서로 다른 동기화 설정을 사용하여 여러 연결을 설정할 수 있습니다. 예를 들어 조직에 일정 요구 사항이 서로 다른 여러 위치가 있는 경우 각 위치에 대해 고유한 동기화 설정이 있는 연결을 만들 수 있습니다. WFM 사이트는 항상 한 팀에만 매핑될 수 있습니다. WFM 사이트가 팀에 이미 매핑된 경우 다른 팀에 매핑할 수 없습니다.

WFM 시스템을 레코드 시스템으로 사용하여 일선 작업자는 교대 근무를 보고 교환하고, 가용성을 관리하며, 디바이스의 Shifts에서 시간을 요청할 수 있습니다. 프런트라인 관리자는 WFM 시스템을 계속 사용하여 일정을 설정할 수 있습니다.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Blue Yonder Workforce Management와 Shifts 통합

현재 마법사는 [Blue Yonder에 Microsoft Teams Shifts 커넥터를 지원합니다](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). 이 커넥터를 사용하면 Shifts를 Blue Yonder Workforce Management(Blue Yonder WFM)와 통합하여 일정을 관리하고 최신으로 유지할 수 있습니다. 이 문서에서는 커넥터를 통해 Blue Yonder WFM에 대한 연결을 설정하기 위해 마법사를 실행하는 방법을 안내합니다.

> [!NOTE]
> PowerShell을 사용하여 Shifts를 Blue Yonder WFM과 통합할 수 있습니다. 자세한 내용은 [PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결합니다](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>시작하기 전에

마법사를 실행하려면 Microsoft 365 관리자 되어야 합니다.

### <a name="prerequisites"></a>필수 구성 요소
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- 매핑하려는 팀에는 일정이 없습니다. 팀에 기존 일정이 있는 경우 Blue [](#remove-schedules-from-teams-you-want-to-map) Yonder WFM 사이트를 매핑하기 전에 팀에서 일정을 제거합니다. 그렇지 않으면 중복된 교대 근무가 표시됩니다.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>매핑할 팀에서 일정 제거
<a name="remove_schedules"> </a>

> [!NOTE]
> Blue Yonder WFM 사이트를 일정이 있는 기존 팀에 매핑하는 경우 이 단계를 완료합니다. 일정이 없는 팀에 매핑하거나 매핑할 새 팀을 만드는 경우 이 단계를 건너뛸 수 있습니다.

PowerShell을 사용하여 팀에서 일정을 제거합니다.

1. 먼저 PowerShell 모듈을 설치하고 설정해야 합니다. 환경을 설정하는 [단계를 따릅니다](shifts-connector-powershell-manage.md#set-up-your-environment).
1. 다음 명령을 실행합니다.

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    매개 변수에 대한 시나리오 `EntityType` 목록을 얻었다면 [Get-CsTeamsShiftsConnectionConnector를 실행합니다](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). 예약 데이터는 지정한 날짜 및 시간 범위에 대해 제거됩니다.

자세한 내용은 [Remove-CsTeamsShiftsScheduleRecord를 참조합니다](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>마법사 실행

### <a name="get-started"></a>시작하기

1. 앱의 [왼쪽 탐색](https://admin.microsoft.com/)에서 **Microsoft 365 관리 센터 설정을 선택한** 다음 앱 및 전자 메일 섹션 **으로** 이동합니다.
1. 인력 **커넥트 시스템을 선택합니다**. 여기에서 Shifts를 WFM 시스템에 연결할 때 Shifts 커넥터 및 최전선 작업자 및 관리자 경험에 대해 자세히 알아보십시오.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="화면의 Shifts 커넥터 마법사의 세부 정보 Microsoft 365 관리 센터." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 준비가 되면 다음을 **시작**.
1. 다음 **을** 선택하여 Blue Yonder WFM 연결을 만들 수 있습니다.

### <a name="enter-connection-details"></a>연결 세부 정보 입력
<a name="connection_details"> </a>

1. 연결 세부 정보 페이지에서 연결에 고유한 이름을 지정합니다. 128자보다 길거나 특별한 문자를 사용할 수 없습니다.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="연결 설정을 보여 주며 마법사의 연결 세부 정보 페이지의 스크린샷입니다." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Blue Yonder WFM 서비스 계정 이름 및 암호 및 서비스 URL을 입력합니다.
1. 완료되면 다음을 선택하여 입력한 설정  과의 연결을 테스트합니다.

### <a name="choose-sync-settings"></a>동기화 설정 선택
<a name="sync"> </a>

동기화 설정 페이지에서 Blue Yonder WFM에서 Shifts로 동기화할 정보, 동기화 빈도 및 Shifts 사용자가 데이터를 변경할 수 있는지 여부를 선택합니다.

1. 시스템 Microsoft 365 입력합니다.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="동기화 설정을 보여 주며 마법사의 동기화 설정 페이지의 스크린샷입니다." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. 전자 **메일 알림 받는 사람 아래** 에서 이 연결에 대한 전자 메일 알림을 받는 사람을 선택하세요. 개별 사용자 및 그룹을 추가할 수 있습니다. 전자 메일 알림에는 연결 설정 상태 및 연결 설정 후 발생할 수 있는 모든 문제 또는 오류에 대한 정보가 포함되어 있습니다.
1. 동기화 설정을 선택합니다.
    1. 일정 **및 교대 근무에서** Shifts 사용자가 보거나 변경할 수 있는 Blue Yonder WFM 데이터를 선택한 다음 동기화 빈도를 설정합니다.
    2. 요청 **에서** Shifts 사용자가 보고 만들 수 있는 요청 유형을 선택해야 합니다.

    > [!IMPORTANT]
    > 열기 교대 근무, 교대 근무 요청 열기, 요청 교환 또는 시간 해제 요청을 사용하지 않도록 설정하려면 Shifts에서 기능을 숨기기 위해 해야 할 또 다른 단계가 있습니다.
    >
    > - 열기 교대 근무: **Shifts 사용자가 Blue Yonder WFM 데이터를 볼 수 없습니다.**
    > - 교환 요청: 모든 사용자에 대해 **기능이 비활성화됩니다.**
    > - 시간 끄기 요청: 모든 사용자에 **대해 기능이 비활성화됩니다.**
    >
    > 마법사를 실행한 후 이 문서의 1부에서 열린 교대 근무 사용 안 의 단계를 수행하고, 교대 근무 요청을 열 [고,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 요청 교환 및 시간 해제 요청 섹션을 수행해야 합니다.
 
1. 설정을 선택하면 연결 만들기 **를 선택합니다**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Blue Yonder Workforce Management 사이트를 팀에 매핑
<a name="sites"> </a>

Shifts에 연결할 Blue Yonder WFM 사이트를 선택합니다. 최대 100개 사이트를 선택할 수 있습니다.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Blue Yonder WFM 사이트 목록을 보여 주며 마법사의 스크린샷입니다." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> 그런 다음 선택한 각 Blue Yonder WFM 사이트를 해당 팀에 Teams. 사이트를 기존 팀에 매핑하거나 새 팀을 만들 수 있습니다.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="검색 팀 옵션을 보여 주며 새 팀 옵션을 만드는 창의 스크린샷입니다." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>사이트를 기존 팀에 매핑하는 경우

1. 사이트 이름을 선택합니다.
2. 창에서 팀을 검색한 다음 선택합니다. 이 연결의 사이트에 이미 매핑된 팀이 검색에 표시되지 않습니다.
3. 표준 시간대 및 가장 가까운 도시를 선택합니다.
4. 저장 **을** 선택한 다음 다음을 **선택합니다**.

#### <a name="to-map-a-site-to-a-new-team"></a>사이트를 새 팀에 매핑하는 경우

1. 사이트 이름을 선택합니다.
2. 창에서 새 팀 **만들기를 선택 합니다**. 브라우저에서 새 탭으로 이동하여 새 팀을 만들 수 Microsoft 365 관리 센터.
    1. 팀에 대한 이름 및 선택적 설명을 입력합니다.
    1. 하나 이상의 팀 소유자를 추가합니다. 소유자로 Microsoft 365 시스템 계정을 추가해야 합니다.
    1. 팀 구성원을 추가합니다.
    1. 팀 전자 메일 주소를 추가하고 개인 정보 설정을 선택하세요.
    1. 설정을 검토한 다음 팀 추가 **를 선택합니다**. 팀이 만들어지면 닫기 를 **선택해야 합니다**.
3. 돌아가기 검색한 다음 만든 새 팀을 선택합니다.
4. 표준 시간대 및 가장 가까운 도시를 선택합니다.
5. 저장 **을** 선택한 다음 다음을 **선택합니다**.

### <a name="review-and-finish"></a>검토 및 완료

설정을 검토합니다. 팀 매핑을 변경해야 하는 경우 편집 **을 선택하세요** . 준비가 완료되면 마쳤 **을 때를 선택합니다**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="매핑을 보여 주며 마법사의 검토 페이지의 스크린샷입니다." lightbox="../../media/shifts-connector-wizard-review.png":::

작업 ID와 함께 요청을 받았는지 확인하는 메시지가 표시됩니다. 작업 ID를 메모합니다. 연결의 설정 상태를 확인하려면 이 설정이 필요합니다.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="확인 메시지 및 작업 ID를 보여 주며 마법사 페이지의 스크린샷입니다." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

마법사는 연결을 설정하고 사이트를 선택한 팀에 매핑하는 프로세스를 시작합니다. 이 프로세스를 완료하는 데 다소 시간이 걸릴 수 있습니다. 선택한 받는 사람은 설정 상태에 대한 전자 메일 알림을 받게 됩니다.

완료 **를** 선택하여 마법사를 종료합니다.

진행 중이지만 아직 완료되지 않았습니다. 전자 메일을 확인해야 합니다. 설정 상태를 확인할 수 있는 방법에 대한 링크와 함께 요청을 받은 확인 메시지가 [](shifts-connector-powershell-manage.md#check-connection-setup-status) 표시됩니다.

> [!NOTE]
> 설정한 후 연결에서 문제가 발생하거나 오류가 발생하면 전자 메일로 알림을 받을 수 있습니다. 전자 메일의 지침에 따라 문제를 해결합니다.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>열려 있는 교대 근무를 사용하지 않도록 설정, 교대 근무 요청 열기, 요청 교환 및 시간 해제 요청

> [!IMPORTANT]
> 다음 옵션 중 하나만 선택하여 개방형 교대 근무, 교대 근무 요청 열기, 요청 교환 또는 마법사에서 시간 해제 요청을 사용하지 않도록 설정한 경우만 다음 단계를 따릅니다. 이 단계를 완료하면 Shifts의 기능이 숨겨지게됩니다.
>
> - 열기 교대 근무: **Shifts 사용자가 Blue Yonder WFM 데이터를 볼 수 없습니다.**
> - 교환 요청: 모든 사용자에 대해 **기능이 비활성화됩니다.**
> - 시간 끄기 요청: 모든 사용자에 **대해 기능이 비활성화됩니다.**
>
> 이 두 번째 단계가 없는 경우 사용자는 Shifts의 기능을 계속 볼 수 있으며, 이를 사용하려고 하면 "지원되지 않는 작업" 오류 메시지가 표시됩니다.

Shifts에서 열린 교대 근무, 요청 [교환 및 시간](/graph/api/resources/schedule?view=graph-rest-1.0) 해제 요청을 숨기기 위해 ```false``` Graph API 예약 리소스 유형을 사용하여 Blue Yonder WFM 사이트에 매핑한 각 팀에 대해 다음 매개 변수를 설정합니다.

- 교대 근무 열기: ```openShiftsEnabled```
- 교환 요청:  ```swapShiftsRequestsEnabled```
- 시간 해제 요청: ```timeOffRequestsEnabled```

Shifts에서 열기 **교** 대 근무 요청을 숨기기 위해 shifts에서 설정 이동한 다음, 열기 교대 근무 **설정을 해제합니다**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>연결을 변경해야 하는 경우
<a name="update_connection"> </a>

연결이 설정된 후 PowerShell을 사용하여 변경합니다. 예를 들어 동기화 설정을 업데이트하고, 팀 매핑을 업데이트하고, 연결에 대한 동기화를 사용하지 않도록 설정할 수 있습니다. 단계별 지침은 [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>관련 기사

- [Shifts 커넥터](shifts-connectors.md)
- [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다.](shifts-connector-powershell-manage.md)
- [앱에서 Shifts 앱을 Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
