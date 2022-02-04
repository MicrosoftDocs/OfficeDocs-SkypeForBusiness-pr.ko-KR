---
title: 학교의 대규모 사용자 집합에 정책 할당
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 그룹 멤버 자격을 기반으로 또는 원격 학교(teleschool, tele-school) 목적에 대한 일괄 처리 할당을 통해 교육 기관의 대규모 사용자 집합에 정책을 할당하는 방법을 알아보습니다.
f1keywords: ''
ms.openlocfilehash: 3cfde2dc523904f571b696e63ea7a5da16afff26
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2022
ms.locfileid: "62362994"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>학교의 대규모 사용자 집합에 정책 할당

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> 정책 할당에 대한 자세한 내용은 Microsoft Teams 사용자에 대한 정책 할당을 [Teams](policy-assignment-overview.md).

## <a name="overview"></a>개요

학생 및 교육자들에게 각기 다른 기능에 대한 액세스 권한을 제공해야 Microsoft Teams. 라이선스 유형별로 조직의 사용자를 빠르게 식별한 다음 적절한 정책을 할당할 수 있습니다. 이 자습서에서는 학교의 대규모 사용자 집합에 모임 정책을 할당하는 방법을 보여줍니다. 관리 센터 및 powerShell을 사용하여 정책을 Microsoft Teams 수 있으며 두 가지 방법을 모두 보여 드 입니다.

사용자가 일괄 처리 정책 할당을 통해 규모에 따라 사용자에 직접 또는 구성원인 보안 그룹에 모임 정책을 할당할 수 있습니다. 다음 방법을 배우게 될 것입니다.

