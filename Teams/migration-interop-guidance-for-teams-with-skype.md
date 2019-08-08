---
title: 비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 팀으로 전환 관리에 대 한 지침
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f8cfe994510c8364b4421f45b48bedfb9f2888f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239310"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침

> [!Tip] 
> [공존 및 상호 운용성](https://aka.ms/teams-upgrade-coexistence-interop) 에 대해 알아보려면 다음 세션을 시청 하세요.

비즈니스용 Skype를 사용 하는 조직에서 팀을 채택 하기 시작 하면 관리자는 TeamsUpgradePolicy의 속성인 공존 "모드"의 개념을 사용 하 여 조직에서 사용자 환경을 관리할 수 있습니다. 관리자는 사업부를 사용 하 여 비즈니스용 Skype에서 팀으로 전환 하는 것으로 interop 및 마이그레이션을 관리 합니다.  사용자의 모드는 클라이언트가 들어오는 채팅 및 통화를 비롯 하 여 어떤 서비스 (팀 또는 비즈니스용 Skype) 새 모임이 예정 되어 있는지를 결정 합니다. 또한 팀 클라이언트에서 사용할 수 있는 기능을 제어 합니다. 


## <a name="fundamental-concepts"></a>기본 개념

1.  *Interop* : Lync/비즈니스용 Skype 사용자와 팀 사용자 간의 통신 1 ~ 1 개.

2.  *페더레이션* : 다른 테 넌 트의 사용자 간 통신

3.  모든 팀 사용자는 온라인 또는 온-프레미스 중 "홈" 인 비즈니스용 Skype 계정을가지고 있습니다.
    - 비즈니스용 Skype Online을 이미 사용 하는 사용자는 기존 온라인 계정을 사용 합니다.
    - 비즈니스용 Skype/Lync 온-프레미스를 이미 사용 중인 사용자는 기존 온-프레미스 계정을 사용 합니다.
    - 기존 비즈니스용 Skype 계정을 검색할 수 없는 사용자는 팀 사용자가 만들어질 때 비즈니스용 Skype Online 계정이 자동으로 프로 비전 됩니다.

4.  비즈니스용 Skype 또는 Lync의 온-프레미스 배포를 사용 하는 경우 해당 사용자를 팀 사용자로 설정 하려면 최소한 Azure AD Connect가 msRTCSIP Locator 특성을 AAD로 동기화 하 여 비즈니스용 Skype를 사용 하도록 해야 합니다. 온라인에서 온-프레미스 환경을 제대로 검색 합니다. 또한 모든 사용자를 팀 전용 모드로 이동 하려면 (예: 사용자 업그레이드) *먼저 비즈니스용 Skype 하이브리드 모드를 구성 해야 합니다*. 자세한 내용은 [비즈니스용 Skype 및 팀에 대 한 AZURE AD Connect 구성을](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)참조 하세요.

5.  팀과 비즈니스용 Skype 사용자 간 상호 운용성은 *팀 사용자가 비즈니스용 skype에서 온라인 상태인 경우*에만 가능 합니다. 받는 사람 비즈니스용 Skype 사용자는 온-프레미스 (비즈니스용 Skype 하이브리드 구성 필요) 또는 온라인 중 하나로 설정할 수 있습니다. 비즈니스용 Skype 온-프레미스에 속한 사용자는이 문서의 뒷부분에 정의 된 아일랜드 모드에서 팀을 사용할 수 있지만, 팀을 사용 하 여 비즈니스용 Skype를 사용 하는 다른 사용자와 상호 운용 하거나 페더레이션 할 수는 없습니다.  

6.  업그레이드 및 interop 동작은 아래에 설명 된 대로 사용자의 공존 모드에 따라 결정 됩니다. Mode는 TeamsUpgradePolicy에 의해 관리 됩니다. 

7.  사용자를 TeamsOnly 모드로 업그레이드 하면 가져온 클라이언트에 관계 없이 모든 수신 채팅 및 통화가 항상 사용자의 팀 클라이언트에 있게 됩니다. 이러한 사용자는 또한 팀의 모든 새 모임을 예약 합니다. Teamonly 모드에 있으려면 비즈니스용 Skype에서 사용자를 온라인으로 전환 해야 합니다. 이는 팀 사용자의 interop, 페더레이션 및 전체 관리를 보장 하는 데 필요 합니다. 사용자를 TeamsOnly로 업그레이드 하려면 다음을 수행 합니다.
    - 사용자가 비즈니스용 Skype online에 있는 경우 (또는 Skype 계정이 없는 경우), PowerShell을 사용 하 여 "UpgradeToTeams" 인스턴스를 사용 하는 경우에만 TeamsUpgradePolicy 모드를 허용 하거나 팀 관리 센터를 사용 하 여 TeamsOnly 모드를 선택 합니다.
    - 사용자가 온-프레미스 인 경우 온-프레미스 `Move-CsUser` 관리 도구에서 사용 하 여 먼저 사용자를 비즈니스용 Skype Online으로 이동 합니다.  비즈니스용 skype Server 2019 또는 CU8 for 비즈니스용 Skype Server 2015이 있는 경우에서 `-MoveToTeams` `Move-CsUser` 전환을 지정 하 여 온라인으로 이동의 일부로 사용자를 직접 팀으로 이동할 수 있습니다. 또한이 옵션은 사용자의 모임을 팀으로 마이그레이션합니다. 이 `-MoveToTeams` 지정 되지 않았거나 사용할 수 없는 경우 완료 후 `Move-CsUser` 에는 PowerShell 또는 팀 관리 센터를 사용 하 여 해당 사용자에 게 팀 전용 모드를 할당 합니다. 자세한 내용은 온 [-프레미스 및 클라우드 간에 사용자 이동을](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)참조 하세요.  모임 마이그레이션에 대 한 자세한 내용은 [MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)을 참조 하세요.

8.  팀과 함께 Microsoft 휴대폰 시스템을 사용 하려면 사용자가 TeamsOnly 모드 (예: 비즈니스용 Skype Online 및 팀으로 업그레이드) 여야 하며, Microsoft 전화 시스템 [다이렉트 라우팅](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277) 에 대해 구성 되어 있어야 하며,이 경우 전화 시스템을 사용할 수 있습니다. 자신의 SIP trunks 및 SBC) 또는 Office 365 통화 요금제를 사용 합니다. Microsoft 전화 시스템 다이렉트 라우팅은 군도 모드에서 지원 되지 않습니다.    

