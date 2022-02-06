---
title: Teams 클라이언트 환경 및 공존 모드 준수
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: '클라이언트 Teams 및 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 대한 준수에 대해 자세히 알아보습니다.'
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
---

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Teams 클라이언트 환경 및 공존 모드 준수

<a name="about-upgrade-basic"></a>

공존 비즈니스용 Skype(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)은 조직이 조직에서 비즈니스용 Skype 예측 가능한 환경을 Teams.  조직으로 이동하는 Teams 유일한 Teams 모드는 각 사용자  에 대한 최종 대상입니다. 그러나 모든 사용자에게 Teams(또는 다른 모드)를 동시에 할당해야 하는 것은 아닙니다  .  TeamsOnly 모드에 도달하기 전에 조직은 모든 비즈니스용 Skype 공존 모드를 사용하여 사용자와 아직 Teams 사용자 간에 예측 가능한 통신을 보장할 수 있습니다. 

사용자가 모든 비즈니스용 Skype 있는 경우 들어오는 모든 채팅 및 호출이 사용자의 비즈니스용 Skype 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 Teams 모드 중 하나에 있는 경우 클라이언트의 호출 및 채팅 비즈니스용 Skype 비활성화됩니다. 마찬가지로 Teams, 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정되어 있습니다.

현재 상태는 채팅 및 통화를 통해 도달성을 표시하기 때문에 채팅 및 통화를 사용하지 않도록 설정하면 Teams(즉, 사용자의 사진에서 클라이언트에 자신의 Teams 표시)도 숨겨져 있습니다. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>클라이언트에서 사용할 수 있는 Teams 모드에 따라 변경되는 방법

사용 가능한 Teams TeamsUpgradePolicy에서 설정한 사용자 공존 모드에 따라 달라 갑니다. 다음 표에서는 동작을 요약합니다.

|사용자의 유효 모드|클라이언트에서 Teams 경험|
|---|---|
|모든 비즈니스용 Skype 모드|통화, 채팅 및 자체 상태는 사용하지 않도록 설정됩니다.|
|SfBWithTeamsCollabAndMeetings|모임일정을 사용할 수 있습니다.|
|SfBWithTeamsCollab 또는 SfBOnly1<sup></sup>|모임일정을 사용할 수 없습니다.|
|||

다음 스크린샷은 Teams **또는** 섬 모드와 다른 모든 모드의 차이점  을 보여 주는 스크린샷입니다. 채팅 및 통화 아이콘은 기본적으로 Teams 또는 섬 모드(왼쪽 스크린샷)와 함께 사용할 수  있지만 다른 모드(오른쪽 **스크린** 샷)에서는 사용할 수 없습니다.

![모드의 나란히 비교 Teams 비교합니다.](media/teams-mode-comparison.png)

또한 여기에서와 같이 다른 모드에서는 셀프 존재를 사용할 수 없습니다.

![모임 첫 번째에서 자기 존재의 스크린샷.](media/meetings-first-no-self-presence-general.png)
 
**참고:**
 <sup>1</sup> 현재 SfBwithTeamsCollab과 SfBOnly는 동일하게 사용되지만 SfBOnly 모드는 SfBOnly 모드에서 채널 및 파일 기능을 사용하지 않도록 설정하기 위한 Teams. 중간에 앱 사용 권한 정책을 사용하여 채널을 숨길 수 있습니다.


## <a name="impact-of-mode-on-other-policy-settings"></a>모드가 다른 정책 설정에 미치는 영향
위에서 설명한 대로 사용자의 공존 모드 영향은 사용자의 클라이언트에서 사용할 수 있는 Teams 영향을 미치게 됩니다. 즉, 모드 값이 모드에 따라 다른 정책 설정 값보다 우선할 수 있습니다. 특히 공존 모드는 다음 정책 설정을 적용하는지 여부에 영향을 미치게 됩니다.

|**모달리티(앱)**|**Policy.Setting**|
|---|---|
|채팅|TeamsMessagingPolicy.AllowUserChat|
|통화|TeamsCallingPolicy.AllowPrivateCalling|
|모임일정|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

관리자는 공생  모드를 사용할 때 이러한 정책 설정을 명시적으로 설정할 필요는 없지만, 이러한 설정이 주어진 모드에 대해 다음과 같이 효과적으로 행동한다는 것을 이해하는 것이 중요합니다. 

|모드|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 또는 Islands|사용 가능|사용 가능|사용 가능|사용 가능|
|SfBWithTeamsCollabAndMeetings|사용 안 함|사용 안 함|사용 가능|사용 가능|
|SfBWithTeamsCollab 또는 SfBOnly|사용 안 함|사용 안 함|사용 안 함|사용 안 함|
||||||

PowerShell `Grant-CsTeamsUpgradePolicy` 을 사용하는 경우 cmdlet은 TeamsMessagingPolicy, TeamsCallingPolicy 및 TeamsMeetingPolicy의 해당 설정의 구성을 검사하여 TeamsUpgradePolicy에서 해당 설정을 대신할지 여부를 확인하고 이 경우 PowerShell에 정보 메시지가 제공됩니다.  위에서 설명한 대로 이러한 다른 정책 설정을 설정하는 데 더 이상 필요하지 않습니다. 다음은 PowerShell 경고의 모양을 예로 들 수 있습니다.

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>관련 항목

[조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype](./migration-interop-guidance-for-teams-with-skype.md)