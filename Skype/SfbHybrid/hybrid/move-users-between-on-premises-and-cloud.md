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
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705877"
---
# <a name="move-users-between-on-premises-and-cloud"></a>온-프레미스와 클라우드 간에 사용자 이동

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype 서버 온-프레미스 배포에서 비즈니스용 Skype 사용자는 Teams를 사용할 수도 있지만 온-프레미스 비즈니스용 Skype 서버 배포를 사용하도록 구성된 경우 이러한 사용자가 모든 Teams 기능을 사용할 수 있는 것은 아닙니다. 이러한 사용자는 온-프레미스에 "홈"이라고 하며, 이러한 사용자가 온-프레미스에 있는 동안에는 특정 Teams 기능을 사용할 수 없습니다. 예를 들면 다음과 같습니다.
- 다른 조직의 사용자와 사용자의 Teams 클라이언트를 통해 페더레이션된 통화 및 채팅을 사용할 수 없습니다.
- 비즈니스용 Skype 클라이언트를 사용하는 조직의 다른 사용자와 사용자의 Teams 클라이언트를 통한 Interop 통신
- PSTN 통화 기능(사용자에게 전화 시스템 라이선스가 할당된 경우).

전체 Teams 기능을 얻으려면 이러한 사용자를 비즈니스용 Skype 온-프레미스에서 클라우드로 이동해야 합니다. 이때 사용자는 TeamsOnly가 됩니다. 사용자를 온-프레미스에서 클라우드로 이동하는 작업은 사용자의 공존 모드를 TeamsOnly로 설정합니다. 사용자가 클라우드로 이동하면 TeamsOnly가 됩니다. 이는 들어오는 모든 채팅 및 통화가 Teams 클라이언트에 있는 것을 의미합니다. 자세한 내용은 [teams와 비즈니스용 Skype](/microsoftteams/coexistence-chat-calls-presence) [함께 사용하는 조직에 대한 비즈니스용 Skype 및 마이그레이션 및 상호 운용성 지침과 Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype) 공존을 참조하세요.

온-프레미스 비즈니스용 Skype 서버 배포에서 클라우드로 사용자를 이동하려면 [비즈니스용 Skype 하이브리드 구성](/skypeforbusiness/hybrid/plan-hybrid-connectivity)이 필요합니다.  하이브리드에 배포를 사용하도록 설정하면 아래 설명된 대로 사용자를 온-프레미스 환경에서 클라우드로 이동하여 TeamsOnly로 만들 수 있습니다. 필요한 경우 TeamsOnly 사용자를 온-프레미스 Bsuiness용 Skype 배포로 다시 이동할 수도 있습니다. 



## <a name="prerequisites"></a>필수 조건

사용자를 TeamsOnly 모드로 이동하기 위한 필수 구성 요소:

- 조직에는 Azure AD Connect가 올바르게 구성되어 있어야 하며 Azure AD [Connect 구성](configure-azure-ad-connect.md)에 설명된 대로 사용자에 대한 모든 관련 특성을 동기화해야 합니다.
- 비즈니스용 Skype 하이브리드 구성에 설명된 대로 [비즈니스용 Skype 하이브리드를 구성](configure-federation-with-skype-for-business-online.md)해야 합니다.
- 사용자에게 Teams 및 비즈니스용 Skype Online(플랜 2)에 대한 라이선스가 할당되어야 합니다. 비즈니스용 Skype Online이 만료된 후에도 비즈니스용 Skype Online 라이선스는 여전히 필요합니다.  또한 다음을 수행합니다.
    - 사용자가 온-프레미스에서 전화 접속 회의를 사용하도록 설정된 경우 사용자를 온라인으로 이동하기 전에 Teams에 오디오 회의 라이선스가 할당되어 있어야 합니다. 클라우드로 마이그레이션된 후 사용자는 클라우드에서의 오디오 회의를 위한 준비를 하게 됩니다. 
    - 사용자가 온-프레미스에서 Enterprise Voice 사용하도록 설정된 경우 사용자를 온라인으로 이동하기 전에 Teams에 Teams Phone 라이선스가 할당되어 있어야 합니다. 클라우드로 마이그레이션되면 사용자는 클라우드의 Phone System에 대해 프로비전됩니다. 
  
