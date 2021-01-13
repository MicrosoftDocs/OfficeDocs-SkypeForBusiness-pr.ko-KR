---
title: Teams 클라이언트 환경 및 공존 모드 준수
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Teams 클라이언트 환경 및 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 대한 준수에 대해 자세히 배워야 합니다.
localization_priority: Normal
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821028"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 클라이언트 환경 및 공존 모드 준수

<a name="about-upgrade-basic"></a>

비즈니스용 Skype 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)의 목적은 조직이 비즈니스용 Skype에서 Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공하는 것입니다.  Teams로 전환하는 조직의 경우 **Teams** 전용 모드는 각 사용자에 대한 최종 대상이지만, 모든 사용자에게 **Teams만(또는** 다른 모드)을 동시에 할당해야 하는 것은 아닙니다.  사용자가 TeamsOnly 모드에 도달하기 전에 조직은 비즈니스용 Skype 공존 모드를 사용하여 **Teams** 전용 사용자와 아직 그렇지 않은 사용자 간에 예측 가능한 통신을 보장할 수 있습니다. 

사용자가 비즈니스용 Skype 모드에 있는 경우 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있는 경우 Teams 클라이언트의 통화 및 채팅 기능이 비활성화됩니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 Teams의 모임 예정이 명시적으로 비활성화되어 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정됩니다.

현재 상태는 채팅 및 통화를 통한 연결 가능성의 표시이기 때문에 채팅 및 통화가 비활성화된 경우 Teams의 셀프 에디스(즉, 사용자의 사진에서 Teams 클라이언트에 자신의 현재 상태 표시)도 숨겨집니다. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Teams 클라이언트에서 사용 가능한 기능이 모드에 따라 변경하는 방식

Teams에서 사용 가능한 기능은 TeamsUpgradePolicy에서 설정한 사용자의 공존 모드에 따라 달라 습니다. 다음 표에서는 동작을 요약합니다.

|사용자의 유효 모드|Teams 클라이언트의 환경|
|---|---|
|비즈니스용 Skype 모드|통화, 채팅 및 셀프 현재 상태는 사용할 수 없습니다.|
|SfBWithTeamsCollabAndMeetings|모임을 사용할 수 있습니다.|
|SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup>|모임을 사용할 수 없습니다.|
|||

다음 스크린샷은 Teams **전용** 모드  또는 제도 모드와 다른 모든 모드 간의 차이점을 보여 주는 스크린샷입니다. 채팅 및 통화 아이콘은 **Teams 전용** 또는 제도  모드(왼쪽 스크린샷)에서 기본적으로 사용할 수 있지만 다른 모드(오른쪽 스크린샷)와는 사용할 수 없습니다.

![Teams 모드의 나란히 비교](media/teams-mode-comparison.png)

또한 다음과 같이 다른 모드에서는 셀프 존재를 사용할 수 없습니다.

![모임 우선의 셀프 에세이트 스크린샷](media/meetings-first-no-self-presence-general.png)
 
**참고:** 
 <sup>1</sup> 현재 SfBwithTeamsCollab 및 SfBOnly는 동일하게 사용되지만, SfBOnly 모드가 Teams에서 채널 및 파일 기능을 사용하지 않도록 설정하기 위한 것입니다. 중간에 앱 사용 권한 정책을 사용하여 채널을 숨길 수 있습니다.


## <a name="impact-of-mode-on-other-policy-settings"></a>모드가 다른 정책 설정에 미치는 영향
위에서 설명한 대로 사용자의 공존 모드는 사용자의 Teams 클라이언트에서 사용할 수 있는 기능에 영향을 미치게 됩니다. 즉 모드 값이 모드에 따라 다른 정책 설정 값보다 우선적으로 적용될 수 있습니다. 특히 공존 모드는 다음 정책 설정을 적용하는지 여부에 영향을 미치게 됩니다.

|**Modality(앱)**|**Policy.Setting**|
|---|---|
|채팅|TeamsMessagingPolicy.AllowUserChat|
|통화|TeamsCallingPolicy.AllowPrivateCalling|
|모임일정|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

관리자는 공생 모드를 사용할 때 이러한 정책 설정을 명시적으로 설정할 필요가 없지만, 이러한 설정이 주어진 모드에 대해 다음과 같이 효과적으로 행동한다는 것을 이해하는 것이 중요합니다.  

|모드|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 또는 Islands|사용|사용|사용|사용|
|SfBWithTeamsCollabAndMeetings|사용 안|사용 안|사용|사용|
|SfBWithTeamsCollab 또는 SfBOnly|사용 안|사용 안|사용 안|사용 안|
||||||

PowerShell을 사용하는 경우 `Grant-CsTeamsUpgradePolicy` cmdlet은 TeamsMessagingPolicy, TeamsCallingPolicy 및 TeamsMeetingPolicy에서 해당 설정의 구성을 확인하여 해당 설정을 TeamsUpgradePolicy로 대신할지 여부를 확인하고, 이 경우 PowerShell에서 정보 메시지가 제공됩니다.  위에서 설명한 대로 이러한 다른 정책 설정을 더 이상 설정할 필요가 없습니다. 다음은 PowerShell 경고의 예입니다.

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




