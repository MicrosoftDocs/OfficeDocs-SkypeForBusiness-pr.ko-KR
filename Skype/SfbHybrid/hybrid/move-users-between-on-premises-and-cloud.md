---
title: 온-프레미스와 클라우드 간에 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 하이브리드을 사용 하도록 설정 된 비즈니스용 Skype Server의 온-프레미스 배포에서 온-프레미스 환경과 클라우드 간에 사용자를 이동할 수 있습니다 (Microsoft 팀 또는 비즈니스용 Skype Online).'
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185457"
---
# <a name="move-users-between-on-premises-and-cloud"></a>온-프레미스와 클라우드 간에 사용자 이동

하이브리드을 사용 하도록 설정 된 비즈니스용 Skype Server의 온-프레미스 배포에서 온-프레미스 환경과 클라우드 간에 사용자를 이동할 수 있습니다 (Microsoft 팀 또는 비즈니스용 Skype Online). 사용자가 온-프레미스에 있든 클라우드에 거주 하 고 있는지 여부를 사용자의 비즈니스용 Skype 홈 이라고 합니다.

- 온-프레미스 비즈니스용 사용자가 비즈니스용 Skype 서버와 상호 작용 합니다.
- 가정용 온라인 사용자는 비즈니스용 Skype Online 서비스와 상호 작용할 수 있습니다.

*팀 사용자는 비즈니스용 skype를 사용 하 든 상관 없이 기본적으로 비즈니스용 Skype home을 보유 하 고 있습니다.* 팀을 함께 사용 하는 비즈니스용 Skype 사용자 (나란히 나란히)가 있는 경우 해당 사용자는 온-프레미스에 있습니다. 비즈니스용 Skype 사용자의 팀에는 비즈니스용 Skype 사용자와의 팀 클라이언트에서 상호 작용 하는 기능이 없으며, 페더레이션된 조직의 사용자와 팀을 통신할 수 없습니다. 이러한 기능은 사용자가 비즈니스용 Skype에서 온라인으로 이동한 후에만 사용할 수 있습니다. 사용자를 온라인으로 이동할 때 비즈니스용 Skype Online을 사용 하도록 허용 하거나 (필요한 경우 팀에서) 팀만 만들 수 있습니다. 조직에서 이미 팀을 사용 하 고 있는 경우에는 팀 전용 모드로 전환 하 여 팀 클라이언트의 모든 수신 채팅 및 통화에 대 한 라우팅이 가능 하도록 하는 것이 좋습니다. 자세한 내용은 비즈니스용 Skype와 함께 팀 [공존](/microsoftteams/coexistence-chat-calls-presence) , 팀을 비즈니스용 [skype를 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](/microsoftteams/migration-interop-guidance-for-teams-with-skype)을 참조 하세요.

## <a name="prerequisites"></a>필요 조건

사용자를 클라우드로 이동 하는 필수 조건 (비즈니스용 Skype만 또는 팀 전용 모드를 사용 해야 하는 경우):

- 조직에서 Azure AD Connect가 올바르게 구성 되어 있어야 하 고 [AZURE Ad Connect 구성](configure-azure-ad-connect.md)에 설명 된 대로 사용자의 모든 관련 특성을 동기화 해야 합니다.
- 비즈니스용 skype 하이브리드 [구성](configure-federation-with-skype-for-business-online.md)에서 설명한 대로 비즈니스용 skype 하이브리드을 구성 해야 합니다.
- 사용자에 게 비즈니스용 Skype Online (계획 2)에 대 한 라이선스가 할당 되어야 하며 팀을 사용 하는 경우 팀 라이선스도 있어야 합니다.  또한:
    - 사용자가 온-프레미스에서 전화 접속 회의를 사용 하도록 설정 된 경우 사용자는 기본적으로 Office 365에서 오디오 회의 라이선스를 할당 한 후에만 온라인으로 이동할 수 있습니다. 클라우드로 마이그레이션한 후에는 사용자가 클라우드에서 오디오 회의를 위해 프로 비전 됩니다. 일부 이유로 사용자를 클라우드로 이동 하지만 오디오 회의 기능을 사용 하지 않으려는 경우에는 `BypassAudioConferencingCheck` 에서 `Move-CsUser`매개 변수를 지정 하 여이 검사를 재정의할 수 있습니다.
    - 사용자가 온-프레미스에서 엔터프라이즈 음성 기능을 사용 하도록 설정 된 경우 사용자가 온라인으로 이동 하기 전에 기본적으로 사용자에 게 Office 365에서 할당 된 전화 시스템 라이선스가 있어야 합니다. 클라우드로 마이그레이션한 후에는 사용자가 클라우드의 전화 시스템용으로 프로 비전 됩니다. 일부 이유로 사용자를 클라우드로 이동 하지만 전화 시스템 기능을 사용 하지 않으려는 경우에는 `BypassEnterpriseVoiceCheck`에서 `Move-CsUser`매개 변수를 지정 하 여이 검사를 재정의할 수 있습니다.


