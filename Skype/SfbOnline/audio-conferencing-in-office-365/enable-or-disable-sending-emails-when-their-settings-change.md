---
title: 비즈니스용 Skype Online에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 하도록 설정
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '고정 변경 또는 기본 회의 번호와 같은 설정이 변경될 때 사용자에게 전자 메일을 보내지 않도록 Skype를 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164267"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 하도록 설정

> [!Note]
> Microsoft Teams에서 전자 메일 보내기 기능을 설정하거나 사용하지 않도록 설정하려면 Microsoft Teams에서 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 을 [참조하세요.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

오디오 회의를 사용하도록 설정하면 사용자에게 전자 메일로 자동으로 알림이 전송됩니다. 그러나 비즈니스용 Skype 사용자에게 전송되는 전자 메일 수를 줄이는 경우도 있을 수 있습니다. 이러한 경우 전자 메일 보내기 기능을 사용하지 않도록 설정할 수 있습니다.
  
전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 오디오 회의를 사용하도록 설정하거나 사용하지 않도록 설정한 경우, PIN이 재설정되는 경우, 전화 회의 ID와 기본 회의 전화 번호가 변경되는 경우를 포함하여 오디오 회의 전자 메일이 사용자에게 전송되지 않습니다.
  
오디오 회의를 사용하도록 설정하면 사용자에게 전송된 전자 메일의 예는 다음과 같습니다.
  
![오디오 회의 전자 메일](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>사용자에게 전자 메일이 전송되는 경우

- 오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.
    
  - 오디오 **회의** 라이선스가 할당된 경우
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정하는 경우
    
  - 사용자의 회의 ID를 수동으로 재설정하는 경우.
    
  - 오디오 **회의** 라이선스가 제거되면
    
  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft로 변경된 경우


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>사용자에게 전자 메일 보내기 사용 또는 사용 안 하도록 설정

비즈니스용 Skype 관리 센터 또는 Windows PowerShell 전자 메일을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.

 
![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**
    
1. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오 회의를 클릭합니다.**
    
2. Microsoft **브리지 설정** 페이지에서 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기를 선택하거나 선택 **취소합니다.**
    
3. **저장** 을 클릭합니다.
    
    > [!TIP]
    > 오디오 회의 사용자로 이동하고 사용자를 선택하고 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을  >  보낼 **수도 있습니다.**  이렇게 하면 전화 회의 ID와 전화 회의 전화 번호만 포함하지만 PIN은 포함하지 않는 전자 메일이 전송됩니다.  자세한 [내용은 오디오](send-an-email-to-a-user-with-their-dial-in-information.md) 회의 정보가 있는 사용자에게 전자 메일 보내기를 참조하세요.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**다음 Windows PowerShell**
  
- 다음을 실행하여 전자 메일 보내기 기능을 사용하지 않도록 설정합니다. 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    이 cmdlet에 대한 도움말은 [Set-CsOnlineDialInConferencingTenantSettings를 참조합니다.](https://go.microsoft.com/fwlink/?LinkId=715757)
    
## <a name="what-else-should-you-know"></a>알아야 할 다른 것은 무엇입니까?

- 자동 전자 메일을 사용하지 않도록 설정한 경우 비즈니스용 Skype 관리 센터를 사용하여 전화 회의 ID 및 전화 번호로 전자 메일 보내기를 수동으로 트리거할 수 있습니다. 그러나 이렇게 하는 경우 PIN은 포함되지 않습니다. 오디오 회의 PIN을 다시 설정하고 전자 메일 보내기 기능을 사용하지 않도록 설정하려면 다른 방법으로 사용자에게 보내야 합니다.
    
- 비즈니스용 Skype 관리 센터 또는 전자 메일 센터를 사용하여 사용자에게 전자 메일을 보내지 않도록 설정할 Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 이러한 cmdlet을 사용하여 시간을 절약하거나 자동화할 수 있습니다.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자를 위한 설정을 변경할 때도 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경될 때 사용자에게 전송된 전자 메일](emails-sent-to-users-when-their-settings-change.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information.md)


