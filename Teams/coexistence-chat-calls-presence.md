---
title: 비즈니스용 Skype와 동시 사용
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 라우팅 매개 변수, 채팅 & 통화 라우팅, 기존 스레드의 채팅 & 통화, 현재 상태 & 등 Teams & 비즈니스용 Skype 간의 공존 동작입니다.
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562397"
---
# <a name="coexistence-with-skype-for-business"></a>비즈니스용 Skype와 동시 사용

비즈니스용 Skype 및 Teams 클라이언트 간의 공존 및 상호 운용성은 공존 모드에 의해 제어됩니다. 자세한 내용은 [비즈니스용 Skype 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 운용성 지침을](migration-interop-guidance-for-teams-with-skype.md) 참조하세요. 2021년 7월 31일에 비즈니스용 Skype Online이 사용 중지된 후 클라우드에 있는 사용자는 항상 TeamsOnly 사용자입니다. 더 이상 TeamsOnly 이외의 공존 모드를 온라인 사용자에게 할당할 수 없습니다. TeamsOnly 이외의 공존 모드는 비즈니스용 Skype 서버 또는 Lync Server 2013의 온-프레미스 배포를 사용하는 조직에만 관련이 있습니다. 이 문서에서는 "비즈니스용 Skype 서버"에 대한 참조가 Lync Server 2013에도 적용됩니다.


## <a name="determining-a-users-coexistence-mode"></a>사용자의 공존 모드 결정
비즈니스용 Skype 서버 온-프레미스 배포가 없는 조직의 모든 사용자는 TeamsOnly 모드이며 테넌트의 유효 모드도 TeamsOnly입니다. 이는 테넌트 또는 Teams PowerShell을 사용하는 사용자의 TeamsUpgradeEffectiveMode 속성을 확인하여 확인할 수 있습니다.   2021년 7월 31일에 비즈니스용 Skype Online이 사용 중지되기 전에 조직은 사용자 또는 테넌트의 공존 모드를 변경할 수 있었습니다. 테넌트 차원의 TeamsOnly 모드가 없어야 하는 비즈니스용 Skype 서버 온-프레미스 배포를 사용하는 조직을 제외하고는 더 이상 불가능합니다. 사용자 또는 테넌트에서 TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications"인 경우 공존 모드를 더 이상 변경할 수 없음을 확인할 수 있습니다.  (모든 사용자의 TeamsUpgradePolicyIsReadOnly는 테넌트의 값과 동일한 값을 갖습니다.)  


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

온-프레미스 배포가 비즈니스용 Skype 서버 조직에서 TeamsUpgradePolicy에 대한 테넌트 전역 정책은 *TeamsOnly 이외의* 모드를 가질 수 있습니다. 허용되는 모드는 *SfBOnly*, *SfBWithTeamsCollab* 및 *SfBWithTeamsCollabAndMeetings* 입니다. 테넌트 전역 정책을 대체하는 TeamsUpgradePolicy 인스턴스를 사용자에게 직접 할당할 수도 있습니다.  클라우드에 있는 사용자는 TeamsOnly여야 하며 온-프레미스에 있는 사용자는 TeamsOnly 이외의 모드여야 합니다.  사용자에게 TeamsUpgradePolicy 인스턴스가 할당되지 않은 경우 사용자는 테넌트 전역 정책에서 값을 받습니다. 

## <a name="routing-parameters"></a>라우팅 매개 변수

받는 사람의 공존 모드는 테넌트 내 및 페더레이션된 테넌트 간에 채팅, 통화 및 현재 상태의 동작을 결정합니다. 발신자가 Teams를 사용하는 경우 새 대화 스레드를 만들 때 라우팅 결정이 내려집니다. 대화 스레드가 만들어지면 해당 라우팅은 변경되지 않으며 스레드를 만들 때 결정된 라우팅 메서드를 유지합니다.

스레드 라우팅 방법은 다음과 같습니다.

- 테넌트 내 Teams 대화에 대한 *네이티브*
- 테넌트에서 대화를 비즈니스용 Skype Teams용 *interop*
- 두 사용자 모두 TeamsOnly 모드가 있는 경우 테넌트 간에 페더레이션된 대화를 위해 네이 *티브 페더레이션* 됩니다. 
- interop은 비즈니스용 Skype Teams 간의 interop에 의존하는 테넌트 간에 페더레이션된 대화를 위해 *페더레이션* 됩니다.

