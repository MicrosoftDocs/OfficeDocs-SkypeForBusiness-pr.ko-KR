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
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: '비즈니스용 Skype 또는 Microsoft 팀 앱을 사용 하지 않을 때 모임 이끌이의 이름 및 pin을 수집 하는 데 사용 되는 회의 브리지에 대 한 설정을 변경 해야 하는 단계를 확인 하세요. '
ms.openlocfilehash: b7ac85729bafe9d27f9e33cfa22597811b8d3d0b
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "37516955"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>오디오 회의 브리지의 설정 변경

Office 365에서 오디오 회의를 설정 하는 경우 오디오 회의 브리지 라고 하는 사용자의 전화 번호를 받게 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함 될 수 있습니다. 이러한 전화 번호는 발신자가 모임에 전화를 걸 때 사용 됩니다. 전화 번호는 비즈니스용 Skype 또는 Microsoft 팀 모임 초대의 아래쪽에 포함 되어 있습니다.
  
회의 브리지는 전화를 걸거나 모임 자동 전화 교환을 사용 하 여 음성 메시지를 발신자에 게 메시지를 표시 하 고, 설정에 따라 알림을 재생 하 고, 발신자에 게 자신의 이름을 기록 하도록 요청 하 고, PIN 설정을 제어할 수 있습니다. 모임이 비즈니스용 Skype 또는 Microsoft 팀 앱을 사용 하지 않는 경우 모임을 시작할 수 있도록 모임 이끌이에게 Pin이 지정 됩니다.

  > [!IMPORTANT]
  > PIN은 비즈니스용 Skype 또는 Microsoft 팀 사용자가 아직 모임을 시작 하지 않은 경우 모임 이끌이에게만 필요 합니다. 모든 사용자가 모임에 전화를 거는 경우 모임 이끌이가 모임을 시작 하려면 PIN이 필요 합니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Microsoft 팀 로고를 표시 하는 아이콘](media/teams-logo-30x30.png) Microsoft 팀 관리 센터 사용

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 다음을 선택 합니다. 
   - **모임 입력 및 종료 알림** 이 기능을 해제 하면 모임에 참가 한 사용자는 다른 사용자가 모임을 시작 하거나 떠날 때 알림을 받을 수 없습니다.
    
     모임 입장을 켜고 **알림을 종료**하면 다음 옵션을 선택할 수 있습니다.
    
   - **이름 또는 전화 번호** 사용자가 모임에 전화를 걸 때 전화 번호는 참가할 때 재생 됩니다.
    
   - **톤** 사용자가 모임에 전화를 걸 때 오디오 신호음이 참가할 때 재생 됩니다.
      
   - **모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청** 이 기능을 해제 하면 호출자가 모임에 참가 하기 전에 해당 이름을 기록 하 라는 메시지가 표시 되지 않습니다.

4. 모임의 PIN 길이를 설정 하려면 **pin 길이** 목록에서 원하는 pin의 자릿수를 선택 합니다.

5. 사용자에 게 전자 메일을 보낼지 여부를 지정 하려면 **오디오 회의 구성이 변경 되는 경우 자동으로 전자 메일을 사용자에 게 보내기를**설정 하거나 해제 합니다.
    자세한 내용은 [비즈니스용 Skype Online에서 설정이 변경 될 때 사용자에 게 전송](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 되 [는 Microsoft 팀 또는 전자 메일에서 오디오 회의 설정이 변경 될 때 사용자에 게 자동으로 전송 되는 전자 메일을](emails-sent-to-users-when-their-settings-change-in-teams.md) 참조 하세요.
 
6. **저장**을 클릭 합니다. 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![비즈니스용 Skype 로고를 표시 하는 아이콘](media/sfb-logo-30x30.png)  비즈니스용 Skype 관리 센터 사용

 **발신자가 모임에 참가 하는 경우의 모임 환경 설정**
    
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.
    
2. **Microsoft 브리지 설정** 페이지의 **모임 참가 환경**에서 다음을 선택 합니다.
    
   - **모임 입력 및 종료 알림이 설정 되도록 설정** 이 옵션이 기본적으로 선택 되어 있습니다. 확인란의 선택을 취소 하면 모임에 이미 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.
    
   - **모임 시작 및 종료 알림 사용을**선택 하 여 설정 하는 경우 **입력/종료 알림 형식** 목록에서 다음 옵션을 선택할 수 있습니다.
    
   - **이름 또는 전화 번호** 사용자가 모임에 전화를 걸 때 전화 번호는 참가할 때 재생 됩니다.
    
   - **톤** 사용자가 모임에 전화를 걸 때 오디오 신호음이 참가할 때 재생 됩니다.
  
   - **모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청** 이 옵션이 기본적으로 선택 되어 있습니다. 확인란의 선택을 취소 한 경우에는 호출자가 모임에 참가 하기 전에 해당 이름을 기록해 야 한다는 메시지가 표시 되지 않습니다.
    
3. 변경 작업을 수행한 후 **저장**을 클릭 합니다.
    
**모임의 PIN 길이 설정**
  
1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.
    
2. **Microsoft 365 관리 센터** > **비즈니스용 Skype**로 이동 합니다.
    
3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.
    
4. **Microsoft 브리지 설정** 페이지의 **보안**에서 **PIN 길이** 목록에 원하는 pin의 자릿수를 입력 한 다음 **저장**을 클릭 합니다.
    
    > [!IMPORTANT]
    > PIN은 4 ~ 12 자리 여야 합니다. 
  
**사용자에 게 전자 메일을 보낼지 여부 선택**
  
1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.
    
2. **Microsoft 365 관리 센터** > **비즈니스용 Skype**로 이동 합니다.
    
3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.
    
4. **Microsoft 브리지 설정** 페이지에서 **전화 접속 정보가 변경 된 경우 자동으로 전자 메일을 사용자에 게 보내기를**선택 하거나 선택을 취소 한 다음 **저장**을 클릭 합니다.
    
    자세한 내용은 [비즈니스용 Skype Online에서 설정이 변경 될 때 사용자에 게 전송](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) 되 [는 Microsoft 팀 또는 전자 메일에서 오디오 회의 설정이 변경 될 때 사용자에 게 자동으로 전송 되는 전자 메일을](emails-sent-to-users-when-their-settings-change-in-teams.md) 참조 하세요.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 프로세스를 자동화 하려면 [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet을 사용 하면 됩니다.
    
- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 주제

[Microsoft 팀을 위한 오디오 회의 설정](set-up-audio-conferencing-in-teams.md)

[비즈니스용 Skype Online에 대 한 오디오 회의 설정](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
