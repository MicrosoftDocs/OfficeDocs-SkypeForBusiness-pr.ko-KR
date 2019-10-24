---
title: 비즈니스용 Skype Online에서 PIN 없이 전화를 통해 음성 회의 시작
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '비즈니스용 Skype 관리 센터에서 또는 PowerShell 스크립트를 사용 하 여 익명 호출자가 모임에 참가 하는 것을 허용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 1cdcbd2f610c3d60ba2fb4e554823d410fd4ae8f
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642225"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 PIN 없이 전화를 통해 음성 회의 시작

> [!Note]
> Microsoft 팀에서 PIN 없이 오디오 회의를 시작 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 pin 없이 전화로 오디오 회의 시작](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)을 참조 하세요.

비즈니스용 Skype 모임 이끌이가 모임을 시작 하지 않았기 때문에 모임에 전화 접속 하는 사용자가 음악을 듣는 사람에 게이를 유지 하기 어려울 수 있습니다. 
  
모임 이끌이가 모임에 전화를 거는 경우 기본적으로 모임을 시작 하려면 PIN이 필요 합니다. 다른 사용자가 모임에 전화를 걸 수 있도록 설정할 수 있으며 모임 시작을 위해 PIN을 묻지 않습니다. 비즈니스용 Skype 관리 센터를 사용 하 여 단일 사용자에 대해이 설정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.
  
다른 사용자가 비즈니스용 Skype 앱에서 모임을 시작 했다면 모임 이끌이에게는 PIN이 필요 하지 않습니다. PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가 하는 경우에만 필요 합니다. 모임에 대 한 PIN은 오디오 **회의** 라이선스를 할당 하 고 오디오 회의를 사용할 수 있는 경우 오디오 사용자에 게 전송 됩니다. 음성 회의 [설정이 변경 될 때 자동으로 사용자에 게 전송 되는](emails-sent-to-users-when-their-settings-change.md) [전자 메일을 사용자에 게 오디오 회의 정보](send-an-email-to-a-user-with-their-dial-in-information.md) 및 메일로 보내기를 참조 하세요.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 호출자가 모임에 참가 하지 못하도록 설정 또는 해제
    
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **사용자**로 이동 합니다. 
    
2. 목록에서 사용자를 선택 하 고 작업 창에서 **편집**을 클릭 합니다. 
    
3. 사용자의 속성 페이지에 있는 **모임 옵션**에서 **인증 되지 않은 발신자가 모임에서 첫 번째 사용자가 되도록 허용을 선택 하거나 선택을 취소 합니다. 그렇지 않은 경우에는 인증 된 사용자가 참가할 때까지 대기실에서 대기**합니다.
    
4. **저장**을 클릭 합니다. 


    
 **Windows Powershell 사용**
  
- 다음을 실행 합니다. 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>알아야 할 기타 사항

- PIN을 다시 설정 하려면 [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin.md)참조 하세요.
    
- 익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 사용 하지 않도록 설정 됩니다.
    
  - 모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하는 경우 호출자에 게 해당 사람이 이끌이 인지 묻는 메시지가 표시 됩니다. 예, pin을 입력 하 라는 메시지가 표시 되 면, 모임이 시작 되 고 사용자가 모임에 참가 합니다.
    
  - 모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 참가 한 경우): 주최자가 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않으면 발신자에 게 메시지가 표시 되지 않습니다. 모임이 이미 시작 되었으며 호출자가 참가 하 게 됩니다.
    
- 익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 다음을 사용 합니다.
    
  - 모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하 라는 메시지가 표시 되지 않습니다. 주최자는 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않습니다. 이끌이의 설정이 off로 설정 되어 있으므로 모임이 시작 되 고 익명 발신자가 모임에 참가 합니다.
    
  - 모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 속해 있는 경우), 발신자에 게 메시지가 표시 되지 않으며, PIN을 입력 하 라는 메시지가 표시 되지 않으며, 모임이 이미 시작 되어 발신자가 참여 하 게 됩니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 여러 사용자에 대해 시간을 절약 하거나이 작업을 자동화 하려면 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용 하면 됩니다.
    
- Windows PowerShell을 사용할 때 비즈니스용 Skype Online은 사용자 관리와 사용자가 허용 하거나 허용 하지 않는 작업에 대 한 정보를 제공 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
