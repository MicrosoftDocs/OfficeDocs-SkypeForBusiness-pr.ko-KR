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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 하이브리드를 사용할 수 있는 비즈니스용 Skype 서버의 온-프레미스 배포에서 온-프레미스 환경과 클라우드 간에 사용자를 이동할 수 있습니다 (Microsoft 팀 또는 비즈니스용 Skype Online)...'
ms.openlocfilehash: aea3bed7db6c7821d957aa0e6d56cbafd548edb7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780087"
---
# <a name="move-users-between-on-premises-and-cloud"></a>온-프레미스와 클라우드 간에 사용자 이동

하이브리드를 사용하도록 설정된 비즈니스용 Skype 서버 온-프레미스 배포에서 온-프레미스 환경과 클라우드(Microsoft Teams나 비즈니스용 Skype Online에 상관없이) 사이의 사용자를 이동할 수 있습니다. 사용자는 온-프레미스 아니면 클라우드에 있는지에 상관없이 사용자의 비즈니스용 Skype 홈이라고 합니다.

- 온-프레미스 사용자가 온-프레미스 비즈니스용 Skype 서버와 상호 작용 합니다.
- 홈 온라인 사용자는 비즈니스용 Skype Online 서비스와 상호 작용할 수도 있습니다.

*Teams 사용자는 비즈니스용 Skype의 사용 여부에 상관없이 비즈니스용 Skype 홈을 기본적으로 가지고 있습니다.* 팀을 함께 사용 하는 온-프레미스 비즈니스용 Skype 사용자 (나란히)가 있는 경우 해당 사용자가 온-프레미스에 속해 있습니다. 비즈니스용 Skype를 사용 하는 팀 사용자는 자신의 팀 클라이언트에서 비즈니스용 Skype 사용자와 상호 작용 하는 기능이 없으며, 페더레이션 조직의 사용자와 팀 으로부터 통신할 수도 없습니다. 이러한 기능은 사용자가 온-프레미스에서 온라인으로 이동한 후에만 사용할 수 있습니다. 사용자를 온라인으로 이동하는 경우 비즈니스용 Skype Online(및 선택적으로 Teams)을 사용하도록 허용하거나 TeamsOnly 모드로 설정할 수 있습니다. 조직에서 이미 Teams를 사용하고 있는 경우 Teams 클라이언트에서 들어오는 모든 채팅 및 통화의 라우팅을 보장하는 Teams Only 모드로 이동시킬 것을 강력히 권장합니다. 자세한 내용은 팀과 비즈니스용 skype 및 [마이그레이션 및 상호 운용성 지침을 skype를 사용 하는 조직에 대 한 통합](/microsoftteams/migration-interop-guidance-for-teams-with-skype) [문서](/microsoftteams/coexistence-chat-calls-presence) 를 참조 하세요.

## <a name="prerequisites"></a>필수 구성 요소

사용자를 클라우드로 이동 하는 필수 구성 요소 (비즈니스용 Skype 전용 또는 팀 전용 모드에 관계 없음):

- 조직에서 azure ad connect를 올바르게 구성 했으며 [AZURE Ad Connect 구성](configure-azure-ad-connect.md)에 설명 된 대로 사용자에 대 한 모든 관련 특성을 동기화 해야 합니다.
- 비즈니스용 [skype 하이브리드 구성](configure-federation-with-skype-for-business-online.md)에 설명 된 대로 비즈니스용 skype 하이브리드를 구성 해야 합니다.
- 사용자에게 비즈니스용 Skype Online(플랜 2)에 대한 라이선스를 할당해야 하며, Teams를 사용 하는 경우에는 Teams 라이선스도 있어야 합니다.  또한 다음을 수행합니다.
    - 사용자가 온-프레미스에서 전화 접속 회의를 사용 하도록 설정 된 경우에는 기본적으로 사용자가 온라인으로 이동을 실행 하기 전에 Office 365에서 음성 회의 라이선스를 할당 받아야 합니다. 클라우드로 마이그레이션된 후 사용자는 클라우드에서의 오디오 회의를 위한 준비를 하게 됩니다. 일부 이유로 사용자를 클라우드로 이동 하 되 오디오 회의 기능을 사용 하지 않으려는 경우에는 `BypassAudioConferencingCheck` 에서 `Move-CsUser`매개 변수를 지정 하 여이 검사를 다시 정의할 수 있습니다.
    - 온-프레미스에서 Enterprise Voice를 사용 하도록 설정 된 경우 사용자를 온라인으로 이동 하기 전에 기본적으로 사용자에 게 Office 365에서 전화 시스템 라이선스가 할당 되어 있어야 합니다. 클라우드로 마이그레이션된 후 사용자는 클라우드에서의 전화 시스템을 위한 준비를 하게 됩니다. 일부 이유로 사용자를 클라우드로 이동 해야 하지만 전화 시스템 기능을 사용 하지 않으려는 경우에는 `BypassEnterpriseVoiceCheck`에서 `Move-CsUser`매개 변수를 지정 하 여이 검사를 다시 정의할 수 있습니다.


