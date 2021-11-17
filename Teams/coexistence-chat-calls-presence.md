---
title: 비즈니스용 Skype와 동시 사용
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: 라우팅 매개 변수를 Teams & 비즈니스용 Skype, 채팅 & 통화 라우팅, 기존 스레드에서 & 채팅, 현재 상태 & 공존 동작.
ms.openlocfilehash: 5c32e99ad7cd74966cc7d8f22bd19a2520249b85
ms.sourcegitcommit: a5b80ad33b4ee9505ea2be1a37f5ec2d8bf5ba76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61042369"
---
# <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

클라이언트와 비즈니스용 Skype Teams 상호운용성은 공존 모드에 의해 제어됩니다. 자세한 내용은 와 함께 Teams 조직에 대한 마이그레이션 및 상호 [비즈니스용 Skype.](migration-interop-guidance-for-teams-with-skype.md) 2021년 7월 31일 비즈니스용 Skype 온라인이 사용 중지된 후 클라우드에 있는 사용자는 항상 TeamsOnly 사용자입니다. TeamsOnly 외의 공존 모드를 온라인 사용자에게 더 이상 할당할 수 없습니다. TeamsOnly가 아니라 공존 모드는 온-프레미스 배포 또는 Lync Server 2013의 온-프레미스 비즈니스용 Skype 서버 관련이 있습니다. 이 문서에서는 "비즈니스용 Skype 서버"에 대한 모든 참조가 Lync Server 2013에도 적용됩니다.


## <a name="determining-a-users-coexistence-mode"></a>사용자의 공존 모드 결정
모든 프레미스 배포가 없는 조직의 모든 비즈니스용 Skype 서버 TeamsOnly 모드입니다. 테넌트의 유효 모드도 TeamsOnly입니다. 이 속성은 PowerShell을 사용하여 테넌트 또는 사용자에 있는 TeamsUpgradeEffectiveMode 속성을 Teams 확인할 수 있습니다.   2021년 7월 31일 비즈니스용 Skype Online을 사용 중지하기 전에 조직은 사용자 또는 테넌트에 대한 공존 모드를 변경할 수 있습니다. 이는 테넌트 전체의 TeamsOnly 모드가 비즈니스용 Skype 서버 배포된 조직을 제외하고는 더 이상 사용할 수 없습니다. TeamsUpgradePolicyIsReadOnly = 사용자 또는 테넌트에서 "ModeAndNotifications"인 경우 공존 모드를 더 이상 변경할 수 없음을 확인할 수 있습니다.  (TeamsUpgradePolicyIsReadOnly는 모든 사용자의 테넌트 값과 동일한 값을 하게 됩니다.)  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

프레미스에 대한 프레미스 배포를 비즈니스용 Skype 서버 TeamsUpgradePolicy에 대한 테넌트 전역 정책은 *TeamsOnly가* 다른 모드를 사용할 수 있습니다. 허용되는 모드는 *SfBOnly,* *SfBWithTeamsCollab* 및 *SfBWithTeamsCollabAndMeetings입니다.* 또한 사용자는 테넌트 전역 정책을 능가하는 TeamsUpgradePolicy 인스턴스를 직접 할당할 수도 있습니다.  클라우드에 홈이 있는 사용자는 TeamsOnly이 되어야 합니다.온-프레미스에 홈이 있는 사용자는 TeamsOnly가 다른 모드가 되어야 합니다.  사용자가 TeamsUpgradePolicy의 인스턴스를 할당하지 않은 경우 사용자는 테넌트 전역 정책에서 값을 수신합니다. 

## <a name="routing-parameters"></a>라우팅 매개 변수

받는 사람의 공존 모드는 테넌트 내 및 페더리드 테넌트에서 채팅, 호출 및 현재 상태의 동작을 결정합니다. 보낸 사람이 새 대화 스레드를 Teams 라우팅 결정을 내릴 수 있습니다. 대화 스레드를 만들면 해당 라우팅은 변경되지 않습니다. 스레드를 만들 때 결정된 라우팅 메서드가 유지됩니다.

스레드 라우팅 메서드는:

