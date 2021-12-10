---
title: 온-프레미스와 클라우드 간에 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 하이브리드를 사용하도록 설정된 비즈니스용 Skype 서버 배포에서 사용자를 사내 환경과 클라우드 간에 이동할 수 있습니다.'
ms.openlocfilehash: 5d5f14cfdb5de2e11c95a2532900dfa3fcf669a1
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410709"
---
# <a name="move-users-between-on-premises-and-cloud"></a>온-프레미스와 클라우드 간에 사용자 이동

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

하이브리드에 대해 사용하도록 설정된 비즈니스용 Skype 서버 배포에서는 사용자를 사내 환경과 하이브리드 환경 간에 이동할 수 Teams. 사용자는 온-프레미스 아니면 클라우드에 있는지에 상관없이 사용자의 비즈니스용 Skype 홈이라고 합니다.

- 프레미스에 있는 사용자는 프레미스 서버와 비즈니스용 Skype 상호 작용합니다.
- 온라인에 있는 사용자는 Teams 있습니다.

*Teams 사용하는지 여부에 비즈니스용 Skype 본질적으로 비즈니스용 Skype 있습니다.* 나란히(나란히) 비즈니스용 Skype 사용자가 있는 Teams 사용자가 있는 경우 해당 사용자는 프레미스에 있습니다. Teams 비즈니스용 Skype 사용자가 비즈니스용 Skype 클라이언트에서 Teams 사용자와 상호 작업을 할 수 없으며 Teams 조직의 사용자와 통신할 수도 없습니다. 이러한 기능은 사용자가 온-프레미스에서 온라인으로 비즈니스용 Skype TeamsOnly로 설정한 후에만 완전히 사용할 수 있습니다. 사용자를 TeamsOnly 모드로 이동하여 들어오는 모든 채팅 및 통화의 라우팅이 해당 클라이언트에서 Teams 좋습니다. 자세한 내용은 Teams [](/microsoftteams/coexistence-chat-calls-presence) 함께 비즈니스용 Skype 조직에 대한 마이그레이션 및 상호 Teams 지침을 [비즈니스용 Skype.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>필수 구성 요소

사용자를 TeamsOnly 모드로 이동하기 위해의 선행 사항:

- 조직은 Azure AD 커넥트 구성에 설명된 바와 같이 사용자에 대한 모든 관련 특성을 올바르게 구성하고 동기화해야 [커넥트.](configure-azure-ad-connect.md)
- 비즈니스용 Skype 하이브리드 구성에 설명된 바와 같이 하이브리드를 [구성해야 비즈니스용 Skype 합니다.](configure-federation-with-skype-for-business-online.md)
- 사용자에게 Teams 및 비즈니스용 Skype 온라인(계획 2)에 대한 라이선스가 할당되어야 합니다. 온라인에서 비즈니스용 Skype 후에도 비즈니스용 Skype Online 라이선스가 필요합니다.  또한 다음을 수행합니다.
    - 사용자가 프레미스에서 전화 접속 회의를 사용할 수 있도록 설정된 경우 사용자를 온라인으로 이동하기 전에 기본적으로 사용자에게 Teams 할당된 오디오 회의 라이선스도 있어야 합니다. 클라우드로 마이그레이션된 후 사용자는 클라우드에서의 오디오 회의를 위한 준비를 하게 됩니다. 어떠한 이유로 사용자를 클라우드로 이동은 하지만 오디오 회의 기능을 사용하지 않도록 하려는 경우 `Move-CsUser`에서 `BypassAudioConferencingCheck` 매개 변수를 지정하여 이 검사를 재정의할 수 있습니다.
    - 사용자가 Enterprise Voice 프레미스에서 사용할 수 있도록 설정된 경우 사용자를 온라인으로 이동하기 전에 전화 시스템 할당된 Teams 라이선스가 있어야 합니다. 클라우드로 마이그레이션된 후 사용자는 클라우드에서의 전화 시스템을 위한 준비를 하게 됩니다. 어떤 이유로 사용자를 클라우드로 이동하지만 전화 시스템 기능을 사용하지 않을 경우 에서 매개 변수를 지정하여 이 검사를 다시 정의할 `BypassEnterpriseVoiceCheck` 수 `Move-CsUser` 있습니다.


## <a name="moving-users"></a>사용자 이동

사용자가 온-프레미스에서 클라우드로 이동 시,

- Teams 사용자와의 상호 비즈니스용 Skype 사용할 수 있으며, TeamsOnly인 경우 다른 조직과 페더러인 것일 수도 있습니다.

- 연락처는 프레미스에서 연락처로 Teams.

- 앞으로 예약된 기존 모임이 온라인으로 마이그레이션됩니다. 사용자가 TeamsOnly로 직접 이동하면(아래 참조) 모임은 Teams 모임으로 변환됩니다. 그렇지 않으면 모임은 비즈니스용 Skype 남아 있지만 마이그레이션되어 사용자가 온라인이 아닌 온라인에서 호스팅됩니다.  모임의 마이그레이션은 비동기적으로 진행되며 사용자를 이동하고 약 90분 후에 시작됩니다.  모임의 마이그레이션 상태를 판단하려면 [가져오기-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)를 사용할 수 있습니다. 모임 전에 업로드된 콘텐츠는 이동되지 않습니다.

사용자를 Teams 이동하려면 Move-CsUser cmdlet 또는 비즈니스용 Skype 관리 제어판을 사용합니다. 이 두 cmdlet은 모두 사내 도구입니다. 이러한 도구는 다음과 같은 이동 경로를 지원합니다.

- [비즈니스용 Skype 서버(비즈니스용 Skype 서버)에서 Teams(또한](move-users-from-on-premises-to-teams.md) 비즈니스용 Skype Online으로 이동)  온-프레미스에서 Teams Lync Server가 사용되는 버전에 관계없이 온-프레미스에서 비즈니스용 Skype 서버 동작만 자동으로 수행됩니다. 이 동작을 위해 스위치를 더 이상 `-MoveToTeams` 지정할 필요가 없습니다.  
- [온라인(Teams 여부와는 무관)에서 프레미스로.](move-users-from-the-cloud-to-on-premises.md)

> [!NOTE] 
> 사용자를 프레미스에서 TeamsOnly로 직접 이동하기 위해 Move-CsUser -MoveToTeams 스위치를 더 이상 지정할 필요는 없습니다. 이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 프레미스에서 비즈니스용 Skype Online으로 전환한 모드는 변경되지 않았습니다. 이제 Move-CsUser를 사용하여 사용자를 사내에서 클라우드로 이동할 때 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 전환이 실제로 지정되어 있는지 여부에 관계없이 전환이 지정된 경우와 같은 Teams 모임이 자동으로 Teams 모임으로 `-MoveToTeams` 변환됩니다. 
> 

## <a name="required-administrative-credentials"></a>필수 관리 자격 증명

사용자를 사내와 클라우드 간에 이동하려면 조직뿐만 아니라 비즈니스용 Skype 서버 환경 모두에서 충분한 권한이 있는 계정을 Teams 합니다. 필요한 모든 권한이 있는 하나의 계정을 사용할 수도 있으며, 두 개의 계정을 사용할 수도 있습니다. 이 경우 두 계정을 사용할 수 있습니다. 이 경우, 이 경우 프레미스 자격 증명을 사용하여 사내 도구에 액세스한 다음 이러한 도구에서 Teams 관리 계정에 대한 추가 자격 증명을 제공하게 됩니다.  

- 사내 환경에서 이동을 수행하는 사용자에게는 이동에 대한 CSServerAdministrator 및 CsUserAdministrator 역할이 비즈니스용 Skype 서버.
- 이 Teams 이동을 수행하는 사용자는 다음 조건 중 하나를 충족해야 합니다.
  - 사용자가 전역 관리자 역할의 구성원입니다.
  - 사용자가 Teams 관리자 역할의 구성원입니다.
  - 사용자가 비즈니스용 Skype 관리자 역할의 구성원입니다.  

    > [!Important]
    > - 비즈니스용 Skype 관리 제어판을 사용하는 경우 위에 설명된 대로 적절한 역할을 Microsoft 365 계정의 자격 증명을 제공하라는 메시지가 표시됩니다. .onmicrosoft.com. 가능하지 않은 경우 cmdlet을 Move-CsUser 합니다.
    >- PowerShell에서 Move-CsUser 사용하는 경우 .onmicrosoft.com 로 끝나는 계정을 사용할 수도 있습니다. 또는 cmdlet에 HostedMigrationOverrideUrl 매개 변수도 지정하는 경우 Azure AD와 동기화된 모든 사내 계정을 사용할 수 있습니다. 호스팅된 마이그레이션 오버라이드 URL의 값은 다음 URL의 변형입니다. https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>위의 URL에서 XX를 다음과 같이 결정된 2~3자 중 하나로 바 사용합니다.
    >   - PowerShell Teams 다음 cmdlet을 실행합니다.<br>`Get-CsTenant|ft identity`
    >   - 결과 값은 다음과 같은 형식입니다.<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - 2자리 또는 3자리 코드는 DC=lyncXX001 섹션에 포함된 XX입니다. 2자리 코드인 경우 숫자 다음에 숫자(예: 0a)가 오게 됩니다. 3문자 코드인 경우 두 글자 다음에 숫자(예: jp1)가 표시됩니다. 모든 경우에 XX 코드 바로 다음에 001이 표시 됩니다.


## <a name="voice-configuration-requirements"></a>음성 구성 요구 사항

사용자가 프레미스에서 엔터프라이즈 음성에 대해 구성된 경우 온라인으로 이동할 때 음성 구성 업데이트를 조정해야 합니다. 또는 전화 통신 기능이 없는 사용자도 마이그레이션할 수 있습니다. 사용 가능한 옵션은 사용자가 온라인에 있는 클라이언트를 사용할지 Teams 비즈니스용 Skype 여부에 따라 결정됩니다.

- 사용자의 전화 통신 공급자를 업데이트하여 [Microsoft 통화 플랜을 사용할 수 있습니다.](/microsoftteams/calling-plans-for-office-365) 이 옵션은 사용자가 클라이언트를 사용할지 Teams 비즈니스용 Skype 옵션입니다.
- 다음의 경우 계속해서 사내 PSTN 공급자를 사용할 수 있습니다.
  - 직접 라우팅에 Teams 음성 사용자를 [구성해야 합니다.](/microsoftteams/direct-routing-plan) 직접 라우팅은 사용자가 프레미스에서 온라인으로 이동한 후에만 사용할 수 있습니다.
  - 온라인에서 이동된 후 비즈니스용 Skype 클라이언트를 사용할 음성 사용자는 음성 비즈니스 하이브리드용 Skype 구성해야 합니다.

지원 가능성 매트릭스뿐만 아니라 하이브리드 환경의 전화 통신 옵션에 대한 자세한 내용은 PSTN 연결이 있는 하이브리드 환경의 사용자 계정을 [참조하세요.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>기타 고려 사항

온-프레미스와 온라인 환경의 정책(예: 메시징, 모임, 통화 동작)은 독립적입니다. 해당 사용자를 온라인으로 마이그레이션하는 즉시 올바른 구성을 하도록 해당 사용자를 프레미스에서 클라우드로 이동하기 전에 환경에서 정책을 구성하고 사용자에게 할당하는 것을 고려할 수 있습니다.

## <a name="see-also"></a>참고 항목

[사용자를 온-프레미스에서 Teams로 이동](move-users-from-on-premises-to-teams.md)

[MMS(Meeting Migration Service) 설정](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[직접 라우팅 계획](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
