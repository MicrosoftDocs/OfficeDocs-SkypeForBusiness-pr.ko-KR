---
title: Microsoft EDU 부모 앱에 대한 관리자 Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams 구성 및 부모 앱에 대한 설정을 문서화하는 EDU 문서에 대한 자세한 정보입니다.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9243dfedb11c9102673e821bd2fac9d06cf3c834
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887296"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>부모 앱을 Microsoft Teams

부모 앱은 교사가 교사의 조직 전체에서 확장되는 Teams 사용하여 수업 팀의 학생의 부모 및 보호자와 안전하게 연결하고 참여할 수 있도록 합니다. 모든 부모 및 보호자 데이터를 사용하여 프로비전되므로 IT 학교 데이터 동기화 원활하게 설정할 수 있습니다.

## <a name="requirements"></a>요구 사항

### <a name="school-data-sync"></a>학교 데이터 동기화

- 각 학교 데이터 동기화 보호자 관련 연락처 정보를 채우기 위해 SDS(SDS)가 **필요합니다.**
  - [SDS 배포](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- SDS를 설정하고 테넌트의 학생에 대한  부모 및 보호자 관련 연락처를 채우는 데 도움이 필요한 경우 다음을 통해 EDU 고객 성공 팀에 문의하세요.
  - 에서 RFA [프로세스를 FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - 지원 에서 [티켓을 여는 중입니다.](https://aka.ms/sdssupport)

### <a name="teams-admin-center---policies"></a>Teams 관리 센터 - 정책

- 수업 팀 소유자는 채팅을 Teams 있어야 합니다.
- 클래스 팀 소유자는 조직에서 관리하지 않는 Teams 외부 **액세스 권한이 있어야** 합니다. 
  - 테넌트 수준 및 사용자 수준에서 사용하도록 설정해야 합니다. 테넌트 수준 설정은  사용자 > 관리 센터의 Teams 있습니다. 이 설정은 PowerShell을 통해 액세스할 수도 있습니다. 사용자 수준 외부 액세스 정책은 PowerShell을 통해서만 액세스할 수 있습니다. 자세한 내용은 아래 PowerShell 명령을 참조하세요.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>조직에서 관리하지 Teams 계정으로 외부 액세스 사용

1. 최신 PowerShell Microsoft Teams 미리 보기를 설치합니다.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 관리자 권한이 있는 자격 증명을 사용하여 다음 명령을 실행합니다.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

사용자 수준에서 조직에서 관리하지 Teams 계정으로 외부 액세스를 허용하는 정책 설정은 모든 사용자 수준 외부 액세스 정책에 대해 기본적으로 `EnableTeamsConsumerAccess` 활성화됩니다. 사용자가 조직에서 관리하지 않는 계정이 있는 외부 Teams 테넌트 수준 설정과 사용자 수준 정책 설정을 사용하도록 설정해야 합니다. 테넌트의 모든 사용자가 이 액세스를 사용하도록 설정하지 않도록 설정하지 않도록 설정하려면 테넌트 수준 설정을 사용하지 않도록 설정하고, 사용자에게 할당된 사용자 수준 외부 액세스 정책을 업데이트한 다음 테넌트 수준 설정을 사용하도록 설정해야 합니다.

어떤 사용자 수준 외부 액세스 정책이 존재하고 할당된 사용자를 확인하기 위해 다음 단계를 사용할 수 있습니다.
    
3. 어떤 사용자 수준 외부 액세스 정책이 존재하는지 검사합니다.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. '전역' 정책이 다른 각 정책에 대해 정책이 할당된 사용자를 검사합니다. 참고: 특정 정책이 할당되지 않은 사용자는 '글로벌' 정책으로 돌아오게 됩니다. 테넌트에 추가된 모든 새 사용자에게는 '전역' 정책이 할당됩니다.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

모든 사용자 수준 외부 액세스 정책이 기본적으로 true로 설정되어 있습니다. 특정 사용자에 대한 설정을 조정하려면 다음 `EnableTeamsConsumerAccess` PowerShell cmdlet을 사용하여 조정된 설정을 사용하여 기존 외부 액세스 정책을 만들고 수정하거나 사용자를 새 정책 또는 기존 정책으로 다시 설정할 `EnableTeamsConsumerAccess` 수 있습니다.

- 새 외부 액세스 정책 만들기: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 기존 외부 액세스 정책 사용자 지정('전역' 정책 포함): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'는 다음과 같은 구독 기본 정책을 수정할 수 없습니다. 기본적으로 모든 사용자에게 할당되는 데 사용되는 'FederationAndPICDefault' 정책은 새 사용자에게는 기본적으로 '전역' 정책이 할당됩니다. 이러한 구독 기본 정책이 할당된 사용자에 대한 정책 설정을 변경해야 하는 경우 이러한 사용자에게 올바른 설정으로 다른 정책을 할당합니다.

- 단일 사용자에게 외부 액세스 정책 할당: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 사용자 집합에 정책 할당: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

테넌트의 사용자에 대해 사용자 수준 외부 액세스 정책이 올바르게 설정되면 다음 cmdlet을 사용하여 테넌트에 대한 테넌트 수준 설정() 을 사용하도록 설정할 `AllowTeamsConsumer` 수 있습니다.

- 테넌트에 대한 페더넌트 구성 설정 설정: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="disabling-the-parents-app"></a>부모 앱 사용 안 하여

부모 앱은 기본적으로 사용하도록 설정되어 있으므로 모든 수업 팀 소유자가 해당 수업 팀에 앱을 볼 수 있습니다. 

관리 센터의 앱 허용 및 차단을 사용하여 테넌트 수준에서 앱을 Microsoft Teams 수 있습니다. [](manage-apps.md#allow-and-block-apps) 앱이 테넌트 수준에서 사용하지 않도록 설정되어 있는 경우 사용자 수준 사용 권한이 활성화되어 있는 경우에도 모든 사용자에 대해 앱이 차단됩니다.

에서 앱 권한 관리 정책을 사용하여 사용자 수준에서 앱을 사용하지 않도록 설정할 [수도 Microsoft Teams.](teams-app-permission-policies.md)

## <a name="more-information"></a>추가 정보

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