- *테넌트* 내 Teams Teams 네이티브
- *테넌트* 내 Teams 비즈니스용 Skype interop
- *두 사용자가* TeamsOnly 모드가 있는 경우 테넌트에서 페더리된 대화에 대해 네이티브 페더러드됩니다. 
- *테넌트* 간에 페더리된 대화를 위해 페더러드된 interop은 비즈니스용 Skype Teams.

> [!NOTE]
> - 동일한 테넌트 또는 페더리드 시나리오에서 네이티브 대화는 수신기와 보낸 사람 모두 TeamsOnly 모드가 있는 경우 발생합니다. 대화는 모든 풍부한 메시징 및 호출 기능을 포함하는 네이티브 채팅 환경입니다. 자세한 내용은 의 [외부(페더리화)](native-chat-for-external-users.md)사용자에 대한 네이티브 채팅 환경을 Teams. 
> - 대화 참가자 중 하나에 TeamsOnly 모드가 없는 경우 대화는 텍스트 전용 메시지와 상호 연결 환경입니다.
> - 다중 테넌트 클라우드 및 특수 클라우드 환경(예: 정부 클라우드)의 TeamsOnly 사용자 간에 페더리된 통신이 상호 페더리된 채팅으로 표시됩니다.


새 대화를 만들 때 스레드가 라우팅되는 방법을 결정하는 요소는 다음입니다.

- 받는 사람의 공존 모드
- 보낸 사람이 사용하는 클라이언트
- 대화가 테넌트 내인지 페더리드인지 여부
- 대화가 가능한지 여부입니다. 사용자에게 비즈니스용 Skype 있는 계정이 있는 경우 해당 사용자는 테넌트 내 Teams 페더니게이트에 대해 Teams 클라이언트를 사용할 수 없습니다. 해당 사용자는 상호 비즈니스용 Skype 페더리에 대해 비즈니스용 Skype 클라이언트만 사용할 수 있습니다. 통신을 Teams Teams 항상 테넌트에서 통신할 수 있습니다.

## <a name="chat-and-call-routing"></a>채팅 및 통화 라우팅
아래 표에는 발신자(가장 왼쪽 세 개 열)에서 호출을 받을 클라이언트가 표시됩니다. 호출을 수신하는 cient는 발신자 모드, 선택한 클라이언트 및 비즈니스용 Skype 계정이 홈되는 위치(온-프레미스 또는 온라인)에 따라 결정됩니다.

다음 표에서 다음을 수행합니다.

- **비즈니스용 Skype** _ 은 _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings* 중 어느 것이든 표시됩니다.
- *이탈 텍스트는* 상호 대화를 강조 표시합니다.
- **불가능은** 채팅 또는 통화가 불가능한 상황을 나타 내는 것입니다. 이러한 경우 대신 비즈니스용 Skype 를 사용해야 합니다. 이는 Microsoft의 프레미스 및 하이브리드 고객에 대한 지침이 아일랜드(일반적으로 SfBWithTeamsCollab)가 아니라 다른 모드를 사용하여 업그레이드 여정의 시작점으로 Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 테넌트 내 라우팅

아래 표는 테넌트 내 채팅 및 통화의 라우팅을 캡처하며, 기존 스레드에서 시작되지 않은 새 통화 또는 채팅에 유효합니다. 왼쪽에 있는 사용자가 시작한 경우 오른쪽의 테넌트 받는 사람 사용자에게 새 호출 또는 채팅을 받을 클라이언트를 설명합니다.  TeamsOnly 사용자에게 보낸 메시지는 항상 해당 메시지로 Teams. 사용자가 비즈니스용 Skype 보낸 메시지는 항상 비즈니스용 Skype. Islands 사용자에게 보낸 메시지는 항상 전송된 동일한 클라이언트로 라우팅됩니다.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>표 1a: 테넌트 내 새 채팅 또는 TeamsOnly 모드 받는 사람에게 라우팅 호출

<br>

|<br><br>모드|발신자<br><br>클라이언트|<br><br>비즈니스용 Skype &nbsp; 홈|<br><br>Route->|TeamsOnly 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|Teams|
|아일랜드|Teams <br> 비즈니스용 Skype| On-Premises <br> On-Premises|&boxv;<br>&boxv;|Teams <br> *Teams*|
|비즈니스용 Skype | 비즈니스용 Skype | On-Premises|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>표 1b: 테넌트 내 새 채팅 또는 섬 모드 받는 사람에게 라우팅 호출

