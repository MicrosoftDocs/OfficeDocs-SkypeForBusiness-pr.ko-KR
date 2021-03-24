---
title: 마이그레이션 및 상호 실행성 - 비즈니스용 Skype
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 조직의 전환을 관리하는 기본 개념을 이해합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a446213a5c10126b9ae42986fe2fa1986bc9e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098334"
---
# <a name="coexistence-modes---reference"></a>공존 모드 - 참조

공존 모드는 조직이 비즈니스용 Skype에서 Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공합니다. Teams로 이동하는 조직의 경우 TeamsOnly 모드는 각 사용자의 최종 대상입니다. 하지만 모든 사용자가 TeamsOnly(또는 모든 모드)를 동시에 할당해야 하는 것은 아닙니다. TeamsOnly 모드에 도달하기 전에 조직은 비즈니스용 Skype 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)를 사용하여 TeamsOnly 사용자와 아직 없는 사용자 간에 예측 가능한 통신을 보장할 수 있습니다.

기술적인 관점에서 사용자의 모드는 사용자의 환경의 여러 측면을 관리합니다.

- *들어오는 라우팅*: 들어오는 채팅 및 통화를 하는 클라이언트(Teams 또는 비즈니스용 Skype)는 어떤가요? 
- *현재 상태 게시*: Teams 또는 비즈니스용 Skype의 활동을 기반으로 다른 사용자에게 표시되는 사용자의 현재 상태인가요? 
- *모임일정*: 새 모임을 일주하고 Outlook에 적절한 추가 기능을 제공하는 데 사용되는 서비스는 무엇입니까? TeamsUpgradePolicy는 모임 조인을 관리하지 않습니다. 사용자는 *비즈니스용* Skype 모임이든 Teams 모임이든 항상 모임에 참가할 수 있습니다.
- *클라이언트 환경*: Teams 및/또는 비즈니스용 Skype 클라이언트에서 사용할 수 있는 기능은 무엇입니까? 사용자가 Teams, 비즈니스용 Skype 또는 둘 다에서 통화 및 채팅을 시작할 수 있나요? Teams & 채널 환경을 사용할 수 있나요?  

모드를 기반으로 하는 라우팅 및 현재 상태 동작에 대한 자세한 내용은 [비즈니스용 Skype와 공존을 참조하세요.](./coexistence-chat-calls-presence.md)

그러나 환경 관점에서 모드는 다음에 대한 환경을 정의하는 것으로 설명할 수 있습니다.
- *채팅 및 통화*: 사용자가 어떤 클라이언트를 사용하나요?
- *모임 일정:* 사용자가 Teams 또는 비즈니스용 Skype 모임으로 새 모임을 예약하나요?
- *Teams 클라이언트의* 공동 작업 기능 가용성 Teams & 및 파일 기능을 사용할 수 있는 반면 사용자는 비즈니스용 Skype를 사용할 수 있나요?

모드는 아래에 나열되어 있습니다.
</br>
</br>

|모드|통화 및 채팅|모임 예정<sup>1</sup>|팀 & 채널|사용 사례|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*비즈니스용 Skype Online에 홈 필요*|Teams|Teams|예|업그레이드할 최종 상태입니다. 또한 새 테넌트의 기본값입니다.|
|Islands|둘 중 하나|둘 중 하나|예|기본 구성입니다. 단일 사용자가 두 클라이언트를 나란히 평가할 수 있습니다. 채팅 및 통화는 두 클라이언트 모두에 착륙할 수 있으므로 사용자는 항상 두 클라이언트를 모두 실행해야 합니다. 비즈니스용 Skype 환경을 혼동하거나 회귀하지 않도록 하기 위해 외부(페더링) 통신, PSTN 음성 서비스 및 음성 애플리케이션, Office 통합 및 기타 여러 통합은 비즈니스용 Skype에서 계속 처리됩니다.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|비즈니스용 Skype|Teams|예|"모임 먼저". 클라우드로 통화를 이동할 준비가 되지 않은 경우 주로 조직에서 Teams 모임 기능을 활용하기 위한 것입니다.|
|SfBWithTeamsCollab|비즈니스용 Skype|비즈니스용 Skype|예|더 엄격한 관리 제어가 필요한 복잡한 조직의 대체 시작점입니다.|
|SfBOnly|비즈니스용 Skype|비즈니스용 Skype|아니요<sup>3</sup>|데이터 제어에 대한 엄격한 요구 사항이 있는 조직에 대한 특수 시나리오입니다. 팀은 다른 사람이 예약한 모임에 참가하는 데만 사용됩니다.|
||||||

</br>
</br>

**참고 사항:**

