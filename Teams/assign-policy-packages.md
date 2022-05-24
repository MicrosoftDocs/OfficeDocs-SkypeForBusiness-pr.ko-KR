---
title: 사용자 및 그룹에 정책 패키지 할당
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 사용자 및 그룹에 정책 패키지를 할당하는 다양한 방법을 알아봅니다.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 48391db005ca7d40081c0aeb22f71be58fcc9f9f
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646527"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>사용자 및 그룹에 정책 패키지 할당

이 문서에서는 Microsoft Teams 사용자 및 그룹에 정책 패키지를 할당하는 다양한 방법을 검토합니다. 읽기 전에 [시작 - Teams 정책 할당](policy-assignment-overview.md)을 읽었는지 확인합니다.

> [!NOTE]
> 사용자 지정 정책 패키지 할당을 받으려면 각 사용자에게 고급 통신 추가 기능이 필요합니다. 자세한 내용은 [Microsoft Teams를 위한 고급 통신 추가 기능](/microsoftteams/teams-add-on-licensing/advanced-communications)을 참조하세요.

## <a name="assign-a-policy-package-to-users"></a>사용자에게 정책 패키지 할당

Teams 정책 패키지는 조직에서 동일하거나 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다. 각 정책 패키지는 사용자 역할을 중심으로 설계되었으며 해당 역할에 대한 일반적인 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다. 정책 패키지의 몇 가지 예로는 Education(교사) 패키지 및 의료(임상 작업자) 패키지가 있습니다. 자세한 내용은 [Teams 정책 패키지 관리를](manage-policy-packages.md) 참조하세요.

### <a name="assign-a-policy-package-to-one-user"></a>한 사용자에게 정책 패키지 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음 사용자를 선택합니다.

2. 사용자 페이지에서 **정책을** 선택한 다음 정책 **패키지** 옆에 있는 **편집** 을 선택합니다.

3. **정책 패키지 할당** 창에서 할당할 패키지를 선택한 다음 **저장** 을 선택합니다.

