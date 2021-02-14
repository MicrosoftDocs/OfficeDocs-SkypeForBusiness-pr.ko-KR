---
title: 비즈니스용 Skype Online에서 설정이 변경될 때 사용자에게 전송된 전자 메일
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '비즈니스용 Skype Online에서 전화 접속 회의 설정이 변경될 때 사용자에게 전자 메일로 자동으로 전송되는 정보에 대해 자세히 배워야 합니다. '
ms.openlocfilehash: e2f58bfe582b7adc6672c06bec0e90571ff9a96a
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164277"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 설정이 변경될 때 사용자에게 전송된 전자 메일

> [!Note]
> Microsoft Teams에서 자동 전자 메일 정보를 찾고 있는 경우 Microsoft Teams에서 설정이 변경될 때 사용자에게 전송된 전자 메일을 [참조하세요.](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)

오디오 회의 공급자로 Microsoft를 [](set-up-audio-conferencing.md) 사용하여 오디오 회의를 사용하도록 설정된 사용자에게 전자 메일이 자동으로 전송됩니다.
  
기본적으로 오디오 회의를 사용하도록 설정된 사용자에게 전송되는 전자 메일에는 네 가지 유형이 있습니다. 그러나 사용자에게 전송된 전자 메일 수를 제한하려는 경우 해제할 수 있습니다. Microsoft 365 또는 Office 365의 오디오 회의는 다음의 경우 사용자의 전자 메일로 전자 메일을 전송합니다.
  