## <a name="moving-users"></a>사용자 이동

사용자가 온-프레미스에서 클라우드로 이동 하는 경우:

- Skype for Business 기능을 위해 사용자는 클라우드에서 비즈니스용 Skype Online 서비스를 사용 하기 시작 합니다.
- 팀 사용자는 비즈니스용 Skype 사용자와의 상호 운용성을 사용할 수 있게 되며 다른 조직과 페더레이션 할 수도 있습니다.
- 온-프레미스의 연락처가 클라우드로 이동 됩니다 (비즈니스용 Skype 또는 팀).
- 앞으로 예약 된 기존 모임이 온라인으로 마이그레이션: 사용자가 팀에만 (아래 참조)으로 전환 되 고, 모임이 팀원에 게 남아 있지만, 그렇지 않으면 모임이 비즈니스용 Skype로 유지 되지만,이를 위해 마이그레이션됩니다. 온-프레미스 대신 온라인으로 호스팅  모임 마이그레이션은 비동기적으로 수행 되며 사용자를 이동한 후 약 90 분이 시작 됩니다.  모임 마이그레이션의 상태를 확인 하려면 [get-help를 csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)를 사용할 수 있습니다. 모임이 진행 되는 동안 업로드 된 콘텐츠는 이동 되지 않습니다.

온-프레미스와 클라우드 간에 사용자를 이동 하려면 (팀에 있든 비즈니스용 Skype Online) 두 가지 모두 온-프레미스 도구를 사용 하 여 이동-CsUser cmdlet 또는 비즈니스용 Skype 관리 제어판을 사용할 수 있습니다. 이러한 도구는 세 가지 이동 경로를 지원 합니다.

- 비즈니스용 skype [서버 (온-프레미스)에서 비즈니스용 Skype Online을 사용할 수](move-users-from-on-premises-to-skype-for-business-online.md)있습니다.
- [비즈니스용 Skype 서버 (온-프레미스)에서 팀 으로만 직접](move-users-from-on-premises-to-teams.md) (이렇게 하면 비즈니스용 Skype Online으로 이동 합니다.)  온-프레미스에서 팀으로 직접 이동 하는 옵션은 비즈니스용 Skype 서버 2019 뿐만 아니라 비즈니스용 Skype Server 2015의 누적 업데이트 8도 사용할 수 있습니다. 이전 버전의 비즈니스용 Skype Server를 사용 하는 조직에서는 먼저 비즈니스용 Skype Online으로 이동한 다음 온라인 상태일 때이 사용자에 게 팀 전용 모드를 적용 하 여 사용자를 이동할 수 있습니다.
- [온라인 (팀 전용 여부에 관계 없음), 온-프레미스로](move-users-from-the-cloud-to-on-premises.md)

## <a name="required-administrative-credentials"></a>필수 관리 자격 증명

온-프레미스와 클라우드 간에 사용자를 이동 하려면 Office 365 테 넌 트에서 뿐만 아니라 온-프레미스 비즈니스용 Skype 서버 환경 모두에서 충분 한 권한이 있는 계정을 사용 해야 합니다. 필요한 권한이 있는 계정을 하나 사용 하거나, 두 개의 계정을 사용 하 여 온-프레미스 자격 증명을 사용 하는 온-프레미스 도구에 액세스 한 다음 해당 도구에서 Office 365에 대 한 추가 자격 증명을 제공할 수 있습니다. 관리 계정.  

