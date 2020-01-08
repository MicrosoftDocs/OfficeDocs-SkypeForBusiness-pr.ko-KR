---
title: 비즈니스용 Skype Online에서 오디오 회의를 통해 사용자에 게 전자 메일 보내기
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: 비즈니스용 Skype Online의 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일을 보냅니다.
ms.openlocfilehash: 08e1f67f042d9497854f6d96643ff41e9bf528ed
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962576"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기

> [!Note]
> Microsoft 팀의 사용자에 게 오디오 회의 정보를 보내는 방법에 대 한 자세한 내용은 [Microsoft Teasms의 오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)참고 하세요.

비즈니스용 Skype 사용자에 게 오디오 회의 정보를 보내야 할 경우도 있습니다. **비즈니스용 Skype 관리 센터** 를 사용 하 여이 작업을 수행 하 고 사용자의 속성 아래에서 **전자 메일을 통해 회의 정보 보내기를** 클릭할 수 있습니다. 이 전자 메일을 보낼 때 다음을 비롯 한 모든 오디오 회의 정보가 포함 됩니다.
  
- 사용자의 컨퍼런스 전화 또는 전화 접속 전화 번호입니다.
    
- 사용자의 전화 회의 ID입니다.
    
   
다음은 전송 되는 전자 메일의 예입니다.
  
![전화 접속 회의 전자 메일](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. 페이지 맨 위에서 **편집**을 클릭 합니다.

3. **오디오 회의**에서 **전자 메일로 회의 정보 보내기를**클릭 합니다.

1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.
    
2. **비즈니스용 Skype**> 관리 센터로 이동 하 고 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.
    
3. **사용자**를 클릭 한 다음 사용자를 선택 합니다.
    
4. 작업 창에서 **전자 메일을 통해 회의 정보 보내기를**클릭 합니다.
    
> [!TIP]
> 사용자의 속성을 편집 하 고 **오디오 회의** > 를 클릭 하 여 전자 메일을**통해**음성 회의 설정으로 사용자에 게 전자 메일을 보낼 수도 있습니다. 

## <a name="what-else-should-you-know-about-this-email"></a>이 전자 메일에 대해 알아야 할 기타 사항

- 오디오 회의를 사용 하도록 설정 하면 조직의 사용자에 게 여러 개의 전자 메일이 전송 됩니다.
    
  - **오디오 회의** 라이선스가 할당 된 경우
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정 합니다.
    
  - 수동으로 사용자의 전화 회의 ID를 다시 설정 합니다.
    
  - **오디오 회의** 라이선스가 제거 된 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음**으로 변경 되는 경우
    
  - 사용자의 오디오 회의 공급자가 Microsoft로 변경 된 경우
    
- 기본적으로 전자 메일을 보낸 사람은 Office 365에 있지만, Windows PowerShell 및 [사용](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet을 사용 하 여 전자 메일 주소와 표시 이름을 변경할 수 있습니다. 사용자에 게 전자 메일을 보내는 전자 메일 주소를 변경 하려면 다음을 수행 해야 합니다.
    
  - SendEmailFromAddress 매개 변수에 전자 메일 주소를 입력 합니다.
    
  - "=" 매개 변수를 True로 설정 합니다.
    
  - 이 매개 변수에 전자 메일 표시 이름을 입력 합니다.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > 전자 메일 주소 정보를 변경 하려는 경우 조직의 인바운드 전자 메일 정책에서 설정 된 사용자 지정 전자 메일 주소에서 보낸 전자 메일이 허용 되는지 확인 해야 합니다. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 작업을 자동화 하려면 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용 하면 됩니다.
    
    오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일을 보내려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

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