> [!NOTE]
> - 동일한 테넌트 또는 페더레이션된 시나리오에서 네이티브 대화는 수신자와 보낸 사람 모두 TeamsOnly 모드가 있을 때 발생합니다. 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 네이티브 채팅 환경이 됩니다. 자세한 내용은 [Teams의 외부(페더레이션) 사용자에 대한 네이티브 채팅 환경을](native-chat-for-external-users.md) 읽어보세요. 
> - 대화 참가자 중 하나에 TeamsOnly 모드가 없는 경우 대화는 텍스트 전용 메시지를 사용하는 interop 환경입니다.
> - 다중 테넌트 클라우드의 TeamsOnly 사용자와 특수 클라우드 환경(예: 정부 클라우드)의 페더레이션된 통신은 interop 페더레이션 채팅으로 표시됩니다.


새 대화를 만들 때 스레드가 라우팅되는 방식을 결정하는 요소는 다음과 같습니다.

- 받는 사람의 공존 모드
- 보낸 사람에서 사용하는 클라이언트
- 대화가 테넌트 내인지 아니면 페더레이션되었는지 여부
- 대화가 가능한지 여부입니다. 사용자에게 온-프레미스에 비즈니스용 Skype 계정이 있는 경우 해당 사용자는 테넌트 내 상호 운용성 또는 페더레이션을 위해 Teams 클라이언트를 사용할 수 없습니다. 해당 사용자는 상호 운용성 및 페더레이션을 위해 비즈니스용 Skype 클라이언트만 사용할 수 있습니다. Teams 간 통신은 항상 테넌트에서 가능합니다.

## <a name="chat-and-call-routing"></a>채팅 및 통화 라우팅
아래 표에서는 지정된 모드의 클라이언트가 발신자로부터 호출을 받을지 보여 줍니다(맨 왼쪽 열 3개). 호출을 받는 cient는 보낸 사람의 모드, 선택한 클라이언트 및 비즈니스용 Skype 계정이 있는 위치(온-프레미스 또는 온라인)에 따라 달라집니다.

다음 표에서 다음을 수행합니다.

- **비즈니스용 Skype** _는 _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings* 모드를 나타냅니다.
- *기울임꼴 텍스트* 는 interop 대화를 강조 표시합니다.
- **가능하지 않음** 은 채팅 또는 통화가 불가능한 상황을 나타냅니다. 이러한 경우 대신 비즈니스용 Skype 사용해야 합니다. 온-프레미스 및 하이브리드 고객에 대한 Microsoft의 규범적 지침이 Teams로의 업그레이드 여정의 시작점으로 Islands(일반적으로 SfBWithTeamsCollab) 이외의 모드를 사용하는 이유 중 하나입니다.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 테넌트 내 라우팅

아래 표는 테넌트 내 채팅 및 통화의 라우팅을 캡처하며 기존 스레드에서 시작되지 않은 새 통화 또는 채팅에 유효합니다. 왼쪽에 있는 사용자가 오른쪽에 있는 테넌트 내 받는 사람에게 새 통화 또는 채팅을 받을 클라이언트에 대해 설명합니다.  TeamsOnly 사용자에게 보낸 메시지는 항상 Teams로 라우팅됩니다. 비즈니스용 Skype 사용자에게 보낸 메시지는 항상 비즈니스용 Skype 라우팅됩니다. 아일랜드 사용자에게 전송된 메시지는 항상 전송된 동일한 클라이언트로 라우팅됩니다.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>표 1a: 테넌트 내 새 채팅 또는 TeamsOnly 모드 받는 사람에게 라우팅 호출

<br>

|<br><br>모드|보낸 사람<br><br>클라이언트|<br><br>&nbsp;비즈니스용 Skype|<br><br>경로-->|TeamsOnly 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|Teams|
|아일랜드|Teams <br> 비즈니스용 Skype| 온-프레미스 <br> 온-프레미스|&boxv;<br>&boxv;|Teams <br> *Teams*|
|비즈니스용 Skype | 비즈니스용 Skype | 온-프레미스|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>표 1b: 테넌트 내 새 채팅 또는 아일랜드 모드 수신자에게 라우팅 호출

<br>