9.  사용자가 비즈니스용 Skype Online 또는 비즈니스용 Skype 온-프레미스를 사용 하 고 있는지 여부에 관계 없이 오디오 회의를 통한 팀 회의 예약 (PSTN을 통한 전화 접속 또는 다이얼 아웃)을 사용할 수 있습니다. 


## <a name="coexistence-modes"></a>공존 모드

Interop 및 마이그레이션은 TeamsUpgradePolicy를 사용 하 여 "공존 모드"에 따라 관리 됩니다. 공동 존재 모드는 조직이 비즈니스용 Skype에서 팀으로 전환 하는 것 처럼 최종 사용자에 게 예측 가능한 간단한 환경을 제공 합니다. 팀으로 이동 하는 조직의 경우 모든 사용자가 동시에 Teamonly (또는 모든 모드)를 할당 해야 하는 것은 아니지만 TeamsOnly 모드는 각 사용자의 최종 대상입니다. 사용자가 팀의 유일한 모드에 도달 하기 전에, 조직에서 비즈니스용 Skype 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)를 사용 하 여 팀이 자신을 대상으로 하 고 아직 받지 않은 사용자 간에 예측 가능한 의사 소통을 보장할 수 있습니다.


기술적 관점에서 보면 사용자의 모드는 사용자 환경의 몇 가지 측면을 제어 합니다.

- *수신 라우팅*: 들어오는 채팅 및 통화를 수행 하는 클라이언트 (팀 또는 비즈니스용 Skype) 
- *현재 상태 게시*: 팀 또는 비즈니스용 Skype의 활동에 따라 다른 사용자에 게 표시 되는 사용자의 현재 상태 
- *모임 예약*: 새 모임을 예약 하는 데 사용 되는 서비스와 Outlook에 적절 한 추가 기능이 있는지 확인 합니다. TeamsUpgradePolicy가 모임 참가를 제어 하지 않는다는 점에 유의 하세요. 사용자는 비즈니스용 Skype 모임 또는 팀 모임에 관계 없이 언제 든 지 모임에 *참가할* 수 있습니다.
- *클라이언트 환경*: 팀 및/또는 비즈니스용 Skype 클라이언트에서 어떤 기능을 사용할 수 있나요? 사용자가 팀, 비즈니스용 Skype 또는 둘 다에서 통화와 채팅을 시작할 수 있나요? 팀 & 채널 경험을 사용할 수 있나요?  

모드 기반 라우팅 및 현재 상태 동작에 대 한 자세한 내용은 [비즈니스용 Skype를 사용 하 여 공존](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)을 참조 하세요.