<sup>1</sup> 기존 모임에 참가하는 능력(Teams에서 또는 비즈니스용 Skype에서 예약 여부)은 모드로 관리되지 않습니다. 기본적으로 사용자는 초대된 모든 모임에 항상 참가할 수 있습니다.

<sup>2</sup> 기본적으로 TeamsOnly 또는 SfbWithTeamsCollabAndMeetings를 개별 사용자에게 할당할 때 향후 해당 사용자가 예약한 기존 비즈니스용 Skype 모임은 Teams 모임으로 변환됩니다. 원하는 경우 TeamsUpgradePolicy를 부여할 때를 지정하거나 Teams 관리 포털에서 확인란을 선택하지 않으면 이러한 모임을 비즈니스용 Skype 모임으로 남길  `-MigrateMeetingsToTeams $false` 수 있습니다. 테넌트 전체에 TeamsUpgradePolicy를 부여할 때 비즈니스용 Skype에서 Teams로 모임을 변환하는 기능을 사용할 수 없습니다. 

<sup>3</sup> 현재 Teams에는 Teams 및 채널 기능을 비활성화할 수 없는 기능이 있으므로 현재는 이 기능이 활성화되어 있습니다.


## <a name="using-teamsupgradepolicy"></a>TeamsUpgradePolicy 사용

TeamsUpgradePolicy는 모드 및 NotifySfbUsers의 두 가지 주요 속성을 노출합니다. 
</br>
</br>

|매개 변수|유형|허용된 값</br>(이탈리크의 기본값)|설명|
|---|---|---|---|
|모드|열방|*Islands*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|클라이언트가 실행해야 하는 모드를 나타냅니다.|
|NotifySfbUsers|Bool|*False* 또는 true|Teams가 곧 비즈니스용 Skype를 대체할지 사용자에게 알리는 비즈니스용 Skype 클라이언트에 배너를 표시할지 여부를 나타냅니다. Mode=TeamsOnly의 경우 이 사실이 아닙니다.|
|||||

Teams는 기본 제공 읽기 전용 정책을 통해 TeamsUpgradePolicy의 모든 관련 인스턴스를 제공합니다. 따라서 Get 및 Grant cmdlet만 사용할 수 있습니다. 기본 제공 인스턴스는 아래에 나열되어 있습니다.
</br>
</br>

|Identity|모드|NotifySfbUsers|
|---|---|---|
|Islands|Islands|False|
|IslandsWithNotify|Islands|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|전역</br>*기본값*|Islands|False|
||||

이러한 정책 인스턴스는 개별 사용자에게 또는 테넌트 전체에 부여할 수 있습니다. 예를 들면 다음과 같습니다.
- 사용자($SipAddress)를 Teams로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 부여합니다.</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 전체 테넌트를 업그레이드하려면 부여 명령에서 ID 매개 변수를 생략합니다.</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>비즈니스용 Skype 모드를 사용할 때 Teams 클라이언트 사용자 환경

사용자가 비즈니스용 Skype 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 있는 경우 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 Teams 클라이언트의 통화 및 채팅 기능은 사용자가 비즈니스용 Skype 모드에 있는 경우 자동으로 비활성화됩니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 Teams의 모임 예정이 자동으로 비활성화되고 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 자동으로 활성화됩니다. 자세한 내용은 Teams 클라이언트 환경 및 공존 모드 [준수를 참조하세요.](./teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!Note] 
> - Teams 및 채널의 자동 적용 이전에 SfbOnly 및 SfBWithTeamsCollab 모드는 동일하게 실행됩니다.


## <a name="detailed-mode-descriptions"></a>자세한 모드 설명
</br>
</br>

