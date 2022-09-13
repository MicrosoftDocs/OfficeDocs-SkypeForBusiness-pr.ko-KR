---
title: 마이그레이션 및 상호 운용성 - 비즈니스용 Skype
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype Teams로의 조직 전환을 관리하기 위한 기본 개념을 이해합니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: b6c8e96c1aeb8fabcbe42ba403c51b4a8d6f4836
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657268"
---
# <a name="coexistence-modes---reference"></a>공존 모드 - 참조

> [!Important] 
> - 2021년 7월 31일에 비즈니스용 Skype Online을 사용 중지한 후에는 TeamsOnly 이외의 공존 모드를 클라우드에 있는 사용자에게 더 이상 할당할 수 없습니다. 사용 중지 이전의 경우와 마찬가지로 비즈니스용 Skype 서버 온-프레미스에 있는 사용자는 TeamsOnly *이외의* 모드로 할당할 수 있습니다. 

공존 모드는 조직이 비즈니스용 Skype Teams로 전환함에 따라 최종 사용자에게 간단하고 예측 가능한 환경을 제공합니다. Teams로 이동하는 조직의 경우 TeamsOnly 모드는 각 사용자의 최종 대상이지만 모든 사용자가 TeamsOnly(또는 모든 모드)를 동시에 할당해야 하는 것은 아닙니다. TeamsOnly 모드에 도달하기 전에 조직에서는 비즈니스용 Skype 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)를 사용하여 TeamsOnly 사용자와 아직 없는 사용자 간에 예측 가능한 통신을 보장할 수 있습니다.

기술적 관점에서 사용자 모드는 사용자 환경의 여러 측면을 제어합니다.

- *들어오는 라우팅*: 어떤 클라이언트(Teams 또는 비즈니스용 Skype)에서 들어오는 채팅 및 통화가 시작되나요? 
- *현재 상태 게시*: Teams 또는 비즈니스용 Skype 활동을 기반으로 다른 사용자에게 표시되는 사용자의 현재 상태인가요? 
- *모임 일정*: 새 모임을 예약하고 Outlook에 적절한 추가 기능이 있는지 확인하는 데 사용되는 서비스는 무엇인가요? TeamsUpgradePolicy는 모임 참가를 제어하지 않습니다. 사용자는 비즈니스용 Skype 모임이든 Teams 모임이든 상관없이 언제든지 모든 모임에 *참가* 할 수 있습니다.
- *클라이언트 환경*: Teams 및/또는 비즈니스용 Skype 클라이언트에서 사용할 수 있는 기능은 무엇인가요? 사용자가 Teams, 비즈니스용 Skype 또는 둘 다에서 통화 및 채팅을 시작할 수 있나요? Teams & 채널 환경을 사용할 수 있나요?  

모드 기반 라우팅 및 현재 상태 동작에 대한 자세한 내용은 [비즈니스용 Skype 공존](./coexistence-chat-calls-presence.md)을 참조하세요.

그러나 환경 관점에서 모드는 다음에 대한 환경을 정의하는 것으로 설명할 수 있습니다.
- *채팅 및 통화*: 사용자가 사용하는 클라이언트는 무엇인가요?
- *모임 일정*: 사용자가 Teams 또는 비즈니스용 Skype 모임으로 새 모임을 예약합니까?
- *Teams 클라이언트에서 공동 작업 기능의 가용성* 사용자가 여전히 비즈니스용 Skype 동안 Teams & 채널 및 파일 기능을 사용할 수 있나요?

모드는 아래에 나열되어 있습니다. 클라우드 사용자는 TeamsOnly여야 하며 온-프레미스에 있는 사용자는 TeamsOnly 이외의 모드여야 합니다. 
</br>
</br>

