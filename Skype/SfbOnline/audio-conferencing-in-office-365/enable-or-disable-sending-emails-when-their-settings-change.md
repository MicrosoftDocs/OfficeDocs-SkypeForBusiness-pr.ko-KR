---
title: 온라인에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 비즈니스용 Skype 사용 또는 사용하지 않도록 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '고정 설정이 변경되거나 기본 회의 번호가 변경될 Skype 사용자에게 전자 메일을 보내지 않도록 설정하거나 사용하지 않도록 설정하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 2f322f9cfc9ba7daa60d030c043bdfda4d511d2c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728027"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>온라인에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 비즈니스용 Skype 사용 또는 사용하지 않도록 설정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 전자 메일 보내기 를 사용하도록 설정하거나 사용하지 않도록 설정하려는 Microsoft Teams 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 [Microsoft Teams.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

오디오 회의를 사용하도록 설정하면 사용자에게 전자 메일로 자동으로 알림이 전송됩니다. 그러나 사용자에게 전송되는 전자 메일의 수를 줄이지 않을 비즈니스용 Skype 있습니다. 이러한 경우 전자 메일 보내기 기능을 사용하지 않도록 설정할 수 있습니다.
  
전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정한 경우, PIN이 재설정되는 경우 및 회의 ID 및 기본 회의 전화 번호가 변경될 때 전자 메일을 포함하여 오디오 회의 전자 메일이 사용자에게 전송되지 않습니다.
  
다음은 오디오 회의를 사용하도록 설정하면 사용자에게 전송된 전자 메일의 예입니다.
  
![오디오 회의 전자 메일입니다.](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>사용자에게 전자 메일은 언제 전송하나요?

- 오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.
    
  - 오디오 **회의** 라이선스가 할당되는 경우.
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정하면 됩니다.
    
  - 사용자의 회의 ID를 수동으로 다시 설정하면 됩니다.
    
  - 오디오 **회의** 라이선스가 해당 라이선스에서 제거되면
    
  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft로 변경된 경우


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>사용자에게 전자 메일이 전송되지 않도록 설정하거나 사용하지 않도록 설정

관리자 센터 또는 비즈니스용 Skype 사용하여 Windows PowerShell 전자 메일을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

 
![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용**
    
1. 관리 **비즈니스용 Skype** 왼쪽 탐색에서 오디오 회의 **를 클릭합니다.**
    
2. Microsoft **브리지 설정 페이지에서** 오디오 회의 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기 를 선택하거나 선택 **취소합니다.**
    
3. **저장** 을 클릭합니다.
    
    > [!TIP]
    > 오디오 회의 사용자로 이동하고 사용자를 선택하고 전자 메일을 통해 회의 정보 보내기 를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을  >  보낼 **수도 있습니다.**  이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함하지만 PIN이 아닌 전자 메일이 전송됩니다.  자세한 [내용은](send-an-email-to-a-user-with-their-dial-in-information.md) 오디오 회의 정보를 통해 사용자에게 전자 메일 보내기 를 참조하세요.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Windows PowerShell**
  
- 다음을 실행하여 전자 메일 전송을 사용하지 않도록 설정합니다. 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    이 cmdlet에 대한 도움말은 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)를 참조합니다.
    
## <a name="what-else-should-you-know"></a>또 어떤 것을 알아야 하나요?

- 자동 전자 메일을 사용하지 않도록 설정하면 관리 센터를 사용하여 전화 회의 ID 및 전화 번호가 있는 전자 메일 보내기를 수동으로 비즈니스용 Skype 수 있습니다. 그러나 이렇게 하는 경우 PIN은 포함되지 않습니다. 오디오 회의 PIN을 다시 설정하고 전자 메일을 보내지 않도록 설정하려는 경우 다른 방법으로 사용자에게 보내야 합니다.
    
- 관리자 센터 또는 비즈니스용 Skype 사용하여 사용자에게 전자 메일 보내기 Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 이러한 cmdlet을 사용하여 시간을 절약하거나 자동화할 수 있습니다.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 사용자에 대한 설정을 한 Microsoft 365 관리 센터 설정하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경될 때 사용자에게 전송된 전자 메일](emails-sent-to-users-when-their-settings-change.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information.md)
