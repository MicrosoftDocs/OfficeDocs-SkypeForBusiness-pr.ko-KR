---
title: 오디오 회의 설정이 변경되는 경우 Email 옵션
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: 'Teams에서 고정 변경 또는 기본 회의 번호 변경과 같은 설정이 변경되는 경우 Microsoft Teams에서 사용자에게 전자 메일을 보내지 않도록 설정하거나 사용하지 않도록 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642109"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Microsoft Teams에서 오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함

사용자는 오디오 회의를 사용하도록 설정하면 전자 메일로 자동으로 알림을 받습니다. 그러나 Microsoft Teams 사용자에게 전송되는 전자 메일 수를 줄이려는 경우가 있을 수 있습니다. 이러한 경우 전자 메일 보내기를 사용하지 않도록 설정할 수 있습니다.
  
전자 메일 보내기를 사용하지 않도록 설정하면 사용자가 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정한 경우, PIN이 재설정되는 경우, 회의 ID 및 기본 회의 전화 번호가 변경되는 경우를 위한 전자 메일을 포함하여 오디오 회의 전자 메일이 사용자에게 전송되지 않습니다.
  
다음은 오디오 회의를 사용하도록 설정된 경우 사용자에게 전송되는 전자 메일의 예입니다.
  
![오디오 회의 전자 메일 메시지의 예입니다.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>사용자에게 전자 메일을 보내는 시기는 언제인가요?

- 오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송되는 여러 전자 메일이 있습니다.

  - **오디오 회의** 라이선스가 할당된 경우

  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정하는 경우

  - 사용자의 전화 회의 ID를 수동으로 다시 설정하는 경우

  - **오디오 회의** 라이선스가 제거된 경우

  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **None** 으로 변경되는 경우

  - 사용자의 오디오 회의 공급자가 Microsoft로 변경되는 경우

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>전자 메일이 사용자에게 전송되지 않도록 설정 또는 사용 안 함

Microsoft Teams 또는 Windows PowerShell 사용하여 사용자에게 전송된 전자 메일을 사용하거나 사용하지 않도록 설정할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창에서 **전화 접속 설정이 변경되면 자동으로 사용자에게 전자 메일을 보내도록** 설정하거나 사용하지 않도록 설정합니다.

4. **저장** 을 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Windows PowerShell 사용

Microsoft Teams PowerShell 모듈을 사용하여 다음을 실행할 수도 있습니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

[Set-CsOnlineDialInConferencingTenantSettings를](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.

자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.

## <a name="related-topics"></a>관련 주제

[오디오 회의 설정이 변경되면 사용자에게 보낸 전자 메일](emails-sent-to-users-when-their-settings-change-in-teams.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