|모드|통화 및 채팅|모임 일정<sup>1</sup>|Teams & 채널|사용 사례|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*사용자에게 온-프레미스 계정이 없는 경우에만 비즈니스용 Skype 서버*|Teams|Teams|예|업그레이드되는 최종 상태입니다. 하이브리드 구성이 검색되지 않는 한 새 테넌트에 대한 기본값입니다.|
|아일랜드|둘 중 하나|둘 중 하나|예|하이브리드 조직에 대한 기본 구성입니다. 단일 사용자가 두 클라이언트를 나란히 평가할 수 있습니다. 채팅 및 통화는 두 클라이언트에 모두 연결할 수 있으므로 사용자는 항상 두 클라이언트를 모두 실행해야 합니다. 혼동되거나 회귀된 비즈니스용 Skype 환경을 방지하기 위해 외부(페더레이션) 통신, PSTN 음성 서비스 및 음성 응용 프로그램, Office 통합 및 기타 여러 통합은 비즈니스용 Skype 계속 처리됩니다.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|비즈니스용 Skype|Teams|예|"모임 우선". 주로 온-프레미스 조직이 아직 클라우드로 통화를 이동할 준비가 되지 않은 경우 Teams 모임 기능을 활용할 수 있습니다.|
|SfBWithTeamsCollab|비즈니스용 Skype|비즈니스용 Skype|예|보다 엄격한 관리 제어가 필요한 복잡한 조직의 대체 시작점입니다.|
|SfBOnly|비즈니스용 Skype|비즈니스용 Skype|아니요<sup>3</sup>|데이터 제어에 대한 엄격한 요구 사항이 있는 조직을 위한 특수 시나리오입니다. Teams는 다른 사용자가 예약한 모임에 참가하는 데만 사용됩니다.|
||||||

</br>
</br>

**노트:**

<sup>1</sup> 기존 모임에 참가하는 기능(Teams 또는 비즈니스용 Skype 예약 여부)은 모드에 따라 제어되지 않습니다. 기본적으로 사용자는 항상 초대된 모든 모임에 참가할 수 있습니다.

<sup>2</sup> 기본적으로 TeamsOnly 또는 SfbWithTeamsCollabAndMeetings를 개별 사용자에게 할당할 때 해당 사용자가 나중에 예약한 기존 비즈니스용 Skype 모임은 Teams 모임으로 변환됩니다. 원하는 경우 TeamsUpgradePolicy를 부여할 때를 지정 `-MigrateMeetingsToTeams $false` 하거나 Teams 관리 포털에서 확인란을 선택 취소하여 이러한 모임을 비즈니스용 Skype 모임으로 남길 수 있습니다. 테넌트 전체에서 TeamsUpgradePolicy를 부여할 때 모임을 비즈니스용 Skype Teams로 변환하는 기능은 사용할 수 없습니다. 

<sup>3</sup> 현재 Teams에는 Teams 및 채널 기능을 사용하지 않도록 설정할 수 없으므로 지금은 사용하도록 설정되어 있습니다.


## <a name="using-teamsupgradepolicy"></a>TeamsUpgradePolicy 사용

TeamsUpgradePolicy는 모드 및 NotifySfbUsers라는 두 가지 주요 속성을 노출합니다. 
</br>
</br>

|매개 변수|유형|허용되는 값</br>(기울임꼴의 기본값)|설명|
|---|---|---|---|
|모드|열거형|*아일랜드*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|클라이언트가 실행되어야 하는 모드를 나타냅니다.|
|NotifySfbUsers|Bool|*False* 또는 true|Teams가 곧 비즈니스용 Skype 대체할 것임을 사용자에게 알리는 배너를 비즈니스용 Skype 클라이언트에 표시할지 여부를 나타냅니다. Mode=TeamsOnly인 경우에는 이 작업을 수행할 수 없습니다.|
|||||

Teams는 기본 제공 읽기 전용 정책을 통해 TeamsUpgradePolicy의 모든 관련 인스턴스를 제공합니다. 따라서 Get 및 Grant cmdlet만 사용할 수 있습니다. 기본 제공 인스턴스는 아래에 나열되어 있습니다.
</br>
</br>

|Identity|모드|NotifySfbUsers|
|---|---|---|
|아일랜드|아일랜드|False|
|IslandsWithNotify|아일랜드|사실|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|사실|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|사실|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|사실|
|UpgradeToTeams|TeamsOnly|False|
|전역</br>*기본*|아일랜드|False|
||||

