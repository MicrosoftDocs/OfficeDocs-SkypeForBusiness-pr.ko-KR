---
title: 일반 모임 정책 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: 에서 일반 모임 정책 설정을 관리하는 방법을 Teams.
ms.openlocfilehash: be28acd1a343988fef94546f405a1f7a3684d4ce
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731667"
---
# <a name="meeting-policy-settings---general"></a>모임 정책 설정 - 일반

<a name="bkgeneral"> </a>

이 문서에서는 모임에 대한 다음 일반 정책 Teams 설명합니다.

- [지금 채널에서 모임 시작 허용](#allow-meet-now-in-channels)
- [Outlook 추가 기능 허용](#allow-the-outlook-add-in)
- [채널 모임 예약 허용](#allow-channel-meeting-scheduling)
- [비공개 모임 예약 허용](#allow-scheduling-private-meetings)
- [비공개 모임으로 지금 모임 시작 허용](#allow-meet-now-in-private-meetings)
- [지정된 발표자 역할 모드](#designated-presenter-role-mode)
- [참여 보고서 허용](#allow-engagement-report)
- [모임 등록 허용](#allow-meeting-registration)
- [Who 수 있습니다.](#who-can-register)
- [제도 모드에 대한 모임 공급자](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a>지금 채널에서 모임 시작 허용

이 정책은 사용자별 정책에 해당하며 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 다른 채널에서 모임을 시작할 수 있는지 Teams 제어합니다. 이 기능을 설정하면 사용자는 모임  단추를 클릭하여 모임을 시작하거나 채널에서 모임을 예약할 수 있습니다. 기본값은 True입니다.

[![메시지 아래에 지금 만나기 아이콘을 보여주는 스크린샷입니다. ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="allow-the-outlook-add-in"></a>Outlook 추가 기능 허용

이 정책은 사용자별 정책에 해당하며 모임이 시작되기 전에 적용됩니다. 이 설정은 Teams 모임을 Outlook(Windows, Mac, 웹 및 모바일)에서 예약 가능한지 여부를 제어합니다.

![새 모임을 예약하는 기능을 보여주는 스크린샷입니다.](media/meeting-policies-outlook-add-in.png)

이 기능을 해제하면 사용자가 새 모임을 만들 때 Teams 모임을 예약할 수 Outlook. 예를 들어 Windows 기반 Outlook에서는 **새 Teams 모임** 옵션이 리본에 표시되지 않습니다.

## <a name="allow-channel-meeting-scheduling"></a>채널 모임 예약 허용

기존 AllowChannelMeetingScheding 정책을 사용하여 팀 채널 일정에서 만들 수 있는 이벤트 유형을 제어합니다. 이 정책은 사용자별 정책에 해당하며 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 Teams 채널의 모임을 예약할 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 켜져 있습니다. 

이 정책이 해제된 경우 사용자는 새 채널 모임을 만들 수 없습니다. 단 이벤트 이끌이가 기존 채널 모임을 편집할 수는 있습니다.

모임 예약을 사용할 수 없습니다.

![모임 예약 옵션을 보여 Teams.](media/schedule-meeting-option.png)

채널 선택을 사용할 수 없습니다.

[모임을 예약할 채널을 선택하는 일정 옵션을 보여주는 ![ 스크린샷입니다. ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

채널 게시물 페이지에서는 다음을 사용하지 않도록 설정됩니다.

- 채널 회신 작성란의 **모임 예약** 단추
  ![모임을 예약할 채널을 선택하는 일정 옵션을 보여주는 스크린샷입니다.](media/schedule-meeting-disabled-in-chat2.png)
  
- 채널 헤더의 **모임 예약** 단추
  ![모임을 예약할 채널을 선택하는 일정 옵션을 보여주는 스크린샷입니다.](media/schedule-now-in-header.png)

채널 일정에서:

- 채널 일정의 **새 이벤트 추가** 단추를 사용할 수 없습니다.
  ![모임을 예약할 수 있는 채널을 선택하는 일정 옵션을 보여주는 스크린샷입니다.](media/add-new-event-disabled.png)

- 사용자는 채널 일정에서 시간 블록을 끌어 채널 모임을 만들 수 없습니다.

- 사용자는 바로 가기 키를 사용하여 채널 일정에서 모임을 만들 수 없습니다.

관리 센터에서:

채널 일정 앱이 앱 사용 권한 정책 페이지의 **Microsoft 앱** 섹션에 표시됩니다.

![관리 센터의 앱 사용 권한 정책을 Teams 스크린샷입니다.](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a>비공개 모임 예약 허용

이 정책은 사용자별 정책에 해당하며 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 Teams에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.

비공개 모임 예약  허용을 해제하고 채널 모임 예약 허용을 해제하는 경우  필요한 참석자 추가 및 채널 추가 옵션을 사용할 수 Teams.  이 설정은 기본적으로 켜져 있습니다.

## <a name="allow-meet-now-in-private-meetings"></a>비공개 모임으로 지금 모임 시작 허용

이 정책은 사용자별 정책에 해당하며 모임이 시작되기 전에 적용됩니다. 이 설정은 사용자가 비공개 모임을 시작할 수 있는지 여부를 제어합니다.  이 설정은 기본적으로 켜져 있습니다.

## <a name="designated-presenter-role-mode"></a>지정된 발표자 역할 모드

사용자별 정책에 해당합니다. 이 설정으로 Teams 클라이언트의 **모임 옵션** 에서 **발표할 수 있는 사람** 설정 기본값을 변경합니다. 이 정책 설정은 지금 모임 시작 모임을 비롯한 모든 모임에 영향을 미칩니다.

**발표할 수 있는 사람** 설정을 통해 모임 이끌이는 모임의 발표자 역할을 할 수 있는 사람을 선택합니다. 자세한 내용은 [Teams 모임의 참가자 설정 변경](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 및 [Teams 모임에서의 역할](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)을 참조하세요.

현재 PowerShell을 사용해서만 이 정책 설정을 구성할 수 있습니다. [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존의 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새로운 Teams 모임 정책을 만들고 이를 사용자에게 할당합니다.

Teams의 **발표할 수 있는 사람** 설정 기본값을 지정하려면 **DesignatedPresenterRoleMode** 매개 변수를 다음 중 하나로 설정합니다.

- **EveryoneUserOverride**: 모든 모임 참가자가 발표자가 될 수 있습니다. 이 값은 기본값입니다. 이 매개 변수는 Teams의 **모든 사용자** 설정에 해당합니다.
- **EveryoneInCompanyUserOverride**: 게스트 사용자를 포함한 조직의 인증된 사용자가 발표자가 될 수 있습니다. 이 매개 변수는 Teams의 **내 조직의 사용자** 설정에 해당합니다.
- **OrganizerOnlyUserOverride**: 모임 이끌이만 발표자가 될 수 있으며 모든 모임 참가자는 참석자로 지정됩니다. 이 매개 변수는 Teams의 **나만** 설정에 해당합니다.

기본값을 설정한 후에도 모임 이끌이는 여전히 Teams에서 이 설정을 변경하고 본인이 예약하는 모임에서 발표할 수 있는 사용자를 선택할 수 있습니다.

## <a name="allow-engagement-report"></a>참여 보고서 허용

사용자별 정책에 해당합니다. 이 설정으로 모임 이끌이가 [모임 참석 보고서](teams-analytics-and-reports/meeting-attendance-report.md)를 다운로드할 수 있는지 여부를 제어합니다.

이 정책은 기본적으로 해제되어 있으며 이끌이는 사용자가 설정한 모임 및 웨비나를 등록하고 참석한 사람도 볼 수 있습니다. 이 기능을 Teams 관리 센터에서 설정하려면 모임 모임 정책으로 이동하고 정책을 사용 으로  >   **설정합니다.**

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존의 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새로운 Teams 모임 정책을 만들고 이를 사용자에게 할당합니다.

모임 이끌이가 모임 참석 보고서를 다운로드하도록 설정하려면 **AllowEngagementReport** 매개 변수를 사용 으로 **설정합니다.** 사용하도록 설정하면 보고서 다운로드 옵션이 **참가자** 창에 표시됩니다. 기본적으로 이 설정은 사용하도록 설정되지 않습니다.

모임 이끌이가 보고서를 다운로드하지 못하게 하려면 매개 변수를 **사용 안 함** 으로 설정합니다.

## <a name="allow-meeting-registration"></a>모임 등록 허용

사용자별 정책에 해당합니다. 이 기능을 설정하면 조직의 사용자가 웨비나를 설정할 수 있습니다. 이 정책은 기본적으로 사용하도록 설정되어 있습니다.

이 정책을 Teams 관리 센터에서 편집하려면 모임 모임 정책  >  **으로 이동하세요.** 모임 등록을 해제하기 위해 정책을 끄기 로 **설정합니다.**

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존의 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새로운 Teams 모임 정책을 만들고 이를 사용자에게 할당합니다.

모임 등록을 켜기 위해 **AllowMeetingRegistration 매개** 변수를 **True로 설정합니다.** 기본적으로 **True로** 설정됩니다.

모임 등록을 해제하고 사용자가 웨비나를 조정하지 못하게 하여 매개 변수를 **False로 설정합니다.**

## <a name="who-can-register"></a>Who 수 있습니다.

이 정책은 웨비나를 등록하고 참석할 수 있는 사용자를 제어합니다. 이 정책에는 모임 등록 허용이 설정되어 있는 경우만 사용할 **수** 있는 두 가지 옵션이 있습니다.

- 익명 **사용자를 Who** 사용자가  설정한 웨비나를 등록하고 참석하도록 허용하려는 경우 모든 사용자에 등록할 수 있습니다.
- 조직 **Who** 사용자만  등록하고 참석하도록 허용하려는 경우 조직 내 모든 사용자에 등록할 수 있습니다.

기본적으로 Who **수 있는** 설정은 모두로 **설정됩니다.** 이 정책을 Teams 관리 센터에서 편집하려면 모임 모임 정책  >  **으로 이동하세요.**

[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존의 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새로운 Teams 모임 정책을 만들고 이를 사용자에게 할당합니다.

익명 사용자를 비롯한 모든 사용자가 웨비나를 등록하고 참석할 수 있도록 허용하기 위해 **WhoCanRegister 매개** 변수를 모든 으로 **설정합니다.** 기본적으로 모든 **사용자로** 설정됩니다.

조직의 사용자만 웨비나를 등록하고 참석하도록 허용하기 위해 매개 변수를 **EveryoneInCompany로 설정합니다.**

## <a name="meeting-provider-for-islands-mode"></a>제도 모드에 대한 모임 공급자

사용자별 정책에 해당합니다. 이 설정으로 *아일랜드 모드 사용자* 에 대해 사용할 Outlook 모임 추가 기능을 제어합니다. 사용자가 Teams 모임 추가 기능만 사용할 수 있는지 또는 Teams 모임 및 비즈니스용 Skype 모임 추가 기능을 모두 사용하여 Outlook에서 회의를 예약할 수 있는지 여부를 지정할 수 있습니다.

이 정책은 아일랜드 모드이면서 Teams 모임 정책에서 **AllowOutlookAddIn** 매개 변수가 **True** 로 설정된 사용자에게만 적용할 수 있습니다.

현재는 PowerShell을 사용해서만 이 정책을 설정할 수 있습니다. [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존의 Teams 모임 정책을 편집할 수 있습니다. 또는 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새로운 Teams 모임 정책을 만들고 이를 사용자에게 할당합니다.

사용자가 사용할 수 있게 하려는 모임 추가 기능을 지정하려면 **PreferredMeetingProviderForIslandsMode** 매개 변수를 다음과 같이 설정합니다.

- Outlook에서 Teams 모임 추가 기능과 비즈니스용 Skype 추가 기능을 모두 사용하려면 매개 변수를 **TeamsAndSfB** 로 설정합니다. 이 값은 기본값입니다.
- Outlook에서 Teams 모임 추가 기능만 사용하려면 매개 변수를 **Teams** 로 설정합니다. 이 정책을 설정하면 향후 모든 모임에 Teams 모임 참가 링크가 생깁니다. 기존의 비즈니스용 Skype 모임 참가 링크는 Teams로 마이그레이션되지 않습니다. 이 정책을 설정해도 현재 상태, 채팅, PSTN 통화 또는 비즈니스용 Skype의 다른 모든 기능에 영향을 미치지 않습니다. 즉, 사용자는 계속 이들 기능을 위해 비즈니스용 Skype를 사용하게 됩니다.

  매개 변수를 **Teams** 로 설정했다가 다시 **TeamsAndSfB** 로 전환하면 두 모임 추가 기능이 모두 활성화됩니다. 그러나 기존 Teams 모임 조인 링크는 비즈니스용 Skype. 변경 후 예약된 비즈니스용 Skype 모임만 비즈니스용 Skype 모임 참가 링크가 생깁니다.

## <a name="meeting-reactions"></a>모임 반응

AllowMeetingReactions 설정은 PowerShell을 사용하는 경우에만 적용할 수 있습니다. Teams 관리 센터에서 AllowMeetingReactions를 설정하거나 해제하는 옵션은 없습니다.

모임 반응은 기본적으로 해제되어 있습니다. 사용자의 반응 설정을 꺼도 사용자는 본인이 예약한 모임에서 반응을 사용할 수 있습니다. 모임 이끌이는 기본 설정에 관계없이 계속 모임 옵션 페이지에서 반응을 켤 수 있습니다.


## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [정책 할당 Teams](policy-assignment-overview.md)
- [사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제](meeting-policies-restricted-anonymous-access.md)
