---
title: Microsoft 팀에 대 한 사용자 액세스 관리
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 조직의 사용자에 게 팀 라이선스를 할당 하거나 제거 하 여 팀에 대 한 사용자 액세스를 관리 하는 방법을 알아봅니다.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521385"
---
# <a name="manage-user-access-to-teams"></a>Teams에 대한 사용자 액세스 관리

Microsoft 팀 제품 라이선스를 할당 하거나 제거 하 여 사용자 수준에서 팀에 대 한 액세스를 관리 합니다. 조직의 각 사용자는 팀을 사용할 수 있으려면 팀 라이선스가 있어야 합니다. 새 사용자 계정이 만들어지거나 기존 계정이 있는 사용자에 게 팀 라이선스를 할당할 수 있습니다.

기본적으로 라이선스 계획 (예: Microsoft 365 Enterprise E3 또는 Microsoft 365 Business Premium)을 사용자에 게 할당 하면 팀 라이선스가 자동으로 할당 되며 사용자가 팀을 사용할 수 있습니다. 언제 든 지 라이선스를 제거 하거나 할당 하 여 사용자의 팀을 사용 하지 않도록 설정 하거나 설정할 수 있습니다.

팀 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>에서 관리 되는 메시징 정책을 사용 하 여 팀의 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어 합니다. 기본 정책을 사용 하거나 조직의 사용자를 위해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다. 자세한 내용은 [팀에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참고 하세요.
Microsoft 365 관리 센터에서 또는 PowerShell을 사용 하 여 팀 라이선스를 관리 합니다. 라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 여야 합니다.

> [!NOTE]
> 팀이 프로젝트 및 기타 동적 이니셔티브에 organically 수 있도록 모든 사용자에 대해 팀을 사용 하도록 설정 하는 것이 좋습니다. 파일럿을 실행 하는 경우에도 팀을 모든 사용자에 게 사용 하도록 설정 하는 것이 좋지만, 사용자의 파일럿 그룹에 대 한 대상 통신만을 유지 하는 것이 유용할 수 있습니다.

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용

팀 사용자 수준 라이선스는 Microsoft 365 관리 센터 사용자 관리 인터페이스를 통해 직접 관리 됩니다. 관리자는 새 사용자 계정이 만들어지거나 기존 계정이 있는 사용자에 게 라이선스를 할당할 수 있습니다. 

> [!IMPORTANT]
> 관리자가 Microsoft 팀 라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 권한이 있어야 합니다.
Microsoft 365 관리 센터를 사용 하 여 개별 사용자 또는 소규모 사용자 집합에 대 한 팀 라이선스를 한 번에 관리할 수 있습니다. **라이선스** 페이지 (한 번에 최대 20 명의 사용자) 또는 **활성 사용자** 페이지에서 팀 라이선스를 관리할 수 있습니다. 특정 사용자에 대 한 제품 라이선스를 관리 하거나 특정 제품에 대 한 사용자 라이선스를 관리할 것인지 여부에 따라 다른 방법이 선택 됩니다.

수백 또는 수천 명의 사용자와 같이 많은 사용자의 팀 라이선스를 관리 해야 하는 경우 Powershell 또는 azure [Active Directory (AZURE AD)의 그룹 기반 라이선스](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)를 [사용](#using-powershell) 합니다. 

### <a name="assign-a-teams-license"></a>팀 라이선스 할당

단계는 **라이선스** 페이지 또는 **활성 사용자** 페이지 사용 여부에 따라 달라 집니다.  단계별 지침은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.

|||
|---------|---------|
|![사용자가 사용할 수 있는 팀 라이선스의 스크린샷](media/assign-teams-licenses-1.png)    | ![사용자가 사용할 수 있는 팀 라이선스의 스크린샷](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>팀 라이선스 제거

사용자에 게 팀 라이선스를 제거 하면 해당 사용자에 대해 팀이 비활성화 되 고 앱 시작 관리자 또는 홈페이지에 팀이 더 이상 표시 되지 않습니다. 자세한 단계는 [사용자의 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)해제를 참조 하세요.

|||
|---------|---------|
|![사용자가 사용할 수 없는 팀 라이선스 스크린샷](media/remove-teams-licenses-1.png)    | ![사용자가 사용할 수 없는 팀 라이선스 스크린샷](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용 하 여 사용자의 팀 라이선스를 대량으로 관리할 수 있습니다. 다른 서비스 계획 라이선스를 사용할 때와 동일한 방식으로 PowerShell을 통해 팀을 활성화 하거나 비활성화 합니다. 팀에 대 한 서비스 계획의 식별자가 필요 합니다 (다음과 같습니다).

- Microsoft 팀: TEAMS1
- GCC 용 Microsoft 팀: TEAMS_GOV
- DoD에 대 한 Microsoft 팀: TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>팀 라이선스를 대량으로 배정

자세한 단계는 PowerShell을 [사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)을 참조 하세요.

### <a name="remove-teams-licenses-in-bulk"></a>팀 라이선스를 대량으로 제거

자세한 단계는 PowerShell을 [사용 하 여 서비스에 대 한 액세스 사용 안 함을](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 참조 하 고 [사용자 라이선스를 할당 하는 동안 서비스에](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)대 한 액세스

#### <a name="example"></a>예 

다음은 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 및 [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlet을 사용 하 여 특정 라이선스 계획이 있는 사용자를 위해 팀을 비활성화 하는 방법의 예입니다. 예를 들어 다음 단계에 따라 특정 라이선스 계획을 보유 하 고 있는 모든 사용자의 팀을 먼저 해제 합니다. 그런 다음 팀에 액세스 해야 하는 각 개별 사용자에 대해 팀을 활성화 합니다.

> [!IMPORTANT]
> [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet은 사용자 지정 스크립트에서 명시적으로 식별 되지 않는 한 이전에 비활성화 된 모든 서비스를 사용 하도록 설정 합니다. 예를 들어 팀을 사용 하지 않도록 설정 하는 동안 Exchange 및 Sway를 모두 사용 하지 않도록 설정 하려면 스크립트에이를 포함 하거나 Exchange 및 Sway 모두를 식별 한 사용자에 대해 사용 하도록 설정 해야 합니다.

다음 명령을 실행 하 여 조직에서 사용 가능한 모든 라이선스 계획을 표시 합니다. 자세히 알아보려면 [PowerShell을 사용 하 여 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)를 참조 하세요.

      Get-MsolAccountSku

\<CompanyName:License>조직 이름과 앞 단계에서 검색 한 라이선스 계획의 식별자 인 다음 명령을 실행 합니다. 예를 들어 ContosoSchool: ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

라이선스 요금제에 대 한 활성 라이선스가 있는 모든 사용자에 대해 팀을 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>조직 수준에서 팀 관리

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>관련 주제

- [팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [PowerShell을 사용 하 여 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [라이선싱에 대한 제품 이름 및 서비스 계획 식별자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [교육 SKU 참조](sku-reference-edu.md)