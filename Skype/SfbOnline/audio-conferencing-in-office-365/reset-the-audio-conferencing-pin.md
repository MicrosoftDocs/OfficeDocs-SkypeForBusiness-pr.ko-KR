---
title: 온라인에서 오디오 회의 PIN 비즈니스용 Skype 재설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'PINS에 대해 알아야 할 것 및 온라인에서 PINS를 다시 설정하는 비즈니스용 Skype 알아 세요. '
ms.openlocfilehash: 79568b3b050f456d64ba4dfc9f1c86b46401536274caf88a4cbc51f20cbd14cc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310247"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>온라인에서 오디오 회의 PIN 비즈니스용 Skype 재설정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 에서 오디오 회의 PI를 다시 설정하는 Microsoft Teams 의 오디오 회의 PIN 재설정을 [Microsoft Teams.](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

PIN은 오디오 회의를 사용하도록 설정된 각 사용자에 대해 비즈니스용 Skype 수로 만든 코드입니다. 오디오 회의 PI는 모임 이끌이가 모임 이끌이로 식별하고 전화를 통해 모임을 시작할 수 있도록 하는 데 사용됩니다. 모임을 비즈니스용 Skype 앱을 사용하는 경우 PIN이 필요하지 않습니다. 사용자가 PIN을 잊어버려 오디오 회의를 사용하도록 설정한 경우 보낸 전자 메일에서 해당 PIN을 찾을 수 없는 경우 관리자가 PIN을 다시 설정할 수 있습니다.
  
모임은 인증된 사용자가 앱을 사용하여 비즈니스용 Skype 또는 이끌이가 휴대폰을 통해 자신의 PIN과 조인할 때 시작할 수 있습니다. 모임을 시작하려면 PIN이 필요한 경우 전화를 통해 참가하는 사용자는 로비에 배치됩니다. 모임이 시작될 때까지 음악이 대기 중입니다. 모임 이끌이가 전화를 통해 모임을 시작하는 데 PIN이 필요하지 않은 경우 발신자는 모임에 참가할 때 PIN을 제공해야 합니다.
  
## <a name="reset-a-users-pin"></a>사용자의 PIN 재설정

1. 직장 또는 학교 계정으로 로그인합니다.
    
2. 관리 센터 > 비즈니스용 Skype **로** 이동하고 왼쪽 탐색에서 오디오 회의 **를 클릭합니다.**
    
3. 사용자를 **클릭하고** PIN을 다시 설정할 사용자를 선택합니다.
    
4. 작업 창의 **PIN** 아래에서 **재설정을 클릭합니다.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>사용자가 자신의 PIN을 다시 설정하도록 설정

전화 접속 회의 페이지에서 PIN 재설정 옵션을 사용하여 **PIN을** 재설정할 **수** 있습니다. 이 페이지는 다음 세 가지 방법 중 하나에서 액세스할 수 있습니다.

* 브라우저에서 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) 로 이동합니다.
* 비즈니스용 Skype 옵션 옆에 있는  메뉴 표시 화살표를 클릭한 다음 도구 전화 접속 회의   >  설정.
* 비즈니스용 Skype 옵션을 클릭하고 왼쪽 메뉴에서 전달을 클릭한 다음, 추가 통화 설정 섹션에서 온라인 **설정 편집을**  **클릭합니다.** 

## <a name="what-else-should-you-know-about-pins"></a>PINS에 대해 알아야 할 다른 것은 무엇입니까?

- 보안을 위해 PIN은 PIN이 재설정된 경우 관리자에게만 한 번만 표시됩니다. 관리자가 PIN을 다시 설정한 후 PIN은 비즈니스용 Skype Windows PowerShell Get-CsCsOnlineDialInConfencingUser 관리  센터에 *************로 나열됩니다.
    
- 사용자에게 자동으로 전자 메일을 보내는 것은 기본적으로 사용되며, 사용자가 오디오 회의를 사용하도록 설정하거나 PIN이 재설정될 때 해당 PIN이 있는 전자 메일을 받게 됩니다. 하지만 자동으로 전자 메일을 보내지 않도록 설정한 경우 PIN 재설정 전자 메일이 사용자에게 전송되지 않고 PIN 정보를 사용자에게 수동으로 보내야 합니다.
    
- 모임이 시작되면 로비의 모든 사용자가 자동으로 참가합니다. 예를 들어 두 참가자가 모임을 시작하기 전에 모임에 참가하려고 하면 로비에 배치되고 대기 중이던 음악을 듣게 되고 모임 이끌이가 전화를 통해 PIN을 사용하여 조인하면 모임이 시작되고 로비의 참가자가 모임에 참가합니다.
    
- 기본 설정은 익명 호출자에 의해 모임을 시작하도록 허용하지 않는 것입니다.
    
- 오디오 회의에 사용자를 사용하도록 설정하면 기본적으로 회의 정보와 해당 PIN이 포함된 전자 메일이 전송됩니다. PIN을 다시 설정하면 새 PIN이 사용자에 대해 설정된 기본 SMTP 주소(별칭)에 전자 메일로 보내지기 때문에 사용자에게 Microsoft 365 Office 365 사서함이 있어야 합니다.
    
- 오디오 회의를 설정할 때 조직의 PI에 필요한 숫자를 설정합니다. PINS는 4~12자리일 수 있습니다. 기본값은 5입니다. PIN 길이 설정을 변경하는 경우 설정은 새로 생성된 PI에만 적용되고 오디오 회의에 사용하도록 설정된 기존 사용자의 PIN 설정에는 적용되지 않습니다. 오디오 회의 모임에 대한 PIN 길이 설정 을 [참조합니다.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- 기본적으로 전자 메일은 사용자의 기본 SMTP Microsoft 365 Office 365 설정됩니다. 핫메일 또는 MSN 전자 메일 주소와 같은 전자 메일을 Microsoft 365 또는 Office 365 주소로 보낼 수 있습니다. 기본 전자 메일 주소를 사용하여 기본 전자 메일 주소를 Windows PowerShell. 이 기능은 사용자에게 Exchange 사서함이 없는 Microsoft 365 Office 365.
    
- 전자 메일이 전송되는 기본 사용자 주소를 다시 지정하려면 테넌트 관리자는 -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "Set-CsOnlineDialInConferencingUser"u@hotmail.com. SendEmail 매개 변수는 사용자의 전자 메일 주소를 다시 정의하는 데 필요합니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet을 사용할 수 있습니다.
    
- 다음을 실행하여 Amos Marble에 대한 PIN을 설정할 수 있습니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 사용자에 대한 설정을 한 Microsoft 365 관리 센터 설정 변경 시와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[사용자의 회의 ID 다시 설정](reset-a-conference-id-for-a-user.md)