|모드|설명|
|---|---|
|**Islands**</br>(기본값)|사용자는 비즈니스용 Skype와 Teams를 나란히 실행합니다. 이 사용자:</br><ul><li>비즈니스용 Skype 또는 Teams 클라이언트에서 채팅 및 VoIP 통화를 시작할 수 있습니다. 참고: 비즈니스용 Skype가 있는 사용자는 받는 사람의 모드에 관계없이 Teams에서 다른 비즈니스용 Skype 사용자에게 도달하도록 시작할 수 없습니다.<li>비즈니스용 Skype & 다른 사용자가 비즈니스용 Skype에서 시작한 VoIP 호출에 대한 채팅을 수신합니다.<li>동일한 테넌트에 & Teams 클라이언트의 다른 사용자가 Teams에서 시작한 VoIP 호출에 대한 채팅을 *수신합니다.*<li>페더리드 테넌트에 & 비즈니스용 Skype 클라이언트의 다른 사용자가 Teams에서 시작한 VoIP 호출에 대한 채팅을 *수신합니다.* <li>아래에 설명된 PSTN 기능이 있습니다.<ul><li>사용자가 비즈니스용 Skype에 홈이 프레미스에 Enterprise Voice 경우 PSTN 호출은 항상 비즈니스용 Skype에서 시작 및 수신됩니다.<li>사용자가 비즈니스용 Skype Online에 상주하고 Microsoft Phone System이 있는 경우 사용자는 항상 비즈니스용 Skype에서 PSTN 호출을 시작하고 수신합니다.<ul><li>이 문제는 사용자가 Microsoft 통화 계획을 밝혔거나 비즈니스용 Skype 클라우드 커넥터 버전 또는 비즈니스용 Skype 서버(하이브리드 음성)의 프레미스 배포를 통해 PSTN 네트워크에 연결하는지 여부에 따라 발생합니다.<li>**참고: 전화 시스템 직접 라우팅은 제도 모드에서 지원되지 않습니다.**</ul></ul><li>비즈니스용 Skype에서 Microsoft 통화 큐 및 자동 참석자 통화를 수신합니다.<ul><li>통화 큐 및 자동 참석자에  할당된 전화 번호는 제도 모드에서 전화 시스템 직접 라우팅 번호일 수 없습니다.</ul></ul><li>Teams 또는 비즈니스용 Skype에서 모임을 예약할 수 있습니다(기본적으로 두 플러그 인이 모두 표시됩니다).<li>비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다. 모임이 해당 클라이언트에서 열립니다.</ul>|
|**SfBOnly**|사용자는 비즈니스용 Skype만 실행합니다. 이 사용자:</br><ul><li>비즈니스용 Skype에서만 채팅 및 통화를 시작할 수 있습니다.<li>비즈니스용 Skype 클라이언트에서 시작 위치와 관계없이 모든 채팅/통화를 수신합니다. 시작자는 비즈니스용 Skype가 있는 Teams 사용자인 경우를 가정합니다. *<li> 비즈니스용 Skype </br> \* 모임만* 예약할 수 있지만 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다. 프레미스 사용자와 섬 모드를 사용하는 것은 SfBOnly 모드의 다른 사용자와 함께 사용하지 않는 것이 좋습니다. 비즈니스용 Skype가 있는 Teams 사용자가 SfBOnly 사용자에 대한 통화 또는 채팅을 시작하면 SfBOnly 사용자에게 도달할 수 없습니다. 부재 중 채팅 또는 통화 전자 메일을 수신합니다.*|
|**SfBWithTeamsCollab**|사용자는 비즈니스용 Skype와 Teams를 나란히 실행합니다. 이 사용자:</br><ul><li>SfBOnly 모드에서 사용자의 기능이 있습니다.<li>Teams가 그룹 공동 작업(채널)에만 사용하도록 설정되어 있습니다. chat/calling/meeting scheduling은 사용할 수 없습니다.</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|사용자는 비즈니스용 Skype와 Teams를 나란히 실행합니다. 이 사용자:<ul><li>SfBOnly 모드에서 사용자의 채팅 및 호출 기능이 있습니다.<li>Teams가 그룹 공동 작업을 사용하도록 설정되어 있습니다(채널 - 채널 대화 포함) 채팅 및 통화를 사용할 수 없습니다.<li>Teams 모임만 예약할 수 있지만 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다.</ul>|
|**TeamsOnly**</br>(SfB Online 홈 필요)|사용자는 Teams만 실행합니다. 이 사용자:<ul><li>시작 위치와 관계없이 Teams 클라이언트에서 채팅 및 통화를 수신합니다.<li>Teams에서만 채팅 및 통화를 시작할 수 있습니다.<li>Teams에서만 모임을 예약할 수 있지만 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다.<li>비즈니스용 Skype IP 휴대폰을 계속 사용할 수 있습니다.<br><br>*TeamsOnly 모드를 섬 모드의 다른 사용자와 함께 사용하는 것은 Teams 채택이 포화될 때까지 권장되지 않습니다. 즉, 모든 아일랜드 모드 사용자는 Teams 및 Skype for Business 클라이언트를 적극적으로 사용하고 모니터링합니다. TeamsOnly 사용자가 섬 사용자에 대한 통화 또는 채팅을 시작하는 경우 해당 호출 또는 채팅은 Islands 사용자의 Teams 클라이언트에 연결됩니다. 섬 사용자가 Teams를 사용하거나 모니터링하지 않는 경우 해당 사용자는 오프라인으로 표시될 것이고 TeamsOnly 사용자가 도달할 수 없습니다.*</ul> |
|||




## <a name="related-topics"></a>관련 주제

[비즈니스용 Skype와 공존](./coexistence-chat-calls-presence.md)

[Teams 클라이언트 환경 및 공존 모드 준수](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)