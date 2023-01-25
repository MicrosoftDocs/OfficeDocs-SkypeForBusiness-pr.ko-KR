---
title: Teams 모임에 대한 익명 참가자 액세스 관리(IT 관리자)
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: IT 전문가의 경우 - Microsoft Teams에서 익명 모임 참여가 작동하는 방식을 알아봅니다.
ms.openlocfilehash: a4f1833059febf2f8481cba9f1b3716519613e89
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983736"
---
# <a name="manage-anonymous-participant-access-to-teams-meetings-it-admins"></a>Teams 모임에 대한 익명 참가자 액세스 관리(IT 관리자)

조직에서 호스트하는 모임의 익명 참가자는 ID를 확인할 수 없는 사용자입니다. 여기에는 다음이 포함될 수 있습니다.

- 회사 또는 학교 계정으로 Teams에 로그인하지 않은 사람 
- 신뢰할 수 없는 조직([외부 액세스](manage-external-access.md)에 구성된 경우) 및 신뢰할 수 있지만 조직을 신뢰하지 않는 조직에서 사람.

익명 모임 참가는 조직 수준 설정 및 사용자 수준 정책에 의해 제어됩니다. 익명 모임 참가가 작동하려면 다음을 수행합니다.
- **익명 사용자가 모임** Teams 모임에 참가할 수 있는 설정(조직 수준)을 설정해야 합니다.
- 모임 이끌이에게 **익명 사용자가** 모임에 참가하도록 허용 컨트롤이 켜져 있는 Teams 모임 정책이 할당되어야 합니다.

익명 모임 참가는 기본적으로 조직 및 기본 전역 모임 정책에 대해 설정됩니다. 조직 수준 설정을 유지하고 모임 정책을 사용하여 다른 사용자(모임 이끌이)에 대해 익명 모임 참가를 설정하거나 해제하는 것이 좋습니다.

익명 모임 참가를 사용하는 경우 로비 정책은 익명 참가자가 모임에 참여하는 방식에 영향을 줍니다. 자세한 내용은 [Microsoft Teams에서 모임 로비를 우회할 수 있는 사용자 제어를 참조하세요](who-can-bypass-meeting-lobby.md).

#### <a name="meetings-with-trusted-organizations"></a>신뢰할 수 있는 조직과의 모임

외부 모임 및 채팅을 위해 신뢰할 수 있는 조직을 설정하는 경우 외부 액세스 설정이 두 조직에 대해 올바르게 구성되지 않은 경우 해당 조직의 모임 참석자는 익명으로 간주될 수 있습니다. 자세한 내용은 [외부 모임 및 채팅에 대한 신뢰할 수 있는 조직을 참조하세요](manage-external-access.md).

## <a name="manage-anonymous-meeting-join-for-the-organization"></a>조직의 익명 모임 참가 관리

익명 참가자를 허용하는 모임을 만들려면 조직의 모든 사용자가 조직 수준 익명 모임 참가 설정을 설정해야 합니다.

> [!Important]
> **익명 참가자가 모임에 참가할 수 있는** 조직 전체 설정은 나중에 제거됩니다. 이 설정을 **켜** 기로 두고 **익명 사용자가 모임** 사용자 수준 모임에 참가하도록 허용 정책 컨트롤을 사용하여 익명 모임 참가를 허용하거나 방지하는 것이 좋습니다.

