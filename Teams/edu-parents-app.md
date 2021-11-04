---
title: EDU Microsoft 부모 앱에 대한 관리자 설정
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 문서 문서의 전제요구 및 부모 앱에 대한 PowerShell 설정에 대해 설명할 수 있습니다.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785151"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>부모 앱을 Microsoft Teams

부모 앱은 교사가 교사 조직 전체에서 확장되는 Teams 사용하여 수업에 있는 학생의 부모 및 보호자와 안전하게 연결하고 참여할 수 있도록 합니다. 모든 부모 및 보호자 데이터는 학교 데이터 동기화 사용하여 프로비전되므로 교육자 및 IT 직원이 원활하게 설정할 수 있습니다.

## <a name="requirements"></a>요구 사항

### <a name="school-data-sync"></a>학교 데이터 동기화

- 각 학교 데이터 동기화 연락처 정보를 채우기 위해 SDS(SDS)가  필요합니다.
  - [SDS 배포](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- SDS를 설정하고 테넌트에서 부모 연락처를 사용하도록 설정하는 데 도움이 필요한 경우 다음을 통해 EDU 고객 성공 팀에 문의하세요.
  - 에서 RFA [프로세스를 FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - 지원 에서 [티켓을 여는 중입니다.](https://aka.ms/sdssupport)

### <a name="teams-admins-center---policies"></a>Teams 관리 센터 - 정책

- 클래스 소유자가 채팅을 사용하도록 설정되어 있어야 합니다.
- 클래스 소유자는 조직에서 관리하지 Teams 계정이 있는 외부 **액세스가 있어야** 합니다. 
  - 이 설정은 테넌트 > 외부 액세스 사용자 또는 특정 사용자 집합에 대해 사용하도록 설정하려면 아래 PowerShell을 참조하세요.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>사용자당 페더링된 채팅 사용

1. 최신 PowerShell Microsoft Teams 미리 보기를 설치합니다.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. 관리자 권한이 있는 자격 증명을 사용하여 명령 창에서 다음 명령을 실행합니다.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

사용자 수준에서 소비자 Teams(EnableTeamsConsumerAccess)를 사용하도록 설정하는 정책 설정은 기본적으로 모든 사용자 수준 외부 액세스 정책에 대해 사용하도록 설정됩니다. 테넌트 수준 설정(AllowTeamsConsumer)과 사용자 수준 정책 설정을 모두 사용하도록 설정해야 사용자에게 외부 Teams 수 있습니다. 테넌트의 모든 사용자가 소비자 외부 Teams 사용하도록 설정하지 못하도록 원하지 않는 경우 테넌트 수준 설정을 사용하도록 설정하기 전에 사용자에게 할당된 사용자 수준 외부 액세스 정책을 업데이트해야 합니다.

존재하는 사용자 수준 외부 액세스 정책과 할당된 사용자를 확인해야 하는 경우 다음 단계를 사용할 수 있습니다.
    
3. 사용자 수준 외부 액세스 정책이 존재하는지 검사합니다.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. '전역' 정책이 다른 각 정책에 대해 정책이 할당된 사용자를 검사합니다. 참고: 특정 정책이 할당되지 않은 사용자는 '전역' 정책으로 돌아오게 됩니다.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>추가 PowerShell 옵션

모든 사용자 수준 외부 액세스 정책에는 EnableTeamsConsumerAccess가 기본적으로 true로 설정되어 있습니다. 이러한 정책을 업데이트하여 EnableTeamsConsumerAccess 설정을 조정하려면 다음 PowerShell을 통해 조정된 설정을 사용하여 새 외부 액세스 정책을 만들거나 사용자를 새 정책 또는 기존 정책으로 다시 설정할 수 있습니다.

- 새 외부 액세스 정책 만들기(이 경우 새 외부 액세스 정책을 만들고 설정을 [정의합니다. New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 기존 외부 액세스 정책 사용자 지정(전역 정책을 비롯한 기존 외부 액세스 정책의 설정 수정): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC"는 수정할 수 없습니다. 이러한 정책이 할당된 사용자에 대한 정책 설정을 변경해야 하는 경우 이러한 사용자에게 올바른 설정으로 다른 정책을 할당합니다.

- 단일 사용자에게 외부 액세스 정책 할당: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 사용자 집합에 정책 할당: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

모든 사용자에 대해 사용자 수준 외부 액세스 정책이 올바르게 설정되어 있다는 확신이 들면 다음 cmdlet을 사용하여 테넌트에 대한 소비자 Teams 제어하는 테넌트 수준 설정을 사용하도록 설정할 수 있습니다.

- 테넌트에 대한 페더넌트 구성 설정 설정(AllowTeamsConsumer를 true로 설정): [Set-CsTenantFederationConfiguration(SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>부모 앱 사용 안 하여

부모 앱은 기본적으로 사용하도록 설정되어 있으므로 모든 수업 소유자가 해당 수업 팀에 앱을 볼 수 있습니다. 관리 센터의 앱 허용 및 차단을 사용하여 테넌트 수준에서 앱을 Microsoft Teams 수 있습니다. [](manage-apps.md#allow-and-block-apps) 테넌트 수준에서 사용하지 않도록 설정되어 있는 경우 사용자 수준 사용 권한이 활성화되어 있는 경우에도 모든 사용자에 대해 차단됩니다.

사용자 수준에서 [앱 사용 권한 정책 관리]를 사용하여 이 기능을 Microsoft Teams. (teams-app-permission-policies.md).

## <a name="more-information"></a>추가 정보

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [사용자에게 정책 할당](/powershell/module/skype/grant-csexternalaccesspolicy)
