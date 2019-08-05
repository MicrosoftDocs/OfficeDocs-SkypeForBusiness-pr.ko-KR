---
title: Microsoft 팀에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin 변경 또는 Microsoft 팀의 기본 회의 번호 변경 등의 설정이 사용자에 게 전자 메일을 보내는 것을 허용 하거나 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 0a86316fcc331e258eb13df73693f32b7ef21814
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2019
ms.locfileid: "36183806"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Microsoft 팀에서 오디오 회의 설정이 변경 될 때 전자 메일 보내기 사용 또는 사용 안 함

사용자가 오디오 회의를 사용 하도록 설정 되 면 전자 메일을 통해 자동으로 알림을 받습니다. 그러나 Microsoft 팀 사용자에 게 전송 되는 전자 메일 수를 줄여야 하는 경우가 있을 수 있습니다. 이러한 경우 전자 메일 보내기를 사용 하지 않도록 설정할 수 있습니다.
  
전자 메일 보내기를 사용 하지 않도록 설정 하는 경우 오디오 회의를 사용 하거나 사용 하지 않도록 설정 하는 경우, PIN이 다시 설정 될 때, 전화 회의 ID 및 기본 회의 전화 번호가 변경 되는 경우의 전자 메일을 포함 하 여 사용자에 게 오디오 회의 전자 메일이 전송 되지 않습니다. .
  
다음은 오디오 회의를 사용 하도록 설정 했을 때 사용자에 게 전송 되는 전자 메일의 예입니다.
  
![오디오 회의 전자 메일 메시지의 예](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>사용자에 게 전자 메일이 전송 되는 경우

- 오디오 회의를 사용 하도록 설정 하면 조직의 사용자에 게 여러 개의 전자 메일이 전송 됩니다.
    
  - **오디오 회의** 라이선스가 할당 된 경우
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정 합니다.
    
  - 수동으로 사용자의 전화 회의 ID를 다시 설정 합니다.
    
  - **오디오 회의** 라이선스가 해당 항목에서 제거 됩니다.
    
  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음**으로 변경 되는 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft로 변경 된 경우


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제

Microsoft 팀 또는 Windows PowerShell을 사용 하 여 사용자에 게 전송 되는 전자 메일을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 **전화 접속 설정이 변경 되는 경우 자동으로 사용자에 게 전자 메일 보내기**사용 또는 사용 안 함을 설정 하거나 해제 합니다.

4. **저장**을 클릭 합니다.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell 사용**
  
자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.

    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
    
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일](emails-sent-to-users-when-their-settings-change-in-teams.md)

[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


