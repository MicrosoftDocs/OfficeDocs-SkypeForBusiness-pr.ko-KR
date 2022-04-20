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
description: Shifts 커넥터 마법사를 사용하여 Teams Shifts를 Blue Yonder Workforce Management와 통합하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593699"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결

## <a name="overview"></a>개요

Microsoft 365 관리 센터 Shifts 커넥터 마법사를 사용하면 Microsoft Teams Shifts 앱을 WFM(인력 관리) 시스템과 통합할 수 있습니다. 연결을 설정한 후 일선 작업자는 Shifts 내에서 WFM 시스템에서 일정을 원활하게 보고 관리할 수 있습니다.

마법사는 Shifts 커넥터를 구성하고, WFM 시스템에 대한 연결을 만들고, 선택한 동기화 설정 및 팀 매핑을 적용합니다. 동기화 설정은 WFM 시스템과 Shifts 간에 동기화되는 일정 정보를 결정합니다. 팀 매핑은 Teams WFM 사이트와 팀 간의 동기화 관계를 정의합니다. 기존 팀과 새 팀에 매핑할 수 있습니다.

각각 다른 동기화 설정을 사용하여 여러 연결을 설정할 수 있습니다. 예를 들어 조직에 일정 요구 사항이 다른 여러 위치가 있는 경우 각 위치에 대해 고유한 동기화 설정을 사용하여 연결을 만듭니다. WFM 사이트는 지정된 시간에 한 팀에만 매핑할 수 있습니다. WFM 사이트가 이미 팀에 매핑된 경우 다른 팀에 매핑할 수 없습니다.

WFM 시스템을 기록 시스템으로 사용하면 일선 작업자가 교대 근무를 보고 교환하고, 가용성을 관리하고, 디바이스의 Shifts에서 휴가를 요청할 수 있습니다. 최전방 관리자는 WFM 시스템을 계속 사용하여 일정을 설정할 수 있습니다.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Blue Yonder Workforce Management와 교대 근무 통합

현재 마법사는 [Blue Yonder용 Microsoft Teams Shifts 커넥터를 지원합니다](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). 이 커넥터를 사용하면 Shifts를 Blue Yonder WFM(Blue Yonder Workforce Management)과 통합하여 일정을 관리하고 최신 상태로 유지할 수 있습니다. 이 문서에서는 마법사를 실행하여 커넥터를 통해 Blue Yonder WFM에 대한 연결을 설정하는 방법을 안내합니다.

> [!NOTE]
> PowerShell을 사용하여 Shifts를 Blue Yonder WFM과 통합할 수도 있습니다. 자세한 내용은 [PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결하는 방법을](shifts-connector-blue-yonder-powershell-setup.md) 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

마법사를 실행하려면 Microsoft 365 전역 관리자여야 합니다.

### <a name="prerequisites"></a>필수 구성 요소
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- 매핑하려는 팀에는 일정이 없습니다. 팀에 기존 일정이 있는 경우 Blue Yonder WFM 사이트를 매핑하기 전에 [팀에서 일정을 제거](#remove-schedules-from-teams-you-want-to-map) 합니다. 그렇지 않으면 중복 교대조가 표시됩니다.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>매핑하려는 팀에서 일정 제거
<a name="remove_schedules"> </a>

> [!NOTE]
> Blue Yonder WFM 사이트를 일정이 있는 기존 팀에 매핑하는 경우 이 단계를 완료합니다. 일정이 없는 팀에 매핑하거나 매핑할 새 팀을 만드는 경우 이 단계를 건너뛸 수 있습니다.

PowerShell을 사용하여 팀에서 일정을 제거합니다.

1. 먼저 PowerShell 모듈을 설치하고 설정해야 합니다. 단계에 따라 [환경을 설정합니다](shifts-connector-powershell-manage.md#set-up-your-environment).
1. 다음 명령을 실행합니다.

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    매개 변수에 대한 `EntityType` 시나리오 목록을 얻으려면 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)를 실행합니다. 지정한 날짜 및 시간 범위에 대한 일정 데이터가 제거됩니다.

자세한 내용은 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)를 참조하세요.

## <a name="run-the-wizard"></a>마법사 실행

### <a name="get-started"></a>시작하기

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/) 왼쪽 탐색 영역에서 **설치** 프로그램을 선택한 다음 **앱 및 전자 메일** 섹션으로 이동합니다.
1. **인력 관리 시스템 커넥트** 선택합니다. 여기서는 Shifts를 WFM 시스템에 연결할 때 Shifts 커넥터 및 최전방 작업자 및 관리자 환경에 대해 자세히 알아볼 수 있습니다.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Microsoft 365 관리 센터 Shifts 커넥터 마법사의 세부 정보 페이지 스크린샷" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 준비가 되면 **시작** 선택합니다.
1. **다음** 을 선택하여 Blue Yonder WFM 연결을 만듭니다.

