---
title: 온라인에서 PIN 없이 전화로 비즈니스용 Skype 시작
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '익명 호출자는 관리자 센터에서 모임에 참가하거나 PowerShell 스크립트를 사용하여 비즈니스용 Skype 사용하지 않도록 설정하거나 사용하지 않도록 설정하는 방법을 알아보습니다. '
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237594"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>온라인에서 PIN 없이 전화로 비즈니스용 Skype 시작

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 에서 PIN 없이 오디오 회의를 시작하는 Microsoft Teams 에서 PIN 없이 전화로 오디오 회의 [시작을 Microsoft Teams.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)

모임 이끌이가 모임을 시작하지 않은 경우 모임의 로비에서 음악이 들리는 모임에 비즈니스용 Skype 사용자가 좌절할 수 있습니다. 
  
모임 이끌이가 모임에 호출하는 경우 기본적으로 모임을 시작하려면 PIN이 필요합니다. 누구나 모임에 전화 접속할 수 있으며 PIN이 모임을 시작하라는 메시지가 표시되지 않을 수 있도록 설정할 수 있습니다. 단일 사용자에 비즈니스용 Skype 이 설정을 사용하도록 설정하거나 사용하지 않도록 설정하려면 관리 센터를 사용할 수 있습니다.
  
다른 사용자가 앱에서 모임을 시작한 경우 모임 이끌이에 PIN이 필요하지 비즈니스용 Skype 없습니다. PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가할 때만 필요합니다. 모임에 대한 PIN은 오디오 회의 라이선스가 할당되어 오디오 회의에 사용할 수 있는 경우 오디오 사용자에게 전송됩니다.  오디오 [회의](send-an-email-to-a-user-with-their-dial-in-information.md) 설정이 변경될 때 사용자에게 자동으로 전송되는 오디오 회의 정보 및 전자 메일이 있는 사용자에게 전자 메일 보내기 를 [참조하세요.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 호출자 모임에 참가하지 않도록 설정하거나 사용하지 않도록 설정
    
1. 비즈니스용 Skype 관리 센터의 왼쪽 탐색에서 **오디오** 회의 사용자로  >  **이동합니다.** 
    
2. 목록에서 사용자를 선택하고 작업 창에서 편집을 **클릭합니다.** 
    
3. 사용자의 속성 페이지에서 모임 옵션에서 확인되지 않은 발신자 허용을 모임의 첫 번째 사용자로 선택하거나 선택  **취소합니다. 그렇지 않은 경우 인증된** 사용자가 조인할 때까지 로비에서 대기합니다.
    
4. **저장** 을 클릭합니다. 


    
 **Powershell Windows 사용**
  
- 다음을 실행합니다. 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>또 어떤 것을 알아야 하나요?

- PIN을 다시 설정하려는 경우 오디오 회의 [PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin.md)
    
- 익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하지 않도록 설정됩니다.
    
  - 모임이 시작되지 않은 경우(모임에 아직 아무도 없습니다. 이끌이인 경우 발신자가 묻는 메시지가 표시됨). 예를 말하면 PIN에 대한 메시지가 표시될 것이고 PIN을 입력하면 모임이 시작하고 사용자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 모임에 이미 있는 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않습니다. PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되어 호출자는 모임에 참가합니다.
    
- 익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하도록 설정합니다.
    
  - 모임을 시작하지 않은 경우(아직 모임에 참석하지 않은 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않고 PIN에 대한 메시지가 표시되지 않습니다. 이끌이의 설정이 해제로 설정되어 있기 때문에 모임이 시작되어 익명 호출자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 모임에 이미 있는 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않습니다. PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자가 참가합니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 여러 사용자에 대해 시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet을 사용할 수 있습니다.
    
- 이 경우 Windows PowerShell 온라인에서 비즈니스용 Skype 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 모두 관리할 수 있습니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 많은 사용자에 대한 설정을 한 Microsoft 365 경우와 같이 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
