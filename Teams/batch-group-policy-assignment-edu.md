---
title: 학교에서 대규모 사용자 집합에 정책 할당
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: 그룹 구성원 자격을 기준으로 또는 원격 school (teleschool, tele) 용도의 일괄 처리를 통해 직접 교육 기관에 정책을 할당 하는 방법에 대해 알아봅니다.
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534132"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>학교에서 대규모 사용자 집합에 정책 할당

> [!NOTE]
> Microsoft 팀의 정책 할당에 대 한 자세한 내용은 [팀에서 사용자에 게 정책 할당](assign-policies.md)을 참조 하세요.

## <a name="overview"></a>개요

학생 및 교사에 게 Microsoft 팀의 다양 한 기능에 대 한 액세스 권한이 필요 한가요? 라이선스 유형을 기준으로 조직의 사용자를 빠르게 식별 한 다음 적절 한 정책을 할당할 수 있습니다. 이 자습서에서는 학교에서 대규모 사용자 집합에 모임 정책을 할당 하는 방법을 보여 줍니다. Microsoft 팀 관리 센터 및 PowerShell을 사용 하 여 정책을 할당할 수 있으며, 두 가지 방법 모두 표시 됩니다.

사용자가 구성원 인 보안 그룹 또는 일괄 처리 정책 할당을 통해 확장할 때 사용자에 게 직접 모임 정책을 할당할 수 있습니다. 다음을 수행 하는 방법에 대해 알아보세요.

