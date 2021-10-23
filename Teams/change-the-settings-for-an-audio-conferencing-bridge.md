---
title: 오디오 회의 브리지의 설정 변경
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 진입 및 종료 알림을 포함하여 오디오 회의 브리지 설정을 변경하고, 이름 또는 전화 번호, 음색을 재생하고, 발신자에 이름을 기록하라는 프롬프트를 선택합니다.
ms.openlocfilehash: 0c64fa8c8717ae7fd401c4476896e6e52e833769
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537050"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>오디오 회의 브리지의 설정 변경

오디오 회의 또는 Microsoft 365 Office 365 설정하면 오디오 회의 브리지라는 사용자에 대한 전화 번호가 수신됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 이러한 전화 번호는 발신자들이 모임에 전화 접속할 때 사용됩니다. 전화 번호는 모임 초대의 비즈니스용 Skype Microsoft Teams 포함됩니다.
  
회의 브리지는 통화에 응답하고 모임 자동 참석을 사용하여 음성 프롬프트를 발신자에게 묻는 메시지를 표시한 다음, 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록하고 PIN 설정을 제어할 수 있습니다. PINS는 모임 이끌이가 앱을 사용하지 않을 때 모임을 시작할 비즈니스용 Skype Microsoft Teams 부여됩니다.

  > [!IMPORTANT]
  > PIN은 앱 사용자가 모임을 비즈니스용 Skype Microsoft Teams 경우 모임 이끌이에게만 필요합니다. 모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

##  <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. 브리지 **설정 창에서** 다음을 선택합니다. 
   - **모임 항목 및 종료 알림** 이 기능을 해제하면 모임에 이미 참가한 사용자는 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.
    
     모임 항목 **및** 종료 알림을 켜면 다음 옵션을 선택할 수 있습니다.
    
   - **이름 또는 전화 번호** 사용자가 모임에 전화 접속하면 참가할 때 해당 전화 번호가 재생됩니다.
    
   - **톤** 사용자가 모임에 전화 접속하면 모임에 참가할 때 오디오 톤이 재생됩니다.
      
   - 모임에 참가하기 전에 발신자들에게 이름을 **기록해달라고 요청합니다.** 이 기능을 해제하면 호출자는 모임에 참가하기 전에 이름을 기록할지 묻는 요청이 없습니다.

4. 모임에 대한 PIN 길이를 설정하려면 PIN 길이 목록에서 PIN에 대해 원하는 숫자 수를 **선택합니다.**

5. 사용자에게 전자 메일을 보낼지 여부를 지정하려면 오디오 회의 구성이 변경될 경우 사용자에게 자동으로 전자 메일 보내기 를 사용하도록 설정하거나 사용하지 **않도록 설정합니다.**
    자세한 [](emails-sent-to-users-when-their-settings-change-in-teams.md) 내용은 오디오 회의 설정이 사용자에 Microsoft Teams 설정이 변경될 때 [](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 사용자에게 자동으로 전송되는 전자 비즈니스용 Skype 참조하세요.
 
6. **저장** 을 클릭합니다. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 이 프로세스를 자동화하기 위해 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet을 사용할 수 있습니다.
    
- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 사용자에 대한 설정을 한 Microsoft 365 관리 센터 설정하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams용 오디오 회의 설정하기](set-up-audio-conferencing-in-teams.md)

[온라인용 오디오 회의 비즈니스용 Skype 설정](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)