2022년 7월 31일부터 온-프레미스 배포와 클라우드 간에 사용자를 이동하려면 다음 최소 버전의 비즈니스용 Skype 서버 또는 Lync Server를 사용해야 합니다.

</br>
</br>

|온-프레미스 제품|필수 최소 버전|필요한 최소 빌드|
|---|---|---|
|비즈니스용 Skype Server 2019| CU6 |7.0.2046.385|
|비즈니스용 Skype Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 핫픽스 7|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>사용자 이동

사용자가 온-프레미스에서 클라우드로 이동 시,

- 사용자는 TeamsOnly 사용자가 됩니다. 즉, 사용자가 다음을 의미합니다.
   -  Teams 클라이언트에서 모든 채팅 및 통화를 수신하고 시작합니다.
   -  Teams에서 모든 모임을 예약합니다.
   -  채팅 또는 통화를 시작하거나 비즈니스용 Skype 모임을 예약할 수 없습니다.
   -  이미 가지고 있거나 나중에 받는 비즈니스용 Skype 모임에 참가할 수 있습니다. 그러나 Microsoft가 지정된 TeamsOnly 사용자에 대한 비즈니스용 Skype Online 인프라를 제거한 후에 TeamsOnly 사용자는 익명으로만 비즈니스용 Skype 모임에 참가할 수 있습니다. 2022년 10월부터 온-프레미스에서 Teams로 이동한 사용자는 하이브리드 조직에서만 더 이상 비즈니스용 Skype Online 인프라로 프로비전되지 않습니다. 이러한 사용자가 비즈니스용 Skype 모임에 초대된 경우 익명으로 참가해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버 온-프레미스 배포를 사용하는 조직에 대한 지침을](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server) 참조하세요.

- 사용자는 비즈니스용 Skype 사용자와의 상호 운용성을 사용하도록 설정되며 다른 조직과도 페더레이션할 수 있습니다.
- 온-프레미스의 연락처가 Teams로 이동됩니다.
- 나중에 예정된 기존 모임은 Teams 모임으로 변환됩니다. 모임의 마이그레이션은 비동기적으로 진행되며 사용자를 이동하고 약 90분 후에 시작됩니다.  모임의 마이그레이션 상태를 판단하려면 [가져오기-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)를 사용할 수 있습니다. 모임 전에 업로드된 모든 콘텐츠는 이동되지 않습니다.
- Teams Phone 라이선스가 할당된 사용자는 제대로 구성되면 PSTN 기능에 액세스할 수 있습니다.
 
사용자를 Teams로 이동하려면 온-프레미스 도구인 Move-CsUser cmdlet 또는 비즈니스용 Skype 관리 제어판 사용합니다. 이러한 도구는 다음과 같은 이동 경로를 지원합니다.

- [비즈니스용 Skype 서버(온-프레미스)에서 Teams 전용으로.](move-users-from-on-premises-to-teams.md)
- [온라인(Teams 전용 여부)에서 온-프레미스로.](move-users-from-the-cloud-to-on-premises.md)


> [!NOTE] 
>  온-프레미스에서 Teams로 직접 이동하는 동작은 사용되는 비즈니스용 Skype 서버 또는 Lync Server 버전에 관계없이 자동으로 수행됩니다. 더 이상 사용자를 온-프레미스에서 TeamsOnly로 직접 이동하기 위해 스위치 `Move-CsUser` 를 지정할 `-MoveToTeams` 필요가 없습니다. 이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 온-프레미스에서 비즈니스용 Skype Online으로 전환되었으며 해당 모드는 변경되지 않았습니다. 이제 사용자를 온-프레미스에서 클라우드로 `Move-CsUser`이동할 때 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되었는지 여부에 관계없이 스위치가 지정된 것처럼 `-MoveToTeams` 온-프레미스에서의 모임이 Teams 모임으로 자동으로 변환됩니다. 


## <a name="required-administrative-credentials"></a>필수 관리 자격 증명