![사용자에게 정책 패키지 할당을 위한 관리 센터 Teams 스크린샷](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a>여러 사용자에게 정책 패키지 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동한 다음 패키지 이름 왼쪽을 클릭하여 할당할 정책 패키지를 선택합니다.

2. **사용자 관리** 를 선택합니다.

3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.

4. 사용자 추가가 완료되면 **저장** 을 선택합니다.


![여러 사용자에게 정책 패키지 할당을 위한 Teams 관리 센터 스크린샷](media/assign-policypackages-multipleusers.png)


## <a name="assign-a-policy-package-to-a-group"></a>그룹에 정책 패키지 할당

그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다. 그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.

그룹에 대한 정책 패키지 할당은 최대 50,000명의 사용자 그룹에 권장되지만 더 큰 그룹에서도 작동합니다.

정책 패키지를 할당하면 즉시 그룹에 할당됩니다. 그러나 그룹 구성원에 대한 정책 할당 전파는 백그라운드 작업으로 수행되며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다. 그룹에서 정책을 할당 취소하거나 그룹에서 구성원을 추가하거나 제거할 때도 마찬가지입니다.

> [!IMPORTANT]
> 시작하기 전에 ([우선 순위 규칙](assign-policies-users-and-groups.md#precedence-rules)) 및 ([그룹 할당 순위](assign-policies-users-and-groups.md#group-assignment-ranking))를 이해하는 것이 중요합니다. 이 문서의 앞부분에서 ([그룹에 대한 정책 할당에 대해 알아야 할](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups) 사항)의 개념을 읽고 이해해야 합니다.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>관리 센터의 사용자 그룹에 정책 패키지 할당

1. Teams 관리 센터에 로그인합니다.

2. 왼쪽 탐색 영역에서 정책 패키지 페이지로 이동합니다.

3. 그룹 정책 할당 탭을 선택합니다.

4. **그룹 추가** 를 선택한 다음 그룹 창에 정책 패키지 할당 창에서 다음을 수행합니다.

    1. 정책 패키지를 할당할 그룹을 검색하고 추가합니다.

    1. 정책 패키지를 선택합니다.

    1. 각 정책 유형에 대한 순위를 설정합니다.

    1. **적용** 을 선택합니다.


       ![는 그룹 정책 할당을 표시합니다.](media/group-pkg-assignment.png)

5. 특정 정책 유형에 대한 순위를 관리하려면 특정 정책 페이지로 이동합니다.

6. 그룹에 정책 패키지를 다시 할당하려면 먼저 그룹 정책 할당을 제거합니다. 그런 다음 위의 단계에 따라 그룹에 정책 패키지를 할당합니다.

### <a name="work-with-powershell"></a>PowerShell 작업

#### <a name="get-the-teams-powershell-module"></a>Teams PowerShell 모듈 가져오기

단계별 지침은 [Teams PowerShell 설치](teams-powershell-install.md)를 참조하세요.

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>사용자 그룹에 정책 패키지 할당

[Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet을 사용하여 그룹에 정책 패키지를 할당합니다. 개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다. 정책 패키지를 할당할 때 정책 패키지의 각 정책 유형에 대한 ([그룹 할당 순위](assign-policies-users-and-groups.md#group-assignment-ranking))를 지정합니다.

이 예제에서는 TeamsAppSetupPolicy 및 TeamsMeetingBroadcastPolicy의 할당 순위가 1이고 TeamsMeetingPolicy의 경우 순위가 2인 그룹에 Education_Teacher 정책 패키지를 할당합니다.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 패키지 할당

일괄 처리 정책 패키지 할당을 사용하면 스크립트를 사용하지 않고도 한 번에 많은 사용자 집합에 정책 패키지를 할당할 수 있습니다. [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 배치 및 정책 패키지를 제출합니다. 할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다. 그런 다음 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.

개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다. 사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 동일한 값을 갖는 경우가 많지만 필수는 아닙니다. UPN 또는 전자 메일을 사용하여 사용자를 지정했지만 SIP 주소와 다른 값을 갖는 경우 사용자에 대한 정책 할당이 실패합니다. 일괄 처리에 중복 사용자가 포함된 경우 일괄 처리 전에 중복 항목이 일괄 처리에서 제거되고 일괄 처리에 남아 있는 고유 사용자에 대해서만 상태가 제공됩니다.

일괄 처리에는 최대 5,000명의 사용자가 포함됩니다. 최상의 결과를 얻으려면 한 번에 몇 개 이상의 일괄 처리를 제출하지 마세요. 더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료되도록 허용합니다.

### <a name="use-the-teams-powershell-module"></a>Teams PowerShell 모듈 사용

다음을 실행하여 [Microsoft Teams PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치합니다(아직 설치하지 않은 경우). 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams 연결하고 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시되면 관리자 자격 증명을 사용하여 로그인합니다.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 패키지 할당

이 예제에서는 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Education_PrimaryStudent 정책 패키지를 사용자 배치에 할당합니다.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>일괄 처리 할당의 상태 보기

다음을 실행하여 일괄 처리 할당의 상태를 가져옵니다. 여기서 OperationId는 지정된 일괄 처리에 대해 cmdlet에서 반환하는 `New-CsBatchPolicyAssignmentOperation` 작업 ID입니다.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

출력에 오류가 발생한 것으로 표시되면 다음을 실행하여 속성에 있는 오류에 `UserState` 대한 자세한 정보를 가져옵니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

자세한 내용은 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)을 참조하세요.

## <a name="related-topics"></a>관련 항목

- [정책을 사용하여 Teams 관리](manage-teams-with-policies.md)
- [Microsoft Teams 정책 패키지 관리](manage-policy-packages.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams 정책 할당 - 시작](policy-assignment-overview.md)