그러나 경험 측면에서 볼 때 다음과 같은 작업 환경을 정의 하는 것으로 모드를 더 간단 하 게 설명할 수 있습니다.
- *채팅 및 통화*: 사용자가 어떤 클라이언트를 사용 합니까?
- *모임 예약*: 사용자가 새 모임을 팀 또는 비즈니스용 Skype 모임으로 예약 하 시겠습니까?
- *팀 클라이언트의 공동 작업 기능 가용성*. 사용자가 비즈니스용 Skype를 사용 하는 동안 사용할 수 있는 채널 및 파일 기능을 & 팀이 있나요?

모드 목록은 다음과 같습니다.
</br>
</br>

|모드|통화 및 채팅|모임 예약<sup>1</sup>|팀 & 채널|사용 사례|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*비즈니스용 Skype Online에 홈이 필요 합니다.*|성과|성과|'|업그레이드 되는 최종 상태입니다. 또한 <500 좌석을 가진 새 테 넌 트의 기본값입니다.|
|분리|어떤|어떤|'|기본 구성. 단일 사용자가 두 클라이언트를 나란히 평가할 수 있도록 합니다. 채팅 및 통화는 두 클라이언트 중 하나에서 발생할 수 있으므로 사용자는 항상 두 클라이언트를 모두 실행 해야 합니다. 비즈니스용 Skype 환경, 외부 (연합) 통신, PSTN 음성 서비스 및 음성 응용 프로그램, 사무실 통합, 기타 여러 통합이 비즈니스용 Skype에서 계속 해 서 처리 되는 것을 방지 합니다.|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|비즈니스용 Skype|성과|'|"모임 먼저". 현재 온-프레미스 조직을 클라우드로의 통화를 진행할 준비가 되지 않은 경우 팀 모임 기능을 활용할 수 있습니다.|
|SfBWithTeamsCollab|비즈니스용 Skype|비즈니스용 Skype|'|보다 엄격한 관리 제어가 필요한 복잡 한 조직의 대체 시작 위치입니다.|
|SfBOnly|비즈니스용 Skype|비즈니스용 Skype|<sup>3</sup> 없음|데이터 제어에 대 한 엄격한 요구 사항이 있는 조직에 대 한 특수 시나리오입니다. 팀은 다른 사람이 예약한 모임에 참가 하는 데만 사용 됩니다.|
||||||

</br>
</br>

**참고:**

<sup>1</sup> 기존 모임에 참가 하는 기능 (팀의 예약 또는 비즈니스용 Skype)은 모드를 통해 제어 되지 않습니다. 기본적으로 사용자는 초대 된 모든 모임에 항상 참가할 수 있습니다.

<sup>2</sup> 개인 사용자에 게 팀 전용 또는 SfbWithTeamsCollabAndMeetings 할당 하는 경우, 이후 해당 사용자가 예약한 모든 비즈니스용 Skype 모임이 팀 모임으로 변환 됩니다. 원할 경우, TeamsUpgradePolicy을 허용 하는 경우를 지정 `-MigrateMeetingsToTeams $false` 하거나 팀 관리 포털에서 확인란을 선택 취소 하 여 이러한 모임을 비즈니스용 Skype 모임으로 남겨둘 수 있습니다.   테 넌 트를 기준으로 TeamsUpgradePolicy 권한을 부여할 때 비즈니스용 Skype에서 팀으로 모임을 변환 하는 기능은 avaialble 되지 않습니다. 

<sup>3</sup> 현재 팀에 팀 및 채널 기능을 사용 하지 않도록 설정 하는 기능이 없으므로 지금이 활성화 된 상태를 유지 합니다.



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 마이그레이션 및 공동 존재 관리

TeamsUpgradePolicy는 Mode 및 NotifySfbUsers 라는 두 가지 키 속성을 표시 합니다. 
</br>
</br>

|매개 변수|유형|허용 되는 값</br>(기울임꼴의 기본값)|설명|
|---|---|---|---|
|모드|열거할|*분리*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|클라이언트가 실행 되어야 하는 모드를 나타냅니다.|
|NotifySfbUsers|부울|*False* 또는 true|Skype for Business 클라이언트에 팀이 곧 비즈니스용 Skype를 교체할 수 있음을 알리는 배너를 표시할지 여부를 나타냅니다. Mode = TeamsOnly에만 해당 하는 경우에는 true를 사용할 수 없습니다.|
|||||

팀은 기본 제공 읽기 전용 정책을 통해 TeamsUpgradePolicy의 모든 관련 인스턴스를 제공 합니다. 따라서 Get 및 Grant cmdlet만 사용할 수 있습니다. 기본 제공 인스턴스가 아래에 나열 되어 있습니다.
</br>
</br>

