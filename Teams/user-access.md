---
title: 사용자 액세스 관리 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 조직에 있는 사용자에게 라이선스를 Teams 사용자 액세스를 관리하는 Teams 방법을 알아보습니다.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4a83d0da32c11406f76b9bc355ceb666d4ea308
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728067"
---
# <a name="manage-user-access-to-teams"></a>Teams에 대한 사용자 액세스 관리

제품 라이선스를 Teams 할당하거나 제거하여 사용자 수준에서 Microsoft Teams 관리합니다. 익명으로 Teams 모임에 참가하는 경우를 제외하고 조직의 각 사용자에게 Teams 라이선스를 Teams. 새 사용자 계정을 만들 때 Teams 사용자 또는 기존 계정이 있는 사용자에게 새 사용자에 대한 라이선스를 할당할 수 있습니다.

기본적으로 라이선스 계획(예: E3 또는 Microsoft 365 Enterprise 또는 Microsoft 365 Business Premium)이 사용자에게 할당되면 Teams 라이선스가 자동으로 할당되고 사용자가 라이선스에 대해 Teams. 라이선스를 제거하거나 Teams 사용자에 대한 사용자 권한을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리되는</a>메시징 정책을 사용하여 Teams 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어할 Teams. 기본 정책을 사용하거나 조직의 사용자 지정 메시징 정책을 하나 이상 만들 수 있습니다. 자세한 내용은 에서 메시징 [정책 관리를 Teams.](messaging-policies-in-teams.md)
PowerShell을 사용하여 Teams 라이선스를 Microsoft 365 관리 센터 관리합니다. 라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자가 되어야 합니다.

> [!NOTE]
> 프로젝트 및 기타 동적 이니셔티브에 대해 팀을 유기적으로 Teams 수 있도록 모든 사용자에 대한 인증을 사용하도록 설정하는 것이 좋습니다. 파일럿을 실행하는 경우에도 모든 사용자에 대해 Teams 유지하지만 파일럿 사용자 그룹에 대한 통신만 사용하도록 설정하는 것이 여전히 유용할 수 있습니다.

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터

Teams 사용자 수준 라이선스는 사용자 관리 인터페이스를 통해 직접 Microsoft 365 관리 센터 관리됩니다. 관리자는 새 사용자 계정을 만들 때 또는 기존 계정이 있는 사용자에게 라이선스를 할당할 수 있습니다. 

> [!IMPORTANT]
> 관리자는 라이선스를 관리하기 위해 전역 관리자 또는 사용자 관리 관리자 권한이 Microsoft Teams 있어야 합니다.
이 Microsoft 365 관리 센터 사용하여 Teams 사용자 또는 소규모 사용자 집합에 대한 라이선스를 관리합니다. 라이선스 페이지에서 Teams(최대 20명 사용자) 또는 활성 사용자 페이지에서 라이선스를 **관리할 수** 있습니다.  선택한 방법은 특정 사용자에 대한 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 결정됩니다.

수백 또는 수천 명의 사용자와 Teams 사용자에 대한 라이선스를 관리해야 하는 경우 [Azure AD(Azure AD)에서](/azure/active-directory/users-groups-roles/licensing-groups-assign) [PowerShell](#using-powershell) 또는 그룹 기반 라이선스를 Azure Active Directory. 

### <a name="assign-a-teams-license"></a>라이선스 Teams 할당

단계는 라이선스 페이지 또는 활성 사용자  페이지를 사용할지 여부에 따라 **다릅니다.**  단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](/microsoft-365/admin/manage/assign-licenses-to-users)

|&nbsp;|&nbsp;|
|---------|---------|
|![사용자에 대해 Teams 라이선스 중 스크린샷 1.](media/assign-teams-licenses-1.png)    | ![사용자에 대해 Teams 라이선스 스크린샷 2](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>라이선스 Teams 제거

> [!IMPORTANT]
> SKU를 사용할 수 Teams 24시간이 소요됩니다.

사용자에서 Teams 라이선스를 제거하면 해당 Teams 라이선스가 비활성화되어 앱 Teams 홈페이지에 해당 라이선스가 더 이상 표시되지 않습니다. 자세한 단계는 사용자로부터 라이선스의 [부가가치화(Unassign) 를 참조하세요.](/microsoft-365/admin/manage/remove-licenses-from-users)

|&nbsp;|&nbsp;|
|---------|---------|
|![사용자에 대해 사용 Teams 라이선스 중 스크린샷 1.](media/remove-teams-licenses-1.png)    | ![사용자에 대해 Teams 라이선스의 스크린샷 2](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 Teams 라이선스를 일괄적으로 관리합니다. 다른 서비스 Teams 라이선스와 동일한 방식으로 PowerShell을 통해 사용 및 비활성화합니다. 다음과 같은 Teams 서비스 계획의 식별자가 필요합니다.

- Microsoft Teams: TEAMS1
- Microsoft Teams GCC: TEAMS_GOV
- Microsoft Teams: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>대량 Teams 라이선스 할당

자세한 단계는 PowerShell을 통해 사용자 계정에 라이선스 [할당을 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>대량 Teams 라이선스 제거

자세한 단계는 [PowerShell을](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 통해 서비스에 대한 액세스 안 하도록 설정하고 사용자 라이선스를 할당하는 동안 서비스에 대한 액세스 사용 안 [을 참조하세요.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>예제 

다음은 [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) 및 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlet을 사용하여 특정 라이선스 계획이 있는 사용자에 대한 Teams 사용하지 않도록 설정하는 방법의 예입니다. 예를 들어 다음 단계를 수행하여 특정 라이선스 Teams 모든 사용자에 대한 Teams 사용하지 않도록 설정합니다. 그런 다음 Teams 액세스 권한이 있는 각 개별 사용자에 대해 Teams.

> [!IMPORTANT]
> [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet은 사용자 지정 스크립트에서 명시적으로 식별되지 않는 한 이전에 비활성화된 모든 서비스를 사용하도록 설정합니다. 예를 들어 Sway를 사용하지 않도록 설정하는 동안 Exchange Sway를 사용하지 않도록 설정하려는 Teams 스크립트에 이 기능을 포함해야 Exchange Sway와 Sway를 모두 사용하도록 설정해야 합니다.

다음 명령을 실행하여 조직에서 사용 가능한 모든 라이선스 계획을 표시합니다. 자세한 내용은 [PowerShell을 통해 라이선스 및 서비스 보기를 참조합니다.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

이전 단계에서 검색한 라이선스 계획의 식별자인 조직 이름과 식별자인 다음 명령을 \<CompanyName:License> 실행합니다. 예를 들어 ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

다음 명령을 실행하여 Teams 라이선스 계획에 대한 활성 라이선스가 있는 모든 사용자에 대해 다음 명령을 사용하지 않도록 설정합니다.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>관련 항목

- [Teams 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [추가 Teams 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [PowerShell을 통해 라이선스 및 서비스 보기](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [라이선싱에 대한 제품 이름 및 서비스 계획 식별자](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [교육 SKU 참조](sku-reference-edu.md)
