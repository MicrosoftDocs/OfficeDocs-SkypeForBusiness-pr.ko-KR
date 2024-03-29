---
title: 교육용 Teams 부모의 관리 설정
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: microsoft Teams 문서에서는 교육용 Teams 부모의 필수 구성 요소 및 설정을 문서화합니다.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- admindeeplinkTEAMS
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32ef76aeff228bc9386917cb2214965942b8be4e
ms.sourcegitcommit: 1f4a0b7cf03f63438bb37668d053853494c92168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69948575"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>교육용 Microsoft Teams 부모 연결 설정

교육용 Teams 부모 연결은 교육자는 Teams를 사용하여 수업 팀의 학생 부모와 보호자를 안전하게 연결하고 참여할 수 있도록 지원합니다.

이 문서에서는 부모 연결의 요구 사항 및 설정에 대한 교육 IT 전문가에게 지침을 제공합니다.

## <a name="share-guardian-and-educator-resources"></a>보호자 및 교육자 리소스 공유

다음은 IT 관리자가 보호자 및 교육자와 부모 연결을 사용하여 시작할 수 있는 방법에 대해 공유할 수 있는 몇 가지 리소스입니다.

- 보호자를 설정하는 방법에 대한 지침은 [Microsoft Teams에서 보호자와 통신을 참조하세요](https://support.microsoft.com/topic/communicate-with-guardians-in-microsoft-teams-01471ecd-eb5d-4eda-9c5d-0064d672960e?ui=en-us&rs=en-us&ad=us).
- 교육자를 설정하는 방법에 대한 지침은 [Teams에서 강사와 연결을 참조하세요](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

## <a name="benefits-of-parent-connection"></a>부모 연결의 이점

부모 연결을 사용하면 교육자와 보호자가 Teams를 사용하여 채팅, 전자 메일 및 통화를 할 수 있습니다.

- 교육자는 보호자와 채팅을 시작할 수 있습니다.
  - 보호자에게 Teams 소비자 계정이 없거나 아직 Teams에 가입하지 않은 경우 교육자로부터 Teams로 이동하라는 이메일 초대와 함께 메시지를 받게 됩니다. 이는 초대 제한에 도달하지 않은 경우에만 적용되며 채팅은 부모 연결에서 다시 입력된 새 채팅 또는 기존 채팅입니다.
- 감독 채팅에서 작동합니다. 자세한 내용은 [Microsoft Teams에서 감독 채팅 사용을 참조하세요](supervise-chats-edu.md).
  - 기본적으로 보호자는 제한된 권한을 가지므로 학생과 채팅하거나 채팅에서 사용자를 제거할 수 없습니다.
  - 이 설정은 테넌트 관리자가 변경할 수 있습니다.
- 교육자는 보호자의 이메일을 선택하여 네이티브 이메일 클라이언트를 사용하여 전자 메일을 보낼 수 있습니다.
- 교육자는 보호자의 전화 번호를 선택하여 Teams 내에서 전화를 걸 수 있습니다.

> [!IMPORTANT]
> Teams에서 기능을 호출하려면 테넌트에서 다음이 필요합니다.
>
> - PBX(Public Branch Exchange) 기능.
> - PSTN에 연결합니다.
>
> Microsoft 365 A1 및 A3 계획에는 PBX 기능이나 PSTN 연결이 포함되지 않습니다. [이러한 각 라이선스에 대한 추가 기능 라이선스를](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 구입할 수 있습니다.
>
> Microsoft 365 A5 계획에는 Teams 전화 시스템을 사용하는 PBX 기능만 포함됩니다. [Teams 통화 플랜을 구매하거나 타사 솔루션을 사용하여](pstn-connectivity.md) PSTN의 외부 번호에 연결해야 합니다.
>
> PSTN 연결을 가져오는 모든 옵션에 대한 자세한 내용은 [PSTN 연결 옵션을 참조하세요](pstn-connectivity.md).
>
> Teams 통화 라이선스에 대한 자세한 내용은 [Teams 추가 기능 라이선스 옵션을 참조하세요](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).

## <a name="requirements"></a>요구 사항

Microsoft Graph 또는 SDS(학교 데이터 동기화)를 사용하여 각 학생의 부모 및 보호자 관련 연락처 정보를 채워야 합니다.

### <a name="graph-api"></a>그래프 API

[이미 Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/overview)를 사용하여 학생 ID를 만드는 경우 [relatedContact 리소스 종류를](/graph/api/resources/relatedcontact) 쉽게 포함할 수 있습니다.

### <a name="school-data-sync"></a>학교 데이터 동기화

SDS가 정기적으로 동기화되도록 설정된 경우 Teams 보호자 연락처 데이터는 SDS(School Data Sync)를 사용하여 SIS와 최신 상태를 유지합니다.

*보호자가 학생의* 레코드에서 제거되면 해당 채팅과 관련된 기존 채팅에는 채팅 소유자가 볼 수 있는 배너가 포함됩니다. 이 배너는 채팅 소유자가 변경 사항을 인식하도록 하여 채팅에서 보호자를 제거하도록 요청합니다. Microsoft는 보호자를 제거하도록 채팅 멤버 자격을 자동으로 업데이트하지 않습니다.

- 각 학생의 부모 및 보호자 **관련 연락처** 정보를 채우려면 SDS(학교 데이터 동기화)가 필요합니다.
  - [SDS 배포](/schooldatasync/parents-and-guardians-in-sds)

- SDS를 설정하고 테넌트의 학생에 대한 부모 및 보호자 **관련 연락처** 를 채우는 데 도움이 필요한 경우 다음을 수행하여 EDU 고객 성공 팀에 문의하세요.
  - [FastTrack](https://www.microsoft.com/fasttrack?rtc=1)에서 RFA 프로세스 완료
  - [지원](https://aka.ms/sdssupport)에서 티켓을 엽니다.

- 현재 SDS는 부모 연락처에 대한 CSV 기반 데이터 수집만 지원합니다. 그러나 모든 명단 데이터에 [PowerSchool API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) 또는 [OneRoster API Sync](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) 를 사용하고 CSV를 사용하여 부모 연락처를 추가할 수 있습니다.
  - [SDS v1 CSV 형식 또는 SDS v2.1 CSV 형식](/schooldatasync/school-data-sync-format-csv-files-for-sds)을 사용하여 두 번째 동기화 프로필을 만듭니[다](/schooldatasync/sds-v2.1-csv-file-format-classic).
  - 나머지 v1/v2.1 [파일이](/schooldatasync/parent-contact-sync-file-format) 비어 있는 채운 부모 파일 두 개(헤더만)를 가져옵니다.
    - User.csv
    - Guardianrelationship.csv
      - 각 부모 및 보호자가 또는 `guardian`인지 `parent` 여부를 나타내려면 *역할* 값을 완료해야 합니다.
        - 또는 `guardian` 의 `parent` 값만 앱에서 지원됩니다. 다른 값으로 인해 오류가 발생합니다.
        - SDS v1 형식의 경우 **역할** 로 레이블이 지정되지만 SDS v2.1 형식의 경우 **relationshipRole** 로 레이블이 지정됩니다.
  - CSV 파일의 샘플 집합을 보려면 [최소 필수 특성 GitHub 파일을 참조하세요](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - 초기 동기화 후 CSV 파일 끌어올리기를 자동화하려면 [CSV 파일 동기화 Automation 문서를](/schooldatasync/csv-file-sync-automation) 읽어보세요.
  - SDS 데이터 동기화 설정에 대한 도움말을 보려면 [고객 성공 팀에](https://www.microsoft.com/fasttrack?rtc=1) 문의하거나 [지원 티켓을 엽니다](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center-policies"></a>Teams 관리 센터 정책

- 수업 팀 소유자는 Teams 채팅이 켜져 있어야 합니다.
- 수업 팀 소유자는 **조직에서 관리하지 않는 Teams 계정이 켜져 있는** 외부 액세스 권한이 있어야 합니다.
  - 테넌트 수준 및 사용자 수준에서 이 설정을 설정해야 합니다. 테넌트 수준 설정은 Teams 관리 센터의 **사용자 > 외부 액세스** 에서 찾을 수 있습니다. 이 설정은 PowerShell을 통해 액세스할 수도 있습니다. 사용자 수준 외부 액세스 정책은 PowerShell을 통해서만 액세스할 수 있습니다. 자세한 내용은 [아래 PowerShell 명령을 참조하세요](#allow-external-access-with-teams-accounts-not-managed-by-an-organization).
- 부모 연결 앱에서 모임을 만들 수 있도록 하려면 다음 정책을 설정해야 합니다.
  - [비공개 모임 예약을 허용합니다](meeting-policies-in-teams.md#allow-scheduling-private-meetings).
  - [익명 사용자가 모임에 참가하도록 허용합니다](meeting-policies-participants-and-guests.md#let-anonymous-people-join-a-meeting).

#### <a name="parent-and-guardian-restrictions"></a>부모 및 보호자 제한 사항

부모 및 보호자는 부모 연결에서 *외부 사용자* 로 분류되므로 전체 테넌트 권한이 없습니다. 채팅에 포함된 채팅 또는 채팅과 채팅에서 공유되는 파일, 이미지 및 기타 콘텐츠에만 액세스할 수 있습니다.

외부 채팅의 경우 내부 및 외부 사용자 모두 채팅에 사용자를 추가할 수 있습니다. 외부 채팅 환경에 대한 자세한 내용은 [Microsoft Teams에서 외부 모임 및 채팅 관리를 참조하세요](manage-external-access.md).

또한 외부 사용자는 조직 사용자의 현재 상태(오프라인, 사용 가능, 사용 중 등)를 볼 수 있지만 PowerShell을 사용하여 사용자의 개인 정보를 보호하기 위해 해제할 수 있습니다. PowerShell에서 [Set-CsPrivacyConfiguration을](/powershell/module/skype/set-csprivacyconfiguration) 사용하고 를 설정합니다 ``EnablePrivacyMode=true``.

부모와 보호자는 외부 사용자이지만 채팅에 대한 기여를 검색할 수 있습니다. Microsoft Teams에서 콘텐츠에 대한 [eDiscovery 조사 수행을 참조하여 Teams eDiscovery 조사를](ediscovery-investigation.md) 수행하는 방법을 알아봅니다.

> [!IMPORTANT]
> IT 관리자는 학생 개인 정보 보호에 대한 위험을 포함하여 채팅을 통해 학생 정보를 공유하기 위한 모범 사례에 대해 모든 수업 소유자에게 교육해야 합니다.

#### <a name="blocking-a-parent-or-guardian-in-a-chat"></a>채팅에서 부모 또는 보호자 차단

교육자는 부모 연결에서 시작된 채팅에서 보호자를 차단할 수 있습니다.

클래스 소유자는 다음을 수행할 수 있습니다.

1. 보호자의 프로필 카드를 열고 타원 및 **사용자 차단** 을 선택합니다.
2. 그런 다음 채팅에서 보호자를 제거합니다.

차단된 사용자는 클래스 소유자와 다른 채팅을 시작할 수 없습니다.

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>조직에서 관리하지 않는 Teams 계정으로 외부 액세스 허용

교육자가 Teams에서 부모 및 보호자와 통신할 수 있도록 교육 테넌트의 IT 관리자는 테넌트 외부의 Teams 계정에 대한 외부 액세스를 허용하도록 테넌트의 정책을 업데이트해야 합니다. 외부 액세스 관리에 대한 자세한 내용은 [Microsoft Teams에서 외부 액세스 관리를 참조하세요](manage-external-access.md).

다음은 부모와 보호자에 대한 외부 액세스를 설정하는 단계입니다.

1. 여기에 최신 Microsoft Teams PowerShell 모듈을 설치합니다 [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. 관리자 권한이 있는 자격 증명을 사용하여 다음 명령을 실행합니다.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    사용자 수준(`EnableTeamsConsumerAccess`)에서 조직에서 관리하지 않는 Teams 계정으로 외부 액세스를 설정하는 정책 설정은 기본적으로 모든 사용자 수준 외부 액세스 정책에 대해 설정됩니다. 사용자가 조직에서 관리하지 않는 Teams 계정으로 외부 액세스 권한을 가지려면 테넌트 수준 설정과 사용자 수준 정책 설정을 모두 설정해야 합니다. 테넌트의 모든 사용자가 이 액세스 권한을 설정하지 않도록 하려면 테넌트 수준 설정이 꺼져 있는지 확인하고, 사용자에게 할당된 사용자 수준 외부 액세스 정책을 업데이트한 다음, 테넌트 수준 설정을 켜야 합니다.

    존재하는 사용자 수준 외부 액세스 정책과 할당된 사용자를 확인하려면 다음 단계를 사용할 수 있습니다.

3. 사용자 수준 외부 액세스 정책이 있는지 확인합니다.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. '전역' 정책이 아닌 각 정책에 대해 정책이 할당된 사용자를 확인합니다.

    > [!NOTE]
    > 특정 정책이 할당되지 않은 모든 사용자는 '전역' 정책으로 대체됩니다. 테넌트 에 추가된 모든 새 사용자에게는 '전역' 정책이 할당됩니다.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

모든 사용자 수준 외부 액세스 정책은 기본적으로 true로 설정되었 `EnableTeamsConsumerAccess` 으므로 특정 사용자에 대한 설정을 조정 `EnableTeamsConsumerAccess` 하려는 경우 다음 PowerShell cmdlet을 사용하여 조정된 설정으로 기존 외부 액세스 정책을 만들거나 수정하거나 새 정책 또는 기존 정책에 사용자를 다시 할당할 수 있습니다.

- 새 외부 액세스 정책 만들기: [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- 기존 외부 액세스 정책 사용자 지정('전역' 정책 포함): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> 'FederationAndPICDefault', 'FederationOnly', 'NoFederationAndPIC' 구독 기본 정책을 수정할 수 없습니다. 기본적으로 모든 사용자에게 할당되던 'FederationAndPICDefault' 정책은 새 사용자에게 기본적으로 '전역' 정책이 할당됩니다. 이러한 구독 기본 정책이 할당된 사용자의 정책 설정을 변경해야 하는 경우 이러한 사용자에게 올바른 설정을 사용하여 다른 정책을 할당합니다.

- 단일 사용자에게 외부 액세스 정책 할당: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- 사용자 집합에 정책 할당: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

테넌트 내 사용자에 대해 사용자 수준 외부 액세스 정책이 올바르게 설정되면 다음 cmdlet을 사용하여 테넌트용 테넌트 수준 설정(`AllowTeamsConsumer`)을 켤 수 있습니다.

- 테넌트에 대한 페더레이션 구성 설정: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Teams 관리 센터에서 부모 앱 켜기

부모 앱은 기본적으로 꺼져 있으므로 수업 팀 소유자는 Teams 관리 센터를 통해 허용될 때까지 수업 팀에서 볼 수 없습니다. 개발자가 차단한 앱 허용을 사용하여 Teams 관리 센터에서 부모 [앱이 켜져 있습니다](manage-apps.md#allow-and-block-apps).

언제든지 Teams 관리 센터에서 [앱 허용 및 차단](manage-apps.md#allow-and-block-apps) 을 사용하여 테넌트 수준에서 앱을 끌 수 있습니다. 테넌트 수준에서 해제된 경우 사용자 수준 권한이 켜져 있더라도 모든 사용자에 대해 차단됩니다.

[Microsoft Teams에서 앱 권한 정책 관리를](teams-app-permission-policies.md) 사용하여 사용자 수준에서 부모 앱을 끌 수도 있습니다.

## <a name="set-a-preferred-invitation-channel"></a>기본 초대 채널 설정

관리자는 기본 설정 부모 연결 초대 채널로 이메일 또는 SMS를 선택할 수 있습니다.

부모 및 보호자에게 보낸 메시지는 HTML, 서식 또는 스타일이 적용되지 않고 일반 텍스트로 표시됩니다.

> [!NOTE]
> 부모 연결 초대를 부모 및 보호자에게 보내기 위한 기본 설정 채널로 SMS를 선택하는 경우 다음 사항에 유의하세요.
>
> - 부모 및 보호자 전화 번호는 SMS 초대 및 프로필 조회가 작동하도록 E.164 형식이어야 합니다.
>   - 예를 들어 전화 번호의 서식을 와 같이 `+12223334444`로 `+[country code][area code][phone number]`지정합니다.
> - 이동 통신 사업자 SMS 요금은 SMS 초대를 받는 부모 및 보호자에게 청구될 수 있습니다.

### <a name="set-a-preferred-invite-channel-in-the-teams-admin-center"></a>Teams 관리 센터에서 기본 설정 초대 채널 설정

1. [Teams 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2066851).
1. **교육** > **부모 및 보호자 설정** 으로 이동합니다.
1. **기본 설정 연락처 방법** 필드에서 **Email** 또는 **휴대폰 - SMS** 를 선택합니다.
1. 변경 내용을 저장합니다.

### <a name="set-a-preferred-invite-channel-using-powershell"></a>PowerShell을 사용하여 기본 설정 초대 채널 설정

1. 에 Teams PowerShell 모듈 [https://www.powershellgallery.com/packages/MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams)의 *4.9.0 버전 이상을* 설치합니다.

1. 아래 명령을 실행하고 관리자 자격 증명으로 로그인합니다.

    ```powershell
    Connect-MicrosoftTeams
    ```

1. 아래 명령을 실행하여 의 현재 값을 확인합니다 `ParentGuardianPreferredContactMethod`.

    ```powershell
    Get-CsTeamsEducationConfiguration
    ```

1. 아래 명령 중 하나를 실행하여 값을 변경합니다.

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod Email
    ```

    ```powershell
    Set-CsTeamsEducationConfiguration -ParentGuardianPreferredContactMethod SMS
    ```

## <a name="more-information"></a>추가 정보

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