이러한 정책 인스턴스는 개별 사용자 또는 테넌트 전체에 부여할 수 있습니다. 예를 들면 다음과 같습니다.
- 사용자($SipAddress)를 Teams로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 부여합니다.</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 전체 테넌트 업그레이드를 수행하려면 grant 명령에서 ID 매개 변수를 생략합니다.</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>비즈니스용 Skype 모드를 사용하는 경우 Teams 클라이언트 사용자 환경

사용자가 비즈니스용 Skype 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 있는 경우 들어오는 모든 채팅 및 호출이 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자의 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있을 때 Teams 클라이언트의 통화 및 채팅 기능이 자동으로 비활성화됩니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있을 때 Teams에서 모임 일정이 자동으로 비활성화되고 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있을 때 자동으로 사용하도록 설정됩니다. 자세한 내용은 [Teams 클라이언트 환경 및 공존 모드 준수를 참조하세요](./teams-client-experience-and-conformance-to-coexistence-modes.md).

> [!Note] 
> - Teams 및 채널의 자동 적용을 전달하기 전에 SfbOnly 및 SfBWithTeamsCollab 모드는 동일하게 작동합니다.


## <a name="detailed-mode-descriptions"></a>자세한 모드 설명
</br>
</br>

|모드|설명|
|---|---|
|**아일랜드**</br>(온-프레미스에만 해당)|사용자는 비즈니스용 Skype Teams를 나란히 실행합니다. 이 사용자는 다음과 같습니다.</br><ul><li>비즈니스용 Skype 또는 Teams 클라이언트에서 채팅 및 VoIP 통화를 시작할 수 있습니다. 참고: 온-프레미스에 비즈니스용 Skype 있는 사용자는 받는 사람의 모드에 관계없이 Teams에서 다른 비즈니스용 Skype 사용자에게 도달하기 위해 시작할 수 없습니다.<li>비즈니스용 Skype 클라이언트의 다른 사용자가 비즈니스용 Skype 시작한 VoIP 호출에 & 채팅을 받습니다.<li>*동일한 테넌트에* 있는 경우 Teams 클라이언트의 다른 사용자가 Teams에서 시작한 VoIP 통화에 & 채팅을 받습니다.<li>*페더레이션된 테넌트에* 있는 경우 비즈니스용 Skype 클라이언트의 다른 사용자가 Teams에서 시작한 VoIP 호출을 & 채팅을 받습니다. <li>아래에 설명된 대로 PSTN 기능이 있습니다.<ul><li>사용자가 비즈니스용 Skype 온-프레미스에 있고 Enterprise Voice 있는 경우 PSTN 호출은 항상 시작되고 비즈니스용 Skype 수신됩니다.<li>사용자가 비즈니스용 Skype Online에 있고 Microsoft Phone System이 있는 경우 사용자는 항상 비즈니스용 Skype PSTN 통화를 시작하고 수신합니다.<ul><li>이는 사용자에게 Microsoft 통화 플랜이 있거나 비즈니스용 Skype 클라우드 커넥터 버전 또는 온-프레미스 비즈니스용 Skype 서버(하이브리드 음성) 배포를 통해 PSTN 네트워크에 연결하든 관계없이 발생합니다.<li>**참고: 전화 시스템 직접 라우팅은 아일랜드 모드에서 지원되지 않습니다.**</ul></ul><li>비즈니스용 Skype Microsoft 통화 큐 및 자동 전화 교환 호출을 수신합니다.<ul><li>통화 큐 및 자동 전화 교환에 할당된 전화 번호는 아일랜드 모드의 전화 시스템 직접 라우팅 번호일 **수 없습니다** .</ul></ul><li>Teams 또는 비즈니스용 Skype 모임을 예약할 수 있습니다(기본적으로 두 플러그 인이 모두 표시됨).<li>모든 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다. 모임은 해당 클라이언트에서 열립니다.</ul>|
|**SfBOnly**</br>(온-프레미스에만 해당)|사용자는 비즈니스용 Skype만 실행합니다. 이 사용자는 다음과 같습니다.</br><ul><li>비즈니스용 Skype 채팅 및 통화만 시작할 수 있습니다.<li>시작자가 온-프레미스에 비즈니스용 Skype 있는 Teams 사용자가 아니면 시작 위치에 관계없이 비즈니스용 Skype 클라이언트에서 채팅/통화를 받습니다.*<li> 비즈니스용 Skype 모임만 예약할 수 있지만 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다.</br>\** SfBOnly 모드의 다른 사용자와 함께 온-프레미스 사용자와 Islands 모드를 사용하는 것은 권장되지 않습니다. 온-프레미스에 비즈니스용 Skype 있는 Teams 사용자가 SfBOnly 사용자에 대한 통화 또는 채팅을 시작하는 경우 SfBOnly 사용자에게 연결할 수 없으며 누락된 채팅 또는 통화 전자 메일을 받습니다.*|
|**SfBWithTeamsCollab**</br>(온-프레미스에만 해당)|사용자는 비즈니스용 Skype Teams를 나란히 실행합니다. 이 사용자는 다음과 같습니다.</br><ul><li>SfBOnly 모드에서 사용자의 기능이 있습니다.<li>Teams는 그룹 공동 작업(채널)에 대해서만 사용하도록 설정되었습니다. 채팅/통화/모임 예약을 사용할 수 없습니다.</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>(온-프레미스에만 해당)|사용자는 비즈니스용 Skype Teams를 나란히 실행합니다. 이 사용자는 다음과 같습니다.<ul><li>SfBOnly 모드에서 사용자의 채팅 및 통화 기능이 있습니다.<li>Teams에서 그룹 공동 작업을 사용하도록 설정했습니다(채널 - 채널 대화 포함). 채팅 및 통화는 사용할 수 없습니다.<li>Teams 모임만 예약할 수 있지만 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다.</ul>|
|**TeamsOnly**</br>(클라우드 사용자만 해당)|사용자는 Teams만 실행합니다. 이 사용자는 다음과 같습니다.<ul><li>시작된 위치에 관계없이 Teams 클라이언트에서 채팅 및 통화를 받습니다.<li>Teams에서만 채팅 및 통화를 시작할 수 있습니다.<li>Teams에서만 모임을 예약할 수 있지만 비즈니스용 Skype 또는 Teams 모임에 참가할 수 있습니다.<li>비즈니스용 SKYPE IP 휴대폰을 계속 사용할 수 있습니다.<br><br>*Teams 채택이 포화될 때까지는 TeamsOnly 모드를 아일랜드 모드의 다른 사용자와 함께 사용하는 것이 좋습니다. 즉, 모든 아일랜드 모드 사용자는 Teams 및 비즈니스용 Skype 클라이언트를 적극적으로 사용하고 모니터링합니다. TeamsOnly 사용자가 아일랜드 사용자에 대한 통화 또는 채팅을 시작하는 경우 해당 통화 또는 채팅은 Islands 사용자의 Teams 클라이언트에 연결됩니다. Islands 사용자가 Teams를 사용하거나 모니터링하지 않으면 해당 사용자가 오프라인으로 표시되고 TeamsOnly 사용자가 연결할 수 없게 됩니다.* <li>경우에 따라 TeamsOnly 모드의 참가자는 익명 사용자로 비즈니스용 Skype Web App 또는 Skype 모임 앱을 사용하여 비즈니스용 Skype 모임에 참가할 수 있습니다. 결국 TeamsOnly 모드의 모든 사용자에 대해 이 사례가 true가 됩니다. 자세한 내용은 [비즈니스용 Skype Online 사용 중지](skype-for-business-online-retirement.md#what-to-expect-post-retirement)를 참조하세요.</ul> |
|||




## <a name="related-topics"></a>관련 주제

[비즈니스용 Skype와 공존](./coexistence-chat-calls-presence.md)

[Teams 클라이언트 환경 및 공존 모드 준수](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