|<br><br>모드|보낸 사람<br><br>클라이언트|<br><br>&nbsp;비즈니스용 Skype|<br><br>경로-->|아일랜드 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|Teams|
|아일랜드| Teams <br> 비즈니스용 Skype|온-프레미스<br>온-프레미스|&boxv;<br>&boxv;| Teams <br> 비즈니스용 Skype|
|비즈니스용 Skype |비즈니스용 Skype | 온-프레미스|&boxv;| 비즈니스용 Skype|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>표 1c: 테넌트 내 새 채팅 또는 비즈니스용 Skype 모드에서 받는 사람에게 라우팅 호출

<br>

|<br><br>모드|보낸 사람<br><br>클라이언트|<br><br>&nbsp;비즈니스용 Skype|<br><br>경로-->|비즈니스용 Skype 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|*비즈니스용 Skype*|
|아일랜드|Teams <br> 비즈니스용 Skype| 온-프레미스 <br> 온-프레미스|&boxv;<br>&boxv;| **불가능** <br> 비즈니스용 Skype|
|비즈니스용 Skype | 비즈니스용 Skype| 온-프레미스|&boxv;| 비즈니스용 Skype|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>새 채팅 또는 통화에 대한 페더레이션 라우팅

아래 표는 페더레이션된 통화 및 채팅의 라우팅을 캡처하며 새 통화 또는 채팅에 유효합니다. 왼쪽의 사용자가 오른쪽에 있는 페더레이션 대상 사용자에게 새 통화 또는 채팅을 받을 클라이언트를 설명합니다. 요약하면 위에서 설명한 대로 대화가 가능한 경우 TeamsOnly 사용자에게 전송된 메시지는 항상 Teams에 전달됩니다. 비즈니스용 Skype 모드로 전송된 메시지는 항상 비즈니스용 Skype. 아일랜드 사용자에게 전송된 메시지는 전송된 클라이언트에 관계없이 항상 비즈니스용 Skype 수신됩니다. 

페더레이션 채팅 및 통화에 대한 라우팅은 아일랜드 사용자가 항상 비즈니스용 Skype 페더레이션 통신을 수신한다는 점에서 테넌트 내 라우팅과 다릅니다. 페더레이션된 파트너가 아직 Teams를 사용하지 않을 수 있기 때문입니다. 모든 아일랜드 모드 recipeint에 대한 비즈니스용 Skype 라우팅하면 메시지가 항상 수신됩니다.  의도한 수신자가 Teams를 사용하지 않는 경우 Teams로 라우팅하면 통신이 누락될 수 있습니다. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>표 2a: TeamsOnly 모드 수신자에게 페더레이션된 새 채팅 또는 통화 라우팅

<br>

|<br><br>모드|보낸 사람<br><br>클라이언트|<br><br>비즈니스용 Skype 홈|<br><br>경로-->|TeamsOnly 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|Teams|
|아일랜드|Teams <br> 비즈니스용 Skype|온-프레미스 <br> 온-프레미스|&boxv;<br>&boxv;|**불가능** <br> *Teams*|
|비즈니스용 Skype |비즈니스용 Skype|온-프레미스|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>표 2b: 아일랜드 수신자에게 페더레이션된 새 채팅 또는 통화 라우팅

<br>

|<br><br>모드|보낸 사람<br><br>클라이언트|<br><br>비즈니스용 Skype 홈|<br><br>경로-->|아일랜드 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|*비즈니스용 Skype*|
|아일랜드|Teams <br> 비즈니스용 Skype| 온-프레미스 <br> 온-프레미스|&boxv;<br>&boxv;| **불가능** <br> 비즈니스용 Skype|
|비즈니스용 Skype |비즈니스용 Skype| 온-프레미스|&boxv;| 비즈니스용 Skype|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>표 2c: 비즈니스용 Skype 모드에서 받는 사람에게 페더레이션된 새 채팅 또는 통화 라우팅

<br>

|<br><br>모드|보낸 사람<br><br>클라이언트|<br><br>비즈니스용 Skype 홈|<br><br>경로-->|비즈니스용 Skype 받는 사람|
|---|---|---|:---:|---|
|TeamsOnly|Teams|온라인|&boxv;|*비즈니스용 Skype*|
|아일랜드|Teams <br> 비즈니스용 Skype| 온-프레미스 <br> 온-프레미스|&boxv;<br>&boxv;|**불가능** <br> 비즈니스용 Skype|
|비즈니스용 Skype |비즈니스용 Skype|온-프레미스|&boxv;<br>&boxv;|비즈니스용 Skype|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>기존 스레드의 채팅 및 호출

