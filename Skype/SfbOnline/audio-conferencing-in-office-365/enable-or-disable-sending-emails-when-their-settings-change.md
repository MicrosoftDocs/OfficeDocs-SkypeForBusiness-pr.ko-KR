---
title: 비즈니스용 Skype Online에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin 변경 또는 기본 회의 번호 변경 등의 설정이 사용자에 게 전자 메일을 보내는 것을 허용 하거나 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 28da70d829972a7b9d3659290652c2482d409364
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642347"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함

> [!Note]
> Microsoft 팀에서 전자 메일 보내기를 사용 하거나 사용 하지 않도록 설정 하려면 [Microsoft 팀에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함을](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)참조 하세요.

사용자가 오디오 회의를 사용 하도록 설정 되 면 전자 메일을 통해 자동으로 알림을 받습니다. 그러나 비즈니스용 Skype 사용자에 게 전송 되는 전자 메일 수를 줄여야 하는 경우가 있을 수 있습니다. 이러한 경우 전자 메일 보내기를 사용 하지 않도록 설정할 수 있습니다.
  
전자 메일 보내기를 사용 하지 않도록 설정 하는 경우 오디오 회의를 사용 하거나 사용 하지 않도록 설정 하는 경우, PIN이 다시 설정 될 때, 전화 회의 ID 및 기본 회의 전화 번호가 변경 되는 경우의 전자 메일을 포함 하 여 사용자에 게 오디오 회의 전자 메일이 전송 되지 않습니다. .
  
다음은 오디오 회의를 사용 하도록 설정 했을 때 사용자에 게 전송 되는 전자 메일의 예입니다.
  
![오디오 회의 전자 메일](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>사용자에 게 전자 메일이 전송 되는 경우

- 오디오 회의를 사용 하도록 설정 하면 조직의 사용자에 게 여러 개의 전자 메일이 전송 됩니다.
    
  - **오디오 회의** 라이선스가 할당 된 경우
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정 합니다.
    
  - 수동으로 사용자의 전화 회의 ID를 다시 설정 합니다.
    
  - **오디오 회의** 라이선스가 해당 항목에서 제거 됩니다.
    
  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음**으로 변경 되는 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft로 변경 된 경우


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제

비즈니스용 Skype 관리 센터 또는 Windows PowerShell을 사용 하 여 사용자에 게 전송 되는 전자 메일을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

 
![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘
    
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.
    
2. **Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 사용자에 게 자동으로 전자 메일 보내기**를 선택 하거나 선택을 취소 합니다.
    
3. **저장**을 클릭 합니다.
    
    > [!TIP]
    > **오디오 회의** > **사용자**로 이동한 다음 사용자를 선택 하 고 **전자 메일을 통해 회의 정보 보내기를**클릭 하 여 오디오 회의 설정을 사용 하 여 사용자에 게 전자 메일을 보낼 수도 있습니다.  이렇게 하면 PIN이 아닌 전화 회의 ID 및 전화 번호만 포함 된 전자 메일이 전송 됩니다.  자세한 내용은 [오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md) 참조 하세요.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Windows PowerShell 사용**
  
- 전자 메일 보내기를 사용 하지 않으려면 다음을 실행 합니다. 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    이 cmdlet에 대 한 도움말은 [Set-사용](https://go.microsoft.com/fwlink/?LinkId=715757)을 참조 하세요.
    
## <a name="what-else-should-you-know"></a>알아야 할 기타 사항

- 자동 전자 메일을 사용 하지 않도록 설정한 경우 비즈니스용 Skype 관리 센터를 사용 하 여 전화 회의 ID 및 전화번호를 포함 하는 전자 메일을 수동으로 보낼 수 있습니다. 그러나이 작업을 수행 하는 경우에는 PIN이 포함 되지 않습니다. 오디오 회의 PIN을 다시 설정 하 고 전자 메일을 보낼 수 없도록 설정 하려면 다른 방식으로 사용자에 게 보내야 합니다.
    
- 비즈니스용 Skype 관리 센터 또는 Windows PowerShell을 사용 하 여 사용자에 게 전자 메일을 보낼 수 없습니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 이러한 cmdlet을 사용 하 여 시간을 절약 하거나이를 자동화할 수 있습니다.
    
  - [Get-사용](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [제거-사용](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-사용](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일](emails-sent-to-users-when-their-settings-change.md)

[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information.md)