## <a name="moving-users"></a>사용자 이동

사용자가 온-프레미스에서 클라우드로 이동 시,

- 사용자는 클라우드에서 비즈니스용 Skype Online 서비스의 비즈니스용 Skype 기능을 사용하기 시작합니다.
- Teams 사용자는 비즈니스용 Skype 사용자와의 상호 운용성을 사용할 수 있게 되고 다른 조직들과 연합할 수도 있습니다.
- 온-프레미스의 연락처가 클라우드 (비즈니스용 Skype 또는 팀)로 이동 됩니다.
- 앞으로 예약 된 기존 모임은 나중에 다시 온라인으로 마이그레이션됩니다. 사용자가 TeamsOnly (아래 참조)로 직접 이동 하는 경우 모임이 팀 회의로 변환 되 고, 그렇지 않으면 모임이 비즈니스용 Skype로 유지 되지만,이 경우에는 온-프레미스 대신 온라인으로 호스트 될 수 있도록 마이그레이션됩니다.  모임의 마이그레이션은 비동기적으로 진행되며 사용자를 이동하고 약 90분 후에 시작됩니다.  모임의 마이그레이션 상태를 판단하려면 [가져오기-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)를 사용할 수 있습니다. 모임 전에 업로드된 콘텐츠는 이동되지 않습니다.

온-프레미스와 클라우드 간에 사용자를 이동 하려면 (팀에서 또는 비즈니스용 Skype Online) 두 가지 모두 온-프레미스 도구인 Move-CsUser cmdlet 또는 비즈니스용 Skype 관리 제어판을 사용 합니다. 이들 도구는 세 가지 다양한 이동 경로를 지원합니다.

- 비즈니스용 skype [서버 (온-프레미스)에서 비즈니스용 Skype Online으로 이동할 수](move-users-from-on-premises-to-skype-for-business-online.md)있습니다.
- 비즈니스용 [Skype 서버 (온-프레미스)에서 팀에 직접](move-users-from-on-premises-to-teams.md) (비즈니스용 skype Online으로 이동) 합니다.  온-프레미스에서 팀으로 직접 이동 하는 옵션은 비즈니스용 skype 서버 2019, 비즈니스용 skype 서버 2015에 대 한 누적 업데이트 8이 제공 됩니다. 이전 버전의 비즈니스용 Skype 서버를 사용하는 조직은 먼저 사용자를 비즈니스용 Skype Online으로 이동한 후 이들이 온라인 상태가 되면 TeamsOnly 모드를 적용하여 이들을 TeamsOnly 모드로 이동할 수 있습니다.
- [온라인 (팀 전용 여부에 관계 없음)에서 온-프레미스로](move-users-from-the-cloud-to-on-premises.md)

## <a name="required-administrative-credentials"></a>필수 관리 자격 증명

온-프레미스와 클라우드 간에 사용자를 이동 하려면 Office 365 조직 뿐만 아니라 온-프레미스 비즈니스용 Skype 서버 환경 둘 다에서 충분 한 권한이 있는 계정을 사용 해야 합니다. 모든 필수 권한이 있는 하나의 계정을 사용하거나 두 개의 계정을 사용할 수 있으며 이러한 경우 온-프레미스 도구에 온-프레미스 자격 증명을 사용하여 액세스한 후 이들 도구에서 Office 365 관리 계정에 대한 추가 자격 증명을 제공합니다.  