|Identity|모드|NotifySfbUsers|
|---|---|---|
|분리|분리|해제|
|IslandsWithNotify|분리|False|
|SfBOnly|SfBOnly|해제|
|SfBOnlyWithNotify|SfBOnly|False|
|SfBWithTeamsCollab|SfBWithTeamsCollab|해제|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|해제|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|False|
|업그레이드 팀|TeamsOnly|해제|
|전역</br>*기본값*|분리|해제|
||||

이러한 정책 인스턴스는 개별 사용자에 게 부여 하거나 테 넌 트 전체에 부여할 수 있습니다. 예를 들면 다음과 같습니다.
- 사용자 ($SipAddress)를 팀으로 업그레이드 하려면 "UpgradeToTeams" 인스턴스를 부여 합니다.</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 전체 테 넌 트를 업그레이드 하려면 grant 명령에서 identity 매개 변수를 생략 합니다.</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>페더레이션 고려 사항

비즈니스용 Skype를 사용 하 여 팀에서 다른 사용자에 게 페더레이션 하려면 비즈니스용 Skype에서 팀 사용자가 온라인 상태 여야 합니다. 최종적으로 비즈니스용 Skype에 있는 팀 사용자는 팀 전용 사용자와 페더레이션 할 수 있습니다.

TeamsUpgradePolicy는 들어오는 페더레이션된 채팅 및 통화에 대 한 라우팅을 제어 합니다. 페더레이션된 라우팅 동작은 *아일랜드 모드를 제외*하 고 동일한 테 넌 트 시나리오와 동일 합니다.  받는 사람이 아일랜드 모드일 때: 
- 받는 사람이 *페더레이션 테 넌 트*에 있는 경우 SfB에서 팀이 시작한 채팅 및 통화입니다.
- 받는 사람이 *동일한 테 넌 트*에 있는 경우 팀에서 팀에서 시작한 채팅 및 통화입니다.
- SfB에서 시작 되는 채팅 및 통화는 항상 비즈니스용 Skype에 있습니다.

자세한 내용은 비즈니스용 [Skype를 사용 하 여 공존](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)을 참조 하세요.

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>SfB 모드를 사용할 때의 팀 클라이언트 사용자 환경
사용자가 비즈니스용 Skype 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 있는 경우 모든 수신 채팅 및 통화는 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 사용자가 비즈니스용 Skype 모드에 있는 경우 최종 사용자의 혼란을 방지 하 고 팀 클라이언트의 통화 및 채팅 기능이 자동으로 비활성화 되도록 하는 것이 좋습니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 팀에서 모임 일정이 자동으로 해제 되 고 사용자가 SfBWithTeamsCollabAndMeetings 모드일 때 자동으로 활성화 됩니다. 자세한 내용은 [팀 클라이언트 환경 및 공존 모드 준수](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)를 참조 하세요.

> [!Note] 
> - 팀 및 채널의 자동 적용을 하기 전에 SfbOnly 및 SfBWithTeamsCollab 모드가 동일 하 게 작동 합니다.


## <a name="detailed-mode-descriptions"></a>자세한 모드 설명
</br>
</br>

