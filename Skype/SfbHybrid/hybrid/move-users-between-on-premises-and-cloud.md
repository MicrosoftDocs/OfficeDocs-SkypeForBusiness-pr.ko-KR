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
description: '요약: 하이브리드에 사용하도록 설정된 비즈니스용 Skype 서버 온-프레미스 배포에서 온-프레미스 환경과 클라우드 간에 사용자를 이동할 수 있습니다.'
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304010"
---
# <a name="move-users-between-on-premises-and-cloud"></a>온-프레미스와 클라우드 간에 사용자 이동

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

하이브리드에 사용할 수 있는 비즈니스용 Skype 서버 온-프레미스 배포에서 온-프레미스 환경과 Teams 간에 사용자를 이동할 수 있습니다. 사용자는 온-프레미스 아니면 클라우드에 있는지에 상관없이 사용자의 비즈니스용 Skype 홈이라고 합니다.

- 온-프레미스에 있는 사용자는 온-프레미스 비즈니스용 Skype 서버와 상호 작용합니다.
- 온라인 홈인 사용자는 Teams 서비스와 상호 작용할 수 있습니다.

*Teams 사용자는 기본적으로 비즈니스용 Skype 사용 여부에 관계없이 비즈니스용 Skype 홈을 가지고 있습니다.* Teams 사용하는 온-프레미스 비즈니스용 Skype 사용자가 있는 경우 해당 사용자는 온-프레미스에 있습니다. 온-프레미스에 비즈니스용 Skype 있는 Teams 사용자는 Teams 클라이언트의 비즈니스용 Skype 사용자와 상호 운용할 수 없으며 페더레이션된 조직의 사용자와 Teams 통신할 수 없습니다. 이러한 기능은 사용자가 비즈니스용 Skype 온-프레미스에서 온라인으로 이동하고 TeamsOnly를 만든 후에만 완전히 사용할 수 있습니다. 사용자를 TeamsOnly 모드로 이동하는 것이 좋습니다. 그러면 들어오는 모든 채팅 및 통화의 라우팅이 Teams 클라이언트에 배치됩니다. 자세한 내용은 [비즈니스용 Skype 함께 Teams](/microsoftteams/coexistence-chat-calls-presence) [사용하는 조직의 비즈니스용 Skype 및 마이그레이션 및 상호 운용성 지침과 Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype) 공존을 참조하세요.

## <a name="prerequisites"></a>필수 구성 요소

사용자를 TeamsOnly 모드로 이동하기 위한 필수 구성 요소:

- 조직은 Azure AD 커넥트 [구성](configure-azure-ad-connect.md)에 설명된 대로 Azure AD 커넥트 올바르게 구성되고 사용자에 대한 모든 관련 특성을 동기화해야 합니다.
- 비즈니스용 Skype 하이브리드 구성에 설명된 대로 [비즈니스용 Skype 하이브리드를 구성](configure-federation-with-skype-for-business-online.md)해야 합니다.
- 사용자에게 Teams 및 비즈니스용 Skype Online(플랜 2)에 대한 라이선스가 할당되어야 합니다. 비즈니스용 Skype Online이 사용 중지된 후에도 비즈니스용 Skype Online 라이선스가 여전히 필요합니다.  또한 다음을 수행합니다.
    - 사용자가 온-프레미스에서 전화 접속 회의를 사용하도록 설정된 경우 사용자를 온라인으로 이동하기 전에 Teams 할당된 오디오 회의 라이선스도 있어야 합니다. 클라우드로 마이그레이션된 후 사용자는 클라우드에서의 오디오 회의를 위한 준비를 하게 됩니다. 
    - 사용자가 온-프레미스에서 Enterprise Voice 사용하도록 설정된 경우 사용자를 온라인으로 이동하기 전에 Teams 할당된 전화 시스템 라이선스가 사용자에게 있어야 합니다. 클라우드로 마이그레이션되면 사용자는 클라우드에서 전화 시스템 프로비전됩니다. 


## <a name="moving-users"></a>사용자 이동

사용자가 온-프레미스에서 클라우드로 이동 시,

- Teams 사용자가 비즈니스용 Skype 사용자와의 상호 운용성을 사용하도록 설정되고 TeamsOnly인 경우 다른 조직과도 페더레이션할 수 있습니다.

- 온-프레미스의 연락처가 Teams 이동합니다.

- 향후 예정된 기존 모임은 Teams 모임으로 전환됩니다. 모임의 마이그레이션은 비동기적으로 진행되며 사용자를 이동하고 약 90분 후에 시작됩니다.  모임의 마이그레이션 상태를 판단하려면 [가져오기-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)를 사용할 수 있습니다. 모임 전에 업로드된 모든 콘텐츠는 이동되지 않습니다.

사용자를 Teams 이동하려면 온-프레미스 도구인 Move-CsUser cmdlet 또는 비즈니스용 Skype Admin 제어판 사용합니다. 이러한 도구는 다음과 같은 이동 경로를 지원합니다.

- [비즈니스용 Skype 서버(온-프레미스)에서 Teams Only로 직접 연결합니다](move-users-from-on-premises-to-teams.md).  온-프레미스에서 Teams 직접 이동하는 동작은 이제 사용되는 비즈니스용 Skype 서버 또는 Lync Server 버전에 관계없이 자동입니다. 이 동작을 가져오기 위해 스위치를 `-MoveToTeams` 더 이상 지정할 필요가 없습니다.  
- [온라인(Teams 전용인지 여부)에서 온-프레미스로.](move-users-from-the-cloud-to-on-premises.md)