<br>

|<br><br>모드|발신자<br><br>클라이언트|<br><br>비즈니스용 Skype &nbsp; 홈|<br><br>Route->|제도 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|Teams|
|아일랜드| Teams <br> 비즈니스용 Skype|On-Premises<br>On-Premises|&boxv;<br>&boxv;| Teams <br> 비즈니스용 Skype|
|비즈니스용 Skype |비즈니스용 Skype | On-Premises|&boxv;| 비즈니스용 Skype|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>표 1c: 테넌트 내 새 채팅 또는 수신자에 대한 라우팅을 비즈니스용 Skype 모드

<br>

|<br><br>모드|발신자<br><br>클라이언트|<br><br>비즈니스용 Skype &nbsp; 홈|<br><br>Route->|비즈니스용 Skype 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|*비즈니스용 Skype*|
|아일랜드|Teams <br> 비즈니스용 Skype| On-Premises <br> On-Premises|&boxv;<br>&boxv;| **가능하지 않습니다.** <br> 비즈니스용 Skype|
|비즈니스용 Skype | 비즈니스용 Skype| On-Premises|&boxv;| 비즈니스용 Skype|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 페더리된 라우팅

아래 표는 페더링된 통화 및 채팅의 라우팅을 캡처하며 새 통화 또는 채팅에 유효합니다. 왼쪽에 있는 사용자가 시작한 경우 오른쪽의 페더리드 대상 사용자에게 새 호출 또는 채팅을 받을 클라이언트를 설명합니다. 요약하면 위에서 설명한 대로 대화가 가능한 경우 TeamsOnly 사용자에게 보낸 메시지는 항상 Teams 있습니다. 비즈니스용 Skype 모드로 전송된 메시지는 항상 비즈니스용 Skype, Islands 사용자에게 전송된 메시지는 항상 비즈니스용 Skype 클라이언트에 관계없이 항상 비즈니스용 Skype 있습니다. 

페더링된 채팅 및 통화에 대한 라우팅은 아일랜드 사용자가 항상 페더리드 통신을 받게 되는 테넌트 내 라우팅과는 비즈니스용 Skype. 페더러드 파트너가 아직 페더러를 사용하지 않을 수 Teams. 모든 비즈니스용 Skype 모드 레시피에 대한 라우팅은 메시지를 항상 수신하도록 보장합니다.  Teams 받는 사람이 메시지를 사용하지 않는 경우 통신이 누락될 수 Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>표 2a: TeamsOnly 모드 받는 사람에게 새 채팅 또는 통화 라우팅 페더링

<br>

|<br><br>모드|발신자<br><br>클라이언트|<br><br>비즈니스용 Skype 홈|<br><br>Route->|TeamsOnly 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|Teams|
|아일랜드|Teams <br> 비즈니스용 Skype|On-Premises <br> On-Premises|&boxv;<br>&boxv;|**가능하지 않습니다.** <br> *Teams*|
|비즈니스용 Skype |비즈니스용 Skype|On-Premises|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>표 2b: 섬 받는 사람에게 새 채팅 또는 통화 라우팅 페더링

<br>

|<br><br>모드|발신자<br><br>클라이언트|<br><br>비즈니스용 Skype 홈|<br><br>Route->|제도 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|*비즈니스용 Skype*|
|아일랜드|Teams <br> 비즈니스용 Skype| On-Premises <br> On-Premises|&boxv;<br>&boxv;| **가능하지 않습니다.** <br> 비즈니스용 Skype|
|비즈니스용 Skype |비즈니스용 Skype| On-Premises|&boxv;| 비즈니스용 Skype|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>표 2c: 페더링된 새 채팅 또는 수신자에 대한 비즈니스용 Skype 모드

<br>

