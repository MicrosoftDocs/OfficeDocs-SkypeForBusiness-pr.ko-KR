---
title: Teams에서 PIN 없이 휴대폰을 통해 오디오 회의 시작
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '익명 발신자가 Teams 관리 센터에서 모임에 참가하지 못하도록 설정하거나 사용하지 않도록 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641949"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams에서 PIN 없이 휴대폰을 통해 오디오 회의 시작

Microsoft Teams 모임 이끌이가 모임을 시작하지 않았기 때문에 모임 로비에서 모임에 전화를 걸어 음악을 듣는 사용자에게는 실망스러울 수 있습니다.
  
모임 이끌이가 모임에 전화하는 경우 기본적으로 모임을 시작하려면 PIN이 필요합니다. 누구나 모임에 전화를 걸 수 있고 PIN으로 모임을 시작하라는 메시지가 표시되지 않도록 설정할 수 있습니다. 관리 센터를 사용하여 단일 사용자에 대해 이 설정을 사용하거나 사용하지 않도록 설정할 수 있습니다.
  
누군가가 Microsoft Teams 앱에서 모임을 시작한 경우 모임 이끌이에게 PIN이 필요하지 않습니다. PIN은 모임 이끌이가 전화를 통해 모임에 참가하는 경우에만 필요합니다. 모임의 PIN은 **오디오 회의** 라이선스가 할당되고 오디오 회의를 사용하도록 설정된 경우 오디오 사용자에게 전송됩니다. 오디오 회의 [설정이 변경되면 사용자에게 자동으로 전송되는 오디오 회의 정보 및 전자 메일을 사용하여 사용자에게 전자 메일 보내기를](emails-sent-to-users-when-their-settings-change-in-teams.md) 참조하세요.[](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 발신자가 모임에 참가하지 못하도록 설정하거나 사용하지 않도록 설정

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 영역에서 **사용자를** 클릭합니다.

2. 목록에서 사용자를 선택한 다음 페이지 맨 위에 있는 **편집** 을 클릭합니다.

3. **오디오 회의** 옆에 있는 **편집** 을 클릭합니다.

4. **오디오 회의** 창에서 전화 접속 발신자를 사용하거나 사용하지 않도록 설정하는 **것이 모임의 첫 번째 사람이 될 수 있습니다**.

5. **적용** 을 클릭합니다.

### <a name="using-windows-powershell"></a>Windows PowerShell 사용

자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.

## <a name="what-else-should-you-know"></a>그 밖에 무엇을 알아야 할까요?

- PIN을 다시 설정하려면 [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md) 참조하세요.

- 익명 액세스를 사용하거나 모임을 시작하기 위해 PIN을 요구하지 않는 경우 다음을 사용할 수 없습니다.

  - 모임이 시작되지 않은 경우(모임에 아직 아무도 없음): 발신자가 이끌이인지 묻는 메시지가 표시됩니다. 예라고 하면 PIN을 입력하라는 메시지가 표시되고 PIN을 입력하면 모임이 시작되고 사용자가 모임에 참가합니다.

  - 모임이 이미 시작된 경우(다른 사람이 이미 모임에 있음): 발신자가 이끌이이고 PIN에 대한 메시지가 표시되지 않으면 호출자에게 메시지가 표시되지 않습니다. 모임이 이미 시작되었으며 호출자가 모임에 참가합니다.

- 익명 액세스를 사용하거나 모임을 시작하기 위해 PIN을 요구하지 않는 경우 다음을 사용할 수 있습니다.

  - 모임이 시작되지 않은 경우(모임에 아직 아무도 없음): 발신자가 이끌이인지 묻는 메시지가 표시되지 않으며 PIN에 대한 메시지가 표시되지 않습니다. 이끌이 설정이 해제되어 있으므로 모임이 시작되고 익명의 발신자가 모임에 참가합니다.

  - 모임이 이미 시작된 경우(다른 사람이 이미 모임에 있음): 발신자가 이끌이인지 묻는 메시지가 표시되지 않으며 PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되었으며 호출자가 모임에 참가합니다.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.
  
## <a name="related-topics"></a>관련 주제

[Microsoft Teams용 Microsoft 365에서 오디오 회의 체험 또는 구매](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
