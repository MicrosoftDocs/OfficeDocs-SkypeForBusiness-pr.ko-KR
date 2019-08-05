---
title: 팀 클라이언트 환경 및 공존 모드 준수
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 팀 클라이언트 환경 및 comformance 공존 모드
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183926"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>팀 클라이언트 환경 및 공존 모드 준수

> [!NOTE]
> 이 페이지에서는 사용자가 비즈니스용 Skype 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 있는 경우 팀 클라이언트의 동작에서 최근에 발표 된 중요 한 변경 사항에 대해 설명 합니다.


공존 모드의 용도는 조직이 비즈니스용 Skype에서 팀으로 전환 하는 것 처럼 최종 사용자에 게 예측 가능한 간단한 환경을 제공 하는 것입니다.  팀으로 이동 하는 조직의 경우 모든 사용자에 게 동시에 Teamonly (또는 기타 모드)를 할당 해야 하는 것은 아니지만 TeamsOnly 모드는 각 사용자의 최종 대상입니다.  사용자가 팀의 유일한 모드에 도달 하기 전에, 조직에서 비즈니스용 Skype 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)를 사용 하 여 팀이 자신을 대상으로 하 고 아직 받지 않은 사용자 간에 예측 가능한 의사 소통을 보장할 수 있습니다. 

사용자가 비즈니스용 Skype 모드에 있는 경우 모든 수신 채팅 및 통화는 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 사용자가 비즈니스용 Skype 모드에 있는 경우 최종 사용자의 혼란을 방지 하 고 팀 클라이언트의 통화 및 채팅 기능을 사용할 수 없도록 설정 합니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있고 사용자가 SfBWithTeamsCollabAndMeetings 모드일 때 명시적으로 사용 하도록 설정 되어 있는 경우 팀에서 모임 예약을 명시적으로 사용할 수 없습니다.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>팀 클라이언트에서 사용 가능한 기능이 모드에 따라 변경 되는 방식
팀에서 사용할 수 있는 기능은 TeamsUpgradePolicy에서 설정한 사용자의 공존 모드에 따라 달라 집니다. 다음 표에서는 동작을 요약 하 여 설명 합니다.

|사용자의 유효 모드|팀 클라이언트의 환경|
|---|---|
|모든 비즈니스용 Skype 모드|통화 및 채팅을 사용할 수 없습니다.|
|SfBWithTeamsCollabAndMeetings|모임 예약을 사용할 수 있습니다.|
|SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup>|모임 예약을 사용할 수 없습니다.|
|||

다음 스크린샷은 팀 전용 또는 아일랜드 모드와 다른 모드의 차이를 보여 줍니다. 채팅 및 통화 아이콘은 팀 전용 또는 아일랜드 모드 (왼쪽 스크린샷)와 함께 사용할 수 있지만 다른 모드 (오른쪽 스크린샷)에는 제공 되지 않습니다.

![팀 모드의 병렬 비교](media/teams-mode-comparison.png)


 
**참고:**
<sup>1</sup> 이제 SfBwithTeamsCollab 및 SfBOnly는 동일 하 게 작동 하지만 SfBOnly 모드에서 팀의 채널과 Files 기능을 사용 하지 않도록 설정할 수 있습니다. 그러나 현재 팀에서이 기능을 사용 하지 않도록 설정할 수 있는 설정은 없습니다.


## <a name="impact-of-mode-on-other-policy-settings"></a>다른 정책 설정에 대 한 모드의 영향
위에서 설명한 대로 사용자의 공존 모드 영향에 따라 사용자의 팀 클라이언트에서 사용할 수 있는 기능이 결정 됩니다. 즉, mode에 따라 mode의 값이 다른 정책 설정의 값 보다 우선 될 수 있습니다. 특히 공존 모드는 다음 정책 설정이 허용 되는지 여부에 영향을 줍니다.

|**모달 (앱)**|**정책. 설정**|
|---|---|
|채트|TeamsMessagingPolicy. AllowUserChat|
|전화|TeamsCallingPolicy. AllowPrivateCalling|
|모임 예약|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

공동 존재 ** 모드를 사용 하는 경우 관리자는 이러한 정책 설정을 명시적으로 설정할 필요가 없지만, 이러한 설정은 지정 된 모드에서 다음과 같이 효과적으로 동작 한다는 것을 이해 하는 것이 중요 합니다. 

|모드|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 또는 군도|수|수|수|수|
|SfBWithTeamsCollabAndMeetings|비활성화|비활성화|수|수|
|SfBWithTeamsCollab 또는 SfBOnly|비활성화|비활성화|비활성화|비활성화|
||||||

PowerShell을 사용 하는 `Grant-CsTeamsUpgradePolicy` 경우 Cmdlet은 TeamsMessagingPolicy, Teamsmessagingpolicy 및 TeamsMeetingPolicy에서 해당 설정의 구성을 확인 하 여 해당 설정이 TeamsUpgradePolicy로 대체 되는지 여부를 결정 합니다. 알림 메시지는 PowerShell에서 제공 됩니다.  위에서 설명한 것 처럼 더 이상 다른 정책 설정을 설정할 필요가 없습니다. 다음은 PowerShell 경고가 다음과 같이 표시 되는 예입니다.

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>관련 항목

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