- ** [그룹에 정책 할당](#assign-a-policy-to-a-group) 을 사용 하 여 보안 그룹에 모임 정책을 할당 합니다 (권장)**. 이 방법을 사용 하면 그룹 구성원을 기준으로 정책을 할당할 수 있습니다. 보안 그룹 또는 배포 목록에 정책을 할당할 수 있습니다. 그룹에서 구성원이 추가 되거나 제거 되 면 그에 따라 상속 된 정책 할당이 업데이트 됩니다. 이 방법은 새 사용자에 대 한 정책을 관리 하는 시간을 단축 하거나 사용자의 역할이 변경 되는 경우를 위해 사용 하는 것이 좋습니다. 이 방법은 최대 5만 사용자를 대상으로 하는 그룹에 가장 적합 하지만 대형 그룹과 함께 사용할 수 있습니다.

- ** [일괄 처리 정책 할당](assign-policies.md#assign-a-policy-to-a-batch-of-users) 을 사용 하 여 모임 정책을 사용자에 게 직접 대량으로 할당**합니다. 한 번에 최대 5000 명의 사용자에 대 한 정책을 할당할 수 있습니다. 5000 명 이상의 사용자가 있는 경우 여러 일괄 처리를 제출할 수 있습니다. 이 방법을 사용 하면 새 사용자가 있는 경우 일괄 처리 할당을 다시 실행 하 여 정책을 해당 새 사용자에 게 할당 해야 합니다.

사용자 지정 정책을 만들고 할당 하지 않는 한 팀에서 팀 정책 유형의 전역 (조직 차원의 기본) 정책을 자동으로 얻을 수 있다는 점에 유의 하세요. 학생 집단은 일반적으로 가장 큰 사용자 집합 이므로 가장 제한적인 설정을 받을 수 있으므로 다음을 수행 하는 것이 좋습니다.

- 개인 채팅 및 모임 예약과 같은 핵심 기능을 허용 하는 사용자 지정 정책을 만들어 교직원 및 교육자에 게 정책을 할당 합니다.
- 사용자 지정 정책을 직원과 교육자에 게 할당 합니다.
- 전역 (조직 전체 기본값) 정책을 편집 하 고 적용 하 여 학생에 대 한 접근 권한 제한

사용자 지정 정책을 만들어 교직원과 교육자에 게 배정할 때까지 해당 학교의 모든 사용자에 게 전역 정책이 적용 된다는 점을 기억 하세요.

이 자습서에서 학생 들은 전역 모임 정책을 받게 되며 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 교직원 및 교육자에 게 할당 합니다. 학생에 대 한 모임 설정을 조정 하 고 교직원 및 교사를 위한 모임 환경을 정의 하는 [사용자 지정 정책을 만드는](policy-packages-edu.md) 전역 정책을 편집 했다고 가정 합니다.

![팀 관리 센터의 모임 정책 페이지 스크린샷](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

다음 단계에 따라 직원과 교육자에 대 한 보안 그룹을 만든 다음 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 해당 보안 그룹에 할당 합니다.

### <a name="before-you-get-started"></a>시작하기 전

> [!IMPORTANT]
> 그룹에 정책을 할당 하면 우선 순위 규칙에 따라 정책 할당이 그룹의 구성원에 게 전파 됩니다. 예를 들어 사용자에 게 정책 (개별적으로 또는 일괄 할당을 통해)을 직접 할당 한 경우 해당 정책은 그룹에서 상속 된 정책 보다 우선적으로 적용 됩니다. 또한 사용자에 게 직접 할당 된 모임 정책이 있는 경우 사용자가 해당 모임 정책을 제거 해야 보안 그룹에서 모임 정책을 상속할 수 있습니다.

시작 하기 전에 [우선 순위 규칙](assign-policies.md#precedence-rules) 및 [그룹 배정 순위](assign-policies.md#group-assignment-ranking)를 이해 하는 것이 중요 합니다. ** [그룹에 대 한 정책 할당에 대해 알아야 할](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)개념을 읽고 이해**해야 합니다.

교직원과 교육자는 보안 그룹에서 모임 정책을 상속 받도록 모든 단계를 완료 해야 합니다.

1. [보안 그룹을 만듭니다](#create-security-groups).
2. [보안 그룹에 정책을 할당](#assign-a-policy-to-a-security-group)합니다.
3. [사용자에 게 직접 할당 된 정책을 제거](#remove-a-policy-that-was-directly-assigned-to-users)합니다.

### <a name="create-security-groups"></a>보안 그룹 만들기

먼저 직원과 교육자를 위한 보안 그룹을 만듭니다.

SDS ( [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) )를 사용 하 여 학교에서 [보안 그룹 교육자 및 학생을 쉽게 만들](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) 수 있습니다. SDS를 사용 하 여 정책을 관리 하는 데 필요한 보안 그룹을 만드는 것이 좋습니다.

환경 내에 SDS를 배포할 수 없는 경우 [이 PowerShell 스크립트](scripts/powershell-script-security-groups-edu.md) 를 사용 하 여 두 개의 보안 그룹을 만들고, 교직원 라이선스를 할당 받은 모든 직원과 강사와 학생 라이선스가 할당 된 모든 학생에 게 각각에 대해 하나씩을 만듭니다. 그룹을 최신 상태로 유지 하려면이 스크립트를 정기적으로 실행 해야 합니다.

### <a name="assign-a-policy-to-a-security-group"></a>보안 그룹에 정책 할당

#### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

> [!NOTE]
> 현재 Microsoft 팀 관리 센터를 사용 하는 그룹에 대 한 정책 할당은 팀 호출 정책, 팀 통화 대기 정책, 팀 정책, 팀 live 이벤트 정책, 팀 모임 정책, 팀 메시징 정책에만 사용할 수 있습니다. 다른 정책 유형의 경우 PowerShell을 사용 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **모임 정책**으로 이동 합니다.
2. **그룹 정책 할당** 탭을 선택 합니다.
3. **그룹 추가**를 선택 하 고 **그룹에 정책 할당** 창에서 다음을 수행 합니다.

    ![모임 정책이 표시 된 설정 편집 창의 스크린샷](media/batch-group-policy-assignment-edu-group.png)
    1. **그룹 선택** 상자에서 직원과 교사를 포함 하는 보안 그룹을 검색 하 여 추가 합니다.
    2. **순위 선택** 상자에 **1**을 입력 합니다.
    3. **정책 선택** 상자에서 **EducatorMeetingPolicy**를 선택 합니다.
    4. **적용**을 선택 합니다.

그룹 정책 할당을 제거 하려면 정책 페이지의 **그룹 정책 할당** 탭에서 그룹 할당을 선택한 다음 **제거**를 선택 합니다.

그룹 할당 순위를 변경 하려면 먼저 그룹 정책 할당을 제거 해야 합니다. 그런 다음 위의 단계에 따라 정책을 그룹에 할당 합니다.

#### <a name="using-powershell"></a>PowerShell 사용

> [!NOTE]
> 현재 모든 팀 정책 유형에는 PowerShell을 사용 하는 그룹에 대 한 정책 할당을 사용할 수 없습니다. 지원 되는 정책 유형 목록에 대 한 [새 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 을 참조 하세요.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.

다음을 실행 하 여 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 설치 되지 않은 경우). 버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.

##### <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

다음을 실행 하 여 EducatorMeetingPolicy 라는 모임 정책을 교직원 및 교육자가 포함 된 보안 그룹에 할당 하 고 과제 순위를 1로 설정 합니다. 개체 Id, SIP (세션 시작 프로토콜) 주소 또는 전자 메일 주소를 사용 하 여 보안 그룹을 지정할 수 있습니다. 이 예제에서는 전자 메일 주소 (staff-faculty@contoso.com)를 사용 합니다.

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a>사용자에 게 직접 할당 된 정책 제거

사용자가 정책을 직접 할당 하는 경우 (개별적으로 또는 일괄 할당을 통해) 해당 정책이 우선 한다는 점에 유의 하세요. 즉, 사용자에 게 직접 할당 된 모임 정책이 있는 경우 사용자가 해당 모임 정책을 제거 해야 보안 그룹에서 모임 정책을 상속할 수 있습니다.

자세히 알아보려면 [그룹에 정책 할당에 대해 알아야 할 사항](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)을 참조 하세요.

다음 단계에 따라 직원과 교육자에 직접 할당 된 모임 정책을 제거 합니다.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.

다음을 실행 하 여 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 설치 되지 않은 경우). 버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.

```powershell
Connect-MicrosoftTeams
```
메시지가 표시 되 면 Azure AD에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a>사용자에 게 직접 할당 된 정책 할당 취소

다음을 실행 하 여 해당 정책을 직접 할당 한 사용자에 게 서 모임 정책을 제거 합니다. 전자 메일 주소 또는 개체 ID를 기준으로 사용자를 지정할 수 있습니다.

이 예제에서 모임 정책은 전자 메일 주소로 지정 된 사용자에서 제거 됩니다.

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

이 예제에서 모임 정책은 user_ids.txt 라는 텍스트 파일의 사용자 목록에서 제거 됩니다. 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a>그룹에 대 한 정책 할당 가져오기

특정 보안 그룹에 지정 된 모든 정책을 보려면 다음을 실행 합니다. 그룹은 해당 SIP 주소 또는 전자 메일 주소가 정책을 할당 하는 데 사용 된 경우에도 그룹 Id에 의해 항상 나열 됨을 참고 하세요.

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a>사용자에 게 할당 된 정책 가져오기

특정 사용자에 게 할당 된 모든 정책을 보려면 다음을 실행 합니다. 다음 예에서는 reda@contoso.com에 할당 된 정책을 가져오는 방법을 보여 줍니다.

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 할당

다음 단계에 따라 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 교직원에 게 직접 할당 하 고 교사에 게 대량으로 지정 합니다.

### <a name="using-powershell"></a>PowerShell 사용

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Graph 모듈 및 팀 PowerShell 모듈에 대 한 Azure AD PowerShell에 연결

이 문서의 단계를 수행 하기 전에 Graph 모듈에 대 한 Azure AD PowerShell을 설치 하 고 연결 (사용자에 게 할당 된 라이선스를 식별 하기 위해) 하 고 Microsoft 팀 PowerShell 모듈 (해당 사용자에 게 정책을 할당 해야 함) 합니다.

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Graph 모듈에 대 한 Azure AD PowerShell 설치 및 연결

관리자 권한으로 windows PowerShell 명령 프롬프트를 열고 (관리자로 Windows PowerShell 실행) 다음을 실행 하 여 Graph 모듈에 대 한 Azure Active Directory PowerShell을 설치 합니다.

```powershell
Install-Module -Name AzureAD
```

Azure AD에 연결 하려면 다음을 실행 합니다.

```powershell
Connect-AzureAD
```

메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.

자세한 내용은 [Graph 용 Azure Active Directory PowerShell 모듈을 사용 하 여 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)을 참조 하세요.

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.

다음을 실행 하 여 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 설치 되지 않은 경우). 버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.

```powershell
Connect-MicrosoftTeams
```
메시지가 표시 되 면 Azure AD에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.

#### <a name="identify-your-users"></a>사용자 식별

먼저 다음을 실행 하 여 라이선스 유형별로 교직원 및 교사를 식별 합니다. 조직에서 사용 중인 Sku를 알 수 있습니다. 그런 다음 교직원 SKU가 지정 된 교직원 및 교사를 식별할 수 있습니다.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

반환 되는 결과:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

이 예제에서는 교직원 라이선스 SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" 라는 것을 출력에 표시 합니다.

> [!NOTE]
> 교육 Sku 및 SKU Id 목록을 보려면 [교육 sku 참조](sku-reference-edu.md)를 참조 하세요.

다음으로, 다음을 실행 하 여이 라이선스가 있는 사용자를 식별 하 고 함께 수집 합니다.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a>대량으로 정책 할당

이제 사용자에 게 적절 한 정책을 대량으로 할당 합니다. 정책을 할당 하거나 업데이트 하는 데 사용할 수 있는 최대 사용자 수는 한 번에 5000입니다. 예를 들어 5000 개 이상의 직원과 교육자가 있는 경우 여러 일괄 처리를 제출 해야 합니다.

다음을 실행 하 여 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 교직원 및 교육자에 게 할당 합니다.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy와 같이 대량으로 다른 정책 유형을 할당 하려면 ```PolicyType``` 할당할 정책 및 ```PolicyName``` 정책 이름으로 변경 해야 합니다.

#### <a name="get-the-status-of-a-bulk-assignment"></a>대량 배정 상태 가져오기

각 대량 과제는 정책 할당의 진행률을 추적 하거나 발생할 수 있는 오류를 식별 하는 데 사용할 수 있는 작업 ID를 반환 합니다. 예를 들어 다음을 실행 합니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

일괄 작업에서 각 사용자의 할당 상태를 보려면 다음을 실행 합니다. 각 사용자에 대 한 세부 정보는 속성에 있습니다 ```UserState``` .

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a>5000 명 이상의 사용자가 있는 경우 대량으로 정책 할당

먼저 다음을 실행 하 여 보유 하 고 있는 교직원 및 강사 수를 확인 합니다.

```powershell
$faculty.count
```

사용자 Id의 전체 목록을 제공 하는 대신 다음을 실행 하 여 첫 번째 5000을 지정 하 고 다음 5000 등

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

전체 사용자 목록에 도달할 때까지 사용자 Id의 범위를 변경할 수 있습니다. 예를 들어 첫 번째 일괄 처리를 입력 하 고 두 번째 일괄 처리에 대해 ```$faculty[0..4999``` ```$faculty[5000..9999``` , ```$faculty[10000..14999``` 세 번째 일괄 처리에 대해 enter 키를 사용 합니다.

#### <a name="get-the-policies-assigned-to-a-user"></a>사용자에 게 할당 된 정책 가져오기

특정 사용자에 게 할당 된 모든 정책을 보려면 다음을 실행 합니다. 다음 예에서는 hannah@contoso.com에 할당 된 정책을 가져오는 방법을 보여 줍니다.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**팀에 대 한 PowerShell에 익숙하지 않습니다. 자세한 내용은 어디에서 확인할 수 있나요?**

PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 개요는 [팀 powershell 개요](teams-powershell-overview.md)를 참조 하세요. 이 문서에서 사용 되는 cmdlet에 대 한 자세한 내용은 다음을 참조 하세요.

- [새-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [새로운 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a>관련 항목

- [사용자에 게 정책 할당](assign-policies.md)
- [교육용 팀 정책 및 정책 패키지](policy-packages-edu.md)
- [팀에서 모임 정책 관리](meeting-policies-in-teams.md)