> [!NOTE] 
> 더 이상 사용자를 온-프레미스에서 TeamsOnly로 직접 이동하기 위해 Move-CsUser -MoveToTeams 스위치를 지정할 필요가 없습니다. 이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 온-프레미스에서 비즈니스용 Skype Online으로 전환되었으며 해당 모드는 변경되지 않았습니다. 이제 Move-CsUser를 사용하여 온-프레미스에서 클라우드로 사용자를 이동할 때 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되었는지 여부에 관계없이 스위치가 지정된 것처럼 `-MoveToTeams` 온-프레미스에서의 모임이 자동으로 Teams 모임으로 변환됩니다. 
> 

## <a name="required-administrative-credentials"></a>필수 관리 자격 증명

온-프레미스와 클라우드 간에 사용자를 이동하려면 온-프레미스 비즈니스용 Skype 서버 환경과 Teams 조직 모두에서 충분한 권한이 있는 계정을 사용해야 합니다. 필요한 모든 권한이 있는 하나의 계정을 사용하거나 두 개의 계정을 사용할 수 있습니다. 두 계정을 사용하는 경우 온-프레미스 자격 증명을 사용하여 온-프레미스 도구에 액세스한 다음 해당 도구에서 Teams 관리 계정에 대한 추가 자격 증명을 제공합니다.  

- 온-프레미스 환경에서 이동을 수행하는 사용자에게는 비즈니스용 Skype 서버 CSServerAdministrator, CsUserAdministrator 및 RTCUniversalUserAdmins 역할이 있어야 합니다.
- Teams 이동을 수행하는 사용자는 다음 역할 중 하나 이상의 멤버여야 합니다.
  - 전역 관리자 역할
  - Teams 관리자 역할
  - 비즈니스용 Skype 관리자 역할.  

    > [!Important]
    > - 비즈니스용 Skype Admin 제어판 사용하는 경우 위에서 설명한 대로 적절한 역할을 가진 Microsoft 365 계정에 대한 자격 증명을 제공하라는 메시지가 표시됩니다. .onmicrosoft.com 끝나는 계정을 제공해야 합니다. 가능하지 않은 경우 Move-CsUser cmdlet을 사용합니다.
    >- PowerShell에서 Move-CsUser 사용하는 경우 .onmicrosoft.com 끝나는 계정을 사용하거나 cmdlet에서 HostedMigrationOverrideUrl 매개 변수를 지정하는 경우 Azure AD 동기화되는 온-프레미스 계정을 사용할 수 있습니다. 호스트된 마이그레이션 재정의 URL의 값은 다음 URL의 변형입니다. https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>위의 URL에서 XX를 다음과 같이 결정된 두 개 또는 세 개의 문자로 바꿉니다.
    >   - Teams PowerShell 세션에서 다음 cmdlet을 실행합니다.<br>`Get-CsTenant | ft ServiceInstance`
    >   - 결과 값은 다음과 같은 형식입니다.<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 2자 또는 3자 코드는 YYYY-XX-ZZ 섹션에 포함된 XX입니다. 두 문자 코드인 경우 숫자 뒤에 숫자(예: 4A)가 잇는 숫자입니다. 3자 코드인 경우 두 글자 뒤에 숫자(예: JP1)가 됩니다. 예를 들어 NOAM-4A-S7이 있습니다.


## <a name="voice-configuration-requirements"></a>음성 구성 요구 사항

사용자가 온-프레미스에서 엔터프라이즈 음성으로 구성된 경우 온라인으로 이동할 때 음성 구성 업데이트를 조정해야 합니다. 또는 전화 통신 기능 없이 마이그레이션할 수 있습니다. 사용 가능한 옵션은 사용자가 온라인 상태가 되면 Teams 또는 비즈니스용 Skype 클라이언트를 사용할지 여부에 따라 달라집니다.

- [Microsoft 통화 플랜](/microsoftteams/calling-plans-for-office-365)을 사용하도록 사용자의 전화 통신 공급자를 업데이트할 수 있습니다. 이 옵션은 사용자가 Teams 또는 비즈니스용 Skype 클라이언트를 사용할지 여부입니다.
- 온-프레미스 PSTN 공급자를 계속 사용할 수 있습니다.
  - Teams 사용할 음성 사용자는 [직접 라우팅](/microsoftteams/direct-routing-plan)에 대해 구성해야 합니다. 직접 라우팅은 사용자가 온-프레미스에서 온라인으로 이동한 후에만 사용할 수 있습니다.
  - 온라인으로 이동한 후 비즈니스용 Skype 클라이언트를 사용하는 음성 사용자는 비즈니스 하이브리드용 Skype 음성 기능에 대해 구성해야 합니다.

지원 가능성 매트릭스를 포함하여 하이브리드 환경의 전화 통신 옵션에 대한 자세한 내용은 [PSTN 연결이 있는 하이브리드 환경의 사용자 계정을 참조하세요](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>기타 고려 사항

온-프레미스와 온라인 환경의 정책(예: 메시징, 모임, 통화 동작)은 독립적입니다. 온-프레미스에서 클라우드로 해당 사용자를 이동하기 전에 환경에서 정책을 구성하고 사용자에게 할당하는 것이 좋습니다. 따라서 온라인으로 마이그레이션되는 즉시 올바른 구성이 가능합니다.

## <a name="see-also"></a>참고 항목

[사용자를 온-프레미스에서 Teams로 이동](move-users-from-on-premises-to-teams.md)

[MMS(Meeting Migration Service) 설정](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[직접 라우팅 계획](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