|모드|볼|
|---|---|
|**분리**</br>기본값|사용자가 비즈니스용 Skype와 팀을 함께 실행 합니다. 사용자:</br><ul><li>비즈니스용 Skype 또는 팀 클라이언트에서 채팅 및 VoIP 통화를 시작할 수 있습니다. 참고: 받는 사람 모드에 관계 없이 비즈니스용 Skype를 사용 하는 사용자가 다른 비즈니스용 Skype 사용자에 게 연결 하도록 초기화할 수 없습니다.<li>비즈니스용 skype 클라이언트의 다른 사용자가 비즈니스용 Skype에서 시작한 채팅 & VoIP 통화를 받습니다.<li>팀에서 시작한 채팅 & VoIP 통화를 팀 클라이언트의 다른 사용자가 *동일한 테 넌 트*에 있는 경우이를 받습니다.<li>다른 사용자가 *페더레이션된 테 넌 트*를 사용 하는 경우 비즈니스용 Skype 클라이언트에서 팀에서 시작한 채팅 & VoIP 통화를 받습니다. <li>아래에 명시 된 대로 PSTN 기능을가지고 있습니다.<ul><li>사용자가 비즈니스용 Skype 온-프레미스에 있고 Enterprise Voice를 사용 하는 경우 항상 비즈니스용 Skype에서 PSTN 통화가 시작 되 고 수신 됩니다.<li>사용자가 비즈니스용 Skype Online에 있고 Microsoft 전화 시스템을 사용 하는 경우, 사용자는 항상 비즈니스용 Skype에서 PSTN 통화를 시작 하 고 받습니다.<ul><li>이 작업은 사용자에 게 Microsoft 호출 계획이 있는지 여부에 관계 없이 또는 비즈니스용 skype 클라우드 커넥터 에디션을 통해 PSTN 네트워크에 연결 하거나 비즈니스용 Skype 서버 (하이브리드 voice)의 온-프레미스 배포를 통해 수행 됩니다.<li>**참고: Microsoft 팀 전화 시스템 다이렉트 라우팅은 군도 모드에서 지원 되지 않습니다.**</ul></ul><li>비즈니스용 Skype에서 Microsoft 통화 대기열 및 자동 전화 교환 전화를 받습니다.<li>팀 또는 비즈니스용 Skype에서 모임을 예약할 수 있습니다 (기본적으로 두 플러그 인이 표시 됨).<li>비즈니스용 Skype 또는 팀 모임에 참가할 수 있습니다. 모임이 해당 클라이언트에 열립니다.</ul>|
|**SfBOnly**|사용자가 비즈니스용 Skype만 실행 합니다. 사용자:</br><ul><li>비즈니스용 Skype 에서만 채팅 및 통화를 시작할 수 있습니다.<li>개시자가 비즈니스용 Skype를 사용 하는 팀 사용자가 아닌 경우, 시작 위치에 관계 없이 비즈니스용 Skype 클라이언트에서 채팅/통화를 받습니다. *비즈니스용 skype 모임만 예약할 수 있지만 비즈니스용 skype 또는 팀 모임에 참가할 수 있습니다. <li> </br> *온-프레미스 사용자와의 아일랜드 모드는 SfBOnly 모드의 다른 사용자와 함께 사용 하지 않는 것이 좋습니다. 비즈니스용 Skype를 사용 하는 팀 사용자가 SfBOnly 사용자에 게 전화를 걸거나 채팅을 시작 하는 경우 SfBOnly 사용자에 게 연결할 수 없으며 부재 중 채팅/통화 이메일이 수신 됩니다. *|
|**SfBWithTeamsCollab**|사용자가 비즈니스용 Skype와 팀을 함께 실행 합니다. 사용자:</br><ul><li>SfBOnly 모드에서 사용자의 기능을 사용 합니다.<li>팀에 그룹 공동 작업 (채널)만 사용 하도록 설정 되어 있습니다. 채팅/통화/모임 예약을 사용할 수 없습니다.</ul>|
|**SfBWithTeamsCollab</br>andmeetings**|사용자가 비즈니스용 Skype와 팀을 함께 실행 합니다. 사용자:<ul><li>SfBOnly 모드에서 사용자의 채팅 및 통화 기능을 사용 합니다.<li>그룹 공동 작업에 사용할 수 있는 팀 (채널 대화 포함)이 있습니다. 채팅 및 통화는 사용할 수 없습니다.<li>팀 모임만 예약할 수 있지만 비즈니스용 Skype 또는 팀 모임에 참가할 수 있습니다.</ul>|
|**TeamsOnly**</br>(SfB Online home 필요)|사용자가 팀만 실행 합니다. 사용자:<ul><li>시작 위치에 관계 없이 팀 클라이언트의 모든 채팅 및 통화를 받습니다.<li>팀에서 채팅 및 통화를 시작할 수 있습니다.<li>팀 에서만 모임을 예약할 수 있지만 비즈니스용 Skype 또는 팀 모임에 참가할 수 있습니다.<li>비즈니스용 Skype IP 전화를 계속 사용할 수 있습니다.<br><br>*팀 채택이 포화 상태 (예: 모든 아일랜드 모드)는 팀 및 비즈니스용 Skype 클라이언트를 적극적으로 사용 하 고 모니터링 하는 등의 다른 사용자와 아일랜드 모드를 함께 사용 하는 것이 좋습니다. TeamsOnly만이 통화를 시작 하거나 아일랜드 사용자에 게 채팅할 경우 해당 통화 또는 채팅은 군도 사용자의 팀 클라이언트에 배치 됩니다. 아일랜드 사용자가 팀을 사용 하거나 모니터링 하지 않으면 해당 사용자가 오프 라인으로 표시 되며 TeamsOnly 사용자만 연결할 수 없게 됩니다.*</ul> |
|||




## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype와 공존](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[팀 클라이언트 환경 및 공존 모드 준수](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