온-프레미스와 클라우드 간에 사용자를 이동하려면 온-프레미스 비즈니스용 Skype 서버 환경과 Teams 조직 모두에서 충분한 권한이 있는 계정을 사용해야 합니다. 필요한 모든 권한이 있는 하나의 계정을 사용하거나 두 개의 계정을 사용할 수 있습니다. 두 계정을 사용하는 경우 온-프레미스 자격 증명을 사용하여 온-프레미스 도구에 액세스한 다음, 해당 도구에서 Teams 관리 계정에 대한 추가 자격 증명을 제공합니다.  

- 온-프레미스 환경에서 이동을 수행하는 사용자에게는 비즈니스용 Skype 서버 CSServerAdministrator, CsUserAdministrator 및 RTCUniversalUserAdmins 역할이 있어야 합니다.
- Teams에서 이동을 수행하는 사용자는 다음 역할 중 하나 이상의 구성원이어야 합니다.
  - 전역 관리자 역할
  - Teams 관리자 역할
  - 비즈니스용 Skype 관리자 역할.  

    > [!Important]
    > - 비즈니스용 Skype 관리 제어판 사용하는 경우 위에서 설명한 대로 적절한 역할을 가진 Microsoft 365 계정에 대한 자격 증명을 제공하라는 메시지가 표시됩니다. .onmicrosoft.com 끝나는 계정을 제공해야 합니다. 가능하지 않은 경우 Move-CsUser cmdlet을 사용합니다.
    >- PowerShell에서 Move-CsUser 사용하는 경우 .onmicrosoft.com 끝나는 계정을 사용하거나 cmdlet에서 HostedMigrationOverrideUrl 매개 변수를 지정하는 경우 Azure AD 동기화되는 온-프레미스 계정을 사용할 수 있습니다. 호스트된 마이그레이션 재정의 URL의 값은 다음 URL의 변형입니다. https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>위의 URL에서 XX를 다음과 같이 결정된 두 개 또는 세 개의 문자로 바꿉니다.
    >   - Teams PowerShell 세션에서 다음 cmdlet을 실행합니다.<br>`Get-CsTenant | ft ServiceInstance`
    >   - 결과 값은 다음과 같은 형식입니다.<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 2자 또는 3자 코드는 YYYY-XX-ZZ 섹션에 포함된 XX입니다. 두 문자 코드인 경우 숫자 뒤에 숫자(예: 4A)가 잇는 숫자입니다. 3자 코드인 경우 두 글자 뒤에 숫자(예: JP1)가 됩니다. 예를 들어 NOAM-4A-S7이 있습니다.


## <a name="voice-configuration-requirements"></a>음성 구성 요구 사항

사용자가 온-프레미스에서 엔터프라이즈 음성으로 구성된 경우 온라인으로 이동할 때 음성 구성 업데이트를 조정해야 합니다. 또는 전화 통신 기능 없이 마이그레이션할 수 있습니다. 
- [Microsoft 통화 플랜](/microsoftteams/calling-plans-for-office-365)을 사용하도록 사용자의 전화 통신 공급자를 업데이트할 수 있습니다. 이 옵션은 사용자가 Teams를 사용할지 비즈니스용 Skype 클라이언트를 사용할지 여부입니다.
- 온-프레미스 PSTN 공급자를 계속 사용할 수 있습니다.
  - Teams를 사용할 음성 사용자는 [직접 라우팅](/microsoftteams/direct-routing-plan)에 대해 구성해야 합니다. 직접 라우팅은 사용자가 온-프레미스에서 온라인으로 이동한 후에만 사용할 수 있습니다.

지원 가능성 매트릭스를 포함하여 하이브리드 환경의 전화 통신 옵션에 대한 자세한 내용은 [PSTN 연결이 있는 하이브리드 환경의 사용자 계정을 참조하세요](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>기타 고려 사항

온-프레미스와 온라인 환경의 정책(예: 메시징, 모임, 통화 동작)은 독립적입니다. 온-프레미스에서 클라우드로 해당 사용자를 이동하기 전에 환경에서 정책을 구성하고 사용자에게 할당하는 것이 좋습니다. 따라서 온라인으로 마이그레이션되는 즉시 올바른 구성이 가능합니다.

## <a name="see-also"></a>참고 항목

[사용자를 온-프레미스에서 Teams로 이동](move-users-from-on-premises-to-teams.md)

[MMS(Meeting Migration Service) 설정](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[직접 라우팅 계획](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