### <a name="from-teams"></a>Teams에서

Teams의 기존 대화 스레드에서 시작된 통화 또는 채팅은 해당 스레드와 동일한 방식으로 라우팅됩니다. Teams의 기존 스레드가 네이티브 스레드(예: Teams로 라우팅됨)인 경우 해당 스레드의 추가 채팅 메시지 및 통화가 Teams로 이동합니다. interop 스레드(즉, 비즈니스용 Skype 라우팅됨)인 경우 추가 채팅 메시지 및 통화가 비즈니스용 Skype 이동합니다(라우팅 옵션을 사용할 수 있다고 가정).

> [!NOTE]
> 스레드가 Teams로 업그레이드된 사용자에 대한 interop 스레드인 경우와 같이 Teams의 기존 스레드를 더 이상 라우팅할 수 없습니다. interop 스레드로 만들어졌으므로 스레드는 비즈니스용 Skype 라우팅되지만 해당 사용자는 더 이상 채팅 및 통화에 비즈니스용 Skype 사용할 수 없습니다. 이 경우 스레드는 비활성화되고 추가 통신을 허용하지 않습니다.

### <a name="from-skype-for-business"></a>비즈니스용 Skype

비즈니스용 Skype 스레드는 10분 SIP 세션 시간 제한을 초과하여 유지되지 않습니다. SIP 세션이 만료되기 전에 비즈니스용 Skype 기존 스레드의 채팅 및 호출은 스레드와 동일한 방식으로 라우팅됩니다. SIP 세션 시간 제한을 초과하여 비즈니스용 Skype 기존 스레드의 통화 및 채팅은 원래 스레드가 상대방 쪽에서 온 클라이언트에 관계없이 원격 당사자의 비즈니스용 Skype 라우팅됩니다.

## <a name="presence"></a>현재 상태

일부 사용자가 Teams 클라이언트를 사용하고 다른 사용자가 비즈니스용 Skype 클라이언트를 사용하는 경우 이러한 사용자 중 일부는 두 클라이언트를 모두 사용할 수 있습니다. 현재 상태는 사용자의 공존 모드에 따라 게시된다는 것을 이해하는 것이 중요합니다. 예를 들어, 발신자의 채팅 또는 호출이 대상의 비즈니스용 Skype 클라이언트에 도달해야 하는 경우 비즈니스용 Skype 클라이언트의 현재 상태는 발신자에게 표시되어야 합니다. 대상의 Teams 클라이언트에 도달해야 하는 경우 표시되어야 하는 것은 Teams 클라이언트의 존재입니다.

현재 상태는 아래 설명된 대로 사용자의 공존 모드에 따라 공유됩니다.

- 사용자가 TeamsOnly 모드에 있는 경우 다른 사용자(Teams 또는 비즈니스용 Skype)에는 TeamsOnly 사용자의 Teams 현재 상태가 표시됩니다.
- 사용자가 비즈니스용 Skype 모드(SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings)에 있는 경우 다른 사용자(Teams 또는 비즈니스용 Skype)에는 해당 비즈니스용 Skype 사용자의 비즈니스용 Skype 현재 상태가 표시됩니다.
- 사용자가 아일랜드 모드에 있는 경우 Teams의 현재 상태와 비즈니스용 Skype 현재 상태는 독립적이며(값이 일치하지 않아도 함) 다른 사용자는 동일한 테넌트에 있는지 또는 페더레이션된 테넌트에 있는지, 어떤 클라이언트를 사용하는지에 따라 한 명 또는 다른 아일랜드 사용자의 현재 상태를 볼 수 있습니다.
  - Teams에서 동일한 테넌트 내의 다른 모든 사용자는 Islands 사용자의 Teams 현재 상태를 볼 수 있습니다. 위의 테넌트 내 라우팅 테이블과 정렬됩니다.
  - Teams에서 페더레이션 테넌트의 다른 사용자는 Islands 사용자의 비즈니스용 Skype 현재 상태를 볼 수 있습니다. 이는 위의 페더레이션 라우팅 테이블과 일치합니다.
  - 비즈니스용 Skype 다른 모든 사용자는 Islands 사용자의 비즈니스용 Skype 현재 상태(테넌트 내 및 페더레이션됨)를 볼 수 있습니다. 이는 위의 라우팅 테이블과 일치합니다.

