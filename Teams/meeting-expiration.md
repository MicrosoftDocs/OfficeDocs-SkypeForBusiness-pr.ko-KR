---
title: Microsoft Teams의 모임 정책 및 모임 만료
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Microsoft Teams에서 모임 정책 설정을 사용하여 모임 만료를 제어하는 방법을 배워야 합니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827528"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams의 모임 정책 및 모임 만료

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>개요

[](meeting-policies-in-teams.md) Microsoft Teams의 모임 정책은 조직의 사용자가 모임을 시작하고 예약할 수 있는지 여부와 사용자가 예약한 모임을 위해 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 전역(전체 기본) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. Microsoft Teams 관리 센터에서 또는 [Get,](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy) [New,](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) [Remove,](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy) [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell cmdlet을 사용하여 모임 정책을 관리합니다.

사용자가 모임을 시작하고 예약할 수 있는지 여부를 제어하는 모임 정책 설정도 사용자가 예약한 모임의 만료를 제어합니다. 모임 참가 링크 및 모임의 회의 ID가 만료되면 아무도 모임에 참가할 수 없습니다. 다음 모임 정책 설정은 사용자가 Teams에서 모임을 시작하고 예약할 수 있는지 여부를 결정하며 이 문서 전체에서 해당 사용자를 참조합니다.

- [채널에서 모임](meeting-policies-in-teams.md#allow-meet-now-in-channels)허용: 사용자가 채널에서 즉정 모임을 시작할 수 있는지 여부를 제어합니다.
- [채널 모임](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)예약 허용: 사용자가 채널에서 모임을 예약할 수 있는지 여부를 제어합니다.
- [비공개 모임](meeting-policies-in-teams.md#allow-scheduling-private-meetings)예약 허용: 사용자가 Teams에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다. 모임은 팀의 채널에 게시되지 않은 경우 비공개입니다.
- [Outlook 추가 허용:](meeting-policies-in-teams.md#allow-the-outlook-add-in)사용자가 Outlook에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다. 모임은 팀의 채널에 게시되지 않은 경우 비공개입니다.
- [비공개 모임에서 모임](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)허용: 사용자가 즉사적 비공개 모임을 시작할 수 있는지 여부를 제어합니다.

기본적으로 이러한 설정은 설정되어 있습니다. 이러한 설정이 꺼져 있는 경우 정책이 할당된 사용자는 해당 유형의 새 모임을 시작하거나 예약할 수 없습니다. 동시에 모임 참가는 사용자가 이전에 시작했거나 예약된 해당 유형의 모든 기존 모임의 연결 및 회의 ID를 연결합니다.

예를 들어 사용자에게 이러한 모임 정책 설정이 설정되어 있는 모임 정책이 할당된  경우 채널 설정에서 모임 허용을 해제하면 해당 사용자는 더 이상 채널에서 즉시적 모임을 시작할 수 없습니다. 이제 모임 채널은 사용자가 이전에 만든 링크에 참가할 수 없습니다. 사용자는 다른 모임 유형을 시작 및 예약하고 다른 사용자가 구성한 모임에 참가할 수 있습니다.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>모임 참가 링크 및 회의 ID가 만료되면 어떻게 됩니까?

모임 참가 링크 및 모임의 회의 ID가 만료되면 아무도 모임에 참가할 수 없습니다. 사용자가 링크 또는 전화로 모임에 참가할 때 더 이상 모임을 사용할 수 없음을 표시하는 메시지가 표시됩니다. 모임과 관련된 대화, 파일, 화이트보드, 기록, 기록 및 기타 콘텐츠는 보존되고 사용자는 계속 액세스할 수 있습니다.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>모임 정책 설정을 켜고 끄면 어떻게 하나요?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>모임 정책 설정을 켜기에서 끄기로 전환

모임 정책 설정이 **On으로** 설정되어 있는 경우 정책이 할당된 사용자는 해당 유형의 모임을 시작하거나 예약할 수 있으며 모든 사용자가 참가할 수 있습니다. 모임 정책 설정을 **해제로** 전환하면 정책이 할당된 사용자는 해당 유형의 새 모임을 시작하거나 예약할 수 없습니다. 모임 참가 링크 및 사용자가 이전에 예약한 기존 모임의 회의 ID가 만료됩니다.

사용자가 다른 사용자가 구성한 모임에 계속 참가할 수 있습니다.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>모임 정책 설정을 끄기에서 켜기로 전환

모임 정책 설정을 끄기에서 켜기로 전환하면 정책이 할당된 사용자는 해당 유형의 모임을 시작하거나 예약할 수 있습니다.  모임 정책 설정이 해제되어 있는 경우 사용자에 대해 다시 설정하면 사용자가 구성한 이전에 예약된(및 만료된) 모임이 모두 활성화되고 사용자가 모임 참가 링크 또는 전화로 모임에 참가할 수 있습니다.  

## <a name="meeting-expiration-scenarios"></a>모임 만료 시나리오

다음은 이 문서에서 설명하는 각 모임 정책 설정에 대해 모임 만료가 작동하는 방식에 대한 요약입니다. 

|원하는 경우... |방법  |모임 참가 동작  |
|---------|---------|---------|
|사용자가 시작한 모임 채널 모임 만료  |채널에서 **지금 Meet 허용을 해제합니다.**|사용자가 시작한 채널 모임 모임에 참가할 수 없습니다.         |
|사용자가 예약한 채널 모임 만료   |채널 모임 **허용을 해제합니다.**         |사용자가 예약한 채널 모임에는 아무도 참가할 수 없습니다. 이렇게 하면 사용자가 다음에 참가할 수 없습니다.<ul><li>과거에 발생한 채널 모임입니다.</li> <li>향후에 예정된 모임이 아직 발생하지 않은 채널 모임입니다.</li><li>향후 재발 채널 모임의 인스턴스입니다.</li></ul>       |
|사용자가 예약한 비공개 모임 만료    |비공개 **모임**  허용을 해제하고 Outlook 추가 기능 **허용을 해제합니다.**          |사용자가 예약한 비공개 모임에는 아무도 참가할 수 없습니다. 이렇게 하면 사용자가 다음에 참가할 수 없습니다. <ul><li>과거에 발생한 비공개 모임입니다.</li> <li>향후에 예정된 비공개 모임이 아직 발생하지 않았습니다.</li><li>비공개 모임이 재개될 예정인 경우</li></ul> 비공개 **모임** 예약 및 **Outlook** 추가 기능 허용 모두 사용자가 예약한 비공개 모임을 만료하려면 해제해야 합니다. 한 설정이 해제되고 다른 설정이 설정되면 기존 모임의 모임 참가 링크 및 회의 신원이 활성 상태로 유지되고 만료되지 않습니다.      |
|사용자가 시작한 비공개 모임 만료  |비공개 **모임에서 모임 허용을 해제합니다.**          |누구도 사용자가 시작한 비공개 모임에 참가할 수 없습니다.         |

사용자가 이전에 예약했거나 특정 사용자가 시작한 모임에 액세스하도록 하려는 경우 다음을 할 수 있습니다.

- 해당 사용자의 모임 정책 설정을 켜면 됩니다.
- 해당 사용자의 모임 정책 설정을 해제하고 정책 설정을 사용하도록 설정된 다른 사용자가 만료된 모임을 대체할 새 모임을 만들게 합니다.

> [!NOTE]
> 관리자와 같은 다른 사람을 대신하여 모임 초대를 보낼 수 있는 권한이 부여된 대리인이 모임을 보낸 경우, 사용 권한을 부여한 사용자(관리자)에게 모임 정책 설정이 적용됩니다.

## <a name="related-topics"></a>관련 항목

[Teams에서 모임 정책 관리](meeting-policies-in-teams.md)

[Teams에서 사용자에게 정책 할당](assign-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)