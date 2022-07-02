---
title: Teams 클라이언트 환경 및 공존 모드 준수
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Teams 클라이언트 환경 및 공존 모드 준수에 대해 알아봅니다(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605837"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 클라이언트 환경 및 공존 모드 준수

<a name="about-upgrade-basic"></a>

비즈니스용 Skype 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)의 목적은 조직이 비즈니스용 Skype Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공하는 것입니다.  Teams로 이동하는 조직의 경우 **Teams 전용** 모드는 각 사용자의 최종 대상이지만 모든 사용자에게 **Teams만** (또는 다른 모드)을 동시에 할당할 필요는 없습니다.  TeamsOnly 모드에 도달하기 전에 조직에서는 비즈니스용 Skype 공존 모드를 사용하여 **Teams 전용** 사용자와 아직 연결되지 않은 사용자 간에 예측 가능한 통신을 보장할 수 있습니다. 

사용자가 비즈니스용 Skype 모드에 있으면 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자의 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있을 때 Teams 클라이언트의 통화 및 채팅 기능이 비활성화됩니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있을 때 Teams에서 모임 일정을 명시적으로 사용하지 않도록 설정하고 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있을 때 명시적으로 사용하도록 설정됩니다.

현재 상태는 채팅 및 통화를 통한 연결 가능성을 나타내기 때문에 채팅 및 통화가 비활성화되면 Teams의 자체 존재(즉, 사용자의 그림에서 Teams 클라이언트에 자신의 존재 표시)도 숨겨집니다. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>모드에 따라 Teams 클라이언트에서 사용 가능한 기능이 변경되는 방식

Teams에서 사용할 수 있는 기능은 TeamsUpgradePolicy에서 설정한 대로 사용자의 공존 모드에 따라 달라집니다. 다음 표에서는 동작을 요약합니다.

|사용자의 유효 모드|Teams 클라이언트의 환경|
|---|---|
|모든 비즈니스용 Skype 모드|통화, 채팅 및 자체 프레즌스 사용이 비활성화됩니다.|
|SfBWithTeamsCollabAndMeetings|모임 일정을 사용할 수 있습니다.|
|SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup>|모임 일정을 사용할 수 없음|
|||

다음 스크린샷은 **Teams 전용** 모드 또는 **아일랜드** 모드와 다른 모든 모드 간의 차이점을 보여 줍니다. 채팅 및 통화 아이콘은 기본적으로 **Teams 전용** 또는 **아일랜드** 모드(왼쪽 스크린샷)에서 사용할 수 있지만 다른 모드에서는 사용할 수 없습니다(오른쪽 스크린샷).

![Teams 모드를 나란히 비교합니다.](media/teams-mode-comparison.png)

또한 여기에 표시된 것처럼 다른 모드에서는 자체 프레즌스를 사용할 수 없습니다.

![모임 우선의 자체 현재 상태 스크린샷.](media/meetings-first-no-self-presence-general.png)
 
**참고:**
 <sup>1</sup> 현재 SfBwithTeamsCollab 및 SfBOnly는 동일하게 동작하지만 SfBOnly 모드에서는 Teams에서 채널 및 파일 기능도 사용하지 않도록 설정해야 합니다. 그 동안 앱 사용 권한 정책을 사용하여 채널을 숨길 수 있습니다.


## <a name="impact-of-mode-on-other-policy-settings"></a>모드가 다른 정책 설정에 미치는 영향
위에서 설명한 대로 사용자의 공존 모드는 사용자의 Teams 클라이언트에서 사용할 수 있는 기능에 영향을  미칩니다. 즉, 모드 값이 모드에 따라 다른 정책 설정의 값보다 우선적으로 적용됩니다. 특히 공존 모드는 다음 정책 설정이 적용되는지 여부에 영향을 줍니다.

|**양식(앱)**|**Policy.Setting**|
|---|---|
|채팅|TeamsMessagingPolicy.AllowUserChat|
|통화|TeamsCallingPolicy.AllowPrivateCalling|
|모임 예약|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

관리자는 공존 모드를 사용할 때 이러한 정책 *설정을 명시적으로 설정할* 필요는 없지만, 이러한 설정이 지정된 모드에 대해 다음과 같이 효과적으로 동작한다는 것을 이해하는 것이 중요합니다. 

|모드|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 또는 Islands|사용|사용|사용|사용|
|SfBWithTeamsCollabAndMeetings|사용 안 함|사용 안 함|사용|사용|
|SfBWithTeamsCollab 또는 SfBOnly|사용 안 함|사용 안 함|사용 안 함|사용 안 함|
||||||

PowerShell `Grant-CsTeamsUpgradePolicy` 을 사용하는 경우 cmdlet은 TeamsMessagingPolicy, TeamsCallingPolicy 및 TeamsMeetingPolicy에서 해당 설정의 구성을 확인하여 해당 설정이 TeamsUpgradePolicy로 대체되는지 확인하고, 그렇다면 PowerShell에 정보 메시지가 제공됩니다.  위에서 설명한 것처럼 더 이상 이러한 다른 정책 설정을 설정할 필요가 없습니다. 다음은 PowerShell 경고의 예입니다.

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>관련 항목

[Teams를 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침과 비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)