- **그룹에 [정책 할당을 사용하여](#assign-a-policy-to-a-group)** 보안 그룹에 모임 정책을 할당(권장)합니다. 이 메서드를 사용하면 그룹 멤버 자격에 따라 정책을 할당할 수 있습니다. 보안 그룹 또는 메일 그룹에 정책을 할당할 수 있습니다. 구성원이 그룹에 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다. 새 사용자에 대한 정책을 관리하는 시간을 줄이거나 사용자의 역할이 변경될 때 이 메서드를 사용하는 것이 좋습니다. 이 메서드는 최대 50,000명까지의 그룹에 가장 잘 작동하지만 더 큰 그룹에서도 작동합니다.

- **일 [괄 처리 정책 할당을](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users) 사용하여** 대량으로 사용자에게 모임 정책을 직접 할당합니다. 한 때 최대 5,000명까지 정책을 할당할 수 있습니다. 사용자가 5,000명을 넘은 경우 여러 일괄 처리를 제출할 수 있습니다. 이 메서드를 사용하면 새 사용자가 있는 경우 일괄 처리 할당을 다시 실행하여 해당 새 사용자에게 정책을 할당해야 합니다.

사용자 지정 정책을 Teams 할당하지 않는 한 사용자가 Teams 정책 유형에 대한 전역(org-wide default) 정책을 자동으로 받을 수 있습니다. 학생 인구가 가장 큰 사용자 집합이기 때문에 가장 제한적인 설정을 받는 경우가  종종 있기 때문에 다음을 하는 것이 좋습니다.

- 개인 채팅 및 모임 계획과 같은 핵심 기능을 허용하고 교직원 및 교육자에 정책을 할당하는 사용자 지정 정책을 만들 수 있습니다.
- 교직원 및 교사에게 사용자 지정 정책을 할당합니다.
- 전역(Org-wide default) 정책을 편집하고 적용하여 학생의 기능을 제한합니다.

사용자 지정 정책을 만들고 교직원 및 교사에게 할당할 때까지 전역 정책이 학교의 모든 사용자에게 적용됩니다.

이 자습서에서는 학생에게 글로벌 모임 정책을 적용하고 교직원 및 교사에게 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다. 학생을 위한 모임 설정을 조정하기 위해 전역 정책을 편집하고 교직원 및 교육자 [](policy-packages-edu.md) 에 대한 모임 환경을 정의하는 사용자 지정 정책을 만들었다고 가정합니다.

![관리 센터의 모임 정책 Teams 스크린샷입니다.](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

다음 단계를 수행하여 교직원 및 교육자에 대한 보안 그룹을 만든 다음, 해당 보안 그룹에 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.

### <a name="before-you-get-started"></a>시작하기 전

> [!IMPORTANT]
> 그룹에 정책을 할당하면 우선 순위 규칙에 따라 정책 할당이 그룹의 구성원에게 전파됩니다. 예를 들어 사용자가 정책(개별적으로 또는 일괄 처리 할당을 통해)을 직접 할당하는 경우 해당 정책은 그룹에서 상속된 정책보다 우선합니다. 즉, 사용자에게 직접 할당된 모임 정책이 있는 경우 보안 그룹에서 모임 정책을 상속하기 전에 사용자로부터 해당 모임 정책을 제거해야 합니다.

시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 [이해하는 것이 중요합니다](assign-policies-users-and-groups.md#group-assignment-ranking).[](policy-assignment-overview.md#which-policy-takes-precedence) 그룹에 정책 할당에 대해 알아야 할 개념을 읽고 이해 **[해야 합니다](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)**.

교직원 및 교사가 보안 그룹에서 모임 정책을 상속받기 위해 이러한 모든 단계를 완료해야 합니다.

1. [보안 그룹을 만들 수 있습니다](#create-security-groups).
2. [보안 그룹에 정책을 할당합니다](#assign-a-policy-to-a-security-group).
3. [사용자에게 직접 할당된 정책을 제거합니다](#remove-a-policy-that-was-directly-assigned-to-users).

### <a name="create-security-groups"></a>보안 그룹 만들기

먼저 교직원 및 교육자에 대한 보안 그룹을 만들어야 합니다.

SDS[(학교 데이터 동기화](/SchoolDataSync/))를 사용하면 학교에서 보안 그룹 교육자 및 학생을 [쉽게 만들 수](/SchoolDataSync/edu-security-groups) 있습니다. SDS를 사용하여 학교 정책을 관리하는 데 필요한 보안 그룹을 만드는 것이 좋습니다.

환경 내에서 SDS를 배포할 수 없는 경우 [이 PowerShell](scripts/powershell-script-security-groups-edu.md) 스크립트를 사용하여 교직원 라이선스가 할당된 모든 교직원 및 교육자 및 학생 라이선스가 할당된 모든 학생에 대해 두 개의 보안 그룹을 만들 수 있습니다. 그룹을 최신으로 유지하려면 이 스크립트를 정기적으로 실행해야 합니다.

### <a name="assign-a-policy-to-a-security-group"></a>보안 그룹에 정책 할당

#### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

> [!NOTE]
> 현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 통화 정책, 통화 Teams 정책, Teams 이벤트 정책, Teams 모임 정책 및 Teams 메시지 Teams 사용할 수 있습니다. 다른 정책 형식의 경우 PowerShell을 사용 합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **모임** > **모임 정책** 으로 이동합니다.
2. 그룹 정책 **할당 탭을** 선택합니다.
3. 그룹 **추가를 선택한** 다음 그룹화 정책  할당 창에서 다음을 합니다.

    ![모임 정책을 보여 주며 설정 편집 창의 스크린샷입니다.](media/batch-group-policy-assignment-edu-group.png)
    1. 그룹 **선택 상자에서** 교직원 및 교사가 포함된 보안 그룹을 검색하고 추가합니다.
    2. 순위 **선택 상자에** **1을 입력합니다**.
    3. 정책 **선택 상자에서** **EducatorMeetingPolicy를 선택합니다**.
    4. 적용을 **선택합니다**.

그룹 정책 할당을 제거하려면 정책 페이지의 그룹  정책 할당 탭에서 그룹 할당을 선택한 다음 제거를 **선택합니다**.

그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다. 그런 다음 위의 단계를 수행하여 그룹에 정책을 할당합니다.

#### <a name="using-powershell"></a>PowerShell 사용

> [!NOTE]
> 현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 정책 유형에 Teams 없습니다. 지원되는 정책 유형 목록에 대한 [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) 를 참조하세요.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>PowerShell 모듈을 Microsoft Teams 연결

다음을 실행하여 Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 설치되지 않은 경우). 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.

##### <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

다음을 실행하여 교직원 및 교사가 포함된 보안 그룹에 EducatorMeetingPolicy라는 모임 정책을 할당하고 과제 순위를 1로 설정합니다. 개체 ID, SIP(세션 시작 프로토콜) 주소 또는 전자 메일 주소를 사용하여 보안 그룹을 지정할 수 있습니다. 이 예제에서는 전자 메일 주소(staff-faculty@contoso.com.

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>사용자에게 직접 할당된 정책 제거

사용자가 직접 정책을 할당한 경우(개별적으로 또는 일괄 처리 할당을 통해) 해당 정책이 우선합니다. 즉, 사용자에게 직접 할당된 모임 정책이 있는 경우 보안 그룹에서 모임 정책을 상속하기 전에 사용자로부터 해당 모임 정책을 제거해야 합니다.

자세한 내용은 그룹에 정책 할당에 대해 알아야 할 내용을 [참조합니다](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups).

다음 단계를 수행하여 교직원 및 교육자에 직접 할당된 모임 정책을 제거합니다.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>PowerShell 모듈을 Microsoft Teams 연결

다음을 실행하여 Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 설치되지 않은 경우). 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시될 때 Azure AD에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>사용자에게 직접 할당된 정책 할당을 지정하지 않습니다.

다음을 실행하여 해당 정책을 직접 할당한 사용자에서 모임 정책을 제거합니다. 전자 메일 주소 또는 개체 ID로 사용자를 지정할 수 있습니다.

이 예제에서는 해당 전자 메일 주소로 지정된 사용자에서 모임 정책이 제거됩니다.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

이 예제에서는 모임 정책이 이름의 텍스트 파일의 사용자 목록에서 user_ids.txt.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>그룹에 대한 정책 할당을 얻습니다.

다음을 실행하여 특정 보안 그룹에 할당된 모든 정책을 볼 수 있습니다. 그룹은 정책을 할당하는 데 SIP 주소 또는 전자 메일 주소를 사용하는 경우에도 항상 그룹 ID로 나열됩니다.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>사용자에게 할당된 정책 사용

다음을 실행하여 특정 사용자에게 할당된 모든 정책을 볼 수 있습니다. 다음 예제에서는 해당 정책에 할당된 정책을 reda@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 할당

다음 단계를 수행하여 교직원 및 교육자들에게 직접 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.

### <a name="using-powershell"></a>PowerShell 사용

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>커넥트용 Azure AD PowerShell 모듈 및 Graph PowerShell 모듈에 Teams

이 문서의 단계를 수행하기 전에 Azure AD PowerShell을 설치하고 Graph(할당된 라이선스로 사용자를 식별하기 위해) 및 Microsoft Teams PowerShell 모듈(해당 사용자에게 정책을 할당)에 연결해야 합니다.

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Azure AD PowerShell을 설치하고 Graph 모듈에 연결

관리자 권한 Windows PowerShell 명령 프롬프트(관리자 권한으로 Windows PowerShell 실행)를 열고 다음을 실행하여 Azure Active Directory PowerShell을 Graph.

```powershell
Install-Module -Name AzureAD
```

다음을 실행하여 Azure AD에 연결합니다.

```powershell
Connect-AzureAD
```

메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.

자세한 내용은 커넥트[용 PowerShell Azure Active Directory PowerShell을 사용하여 Graph 참조합니다](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>PowerShell 모듈을 Microsoft Teams 연결

다음을 실행하여 Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 설치되지 않은 경우). 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시될 때 Azure AD에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.

#### <a name="identify-your-users"></a>사용자 식별

먼저 다음을 실행하여 라이선스 유형별로 교직원 및 교육자를 식별합니다. 이렇게 하여 조직에서 어떤 SKUS가 사용 중일지 알 수 있습니다. 그런 다음 교직원 SKU가 할당된 교직원 및 교사를 식별할 수 있습니다.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

반환되는:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

이 예제에서 출력은 교직원 라이선스 SkuId가 "e97c048c-37a4-45fb-ab50-922fbf07a370"입니다.

> [!NOTE]
> Education SKU 및 SKU 아이디 목록을 보시고자 하는 경우 [Education SKU 참조를 참조하세요](sku-reference-edu.md).

다음으로, 다음을 실행하여 이 라이선스가 있는 사용자를 식별하고 모두 함께 수집합니다.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>대량으로 정책 할당

이제 사용자에게 적절한 정책을 일괄적으로 할당합니다. 정책을 할당하거나 업데이트할 수 있는 최대 사용자 수는 5,000명입니다. 예를 들어 5,000명 이상의 교직원 및 교사가 있는 경우 여러 일괄 처리를 제출해야 합니다.

다음을 실행하여 교직원 및 교사에게 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy ```PolicyType``` ```PolicyName``` 와 같은 다른 정책 유형을 대량으로 할당하려면 할당하는 정책과 정책 이름으로 변경해야 합니다.

#### <a name="get-the-status-of-a-bulk-assignment"></a>대량 할당의 상태 확인

각 대량 할당은 정책 할당의 진행률을 추적하거나 발생할 수 있는 모든 실패를 식별하는 데 사용할 수 있는 작업 ID를 반환합니다. 예를 들어 다음을 실행합니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

일괄 처리 작업에서 각 사용자의 할당 상태를 확인한 다음을 실행합니다. 각 사용자의 세부 정보는 속성에 ```UserState``` 있습니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>사용자가 5,000명을 넘을 경우 대량으로 정책 할당

먼저 다음을 실행하여 교직원 및 교육자 수를 봐야 합니다.

```powershell
$faculty.count
```

전체 사용자 ID 목록을 제공하는 대신 다음을 실행하여 처음 5,000개, 다음 5,000개 등 을 지정합니다.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

전체 사용자 목록에 도달할 때까지 사용자 ID의 범위를 변경할 수 있습니다. 예를 들어 첫 ```$faculty[0..4999``` 번째 일괄 처리를 입력하고, ```$faculty[5000..9999``` 두 번째 일괄 처리에 사용하며, ```$faculty[10000..14999``` 세 번째 일괄 처리를 입력합니다.

#### <a name="get-the-policies-assigned-to-a-user"></a>사용자에게 할당된 정책 사용

다음을 실행하여 특정 사용자에게 할당된 모든 정책을 볼 수 있습니다. 다음 예제에서는 사용자에게 할당된 정책을 hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**PowerShell에 익숙하지 Teams. 자세한 내용은 어디서 볼 수 있나요?**

PowerShell을 사용하여 데이터 관리에 대한 개요를 Teams [PowerShell Teams 참조하세요](teams-powershell-overview.md). 이 문서에서 사용되는 cmdlet에 대한 자세한 내용은 다음을 참조하세요.

- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment)
- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>관련 항목

- [사용자에게 정책 할당](policy-assignment-overview.md)
- [교육용 Teams 정책 및 정책 패키지](policy-packages-edu.md)
- [Teams에서의 모임 정책 관리](meeting-policies-overview.md)