|<br><br>모드|발신자<br><br>클라이언트|<br><br>비즈니스용 Skype 홈|<br><br>Route->|비즈니스용 Skype 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|*비즈니스용 Skype*|
|아일랜드|Teams <br> 비즈니스용 Skype| On-Premises <br> On-Premises|&boxv;<br>&boxv;|**가능하지 않습니다.** <br> 비즈니스용 Skype|
|비즈니스용 Skype |비즈니스용 Skype|On-Premises|&boxv;<br>&boxv;|비즈니스용 Skype|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>기존 스레드에서 채팅 및 호출

### <a name="from-teams"></a>시작 Teams

기존 대화 스레드에서 시작된 호출 또는 채팅은 Teams 스레드와 동일한 방식으로 라우팅됩니다. 기존 스레드가 네이티브 스레드인 Teams(예: Teams)인 경우 해당 스레드의 추가 채팅 메시지와 호출이 Teams. 인터팝 스레드인 경우(예: 비즈니스용 Skype 라우팅) 추가 채팅 메시지와 통화가 비즈니스용 Skype(라우팅 옵션을 사용할 수 있는 경우)로 이동됩니다.

> [!NOTE]
> 스레드가 이후로 업그레이드된 사용자에 대한 Teams 스레드인 경우와 같이 기존 스레드가 더 이상 라우팅할 수 Teams. 스레드가 인터프 스레드로 만들어지기 때문에 스레드는 비즈니스용 Skype 라우팅하지만 해당 사용자는 더 이상 채팅 및 비즈니스용 Skype 사용할 수 없습니다. 이 경우 스레드를 사용하지 않도록 설정하고 추가 통신을 허용하지 않습니다.

### <a name="from-skype-for-business"></a>비즈니스용 Skype

비즈니스용 Skype 스레드는 10분 SIP 세션 시간 초과로 유지되지 않습니다. SIP 세션이 만료하기 비즈니스용 Skype 기존 스레드의 채팅 및 호출은 스레드와 동일한 방식으로 라우팅됩니다. SIP 세션 시간 제한을 초과하는 비즈니스용 Skype 기존 스레드의 호출 및 채팅은 원래 스레드가 다른 쪽에서 온 클라이언트에 관계 없이 비즈니스용 Skype 해당 원격 파티의 경로로 라우팅됩니다.

## <a name="presence"></a>현재 상태

일부 사용자가 Teams 클라이언트를 사용하고 있는 비즈니스용 Skype 클라이언트를 사용하는 경우 이러한 사용자 중 일부가 두 클라이언트를 사용할 수 있습니다. 현재 상태는 사용자의 공존 모드를 기반으로 게시됩니다. 예를 들어, 발신자 채팅 또는 통화가 대상의 비즈니스용 Skype 클라이언트에 착륙해야 하는 경우 비즈니스용 Skype 클라이언트의 현재 상태입니다. 대상의 클라이언트에 Teams 표시해야 하는 Teams 클라이언트의 현재 상태입니다.

아래에 설명된 바와 같이 현재 상태는 사용자의 공존 모드를 기반으로 공유됩니다.

- 사용자가 TeamsOnly 모드인 경우 다른 사용자(Teams 또는 비즈니스용 Skype)가 TeamsOnly 사용자의 현재 Teams 표시됩니다.
- 사용자가 모든 비즈니스용 Skype(SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings)에 있는 경우 다른 사용자(Teams 또는 비즈니스용 Skype)에 비즈니스용 Skype 사용자의 현재 비즈니스용 Skype 표시됩니다.
- 사용자가 섬 모드에 있는 경우 Teams 현재 상태 및 비즈니스용 Skype 독립적(값은 일치하지 않습니다)을 표시하며, 다른 사용자는 동일한 테넌트에 있는지, 페더링된 테넌트에 있는지, 어떤 클라이언트에서 사용하는 클라이언트에 따라 섬 사용자의 존재 중 하나 또는 다른 존재를 볼 수 있습니다.
  - Teams 동일한 테넌트 내의 다른 사용자는 Islands 사용자의 현재 Teams 표시됩니다. 위의 테넌트 내 라우팅 테이블과 정렬됩니다.
  - Teams 테넌트의 다른 사용자는 Islands 사용자의 현재 비즈니스용 Skype 표시됩니다. 위의 페더리드 라우팅 테이블에 정렬됩니다.
  - 비즈니스용 Skype 다른 사용자는 Islands 사용자의 현재 비즈니스용 Skype(테넌트 및 페더리드 모두)를 볼 수 있습니다. 위의 라우팅 테이블에 정렬됩니다.

