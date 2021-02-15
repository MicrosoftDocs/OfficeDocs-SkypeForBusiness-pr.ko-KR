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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 입장 및 퇴장 알림을 포함하여 오디오 회의 브리지 설정을 변경하고, 이름이나 전화 번호, 톤을 재생하고, 발신자 이름을 기록하라는 메시지를 표시합니다.
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918710"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>오디오 회의 브리지의 설정 변경

Microsoft 365 또는 Office 365에서 오디오 회의를 설정하는 경우 오디오 회의 브리지라고 하는 사용자에 대한 전화 번호를 받게 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 이러한 전화 번호는 발신자 모임에 전화 접속할 때 사용됩니다. 전화 번호는 비즈니스용 Skype 또는 Microsoft Teams 모임 초대의 아래쪽에 포함됩니다.
  
회의 브리지는 통화에 응답하고 모임 자동 전화 회의를 사용하여 음성 프롬프트로 발신자 메시지를 표시한 다음 설정에 따라 알림을 재생하고 발신자 이름을 기록해 달라고 요청하고 PIN 설정을 제어할 수 있습니다. 모임 이끌이에게는 비즈니스용 Skype 또는 Microsoft Teams 앱을 사용하지 않을 때 모임 이끌이가 모임을 시작할 수 있도록 PI가 부여됩니다.

  > [!IMPORTANT]
  > PIN은 비즈니스용 Skype 또는 Microsoft Teams 앱 사용자가 아직 모임을 시작하지 않은 경우 모임 이끌이에게만 필요합니다. 모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](media/teams-logo-30x30.png) Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 모음에서 모임 회의  >  **브리지로 이동** 

2. 회의 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.** 

3. Bridge **설정 창에서** 다음을 선택합니다. 
   - **모임 입장 및 퇴장 알림** 이 기능을 해제하면 이미 모임에 참가한 사용자는 모임에 입장하거나 퇴장할 때 알림을 들을 수 없습니다.
    
     모임 입장 **및** 퇴장 알림을 켜면 다음 옵션을 선택할 수 있습니다.
    
   - **이름 또는 전화 번호** 사용자가 모임에 전화 접속하면 해당 사용자의 전화 번호가 모임에 참가할 때 재생됩니다.
    
   - **톤** 사용자가 모임에 전화 접속하면 모임에 참가할 때 오디오 음색이 재생됩니다.
      
   - **발신자들에게** 모임에 참가하기 전에 이름을 기록해달라고 요청 이 기능을 해제하면 발신자는 모임에 참가하기 전에 이름을 기록할지 묻는 요청이 없습니다.

4. 모임의 PIN 길이를 설정하려면 PIN 길이 목록에서 **PIN에** 사용할 자릿수를 선택합니다.

5. 사용자에게 전자 메일을 보낼지 여부를 지정하려면 오디오 회의 구성이 변경될 경우 사용자에게 자동으로 전자 메일을 보내거나 사용하지 않도록 **설정하세요.**
    자세한 [내용은 비즈니스용](emails-sent-to-users-when-their-settings-change-in-teams.md) [Skype Online에서](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 설정이 변경될 때 Microsoft Teams 또는 사용자에게 전송된 전자 메일에서 오디오 회의 설정이 변경될 때 사용자에게 자동으로 전송되는 전자 메일을 참조하세요.
 
6. **저장** 을 클릭합니다. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 이 프로세스를 자동화하기 위해 [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet을 사용할 수 있습니다.
    
- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자를 위한 설정을 변경할 때도 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams용 오디오 회의 설정하기](set-up-audio-conferencing-in-teams.md)

[비즈니스용 Skype Online용 오디오 회의 설정](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