조직에 대한 익명 모임 참가를 구성하려면
1. [Teams 관리 센터](https://admin.teams.microsoft.com)로 이동합니다.

1. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.

1. **참가자** 에서 **익명 참가자가 모임에 참가할 수 있도록** **설정**(권장) 또는 **끄기로** 설정합니다.

    ![관리 센터에서 모임에 대한 참가자 설정 스크린샷.](media/meeting-settings-participants.png "Microsoft Teams 관리 센터에서 Teams 모임에 대한 참가자 설정의 스크린샷")

1. **저장** 을 선택합니다.

## <a name="manage-which-meeting-organizers-can-allow-anonymous-meeting-join"></a>익명 모임 참가를 허용할 수 있는 모임 이끌이 관리

익명 참가자를 포함하는 모임을 호스트할 수 있는 사용자 또는 그룹을 제어할 수 있습니다. 이렇게 하려면 익명 참가자와 모임을 호스트해야 하는 각 모임 이끌이에게 익명 모임 참가가 켜져 있는 모임 정책을 할당합니다.

특정 모임 이끌이에 대해 익명 모임 참가를 구성하려면
1. [Teams 관리 센터](https://admin.teams.microsoft.com)로 이동합니다.

1. 왼쪽 탐색 영역에서 **모임 모임** > **정책** 으로 이동합니다.

1. 수정하려는 정책을 선택합니다.

1. **익명 사용자가 모임에 참가** 하도록 허용을 **켜** 기로 설정합니다.

1. **저장** 을 선택합니다.

모임 정책 변경 내용을 적용하는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="configure-anonymous-meeting-join-using-powershell"></a>PowerShell을 사용하여 익명 모임 참가 구성

다음을 사용하여 익명 참가자가 모임에 참가할 수 있는지 여부를 제어할 수 있습니다.

- `-DisableAnonymousJoin` 조직 수준 설정을 구성하기 위한 [Set-CsTeamsMeetingConfiguration](/powershell/module/skype/set-csteamsmeetingconfiguration)의 매개 변수입니다. (이 집합을 False로 설정하고 Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting을 사용하여 사용자 또는 그룹 수준에서 익명 모임 참가를 제어하는 것이 좋습니다.)
- `-AllowAnonymousUsersToJoinMeeting` 사용자 수준 모임 정책을 구성하기 위한 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)의 매개 변수

익명 참가자가 모임에 참가할 수 있도록 하려면 다음 값을 설정하여 익명 모임 참가를 허용하도록 둘 다 구성해야 합니다.

- `Set-CsTeamsMeetingConfiguration -DisableAnonymousJoin`**$false**
- `Set-CsTeamsMeetingPolicy -AllowAnonymousUsersToJoinMeeting` 관련 모임 이끌이에 대한 **$true** 설정

## <a name="block-anonymous-meeting-join-for-specific-client-types"></a>특정 클라이언트 유형에 대한 익명 모임 참가 차단

익명 참가자가 모임에 참가할 수 있는 경우 teams 클라이언트 또는 [Azure Communication Services](/azure/communication-services/) 사용하여 빌드된 사용자 지정 클라이언트를 사용할 수 있습니다. 

관리자는 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy#-blockedanonymousjoinclienttypes)의 매개 변수를 `-BlockedAnonymousJoinClientTypes` 사용하여 이러한 클라이언트 유형 중 하나를 차단할 수 있습니다.

## <a name="anonymous-participants-meeting-experience"></a>익명 참가자 모임 환경

익명 참가자는 다른 모임 참가자와 동일한 기능이 없습니다. 예를 들어 익명 참가자:

- 모임 전후에 모임 채팅에 액세스할 수 없습니다.
- 프로필 카드에 액세스할 수 없음(Microsoft 365의 프로필 카드 - Microsoft 지원)

### <a name="how-anonymous-participants-interact-with-apps-in-meetings"></a>익명 참가자가 모임에서 앱과 상호 작용하는 방법

기본적으로 익명 참가자가 모임에서 앱과 상호 작용할 수 있도록 하는 설정이 사용됩니다.

익명 모임 참가자에 대한 앱 액세스를 구성하려면

1. [Teams 관리 센터](https://admin.teams.microsoft.com)로 이동합니다.

1. 왼쪽 탐색 모음에서 **모임** > **모임 설정** 으로 이동합니다.

1. **참가자** 에서 **익명 참가자가 모임의 앱과 상호 작용할 수 있도록** **설정** 하거나 **끄기로** 설정합니다.

를 사용하여 PowerShell을 사용하여 `Set-CsTeamsMeetingConfiguration -DisableAppInteractionForAnonymousUsers`이를 제어할 수도 있습니다.

익명 참가자는 전역(조직 전체 기본값) Teams 앱 권한 정책을 상속합니다. 익명 참가자는 해당 정책에서 앱을 사용하도록 설정하고 익명 참가자가 모임에서 앱과 **상호 작용할 수 있는 한 Teams 모임에서 앱과 상호 작용할 수 있습니다****.**

익명 참가자는 모임에서 이미 사용할 수 있고 이러한 앱을 획득 및/또는 관리할 수 없는 앱과만 상호 작용할 수 있습니다.

## <a name="related-topics"></a>관련 주제

[Teams 계정 없이 모임 참가](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Microsoft Teams 관리 센터를 사용하여 조직 전체 정책 구성](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[외부 참가자는 "Teams에 로그인하여 참가하거나 모임 이끌이에게 문의"를 받습니다.](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)

[Teams에서 정책 할당 – 시작](policy-assignment-overview.md)