- **오디오 회의 라이선스가 할당되거나 오디오 회의 공급자를 Microsoft로 변경할 때 할당됩니다.**
    
     이 전자 메일에는 회의 ID, 모임의 기본 전화 회의 전화 번호, 사용자의 오디오 회의 PIN, 사용자의 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용하는 지침 및 링크가 포함됩니다. 비즈니스용 [Skype 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 할당 또는 오디오 회의 [공급자로 Microsoft 할당을 참조하세요.](assign-microsoft-as-the-audio-conferencing-provider.md)
    
    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [ID를](using-audio-conferencing-dynamic-ids-in-your-organization.md)설정할 수 있습니다. 
  
    이 전자 메일의 예는 다음과 같습니다.
    
     ![비즈니스용 Skype 라이선스 확인](../images/audio-conferencing-user-enabled.png)
  
    비즈니스용 Skype 추가 기능 라이선스를 참조하여 비즈니스용 Skype 라이선스에 대한 자세한 [정보를 확인할 수 있습니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    
- **사용자의 전화 회의 ID 또는 기본 전화 회의 전화 번호가 변경됩니다.**
    
    이 전자 메일에는 사용자의 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용하는 전화 회의 ID, 기본 전화 회의 번호 및 지침 및 링크가 포함되어 있습니다. 하지만 이 전자 메일에는 사용자의 오디오 회의 PIN이 포함되어 없습니다. 사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user.md)
    
    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [ID를](using-audio-conferencing-dynamic-ids-in-your-organization.md)설정할 수 있습니다. 
  
    이 전자 메일의 예는 다음과 같습니다.
    
     ![전화 접속 회의 정보가 변경되었습니다.](../images/audio-conferencing-info-change.png)
  
- **사용자의 오디오 회의 PIN이 다시 설정됩니다.**
    
    이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 전화 회의 ID 및 사용자의 기본 전화 회의 전화 번호가 포함되어 있습니다. 오디오 [회의 PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [ID를](using-audio-conferencing-dynamic-ids-in-your-organization.md)설정할 수 있습니다. 
  
    이 전자 메일의 예는 다음과 같습니다.
    
     ![전화 접속 회의 PIN이 변경되었습니다.](../images/audio-conferencing-pin-has-changed.png)
  
- **사용자의 라이선스가 제거되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경되면 제거됩니다.**
    
    이 문제는  오디오 회의 라이선스가 사용자로부터 제거되거나 사용자의 오디오 회의 공급자를 Microsoft에서 타사 오디오 회의 공급자로 변경하거나 공급자를 **None으로** 설정할 때 발생합니다. 이 전자 메일에는 사용자가 비즈니스용 Skype Online 모임 업데이트 도구를 사용하여 기본 전화 회의 전화 번호 또는 전화 회의 ID와 같은 오디오 회의 특정 정보를 제거할 수 있는 지침과 정보가 포함되어 있습니다.
    
    비즈니스용 [Microsoft 365 앱에 대한](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)라이선스 할당 또는 제거를 참조하세요.
    
    이 전자 메일의 예는 다음과 같습니다.
    
     ![전화 접속 회의가 꺼져 있습니다.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>전송된 전자 메일 메시지를 변경합니다.

보낸 메일 주소 및 보낸 메일 정보에 포함된 표시 이름을 포함하여 사용자에게 자동으로 전송되는 전자 메일을 변경할 *수* 있습니다. 기본적으로 전자 메일의 보낸 사람이 Microsoft 365 또는 Office 365에서 전송되지만, Windows PowerShell [및 Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일 주소와 표시 이름을 변경할 수 있습니다. 사용자에게 전자 메일을 보내는 전자 메일 주소를 변경하려면 다음을 해야 합니다.
  
- _SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력합니다.
    
- _SendEmailFromDisplayName_ 매개 변수에 전자 메일 표시 이름을 입력합니다.
    
- _SendEmailOverride_ 매개 변수를 _True로 설정_
    
다음을 실행하여 사용자에게 전송된 전자 메일(예: 전자 메일이 전송된 전자 메일 주소 및 전자 메일의 표시 이름)을 변경할 수 있습니다.
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  전자 메일 주소 정보를 변경하려는 경우 사용자 환경의 인바운드 전자 메일 정책에서 주소에서 지정된 사용자 지정에서 오는 전자 메일을 허용하는지 확인해야 합니다. 보낸 메일 정보를 다시  설정하기로 결정한 경우 전자 메일이 사용자에게 올바르게 전송됐는지 확인해야 합니다. 조직의 한 사용자로 이 작업을 테스트하여 이 작업을 할 수 있습니다.
  
[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>전자 메일을 보내지 못하게 하려는 경우 어떻게 하나요?

사용자에게 전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자에게 라이선스가 할당된 경우에도 전자 메일이 전송되지 않습니다. 이 경우 전화 회의 ID, 기본 회의 전화 번호 및 무엇보다도 오디오 회의 PIN은 사용자에게 전송되지 않습니다. 이 경우 사용자에게 별도의 전자 메일을 보내거나 전화를 걸고 알려야 합니다.
  
기본적으로 전자 메일은 사용자에게 전송되지만, 사용자가 오디오 회의에 대한 전자 메일을 받지 못하게 하려는 경우 비즈니스용 Skype 관리 센터 또는 Windows PowerShell. 
 
![비즈니스용 Skype 관리 센터를 사용하여 비즈니스용 Skype 로고를 ](../images/sfb-logo-30x30.png) **보여주는 아이콘**  
    
1. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**
    
2. Microsoft **브리지 설정 페이지에서** 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일을 보내거나 선택 **취소합니다.** 
    
3. **저장** 을 클릭합니다. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**다음 Windows PowerShell**
  
1. 다음을 실행하여 모든 사용자 전자 메일 보내기 기능을 사용하지 않도록 설정합니다.
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.
  
## <a name="what-else-should-you-know-about-this-email"></a>이 전자 메일에 대해 알아야 할 다른 것은 무엇입니까?

- 사용자에게 자동으로 전자 메일을 보내거나 사용하지 않도록 설정하는 데 대한 자세한 내용은 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 [을 참조하세요.](enable-or-disable-sending-emails-when-their-settings-change.md)
    
- 사용자가 오디오 정보를 잃어버려 모든 오디오 정보를 사용자에게 보낼 수 있는 경우도 있습니다. 비즈니스용 Skype 관리 센터를 사용하고 사용자의 오디오  회의 속성 아래에서 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 이 작업을 할 수 있습니다. 오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md) 그러나 이 정보는 오디오 회의 PIN을 포함하지 않습니다.
    
    다음은 전송될 이 전자 메일의 예입니다.
    
     ![전화 접속 회의 전자 메일](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 기본적으로 전자 메일의 보낸 사람이 Microsoft 365 또는 Office 365에서 전송되지만, Windows PowerShell [및 Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.
    
- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자를 위한 설정을 변경할 때도 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information.md)
