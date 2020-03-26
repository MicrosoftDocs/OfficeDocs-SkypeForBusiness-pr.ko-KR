---
title: 학교에서 대규모 사용자 집합에 정책 할당
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 일괄 처리 정책 할당을 사용 하 여 원격 학교 (teleschool, tele) 용도의 교육 기관에 대규모 사용자 집합에 정책을 할당 하는 방법에 대해 알아봅니다.
f1keywords: ''
ms.openlocfilehash: 7e297b6a4b99162fb50564d4f552a06f0dc41a10
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978520"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>학교에서 대규모 사용자 집합에 정책 할당

학생 및 교사에 게 Microsoft 팀의 다양 한 기능에 대 한 액세스 권한이 필요 한가요? 라이선스 유형을 기준으로 조직의 사용자를 빠르게 식별 한 다음 적절 한 정책을 할당할 수 있습니다. 이 자습서에서는 [일괄 처리 정책 할당](assign-policies.md#assign-a-policy-to-a-batch-of-users) 을 사용 하 여 사용자에 게 대량으로 모임 정책을 할당 하는 방법을 보여 줍니다.

사용자 지정 정책을 만들고 할당 하지 않는 한 팀에서 팀 정책 유형의 전역 (조직 차원의 기본) 정책을 자동으로 얻을 수 있다는 점에 유의 하세요. 학생 집단은 일반적으로 가장 큰 사용자 집합 이므로 가장 제한적인 설정을 받을 수 있으므로 다음을 수행 하는 것이 좋습니다.

- 전역 (조직 전체 기본값) 정책을 편집 하 고 적용 하 여 학생에 대 한 접근 권한 제한 
- 개인 채팅 및 모임 예약과 같은 핵심 기능을 허용 하는 사용자 지정 정책을 만들어 교직원 및 교육자에 게 정책을 할당 합니다.

사용자 지정 정책을 만들어 교직원과 교육자에 게 배정할 때까지 해당 학교의 모든 사용자에 게 전역 정책이 적용 된다는 점을 기억 하세요.

이 자습서에서 학생 들은 전역 모임 정책을 받게 되며 PowerShell을 사용 하 여 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 직원 및 교사에 게 대량으로 할당 합니다. 학생에 대 한 모임 설정을 조정 하 고 교직원 및 교사를 위한 모임 환경을 정의 하는 사용자 지정 정책을 만드는 전역 정책을 편집 했다고 가정 합니다.

![팀 관리 센터의 모임 정책 페이지 스크린샷](media/edu-batch-policy-assignment.png)

직원 및 강사에 게 사용자 지정 모임 정책을 대량으로 할당 하려면 다음 단계를 따르세요.

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Graph 모듈 및 팀 PowerShell 모듈에 대 한 Azure AD PowerShell에 연결

이 문서의 단계를 수행 하기 전에 Graph 모듈에 대 한 Azure AD PowerShell을 설치 하 고 연결 (사용자에 게 할당 된 라이선스를 식별 하기 위해) 하 고 Microsoft 팀 PowerShell 모듈 (해당 사용자에 게 정책을 할당 해야 함) 합니다.

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Graph 모듈에 대 한 Azure AD PowerShell 설치 및 연결

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

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.

다음을 실행 하 여 [Microsoft 팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치 합니다. 버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.

```powershell
Connect-MicrosoftTeams
```
메시지가 표시 되 면 Azure AD에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.

## <a name="identify-your-users"></a>사용자 식별

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

## <a name="assign-a-policy-in-bulk"></a>대량으로 정책 할당

이제 사용자에 게 적절 한 정책을 대량으로 할당 합니다. 정책을 할당 하거나 업데이트 하는 데 사용할 수 있는 최대 사용자 수는 한 번에 2만입니다. 예를 들어 2만 개 이상의 직원과 교육자가 있는 경우 여러 일괄 처리를 제출 해야 합니다.

> [!IMPORTANT]
> 현재는 5000 사용자를 한 번에 일괄적으로 할당 하는 것을 제안 하 고 있습니다. 이러한 시간을 연장 하는 동안에는 처리 시간이 지연 될 수 있습니다. 이 늘어난 처리 시간에 대 한 영향을 최소화 하기 위해 최대 5000 사용자에 대 한 작은 일괄 처리 크기를 제출 하 고 이전 작업을 완료 한 후에 각 일괄 처리를 제출 하는 것이 좋습니다. 업무 시간 외에 일괄 처리를 제출 하는 것도 도움이 될 수 있습니다.

다음을 실행 하 여 EducatorMeetingPolicy 이라는 모임 정책을 교직원 및 교육자에 게 할당 합니다.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> TeamsMessagingPolicy와 같이 대량으로 다른 정책 유형을 할당 하려면 할당할 정책 및 ```PolicyType``` ```PolicyName``` 정책 이름으로 변경 해야 합니다.

## <a name="get-the-status-of-a-bulk-assignment"></a>대량 배정 상태 가져오기

각 대량 과제는 정책 할당의 진행률을 추적 하거나 발생할 수 있는 오류를 식별 하는 데 사용할 수 있는 작업 ID를 반환 합니다. 예를 들어 다음을 실행 합니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

일괄 작업에서 각 사용자의 할당 상태를 보려면 다음을 실행 합니다. 각 사용자에 대 한 세부 정보 ```UserState``` 는 속성에 있습니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>2만 명 이상의 사용자가 있는 경우 대량으로 정책 할당

먼저 다음을 실행 하 여 보유 하 고 있는 교직원 및 강사 수를 확인 합니다.

```powershell
$faculty.count
```

사용자 Id의 전체 목록을 제공 하는 대신 다음을 실행 하 여 첫 번째 2만을 지정 하 고 다음 2만 등

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

전체 사용자 목록에 도달할 때까지 사용자 Id의 범위를 변경할 수 있습니다. 예를 들어 첫 ```$faculty[0..19999``` 번째 일괄 처리를 입력 하 ```$faculty[20000..39999``` 고 두 번째 일괄 처리에 ```$faculty[40000..59999``` 대해, 세 번째 일괄 처리에 대해 enter 키를 사용 합니다.

## <a name="get-the-policies-assigned-to-a-user"></a>사용자에 게 할당 된 정책 가져오기

특정 사용자에 게 할당 된 모든 정책을 보려면 다음을 실행 합니다. 다음 예에서는 hannah@contoso.com에 할당 된 정책을 가져오는 방법을 보여 줍니다.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>FAQ

**학생, 교직원 및 교육자 인 모든 사용자가 정책을 할당 하도록 자동으로 설정 하려는 경우 어떻게 하면 되나요?**

팀 제품 팀은 보안 그룹에 정책 지정을 지원 하기 위해 작업을 수행 하 고 있습니다. 이때 학생 및 교사를 위한 그룹을 만든 다음 해당 그룹에 대 한 적절 한 정책을 만들 수 있습니다. 이 자습서를 사용 하 여 할당 한 정책 등의 명시적인 사용자 할당이 그룹에서 상속 된 정책 보다 우선 한다는 점에 유의 하세요. 이 기능이 지원 되는 경우 그룹에 정책 할당을 사용 하 고 상속 된 그룹 정책을 얻을 수 있도록 사용자를 업데이트 하는 방법에 대 한 자세한 지침을 제공 합니다.

**팀에 대 한 PowerShell에 익숙하지 않습니다. 자세한 내용은 어디에서 확인할 수 있나요?**

[팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [사용자에 게 정책 할당](assign-policies.md)
- [새로운 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