- 온-프레미스 환경에서 이동을 수행하는 사용자는 비즈니스용 Skype 서버에서 CSServerAdminstrator 역할이 있어야 합니다.
- Office 365에서 이동을 수행하는 사용자는 전역 관리자이거나 비즈니스용 Skype 관리자와 사용자 관리자 역할이 모두 있어야 합니다.  

    > [!Important]
    > - 비즈니스용 Skype 관리 제어판을 사용 하는 경우에는 위에서 설명한 대로 적절 한 역할을 가진 Office 365 계정에 대 한 자격 증명을 제공 하 라는 메시지가 표시 됩니다. Onmicrosoft.com로 끝나는 계정을 제공 해야 합니다. 이것이 가능 하지 않으면 CsUser cmdlet을 사용 합니다.
    >- PowerShell에서 CsUser User를 사용 하는 경우 cmdlet에 HostedMigrationOverrideUrl 매개 변수도 함께 지정 하는 경우에는 Azure AD로 동기화 되는 모든 온-프레미스 계정을 사용할 수 있습니다. 호스팅된 마이그레이션 재정의 URL의 값은 다음 URL의 변형입니다.https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>위의 URL에서 XX를 다음의 두 문자로 바꾸거나 다음과 같이 결정 합니다.
    >   - 비즈니스용 Skype 온라인 PowerShell 세션에서 다음 cmdlet을 실행 합니다.<br>`Get-CsTenant|ft identity`
    >    - 결과 값의 형식은 다음과 같습니다.<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 두세 자리 코드는 DC = lyncXX001 섹션에 포함 된 XX입니다. 두 문자 코드를 사용 하는 경우에는 숫자가 뒤에 붙는 숫자 (예: 0a)가 됩니다. 이 코드가 3 자 코드 이면 두 개의 문자와 숫자 (예: jp1)가 차례로 이어집니다. 모든 경우에 XX 코드 바로 다음에 001이 표시 됩니다.


## <a name="voice-configuration-requirements"></a>음성 구성 요구 사항

사용자가 enterprise voice for 프레미스에 대해 구성 된 경우 온라인으로 이동할 때 음성 구성을 업데이트 해야 합니까? 아니면 전화 통신 기능 없이 마이그레이션할 수도 있습니다. 사용 가능한 옵션은 사용자가 온라인 상태에서 팀 또는 비즈니스용 Skype 클라이언트를 사용 하 고 있는지 여부에 따라 달라 집니다.

- [Microsoft 통화 계획](/microsoftteams/calling-plans-for-office-365)을 사용 하도록 사용자의 전화 통신 공급자를 업데이트할 수 있습니다. 사용자가 팀 또는 비즈니스용 Skype 클라이언트를 사용할 것인지 여부를 선택 하는 옵션입니다.
- 온-프레미스 PSTN 공급자는 계속 사용할 수 있습니다.
  - 팀을 사용 하는 음성 사용자는 [직접 라우팅으로](/microsoftteams/direct-routing-plan)구성 해야 합니다. 직접 라우팅은 사용자를 온-프레미스에서 온라인으로 이동한 후에만 사용할 수 있습니다.
  - 온라인으로 이동한 후 비즈니스용 Skype 클라이언트를 사용 하는 음성 사용자는 비즈니스용 Skype 하이브리드 음성 기능에 맞게 구성 해야 합니다.

지원 가능성 매트릭스 뿐 아니라 하이브리드 환경의 전화 통신 옵션에 대 한 자세한 내용은 [PSTN 연결을 사용 하는 하이브리드 환경의 사용자 계정을](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)참조 하세요.

## <a name="other-considerations"></a>기타 고려 사항

온-프레미스와 온라인 환경의 정책(예: 메시징, 모임, 통화 동작)은 독립적입니다. 해당 사용자를 온-프레미스에서 클라우드로 이동 하기 전에 환경에서 정책을 구성 하 고 사용자에 게 할당 하 여 온라인으로 마이그레이션되는 즉시 올바른 구성을 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동](move-users-from-on-premises-to-skype-for-business-online.md)

[사용자를 온-프레미스에서 Teams로 이동](move-users-from-on-premises-to-teams.md)

[MMS(Meeting Migration Service) 설정](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[직접 라우팅 계획](/microsoftteams/direct-routing-plan)

[CsUser 이동](https://docs.microsoft.com/powershell/module/skype/move-csuser)
