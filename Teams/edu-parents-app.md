---
title: 부모의 관리자 교육용 Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams 구성의 전제 및 부모 설정을 문서화하는 교육용 Teams.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d1b84fc78558fcbb1945cbc56b311b5e06234a5
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062532"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>상위 연결 설정 교육용 Microsoft Teams

학부모 연결은 교육용 Teams 채팅을 사용하여 수업 팀의 학생의 부모 및 보호자들과 안전하게 연결하고 Teams 수 있도록 하여 교사의 조직 전체에 걸쳐 확장됩니다. 모든 부모 및 보호자 데이터는 학교 데이터 동기화 사용하여 프로비전되므로 IT 직원이 원활하게 설정할 수 있습니다.

교육자 및 보호자가 설정된 후 채팅을 사용하여 서로 채팅할 Teams 있습니다. 

부모 및 보호자가 교육자에 연결되는 방법에 대한 지침은 커넥트 교사와의 [Teams.](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960)

부모 및 보호자와 통신하기 위해 교사를 설정하는 방법에 대한 지침은 보호자 및 보호[자와의 통신을 Microsoft Teams](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).

부모는 감독 채팅에서도 작동합니다. 부모 및 보호자는 모든 권한을 Teams 없습니다. 즉, 학생과의 대화를 시작하거나 채팅에서 전체 사용 권한 사용자(예: 교사)를 제거할 수 없습니다. 감독 채팅에 대한 자세한 내용은 감독 채팅에서 감독 채팅 [사용을 Microsoft Teams](supervise-chats-edu.md).

## <a name="requirements"></a>요구 사항

### <a name="school-data-sync"></a>학교 데이터 동기화

- 각 학교 데이터 동기화 보호자 관련 연락처 정보를 채우기 위해 SDS(SDS)가 **필요합니다**.
  - [SDS 배포](/schooldatasync/parents-and-guardians-in-sds)

