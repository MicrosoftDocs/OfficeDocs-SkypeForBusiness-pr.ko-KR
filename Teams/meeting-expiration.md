---
title: Microsoft 팀에서 모임 정책 및 모임 만료
author: LanaChin
ms.author: v-lanac
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
description: 모임 정책 설정을 사용 하 여 Microsoft 팀에서 모임 만료를 제어 하는 방법에 대해 알아봅니다.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640994"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft 팀에서 모임 정책 및 모임 만료

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>개요

Microsoft 팀의 [모임 정책은](meeting-policies-in-teams.md) 조직의 사용자가 모임을 시작 하 고 예약할 수 있는지 여부와 사용자가 예약한 모임의 모임 참가자가 사용할 수 있는 기능을 제어 하는 데 사용 됩니다. 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. Microsoft 팀 관리 센터에서 모임 정책을 관리 하거나 [Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy), [New](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy), [Set](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy), CsTeamsMeetingPolicy를 [허용](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 하는 PowerShell cmdlet을 사용 합니다.

사용자가 모임을 시작 하 고 예약할 수 있는지 여부를 제어 하는 모임 정책 설정은 또한 사용자가 예약한 모임의 만료를 제어 합니다. 모임의 모임 참가 링크와 전화 회의 ID가 만료 되 면 아무도 모임에 참가할 수 없습니다. 다음 모임 정책 설정은 사용자가 팀에서 모임을 시작 하 고 예약할 수 있는지 여부를 결정 하 고이 문서 전체에서 해당 항목을 참조 합니다.

- [채널에서 모임 시작 허용](meeting-policies-in-teams.md#allow-meet-now-in-channels): 사용자가 채널에서 즉석 모임을 시작할 수 있는지 여부를 제어 합니다.
- [채널 모임 예약 허용](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): 사용자가 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.
- [개인 모임 예약 허용](meeting-policies-in-teams.md#allow-scheduling-private-meetings): 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다. 모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.
- [Outlook 추가 허용](meeting-policies-in-teams.md#allow-the-outlook-add-in): 사용자가 outlook에서 비공개 모임 일정을 예약할 수 있는지 여부를 제어 합니다. 모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.
- [비공개 모임에서 모임 시작 허용](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings): 사용자가 즉석 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.

이 설정은 기본적으로 설정 되어 있습니다. 이러한 설정을 끄면 해당 정책에 할당 된 모든 사용자가 해당 유형의 새 모임을 시작 하거나 예약할 수 없습니다. 이와 동시에 사용자가 이전에 시작 하거나 예약한 해당 유형의 모든 기존 모임의 모임 참가에 대 한 링크와 전화 회의 Id가 만료 됩니다.

예를 들어 사용자에 게 이러한 모임 정책 설정이 **On**으로 설정 되어 있는 모임 정책을 할당 한 다음 **채널에서 모임 시작 허용** 설정을 해제 하면 해당 사용자가 더 이상 채널에서 즉석 모임을 시작할 수 없으며 사용자가 이전에 만든 채널 모임 링크가 현재 만료 됩니다. 사용자는 다른 모임 유형을 시작 및 예약 하 고 다른 사용자가 구성한 모임에 참가할 수 있습니다.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>모임 참가 링크 및 전화 회의 ID가 만료 되 면 어떻게 되나요?

모임의 모임 참가 링크와 전화 회의 ID가 만료 되 면 아무도 모임에 참가할 수 없습니다. 사용자가 링크 또는 전화를 통해 모임에 참가 하려고 할 때 모임이 더 이상 제공 되지 않는다는 메시지가 표시 됩니다. 대화, 파일, 화이트 보드, 녹음/녹화, 모임 관련 기타 콘텐츠는 유지 되며 사용자는 계속 액세스할 수 있습니다.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>모임 정책 설정을 설정 하 고 해제 하면 어떻게 되나요?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>모임 정책 설정에서 해제로 전환

모임 정책 설정이 **On**으로 설정 되 면 정책이 지정 된 사용자는 해당 유형의 모임을 시작 하거나 예약할 수 있으며 모든 사람이 참가할 수 있습니다. 모임 정책 설정을 **해제**로 전환 하면 정책에 할당 된 사용자는 해당 유형의 새 모임을 시작 하거나 예약할 수 없으며 사용자가 이전에 예약한 기존 모임에 대 한 모임 참가 링크와 전화 회의 id가 만료 됩니다.

다른 사용자가 구성한 모임에 계속 참가할 수 있다는 것을 기억 하세요.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>모임 정책 설정을 설정에서 해제로 전환

모임 정책 **설정을 설정에서** **해제** 로 전환 하면 정책에 할당 된 사용자가 해당 유형의 모임을 시작 하거나 예약할 수 있습니다. 모임 정책 설정이 해제 된 다음 사용자에 대해 다시 설정 되 면 사용자가 구성한 이전에 예약 된 모든 모임이 활성 상태가 되 고, 다른 사용자가 모임 참가 링크 또는 휴대폰을 사용 하 여 참가할 수 있습니다.  

## <a name="meeting-expiration-scenarios"></a>모임 만료 시나리오

다음은이 문서에서 설명 하는 각 모임 정책 설정에 대해 모임 만료가 작동 하는 방식을 요약 한 것입니다. 

|원하는 경우 |방법  |모임 참가 동작  |
|---------|---------|---------|
|사용자가 시작 하는 즉시 채널 모임 모임 만료  |**채널에서 모임 시작을 사용**하지 않도록 설정 합니다.|사용자가 시작한 모임에는 채널이 모임에 참가할 수 없습니다.         |
|사용자가 예약한 채널 모임 만료   |**채널 모임 예약 허용**설정을 해제 합니다.         |사용자가 예약한 채널 모임에 참가할 수 없습니다. 이렇게 하면 사용자가 다음에 참여할 수 없습니다.<ul><li>과거에 발생 한 채널 모임</li> <li>향후에 예약 되지 않고 아직 발생 하지 않은 채널 모임</li><li>되풀이 채널 모임의 향후 인스턴스.</li></ul>       |
|사용자가 예약한 비공개 모임 만료    |**비공개 모임 예약 허용** *을 해제 하 고* **Outlook 추가 기능 허용**을 해제 합니다.          |사용자가 예약한 비공개 모임에 참가할 수 없습니다. 이렇게 하면 사용자가 다음에 참여할 수 없습니다. <ul><li>과거에 발생 한 비공개 모임.</li> <li>향후에 예정 된 개인 모임이 아직 발생 하지 않았습니다.</li><li>이후 되풀이 비공개 모임의 인스턴스</li></ul> 사용자가 예약한 비공개 모임을 만료 시키려면 **비공개 모임 예약** 및 **Outlook 추가 기능 허용** 을 해제 해야 합니다. 한 설정이 해제 되어 있고 다른 설정은 켜져 있는 경우 기존 모임의 모임 참가 링크와 회의 Id는 활성 상태로 유지 되며 만료 되지 않습니다.      |
|사용자가 시작 하는 비공개 모임 시작 모임 만료  |**비공개 모임에서 모임 시작 허용 기능을**해제 합니다.          |사용자가 시작한 비공개 모임 시작 모임에 아무도 참가할 수 없습니다.         |

이전에 특정 사용자가 예약 하거나 시작한 모임에 다른 사용자가 액세스 하도록 하려면 다음을 수행 합니다.

- 해당 사용자의 모임 정책 설정을 켭니다.
- 해당 사용자의 모임 정책 설정을 해제 하 고 정책 설정을 사용 하도록 다른 사용자에 게 새 모임을 만들어 만료 된 모임을 바꿉니다.

> [!NOTE]
> 대리인이 모임에 보낸 경우 관리자와 같이 다른 사람을 대신 하 여 모임 초대를 보낼 수 있는 권한을 부여한 경우 모임 정책 설정이 사용 권한을 부여한 사람에 게 적용 됩니다 (관리자).

## <a name="related-topics"></a>관련 항목

[팀에서 모임 정책 관리](meeting-policies-in-teams.md)

[팀에서 사용자에 게 정책 할당](assign-policies.md)

[Teams PowerShell 개요](teams-powershell-overview.md)