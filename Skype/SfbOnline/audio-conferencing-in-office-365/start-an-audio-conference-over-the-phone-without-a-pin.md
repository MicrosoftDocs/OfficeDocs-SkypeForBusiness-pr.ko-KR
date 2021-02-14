---
title: 비즈니스용 Skype Online에서 PIN 없이 전화로 오디오 회의 시작
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
description: '비즈니스용 Skype 관리 센터에서 모임에 참가하거나 PowerShell 스크립트를 사용하여 익명 발신자에 가입하지 않도록 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: f02d458450f07b64f3daf4d23b1c56aa2bb846a3
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163877"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 PIN 없이 전화로 오디오 회의 시작

> [!Note]
> Microsoft Teams에서 PIN 없이 오디오 회의를 시작하는 자세한 내용은 Microsoft Teams에서 PIN 없이 전화로 오디오 회의 시작을 [참조하세요.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)

비즈니스용 Skype 모임 이끌이가 모임을 시작하지 않은 경우 모임에 전화 접속하는 사용자가 모임의 대기실에서 음악을 듣는 데 문제가 될 수 있습니다. 
  
모임 이끌이가 모임에 전화를 걸면 기본적으로 모임을 시작하는 데 PIN이 필요합니다. 누구나 모임에 전화 접속할 수 있도록 설정할 수 있으며 PIN을 사용하여 모임을 시작할지 묻는 메시지가 표시되지 않습니다. 비즈니스용 Skype 관리 센터를 사용하여 단일 사용자에 대해 이 설정을 설정하거나 사용하지 않도록 설정할 수 있습니다.
  
누군가가 비즈니스용 Skype 앱에서 모임을 시작한 경우 모임 이끌이에게 PIN이 필요하지 않습니다. PIN은 모임 이끌이가 전화를 통해 모임에 참가할 때만 필요합니다. 모임에 대한 PIN은 오디오 회의 라이선스가 할당되어 오디오 회의를 사용하도록 설정되면 오디오 사용자에게 전송됩니다.  오디오 [회의](send-an-email-to-a-user-with-their-dial-in-information.md) 설정이 변경될 때 사용자에게 자동으로 전송되는 오디오 회의 정보와 전자 메일이 있는 전자 메일 보내기를 [참조하세요.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 발신자 모임에 참가하지 않도록 설정 또는 해제
    
1. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 오디오 회의 **사용자로**  >  **이동하세요.** 
    
2. 목록에서 사용자를 선택하고 작업 창에서 편집을 **클릭합니다.** 
    
3. 사용자의 속성 페이지의 모임 옵션에서 모임에서 첫 번째 사람이 될 수 있도록 허용을 선택하거나 선택  **취소합니다. 그렇지 않은 경우 인증된** 사용자가 참가할 때까지 대기실에서 대기합니다.
    
4. **저장** 을 클릭합니다. 


    
 **Windows Powershell 사용**
  
- 다음을 실행합니다. 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>알아야 할 다른 것은 무엇입니까?

- PIN을 다시 설정하려는 경우 오디오 회의 PIN 재설정을 [참조합니다.](reset-the-audio-conferencing-pin.md)
    
- 익명 액세스 또는 모임 시작에 PIN을 요구하지 않는 경우 다음을 사용할 수 없습니다.
    
  - 모임이 시작되지 않은 경우(아직 모임에 참석하지 않은 경우): 발신자가 이끌이인 경우 발신자가 묻는 메시지가 표시됨 그렇다면 PIN을 입력하라는 메시지가 표시될 것입니다. PIN을 입력하면 모임이 시작하고 사용자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 이미 모임에 있는 경우): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않습니다. PIN을 묻는 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자도 모임에 참가합니다.
    
- 익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하도록 설정합니다.
    
  - 모임이 시작되지 않은 경우(아직 모임에 다른 사용자가 없음): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않고 PIN을 묻는 메시지가 표시되지 않습니다. 이끌이 설정이 해제되어 있기 때문에 모임이 시작되어 익명 발신자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 이미 모임에 있는 경우): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않습니다. PIN을 묻는 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자가 모임에 참가합니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 여러 사용자에 대해 이 작업을 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용할 수 있습니다.
    
- 비즈니스용 Windows PowerShell Skype Online은 사용자와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자에 대해 설정을 변경할 때도 그렇습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