- 온-프레미스 환경에서 이동을 수행 하는 사용자는 비즈니스용 Skype 서버에서 CSServerAdminstrator 역할을 가져야 합니다.
- Office 365에서 이동을 수행 하는 사용자는 전역 관리자 이거나 비즈니스용 Skype 관리자와 사용자 관리자 역할이 모두 있어야 합니다.  

    > [!Important]
    > - 비즈니스용 Skype 관리 제어판을 사용 하는 경우에는 위에서 설명한 대로 적절 한 역할을 사용 하 여 Office 365 계정에 대 한 자격 증명을 제공 하 라는 메시지가 표시 됩니다. Onmicrosoft.com로 끝나는 계정을 제공 해야 합니다. 이렇게 할 수 없는 경우에는 CsUser cmdlet을 사용 합니다.
    >- PowerShell에서-CsUser Move를 사용 하는 경우 onmicrosoft.com에 끝나는 계정을 사용 하거나 cmdlet에서 HostedMigrationOverrideUrl 매개 변수를 지정 하는 경우 Azure AD로 동기화 되는 모든 온-프레미스 계정을 사용할 수 있습니다. . 호스팅된 마이그레이션 재정의 URL의 값은 다음 URL의 변형입니다.https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>위의 URL에서 다음과 같이 결정 된 2 ~ 3 자로 XX를 바꿉니다.
    >   - 비즈니스용 Skype Online PowerShell 세션에서 다음 cmdlet을 실행 합니다.<br>`Get-CsTenant|ft identity`
    >    - 결과 값은 다음 형식으로 지정 됩니다.<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 두 자리 또는 세 자릿수 코드는 DC = lyncXX001 섹션에 포함 된 XX입니다. 두 문자 코드의 경우 숫자가 뒤에 오며 (예: 0a)가 표시 됩니다. 세 문자 코드 인 경우 두 문자 다음에 숫자가 옵니다 (예: jp1). 모든 경우에 XX 코드 바로 뒤에 001이 표시 됩니다.


## <a name="voice-configuration-requirements"></a>음성 구성 요구 사항

사용자가 온-프레미스에서 enterprise voice에 대해 구성 되어 있는 경우 온라인으로 이동할 때 음성 구성을 업데이트 해야 하며, 그렇지 않은 경우에는 전화 통신 기능 없이 마이그레이션할 수 있습니다. 사용할 수 있는 옵션은 사용자가 온라인 상태에서 팀 또는 비즈니스용 Skype 클라이언트를 사용 하 고 있는지 여부에 따라 달라 집니다.

- 사용자의 전화 통신 공급자를 업데이트 하 여 [Microsoft 통화 계획](/microsoftteams/calling-plans-for-office-365)을 사용할 수 있습니다. 사용자가 팀 또는 비즈니스용 Skype 클라이언트를 사용할 것인지 여부를 선택할 수 있습니다.
- 온-프레미스 PSTN 공급자를 계속 사용할 수 있습니다.
  - 팀을 사용 하는 음성 사용자는 [직접 라우팅](/microsoftteams/direct-routing-plan)하도록 구성 해야 합니다. 직접 라우팅은 사용자가 온-프레미스에서 온라인으로 이동한 후에만 사용할 수 있습니다.
  - 온라인으로 이동한 후 비즈니스용 Skype 클라이언트를 사용 하는 음성 사용자는 비즈니스용 Skype 하이브리드 음성 기능에 맞게 구성 되어야 합니다.

하이브리드 환경의 전화 통신 옵션 및 지원 가능성 매트릭스에 대 한 자세한 내용은 [PSTN 연결을 사용 하는 하이브리드 환경에서 사용자 계정을](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)참조 하세요.

## <a name="other-considerations"></a>기타 고려 사항

온-프레미스 및 온라인 환경의 정책 (예: 메시징, 모임, 통화 동작 제어)은 독립적입니다. 온라인으로 마이그레이션 하는 즉시 올바른 구성을 사용할 수 있도록 환경에서 정책을 구성 하 고 해당 사용자를 사용자에 게 할당 하는 것을 고려해 야 합니다.

## <a name="see-also"></a>참고 항목

[온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동](move-users-from-on-premises-to-skype-for-business-online.md)

[온-프레미스에서 팀으로 사용자 이동](move-users-from-on-premises-to-teams.md)

[MMS (모임 마이그레이션 서비스)를 설정 하는 경우](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[직접 라우팅 계획](/microsoftteams/direct-routing-plan)

[CsUser 이동](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