### <a name="in-tenant-presence"></a>테넌트 내 현재 상태

TeamsOnly 사용자에게 전송된 메시지는 항상 Teams. 대화가 가능한 비즈니스용 Skype 모드로 전송된 메시지는 항상 비즈니스용 Skype 대화가 가능한 경우 항상 해당 모드로 전송됩니다. Islands 사용자에게 전송된 메시지는 항상 원래 클라이언트에 연결됩니다.

이 표에서는 Publisher 모드와 Watcher의 클라이언트(새 스레드의 경우)에 따라 Watcher에서 볼 Publisher 존재를 설명합니다.

#### <a name="table-3-in-tenant-presence-new-thread"></a>표 3: 테넌트 내 현재 상태(새 스레드)

<br>

|감시자<br><br>클라이언트|<br><br>Route->|<br><br>아일랜드|Publisher<br><br>비즈니스용 Skype|<br>Teams 전용|
|---|:---:|---|---|---|
|비즈니스용 Skype|&boxv;|비즈니스용 Skype|비즈니스용 Skype|Teams|
|Teams|&boxv;|Teams|비즈니스용 Skype|Teams|
|||||

### <a name="federated-presence"></a>페더리드 현재 상태

페더리드 상태는 표 2에 표시된 페더리드 도달성을 기반으로 합니다.  아래 표에서는 Publisher 모드와 Watcher의 클라이언트(새 스레드의 경우)에 따라 Watcher에서 볼 수 있는 Publisher 존재를 설명합니다. 실제로 Watcher의 클라이언트는 이 단계에서 페더리에 차이가 없습니다.

#### <a name="table-4-federated-presence-new-thread"></a>표 4: 페더리드된 현재 상태(새 스레드)

<br>

|감시자<br><br>클라이언트|<br><br>Route->|<br><br>아일랜드|Publisher<br><br>비즈니스용 Skype|<br><br>Teams 전용|
|---|:---:|---|---|---|
|비즈니스용 Skype|&boxv;|비즈니스용 Skype|비즈니스용 Skype|Teams|
|Teams|&boxv;|비즈니스용 Skype|비즈니스용 Skype|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>기존 스레드의 현재 상태

기존 스레드에서 현재 상태 및 도달성을 정렬하기 위해 스레드에 노출된 대상의 현재 상태는 스레드의 라우팅에 맞춰야 합니다. 라우팅이 가능하다고 생각하면 됩니다.  특히 이전에 영구 상호프 대화 스레드가 있는 받는 사람이 Teams 스레드가 더 이상 정확한 존재를 반영하지 않고 라우팅할 수 없습니다. 새 스레드를 시작해야 합니다.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>21Vianet에서 운영하는 Office 365 페더전 및 인터팝

다중 테넌트 Office 365 및 Office 365 21Vianet에서 작동하는 페더리화 및 Office 365 전용 모드로 Teams 지원됩니다. 이러한 시나리오에서 비즈니스용 Skype 21Vianet에서 Office 365 온라인 사용자만 채팅 및 통화를 통해 다중 테넌트 Teams 사용자와 통신할 수 Office 365 수 있습니다. 다음 표에서는 이 구성에서 지원되는 시나리오를 보여줍니다.
 
|시나리오|원본|받는 사람|지원되는가요?|
|---|---|---|---|
|현재 상태|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예<br>예|
|채팅|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예(1:1만 해당)<br>예(1:1만 해당)|
|오디오 통화|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예(1:1만 해당)<br>예(1:1만 해당)|
|화상 통화|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예(1:1만 해당)<br>예(1:1만 해당)|
|화면 공유|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams |예(승격된 모임을 통해 Teams)<br>예(승격된 모임을 통해 비즈니스용 Skype)|
|||||


## <a name="related-links"></a>관련 링크
[조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[비디오: 공존성 및 상호 운영성 관리 비즈니스용 Skype 및 Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
