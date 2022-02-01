---
title: 교대 근무 관리를 위한 일정 소유자 관리
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: 일정 관리를 위해 교대 근무 소유자를 관리하는 방법에 대해 자세히 알아보습니다. 팀 구성원의 권한을 일정 소유자로 승강하기 위해 정책을 설정할 수 있습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12cf33f193e7f1d1a976e5cde8612df19108cb69
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288636"
---
# <a name="schedule-owner-for-shift-management"></a>교대 근무 관리 예약 소유자

## <a name="overview"></a>개요

소유자 일정 기능을 사용하면 팀 구성원의 권한을 상승하여 직원을 팀 소유자로 만들지 않고 일정을 관리할 수 있습니다. 일정 소유자 권한을 사용하여 직원은 팀 채널 업데이트, 편집 또는 삭제와 같은 다른 팀 속성을 수정할 수 없이 팀의 일정을 관리할 수 있습니다.

일정 소유자 권한이 있는 사용자는 무엇을 할 수 있나요?

- 팀의 교대 근무 할당을 관리하기 위해 일정을 만들고, 편집하고, 게시합니다.
- 교대 근무를 교환하고 열려 있는 교대 근무를 요청하는 요청을 포함하여 교대 근무 요청을 보고 승인합니다.
- Shifts에서 설정을 관리하여 팀에 대한 특정 기능을 사용하도록 설정합니다.
- 직원 급여를 처리하기 위해 팀의 작업표를 보고 수정합니다.

## <a name="why-schedule-owner"></a>소유자 예약 이유

일정 소유자 기능이 없는 경우 매일 비즈니스 함수가 중단될 수 있습니다. 팀 소유자가 팀을 운영하는 데 도움이 되는 반면, 매일의 일과표를 담당하는 사람이 아닐 수도 있습니다. 이 경우 일정 관리 책임만 다른 팀 구성원에게 양도하면 팀 내에서 매일 작업을 간소화하고 동일한 액세스 권한을 갖는 두 팀 구성원의 혼동을 제거합니다.

## <a name="scenario"></a>시나리오

다음은 조직에서 소유자 예약 기능을 사용하는 방법의 예입니다.

부서 관리자가 저장소 관리자에게 직접 보고하는 대규모 조직에서 작업합니다. 저장소 관리자는 회사 내에서 더 많은 권한을 가집니다. Shifts의 팀 소유자입니다. 반면 부서 관리자는 Shifts에 팀 구성원으로만 추가됩니다. 매장 관리자는 부서 관리자보다 더 높은 연수성을 지만 부서 관리자가 팀의 직원의 하루 일과를 처리하는 것이 더 타당합니다.

*일정 소유자가 없는* 경우 부서 관리자는 팀 소유자와 정확히 동일한 권한을 부여해야 합니다. 최근에는 부서 관리자가 정보를 이동하고 채널 이름을 변경하는 경우 매장 관리자의 작업으로 인해 문제가 발생했습니다. 저장소 관리자는 부서 관리자가 일정을 구성할 수 있도록 하지만 Shifts 외부에서 팀에서 다른 것을 변경할 수 있는 것은 원하지 않습니다.

*일정 소유자를* 사용하여 부서 관리자는 다른 팀 소유자 권한 없이 예약 권한을 부여할 수 있습니다.

## <a name="manage-schedule-ownership"></a>일정 소유권 관리

관리자는 정책을 사용하여 조직의 일정 관리 소유권을 제어합니다. 다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>예제 1

여기서는 예약 소유자 기능이 켜져 있는 ScheduleOwnerPolicy라는 새 정책을 생성합니다.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>예제 2

이 예제에서는 ScheduleOwnerPolicy라는 정책을 remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>관련 기사

- [Teams에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [교대 근무자에 대한 교대 근무 기반 액세스 관리 Teams](manage-shift-based-access-flw.md) 