### <a name="enter-connection-details"></a>연결 세부 정보 입력
<a name="connection_details"> </a>

1. 연결 세부 정보 페이지에서 연결에 고유한 이름을 지정합니다. 128자를 초과하거나 특수 문자를 사용할 수 없습니다.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="연결 설정을 보여 주는 마법사의 연결 세부 정보 페이지 스크린샷" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Blue Yonder WFM 서비스 계정 이름 및 암호 및 서비스 URL을 입력합니다.
1. 완료되면 **다음** 을 선택하여 입력한 설정으로 연결을 테스트합니다.

### <a name="choose-sync-settings"></a>동기화 설정 선택
<a name="sync"> </a>

동기화 설정 페이지에서 Blue Yonder WFM에서 Shifts로 동기화할 정보, 동기화 빈도 및 Shifts 사용자가 데이터를 변경할 수 있는지 여부를 선택합니다.

1. Microsoft 365 시스템 계정을 입력합니다.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="동기화 설정을 보여 주는 마법사의 동기화 설정 페이지 스크린샷." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. **전자 메일 알림 받는 사람** 아래에서 이 연결에 대한 전자 메일 알림을 받는 사람을 선택합니다. 개별 사용자 및 그룹을 추가할 수 있습니다. 이메일 알림에는 연결 설정 상태 및 연결 설정 후 발생할 수 있는 문제 또는 오류에 대한 정보가 포함됩니다.
1. 동기화 설정을 선택합니다.
    1. **일정 및 교대조** 에서 Shifts 사용자가 보거나 변경할 수 있는 Blue Yonder WFM 데이터를 선택한 다음 동기화 빈도를 설정합니다.
    2. **요청** 에서 Shifts 사용자가 보고 만들 수 있는 요청 유형을 선택합니다.

    > [!IMPORTANT]
    > 열린 교대 근무, 열린 교대 근무 요청, 교환 요청 또는 시간 쉬는 요청을 사용하지 않도록 설정하기 위해 다음 옵션 중 원하는 옵션을 선택한 경우 Shifts에서 기능을 숨기기 위해 수행해야 하는 또 다른 단계가 있습니다.
    >
    > - 교대 근무 열기: **교대 근무 사용자는 Blue Yonder WFM 데이터를 볼 수 없습니다**.
    > - 교환 요청: **모든 사용자에 대해 기능이 비활성화됨**
    > - 시간 제한 요청: **모든 사용자에 대해 기능이 비활성화됨**
    >
    > 마법사를 실행한 후 이 문서의 뒷부분에 있는 [열린 교대 근무 사용 안 함, 교대 근무 요청 열기, 요청 교환 및 시간 끄기 요청](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 섹션의 단계를 수행해야 합니다.
 
1. 설정 선택을 마쳤으면 **연결 만들기** 를 선택합니다.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Blue Yonder Workforce Management 사이트를 팀에 매핑
<a name="sites"> </a>

Shifts에 연결하려는 Blue Yonder WFM 사이트를 선택합니다. 최대 100개의 사이트를 선택할 수 있습니다.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Blue Yonder WFM 사이트 목록을 보여 주는 마법사의 스크린샷" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> 그런 다음 선택한 각 Blue Yonder WFM 사이트를 Teams 팀에 매핑합니다. 사이트를 기존 팀에 매핑하거나 새 팀을 만들 수 있습니다.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="검색 팀 옵션 및 새 팀 만들기 옵션을 보여 주는 창의 스크린샷." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>기존 팀에 사이트를 매핑하려면

1. 사이트 이름을 선택합니다.
2. 창에서 팀을 검색한 다음 선택합니다. 이 연결의 사이트에 이미 매핑된 팀은 검색에 표시되지 않습니다.
3. 표준 시간대와 가장 가까운 도시를 선택합니다.
4. **저장****을 선택한 다음** 다음을 선택합니다.

#### <a name="to-map-a-site-to-a-new-team"></a>사이트를 새 팀에 매핑하려면

1. 사이트 이름을 선택합니다.
2. 창에서 **새 팀 만들기를** 선택합니다. 브라우저의 새 탭으로 이동하여 Microsoft 365 관리 센터 새 팀을 만들 수 있습니다.
    1. 팀의 이름과 설명(선택 사항)을 입력합니다.
    1. 하나 이상의 팀 소유자를 추가합니다. Microsoft 365 시스템 계정을 소유자로 추가해야 합니다.
    1. 팀 구성원을 추가합니다.
    1. 팀 전자 메일 주소를 추가하고 개인 정보 설정을 선택합니다.
    1. 설정을 검토한 다음 **팀 추가** 를 선택합니다. 팀이 만들어지면 **닫기를** 선택합니다.
3. 마법사로 돌아가기, 검색한 다음, 만든 새 팀을 선택합니다.
4. 표준 시간대와 가장 가까운 도시를 선택합니다.
5. **저장****을 선택한 다음** 다음을 선택합니다.

### <a name="review-and-finish"></a>검토 및 완료

설정을 검토합니다. 팀 매핑을 변경해야 하는 경우 **편집** 을 선택하여 변경합니다. 준비가 되면 **마침** 을 선택합니다.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="매핑을 보여 주는 마법사의 검토 페이지 스크린샷." lightbox="../../media/shifts-connector-wizard-review.png":::

작업 ID와 함께 요청을 받았는지 확인하는 메시지가 표시됩니다. 작업 ID를 기록해 둡니다. 연결의 설정 상태를 확인하는 데 필요합니다.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="확인 메시지 및 작업 ID를 보여 주는 마법사 페이지의 스크린샷." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

마법사는 연결을 설정하고 선택한 팀에 사이트를 매핑하는 프로세스를 시작합니다. 이 프로세스를 완료하는 데 다소 시간이 걸릴 수 있습니다. 선택한 받는 사람은 설정 상태에 대한 이메일 알림을 받게 됩니다.

**완료** 를 선택하여 마법사를 종료합니다.

당신은 당신의 방법에있어하지만 당신은 아직 완료되지 않았습니다! 전자 메일을 확인해야 합니다. 설치 상태를 확인하는 방법에 대한 [링크](shifts-connector-powershell-manage.md#check-connection-setup-status) 와 함께 요청을 받았다는 확인 메시지가 표시됩니다.

> [!NOTE]
> 설정 후 연결에서 문제 또는 오류가 발생하면 전자 메일로 알림을 받게 됩니다. 전자 메일의 지침에 따라 문제를 해결합니다.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>열린 교대 근무를 사용하지 않도록 설정, 교대 근무 요청 열기, 요청 교환 및 쉬는 시간 요청

> [!IMPORTANT]
> 다음 옵션 중 원하는 옵션을 선택하여 마법사에서 열린 교대 근무, 열린 교대 근무 요청, 교환 요청 또는 시간 쉬는 요청을 사용하지 않도록 설정한 경우에만 다음 단계를 수행합니다. 이 단계를 완료하면 Shifts의 기능이 숨겨지게 됩니다.
>
> - 교대 근무 열기: **교대 근무 사용자는 Blue Yonder WFM 데이터를 볼 수 없습니다**.
> - 교환 요청: **모든 사용자에 대해 기능이 비활성화됨**
> - 시간 제한 요청: **모든 사용자에 대해 기능이 비활성화됨**
>
> 이 두 번째 단계가 없으면 사용자는 Shifts의 기능을 계속 볼 수 있으며 이를 사용하려고 하면 "지원되지 않는 작업" 오류 메시지가 표시됩니다.

Shifts에서 열린 교대 근무, 교환 요청 및 시간 끄기 요청을 숨기려면 Graph API [일정 리소스 유형을](/graph/api/resources/schedule?view=graph-rest-1.0) 사용하여 Blue Yonder WFM 사이트에 매핑한 각 팀에 대해 다음 매개 변수 ```false``` 를 설정합니다.

- 교대 근무 열기: ```openShiftsEnabled```
- 교환 요청:  ```swapShiftsRequestsEnabled```
- 시간 제한 요청: ```timeOffRequestsEnabled```

Shifts에서 열린 교대 근무 요청을 숨기려면 Shifts의 **설정** 이동한 다음 **교대 근무 열기** 설정을 끕니다.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>연결을 변경해야 하는 경우
<a name="update_connection"> </a>

연결이 설정되면 PowerShell을 사용하여 변경합니다. 예를 들어 동기화 설정, 팀 매핑을 업데이트하고 연결에 대한 동기화를 사용하지 않도록 설정할 수 있습니다. 단계별 지침은 [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>관련 기사

- [Shifts 커넥터](shifts-connectors.md)
- [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 교대 근무 연결 관리](shifts-connector-powershell-manage.md)
- [Teams Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
