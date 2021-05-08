---
title: 온라인에서 설정이 변경될 때 사용자에게 비즈니스용 Skype 전자 메일
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
description: '온라인에서 전화 접속 회의 설정이 변경될 때 사용자에게 전자 메일로 자동으로 전송되는 비즈니스용 Skype 대해 자세히 알아보습니다. '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237344"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>온라인에서 설정이 변경될 때 사용자에게 비즈니스용 Skype 전자 메일

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 전자 메일에서 자동 전자 메일 정보를 Microsoft Teams 설정이 변경될 때 사용자에게 전송된 전자 메일을 [Microsoft Teams.](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)

Microsoft를 오디오 회의 공급자로 [](set-up-audio-conferencing.md) 사용하여 오디오 회의를 사용하도록 설정된 사용자에게 전자 메일이 자동으로 전송됩니다.
  
기본적으로 오디오 회의를 사용하도록 설정된 사용자에게 전송되는 4가지 유형의 전자 메일이 있습니다. 그러나 사용자에게 보낸 전자 메일의 수를 제한하려는 경우 해제할 수 있습니다. 다음이 Microsoft 365 또는 Office 365 오디오 회의가 사용자의 전자 메일로 전송됩니다.
  
- **오디오 회의 라이선스가 사용자에게 할당되거나 오디오 회의 공급자를 Microsoft로 변경할 때 할당됩니다.**
    
     이 전자 메일에는 회의 ID, 모임의 기본 전화 번호, 사용자의 오디오 회의 PIN 및 사용자에 대한 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype 온라인 모임 업데이트 도구를 사용하는 지침 및 링크가 포함됩니다. 오디오 [비즈니스용 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 라이선스 할당 또는 Microsoft를 오디오 회의 공급자로 [할당을 참조하세요.](assign-microsoft-as-the-audio-conferencing-provider.md)
    
    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약한 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [아이디를 설정할 수 있습니다.](./reset-a-conference-id-for-a-user.md) 
  
    다음은 이 전자 메일의 예입니다.
    
     ![비즈니스용 Skype 라이선스 확인](../images/audio-conferencing-user-enabled.png)
  
    추가 기능 라이선스를 비즈니스용 Skype 를 참조하여 비즈니스용 Skype [수 있습니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    
- **사용자의 회의 ID 또는 기본 전화 회의 전화 번호가 변경됩니다.**
    
    이 전자 메일에는 사용자에 대한 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype 온라인 모임 업데이트 도구를 사용하는 지침 및 링크가 포함되어 있습니다. 그러나 이 전자 메일에는 사용자의 오디오 회의 PIN이 포함되어 없습니다. 사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user.md)
    
    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약한 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [아이디를 설정할 수 있습니다.](./reset-a-conference-id-for-a-user.md) 
  
    다음은 이 전자 메일의 예입니다.
    
     ![전화 접속 회의 정보가 변경되었습니다.](../images/audio-conferencing-info-change.png)
  
- **사용자의 오디오 회의 PIN이 재설정됩니다.**
    
    이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 회의 ID 및 사용자의 기본 전화 번호가 포함되어 있습니다. 오디오 회의 PIN 재설정을 [참조합니다.](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약한 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [아이디를 설정할 수 있습니다.](./reset-a-conference-id-for-a-user.md) 
  
    다음은 이 전자 메일의 예입니다.
    
     ![전화 접속 회의 PIN이 변경되었습니다.](../images/audio-conferencing-pin-has-changed.png)
  
- **사용자의 라이선스가 제거되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경되는 경우.**
    
    오디오 회의  라이선스가 사용자에서 제거되거나 Microsoft에서 타사 오디오 회의 공급자로 사용자의 오디오 회의 공급자를 변경하거나 공급자를 **없음으로** 설정할 때 발생합니다. 이 전자 메일에는 기본 전화 번호 또는 회의 ID와 같은 오디오 회의 특정 정보를 제거하기 위해 비즈니스용 Skype 온라인 모임 업데이트 도구를 사용하는 사용자에 대한 지침 및 정보가 포함되어 있습니다.
    
    에 대한 라이선스 [할당 또는 제거를 비즈니스용 Microsoft 365 앱.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)
    
    다음은 이 전자 메일의 예입니다.
    
     ![전화 접속 회의가 꺼져 있습니다.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>전송된 전자 메일 메시지를 변경합니다.

전자 메일 주소 및 연락처 정보에 포함된 표시 이름을 포함하여 사용자에게 자동으로 전송되는 전자 메일을 변경할 *수* 있습니다. 기본적으로 전자 메일의 발신자는 Microsoft 365 Office 365 있지만 전자 메일 주소 및 표시 이름을 Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet을 사용하여 변경할 수 있습니다. 사용자에게 전자 메일을 보내는 전자 메일 주소를 변경하려면 다음을 해야 합니다.
  
- _SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력합니다.
    
- _SendEmailFromDisplayName_ 매개 변수에 전자 메일 표시 이름을 입력합니다.
    
- _SendEmailOverride 매개_ 변수를 _True로 설정합니다._
    
다음을 실행하여 사용자에게 보낸 전자 메일(예: 전자 메일 주소 및 전자 메일의 표시 이름)을 변경할 수 있습니다.
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  전자 메일 주소 정보를 변경하려면 환경의 인바운드 전자 메일 정책에서 주소에서 지정된 사용자 지정에서 오는 전자 메일을 허용하는지 확인해야 합니다. 연락처 정보를 다시 보호하기로 결정한 경우 전자 메일이 사용자에게 올바르게 전송된지 확인해야 합니다.  조직에서 한 사용자와 함께 테스트하여 이 작업을 수행하면 됩니다.
  
[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>전자 메일을 보내지 못하게 하려는 경우 어떻게 하나요?

사용자에게 전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 라이선스를 할당한 경우에도 전자 메일이 전송되지 않습니다. 이 경우 회의 ID, 기본 회의 전화 번호 및 더 중요한 것은 해당 오디오 회의 PIN이 사용자에게 전송되지 않습니다. 이 경우 사용자에게 별도의 전자 메일을 보내거나 호출하여 사용자에게 알려야 합니다.
  
기본적으로 전자 메일은 사용자에게 전송되지만 오디오 회의를 위해 전자 메일을 받지 못하게 하려는 경우 비즈니스용 Skype 관리 센터 또는 Windows PowerShell. 
 
![관리 센터를 사용하여 비즈니스용 Skype 로고를 비즈니스용 Skype ](../images/sfb-logo-30x30.png) **아이콘**  
    
1. 관리 **비즈니스용 Skype** 왼쪽 탐색에서 오디오 회의 Microsoft 브리지 설정으로   >  **이동합니다.**
    
2. Microsoft **브리지 설정 페이지에서** 오디오 회의 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기 를 선택하거나 선택 **취소합니다.** 
    
3. **저장** 을 클릭합니다. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Windows PowerShell**
  
1. 다음을 실행하여 모든 사용자 전자 메일 보내기 기능을 사용하지 않도록 설정합니다.
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.
  
## <a name="what-else-should-you-know-about-this-email"></a>이 전자 메일에 대해 알아야 할 다른 것은 무엇입니까?

- 사용자에게 전자 메일을 자동으로 전송하도록 설정하고 사용하지 않도록 설정하는 데 대한 자세한 내용은 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 을 [참조하세요.](enable-or-disable-sending-emails-when-their-settings-change.md)
    
- 사용자가 오디오 정보를 잃어버려 모든 오디오 정보를 해당 사용자에게 보낼 수 있는 경우도 있습니다. 사용자에 대한 오디오 회의 속성 아래에서 비즈니스용 Skype  관리 센터를 사용하여 전자 메일을 통해 회의 정보 보내기 를 클릭하여 이 작업을 할 수 있습니다. 오디오 회의 정보를 통해 사용자에게 전자 메일 [보내기 를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md) 그러나 이 정보는 오디오 회의 PIN을 포함하지 않습니다.
    
    다음은 해당 전자 메일로 전송될 이 전자 메일의 예입니다.
    
     ![전화 접속 회의 전자 메일](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 기본적으로 전자 메일의 발신자는 Microsoft 365 Office 365 있지만 전자 메일 주소 및 표시 이름을 Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet을 사용하여 변경할 수 있습니다.
    
- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 많은 사용자에 대한 설정을 한 Microsoft 365 경우와 같이 관리 센터를 사용하는 것만 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 주제

[오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information.md)
