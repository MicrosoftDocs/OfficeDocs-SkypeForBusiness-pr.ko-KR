---
title: 모임 정책 및 모임 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 모임 정책 설정을 사용하여 모임 만료를 제어하는 Microsoft Teams.
ms.openlocfilehash: 84a944fe23c7ccb54362f1038958763dec2eb1a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607165"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>모임 정책 및 모임 Microsoft Teams

[Microsoft Teams](meeting-policies-in-teams.md) 모임 정책은 조직의 사용자가 모임을 시작하고 예약할 수 있는지 여부를 제어하고 사용자가 예약한 모임을 위해 모임 참가자에게 사용할 수 있는 기능을 제어하는 데 사용됩니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 관리 센터에서 모임 정책을 관리하거나 Microsoft Teams , [](/powershell/module/skype/get-csteamsmeetingpolicy)새로, 설정 [,](/powershell/module/skype/set-csteamsmeetingpolicy) [제거,](/powershell/module/skype/remove-csteamsmeetingpolicy) [부여](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell cmdlet을 사용하여 관리합니다. [](/powershell/module/skype/new-csteamsmeetingpolicy)

사용자가 모임을 시작하고 예약할 수 있는지 여부를 제어하고 사용자가 예약한 모임의 만료를 제어하는 모임 정책 설정입니다. 모임에 대한 모임 참가 링크 및 회의 ID가 만료되면 아무도 모임에 참가할 수 없습니다. 다음 모임 정책 설정은 사용자가 모임을 시작하고 예약할 수 있는지 여부를 Teams. 이 문서에서 모임 설정을 논의합니다.

- [채널에서 지금 모임](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)허용: 사용자가 채널에서 즉사적 모임을 시작할 수 있는지 여부를 제어합니다.
- [채널 모임](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)일정 허용: 사용자가 채널에서 모임을 예약할 수 있는지 여부를 제어합니다.
- [비공개 모임](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)예약 허용: 사용자가 비공개 모임을 예약할 수 있는지 Teams. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.
- [사용자가 Outlook](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)Outlook 모임을 예약할 수 있는지 여부를 제어합니다. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.
- [비공개 모임에서](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)모임 허용: 사용자가 즉사적으로 비공개 모임을 시작할 수 있는지 여부를 제어합니다.

기본적으로 이러한 설정은 설정되어 있습니다. 이러한 설정이 해제된 경우 정책을 할당한 사용자는 해당 유형의 새 모임을 시작하거나 예약할 수 없습니다. 동시에 모임 참가는 사용자가 이전에 시작하거나 예약한 해당 유형의 모든 기존 모임의 연결 및 회의 ID를 연결합니다.

예를 들어 사용자가 이러한 모임 정책 설정을 **켜기로** 설정한 모임 정책을 할당한  다음 채널 설정에서 지금 모임 허용을 해제하면 해당 사용자가 더 이상 채널에서 즉시 모임을 시작할 수 없습니다. 이제 채널 모임에 사용자가 이전에 만든 링크가 만료되었습니다. 사용자는 다른 모임 유형을 시작하고 예약하고 다른 사용자가 구성한 모임에 참가할 수 있습니다.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>모임 조인 링크 및 회의 ID가 만료되면 어떻게 됩니까?

모임에 대한 모임 참가 링크 및 회의 ID가 만료되면 아무도 모임에 참가할 수 없습니다. 사용자가 링크 또는 전화를 통해 모임에 참가할 때 모임을 더 이상 사용할 수 없음을 밝히는 메시지가 표시됩니다. 모임과 관련된 대화, 파일, 화이트보드, 녹음/ 녹취 파일 및 기타 콘텐츠는 보존되고 사용자는 여전히 액세스할 수 있습니다.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>모임 정책 설정을 켜고 끄면 어떻게 하나요?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>모임 정책 설정을 켜기에서 해제로 전환

모임 정책 설정이 **On으로** 설정되어 있는 경우 정책이 할당된 사용자는 해당 유형의 모임을 시작하거나 예약할 수 있으며 모든 사용자가 참가할 수 있습니다. 모임 정책 설정을 **해제로** 전환하면 정책이 할당된 사용자는 해당 유형의 새 모임을 시작하거나 예약할 수 없습니다. 사용자가 이전에 예약한 기존 모임의 연결 및 회의 ID가 만료됩니다.

사용자가 다른 사용자가 구성한 모임에 참가할 수 있습니다.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>모임 정책 설정을 끄기에서 켜기로 전환

모임 정책 설정을 **Off에서** **켜기로** 전환하면 정책이 할당된 사용자는 해당 유형의 모임을 시작하거나 예약할 수 있습니다. 모임 정책 설정이 해제된 다음 사용자에 대해 다시 켜져 있는 경우 사용자가 구성한 이전에 예약된(및 만료된) 모임이 모두 활성화되고 사용자가 모임 참가 링크 또는 전화로 모임에 참가할 수 있습니다.  

## <a name="meeting-expiration-scenarios"></a>모임 만료 시나리오

다음은 이 문서에서 설명하는 각 모임 정책 설정에 대해 모임 만료가 작동하는 방법에 대한 요약입니다.

|원하는 경우...&nbsp;&nbsp; |이 작업을&nbsp;&nbsp;&nbsp;&nbsp;  |모임 조인 동작&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|사용자가 시작한 비공개 모임 만료&nbsp;&nbsp;|비공개 **모임에서 모임 허용을 해제합니다.**&nbsp;&nbsp;|이제 사용자가 시작한 비공개 **모임에** 참가할 수 없습니다.|
|사용자가 예약한 비공개 모임 만료&nbsp;&nbsp;|비공개 **모임을**  허용을 끄고 추가 기능 **허용을 Outlook 끄기** &nbsp;&nbsp;|사용자가 예약한 개인 모임에 참가할 수 없습니다. 이렇게 하면 사용자가 다음 모임에 참가할 수 없습니다.<ul><li>과거에 발생한 비공개 모임입니다.</li><li>향후에 예정된 비공개 모임 및 아직 발생하지 않은 비공개 모임입니다.</li><li>향후 개인 모임의 재발하는 인스턴스입니다.</li></ul><br>둘 다 개인 **모임** 예약을 허용하고 사용자가 **Outlook** 비공개 모임을 만료하려면 추가 기능 허용을 해제해야 합니다. 한 설정이 해제되고 다른 설정이 설정 중이면 기존 모임의 모임 참가 링크 및 회의 신분은 활성 상태로 유지되고 만료되지 않습니다.|
|사용자가 **시작한** 채널 모임 만료&nbsp;&nbsp;|채널에서 지금 모임 허용을 끄고 채널 모임일정 허용을 **끄기**  &nbsp;&nbsp;|이제 사용자가 시작한 채널 **모임에** 참가할 수 없습니다.|
|사용자가 예약한 채널 모임 만료&nbsp;&nbsp;|채널 **모임일정 허용 을 해제합니다.**&nbsp;&nbsp;|사용자가 예약한 채널 모임에 참가할 수 없습니다. 이렇게 하면 사용자가 다음 모임에 참가할 수 없습니다.<ul><li>과거에 발생한 채널 모임입니다.</li><li>향후에 예정된 채널 모임과 아직 발생하지 않은 채널 모임입니다.</li><li>향후 채널 모임의 인스턴스입니다.</li></ul>|

사용자가 이전에 예약했거나 특정 사용자가 시작한 모임에 액세스하려는 경우 다음을 할 수 있습니다.

- 해당 사용자의 모임 정책 설정을 설정합니다.
- 해당 사용자의 모임 정책 설정을 해제하고 정책 설정을 사용하도록 설정된 다른 사용자가 만료된 모임을 대체할 새 모임을 만들게 합니다.

> [!NOTE]
> 관리자와 같은 다른 사람을 대신하여 모임 초대를 보낼 수 있는 권한이 부여된 대리인이 모임을 보낸 경우 모임 정책 설정은 권한을 부여한 사용자(관리자)에게 적용됩니다.

## <a name="related-topics"></a>관련 주제

[Teams에서의 모임 정책 관리](meeting-policies-in-teams.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)