### <a name="in-tenant-presence"></a>테넌트 내 현재 상태

TeamsOnly 사용자에게 전송된 메시지는 항상 Teams에 표시됩니다. 위에서 설명한 대로 대화가 가능한 경우 비즈니스용 Skype 모드로 전송된 메시지는 항상 비즈니스용 Skype. 아일랜드 사용자에게 전송된 메시지는 항상 시작된 클라이언트에 착륙합니다.

이 표에서는 게시자 모드 및 Watcher의 클라이언트(새 스레드의 경우)에 따라 Watcher에서 볼 수 있는 게시자의 현재 상태를 설명합니다.

#### <a name="table-3-in-tenant-presence-new-thread"></a>표 3: 테넌트 내 현재 상태(새 스레드)

<br>

|감시자<br><br>클라이언트|<br><br>경로-->|<br><br>아일랜드|게시자<br><br>비즈니스용 Skype|<br>Teams만|
|---|:---:|---|---|---|
|비즈니스용 Skype|&boxv;|비즈니스용 Skype|비즈니스용 Skype|Teams|
|Teams|&boxv;|Teams|비즈니스용 Skype|Teams|
|||||

### <a name="federated-presence"></a>페더레이션된 현재 상태

페더레이션된 현재 상태는 표 2에 표시된 페더레이션된 연결 가능성을 기반으로 합니다.  아래 표에서는 게시자 모드 및 Watcher의 클라이언트(새 스레드의 경우)에 따라 Watcher에서 볼 수 있는 게시자의 현재 상태를 설명합니다. 실제로 Watcher의 클라이언트는 이 단계에서 페더레이션에 아무런 차이가 없습니다.

#### <a name="table-4-federated-presence-new-thread"></a>표 4: 페더레이션된 현재 상태(새 스레드)

<br>

|감시자<br><br>클라이언트|<br><br>경로-->|<br><br>아일랜드|게시자<br><br>비즈니스용 Skype|<br><br>Teams만|
|---|:---:|---|---|---|
|비즈니스용 Skype|&boxv;|비즈니스용 Skype|비즈니스용 Skype|Teams|
|Teams|&boxv;|비즈니스용 Skype|비즈니스용 Skype|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>기존 스레드의 현재 상태

기존 스레드에서 현재 상태 및 연결 가능성을 맞추기 위해 해당 스레드에 노출된 대상의 현재 상태는 라우팅이 가능하다고 가정하고 스레드의 라우팅에 맞춰야 합니다.  특히 이전에 영구 interop 대화 스레드가 있는 수신자가 Teams로 업그레이드된 경우 해당 스레드는 더 이상 정확한 현재 상태를 반영하지 않으며 더 이상 라우팅할 수 없습니다. 새 스레드를 시작해야 합니다.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>21Vianet에서 운영하는 Office 365 페더레이션 및 interop

다중 테넌트 Office 365 사용자가 Teams 전용 모드에 있는 경우 다중 테넌트 Office 365 및 21Vianet에서 운영하는 Office 365 간의 페더레이션 및 interop이 지원됩니다. 이러한 시나리오에서 21Vianet에서 운영하는 Office 365 비즈니스용 Skype Online 사용자는 채팅 및 통화를 통해 다중 테넌트 Office 365 Teams 전용 사용자와 통신할 수 있습니다. 다음 표에서는 이 구성에서 지원되는 시나리오를 보여 줍니다.
 
|시나리오|기원|받는 사람|지원?|
|---|---|---|---|
|현재 상태|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예<br>예|
|채팅|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예(1:1만 해당)<br>예(1:1만 해당)|
|오디오 통화|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예(1:1만 해당)<br>예(1:1만 해당)|
|화상 통화|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams|예(1:1만 해당)<br>예(1:1만 해당)|
|화면 공유|Teams <br> 비즈니스용 Skype <br> | 비즈니스용 Skype <br> Teams |예(승격된 Teams 모임을 통해)<br>예(승격된 비즈니스용 Skype 모임을 통해)|
|||||


## <a name="related-links"></a>관련 링크
[Teams를 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침과 비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)

[비디오: 비즈니스용 Skype Teams 간의 공존 및 상호 운용성 관리](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
