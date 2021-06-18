---
title: 오디오 회의 설정이 변경될 때 전자 메일 옵션
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '핀이 변경되거나 기본 회의 번호가 변경될 Skype 사용자에게 전자 메일을 보내지 않도록 설정하거나 사용하지 않도록 설정하는 Microsoft Teams. '
ms.openlocfilehash: 17c2864703eafa2c70709da0381f870abba58ad0
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004170"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 Microsoft Teams

오디오 회의를 사용하도록 설정하면 사용자에게 전자 메일로 자동으로 알림이 전송됩니다. 그러나 사용자에게 전송되는 전자 메일의 수를 줄이지 않을 Microsoft Teams 있습니다. 이러한 경우 전자 메일 보내기 기능을 사용하지 않도록 설정할 수 있습니다.
  
전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정한 경우, PIN이 재설정되는 경우 및 회의 ID 및 기본 회의 전화 번호가 변경될 때 전자 메일을 포함하여 오디오 회의 전자 메일이 사용자에게 전송되지 않습니다.
  
다음은 오디오 회의를 사용하도록 설정하면 사용자에게 전송된 전자 메일의 예입니다.
  
![오디오 회의 전자 메일 메시지의 예](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>사용자에게 전자 메일은 언제 전송하나요?

- 오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.
    
  - 오디오 **회의** 라이선스가 할당되는 경우.
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정하면 됩니다.
    
  - 사용자의 회의 ID를 수동으로 다시 설정하면 됩니다.
    
  - 오디오 **회의** 라이선스가 해당 라이선스에서 제거되면
    
  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft로 변경된 경우


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>사용자에게 전자 메일이 전송되지 않도록 설정하거나 사용하지 않도록 설정

사용자가 보낸 전자 Microsoft Teams Windows PowerShell 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. 브리지 **설정 창에서** 전화 접속 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기를 사용하도록 설정하거나 **사용하지 않도록 설정합니다.**

4. **저장** 을 클릭합니다.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell**
  
PowerShell 모듈을 사용하여 Microsoft Teams 실행할 수 있습니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

[Set-CsOnlineDialInConferencingTenantSettings를](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.

자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.

    
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [데이터를 사용하여 Office 365 관리하는 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
    
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경될 때 사용자에게 전송된 전자 메일](emails-sent-to-users-when-their-settings-change-in-teams.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
