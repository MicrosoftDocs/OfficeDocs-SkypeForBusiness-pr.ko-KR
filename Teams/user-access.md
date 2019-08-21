---
title: Microsoft 팀에 대 한 사용자 액세스 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
f1keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: 사용자별로 사용자 수준 액세스를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc5d5b7b97a8105fd8ecc3776479249175962d14
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483987"
---
<a name="manage-user-access-to-microsoft-teams"></a>Microsoft 팀에 대 한 사용자 액세스 관리
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

사용자 수준에서 microsoft 팀 제품 라이선스를 할당 하거나 제거 하 여 사용자 기준으로 Microsoft 팀에 대 한 액세스를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

팀 관리 센터에서 관리 되는 메시징 정책을 사용 하 여 팀의 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어 합니다. 기본 정책을 사용 하거나 조직의 사용자를 위해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다. 자세한 내용은 [팀에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참고 하세요.

> [!NOTE]
>팀에서 프로젝트 및 기타 동적 이니셔티브에 대 한 organically를 만들 수 있도록 회사의 모든 사용자에 대해 팀을 설정 하는 것이 좋습니다. 파일럿을 결정 하는 경우에도 팀이 모든 사용자에 게 사용 하도록 설정 하는 것이 좋지만, 사용자의 파일럿 그룹에 대 한 대상 통신만을 유지 하는 것이 유용할 수 있습니다.

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 통해 팀 관리

팀 사용자 수준 라이선스는 Microsoft 365 관리 센터 사용자 관리 인터페이스를 통해 직접 관리 됩니다. 관리자는 새 사용자 계정이 만들어지거나 기존 계정이 있는 사용자에 게 라이선스를 할당할 수 있습니다. Microsoft 팀 라이선스를 관리 하려면 관리자에 게 Office 365 전역 관리자 또는 사용자 관리 관리자 권한이 있어야 합니다.

E3 또는 E5와 같은 라이선스 SKU가 사용자에 게 할당 되 면 Microsoft 팀 라이선스가 자동으로 할당 되며 사용자가 Microsoft 팀에 대해 사용 하도록 설정 됩니다. 관리자는 모든 Office 365 서비스 및 라이선스를 세부적으로 제어할 수 있으며 특정 사용자 또는 사용자 그룹의 Microsoft 팀 라이선스를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

![관리 센터의 제품 라이선스 섹션 스크린샷](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

팀 사용자 라이선스는 언제 든 지 비활성화할 수 있습니다. 라이선스를 사용 하지 않도록 설정 하면 Microsoft 팀에 대 한 사용자 액세스가 차단 되 고 사용자가 Office 365 앱 시작 관리자 및 홈페이지에서 팀을 더 이상 볼 수 없게 됩니다.

![제품 라이선스 섹션에서 선택한 팀을 보여 주는 스크린샷](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>PowerShell을 통해 관리

> [!IMPORTANT]
> MsolLicenseOptions는 사용자 지정 된 스크립트에서 explictitly identitied 되지 않는 한 이전에 비활성화 한 모든 서비스를 사용 하도록 설정 합니다. 예를 들어 팀을 additonally 사용 하지 않도록 설정 하는 동안 Exchange & Sway를 사용 하지 않도록 설정 하려면 스크립트에서이를 제거 하거나 Exchange & Sway가 확인 된 사용자에 대해 사용 하도록 설정 되어 있어야 합니다. GUI를 이용 하 여이 기능을 관리 하려면 다음을 참조 하세요. [Office 365 라이선스 보고 및 관리 도구-라이선스를 대량으로 제거 할당](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

다른 작업을 수행 하는 것 처럼 PowerShell을 통해 팀을 작업 부하 라이선스로 사용 하지 않도록 설정할 수 있습니다. Microsoft 팀에 대 한 서비스 계획 이름은 TEAMS1입니다. GCC의 경우 서비스 계획 이름은 TEAMS_GOV입니다. GCC High의 경우 서비스 계획 이름은 TEAMS_GCCHIGH입니다. DoD의 경우 서비스 계획 이름은 TEAMS_DOD (자세한 내용은 [Office 365 PowerShell을 사용 하 여 서비스에 대 한 액세스 비활성화](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 를 참조 하세요.)

**샘플:** 다음은 특정 라이선스 유형의 모든 사용자에 대해 팀을 비활성화 하는 방법에 대 한 간단한 예제입니다. 먼저이 작업을 수행한 다음 파일럿을 위해 액세스 해야 하는 사용자에 대해 개별적으로 사용 하도록 설정 해야 합니다.

조직 내에 있는 구독 유형을 표시 하려면 다음 명령을 사용 합니다.

      Get-MsolAccountSku

조직의 이름과 학교에 대 한 계획 (ContosoSchool: ENTERPRISEPACK_STUDENT)을 포함 하는 계획의 이름을 입력 하 고 다음 명령을 실행 합니다.

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
지정 된 요금제에 대 한 활성 라이선스가 있는 모든 사용자에 대해 팀을 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![결정 지점을 나타내는 아이콘](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |판단 요점         |<ul><li>조직에서 온 팀에 대 한 조직의 계획은 무엇 인가요?  (파일럿 또는 열기)</li></ul>         |
|![다음 단계를 나타내는 아이콘](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |다음 단계         |<ul><li>폐쇄형 파일럿을 통해 온 보 딩이 있는 경우 라이선스를 통해 수행할 것인지 또는 대상을 지정 하 여 의사 소통을 할지 결정 하세요.</li><li>의사 결정에 따라 팀에 액세스할 수 있도록 허용 된 파일럿 사용자만 (필요한 경우) 해야 하는지 여부를 확인 하는 단계를 수행 합니다.</li><li>팀에 대 한 액세스 권한이 있는 사용자를 위한 지침을 문서화 합니다.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Office 365 테 넌 트 수준에서 팀 관리
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