- SDS를 설정하고 테넌트의 학생에 대한 부모 및 보호자  관련 연락처를 채우는 데 도움이 필요한 경우 다음을 통해 EDU 고객 성공 팀에 문의하세요.
  - RFA 프로세스를 [FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - 지원에서 티켓 [을 여는 중입니다](https://aka.ms/sdssupport).

- 현재 SDS는 부모 연락처에 대한 CSV 기반 데이터 수집만 지원합니다. 그러나 모든 로스터 데이터에 [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) 또는 [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) 를 사용하고 CSV를 사용하여 상위 연락처를 추가할 수 있습니다.
  - [SDS v1 CSV](/schooldatasync/school-data-sync-format-csv-files-for-sds) 동기화 형식을 사용하여 두 번째 동기화 프로필을 생성합니다.
  - 채워진 두 개의 부모 파일을 [](/schooldatasync/parent-contact-sync-file-format) v1 파일의 나머지 파일(헤더만)을 비워 뽑습니다.
    - User.csv
    - Guardianrelationship.csv
  - v1 CSV 파일의 샘플 집합을 표시하려면 파일에서 필요한 최소 특성 GitHub [참조합니다](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - 초기 동기화 후 CSV 파일 끌어오기를 자동화하려면 [CSV 파일 동기화 자동화 문서를 읽어보아야 합니다](/schooldatasync/csv-file-sync-automation).
  - SDS 데이터 동기화 설정에 대한 도움말을 원하면 고객 성공 팀 [](https://www.microsoft.com/fasttrack?rtc=1) 에 문의하거나 지원 티켓[을 하세요](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams 관리 센터 - 정책

- 수업 팀 소유자는 채팅을 Teams 있어야 합니다.
- 클래스 팀 소유자는 조직에서 관리하지 않는 Teams 외부 액세스 **권한이** 있어야 합니다.
  - 테넌트 수준 및 사용자 수준에서 설정해야 합니다. 테넌트 수준 설정은 관리 센터의 > **외부** 액세스에서 Teams 있습니다. 이 설정은 PowerShell을 통해 액세스할 수도 있습니다. 사용자 수준 외부 액세스 정책은 PowerShell을 통해서만 액세스할 수 있습니다. 자세한 내용은 아래 PowerShell 명령을 참조하세요.

> [!NOTE]
>부모 및 보호자는 부모 기능의 외부 사용자로 분류됩니다. 즉, 전체 테넌트 권한은 없습니다. 채팅에서 공유되는 파일, 이미지 및 기타 콘텐츠뿐만 아니라 추가된 채팅 또는 채팅에만 액세스할 수 있습니다.
>
>또한 외부 사용자는 조직의 사용자의 현재 상태(오프라인, 사용 가능, 사용 중 등)를 볼 수 있지만 PowerShell을 사용하여 사용자의 개인 정보를 보호할 수 있습니다. PowerShell에서 [Set-CsPrivacyConfiguration을 사용하여](/powershell/module/skype/set-csprivacyconfiguration) 을 설정합니다 ``EnablePrivacyMode=true``.
>
>부모와 보호자가 외부 사용자인 경우에도 채팅에 대한 기여를 검색할 수 있습니다. [eDiscovery Teams eDiscovery 조사 수행을 읽고 eDiscovery](ediscovery-investigation.md) 조사를 Microsoft Teams.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>조직에서 관리하지 Teams 계정으로 외부 액세스 허용

교육자가 테넌트의 부모 및 보호자와 Teams 허용하려면 교육 테넌트의 IT 관리자는 테넌트 외부의 계정에 대한 외부 Teams 수 있도록 테넌트의 정책을 업데이트해야 합니다. 외부 액세스 관리에 대한 자세한 내용은 외부 액세스 관리를 [Microsoft Teams.](manage-external-access.md)

다음은 부모 및 보호자에 대한 외부 액세스를 설정하는 단계입니다.

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

    사용자 수준에서`EnableTeamsConsumerAccess` 조직에서 관리하지 Teams 계정으로 외부 액세스를 설정하는 정책 설정은 모든 사용자 수준 외부 액세스 정책에 대해 기본적으로 켜져 있습니다. 사용자가 조직에서 관리하지 않는 계정으로 외부 액세스 권한을 Teams 테넌트 수준 설정과 사용자 수준 정책 설정을 모두 켜야 합니다. 테넌트의 모든 사용자가 이 액세스 권한을 설정하지 않도록 설정하지 않는 경우 테넌트 수준 설정이 해제되어 있는지 확인한 다음 사용자에게 할당된 사용자 수준 외부 액세스 정책을 업데이트한 다음 테넌트 수준 설정을 켜야 합니다.

    어떤 사용자 수준 외부 액세스 정책이 존재하는지 및 할당된 사용자를 확인하기 위해 다음 단계를 사용할 수 있습니다.

3. 사용자 수준 외부 액세스 정책이 존재하는지 검사합니다.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. '전역' 정책이 다른 각 정책에 대해 정책이 할당된 사용자를 검사합니다.

   > [!NOTE]
   > 특정 정책이 할당되지 않은 모든 사용자는 '글로벌' 정책으로 돌아오게 됩니다. 테넌트에 추가된 모든 새 사용자에게는 '전역' 정책이 할당됩니다.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

모든 사용자 `EnableTeamsConsumerAccess` `EnableTeamsConsumerAccess` 수준 외부 액세스 정책이 기본적으로 true로 설정되어 있습니다. 특정 사용자에 대한 설정을 조정하려면 다음 PowerShell cmdlet을 사용하여 조정된 설정을 사용하여 기존 외부 액세스 정책을 만들고 수정하거나 사용자를 새 정책 또는 기존 정책으로 다시 설정할 수 있습니다.

- 새 외부 액세스 정책 만들기: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 기존 외부 액세스 정책 사용자 지정('전역' 정책 포함): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC'는 다음과 같은 구독 기본 정책을 수정할 수 없습니다. 기본적으로 모든 사용자에게 할당되는 데 사용되는 'FederationAndPICDefault' 정책은 새 사용자에게는 기본적으로 '전역' 정책이 할당됩니다. 이러한 구독 기본 정책이 할당된 사용자에 대한 정책 설정을 변경해야 하는 경우 이러한 사용자에게 올바른 설정으로 다른 정책을 할당합니다.

- 단일 사용자에게 외부 액세스 정책 할당: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 사용자 집합에 정책 할당: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

테넌`AllowTeamsConsumer`트의 사용자에 대해 사용자 수준 외부 액세스 정책이 올바르게 설정되면 다음 cmdlet을 사용하여 테넌트에 대한 테넌트 수준 설정()을 설정할 수 있습니다.

- 테넌트에 대한 페더넌트 구성 설정 설정: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>관리 센터에서 부모 Teams 켜기

부모 앱은 기본적으로 해제되어 있으므로 수업 팀 소유자는 관리 센터를 통해 허용될 때까지 수업 팀에 Teams 없습니다. 게시자가 차단한 앱 허용을 Teams 관리 센터에서 부모 앱이 [켜져 있습니다](manage-apps.md#apps-blocked-by-publishers).

관리 센터에서 앱 허용 및 차단을 사용하여 테넌트 수준에서 앱을 Teams 수 [](manage-apps.md#allow-and-block-apps) 있습니다. 테넌트 수준에서 해제된 경우 사용자 수준 사용 권한이 켜져 있는 경우에도 모든 사용자에 대해 차단됩니다.

또한 부모 앱에서 앱 권한 관리 정책을 사용하여 사용자 수준에서 부모 앱을 [Microsoft Teams.](teams-app-permission-policies.md)

## <a name="more-information"></a>추가 정보

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
