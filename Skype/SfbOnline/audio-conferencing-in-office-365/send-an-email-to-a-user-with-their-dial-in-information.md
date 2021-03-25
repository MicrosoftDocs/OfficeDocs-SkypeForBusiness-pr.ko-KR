---
title: 비즈니스용 Skype Online에서 오디오 회의를 통해 사용자에게 전자 메일 보내기
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 비즈니스용 Skype Online에서 오디오 회의 정보가 있는 전자 메일을 사용자에게 전송합니다.
ms.openlocfilehash: f070353069c937a62935e1cc570ebae6c0e981db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110000"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 정보를 통해 사용자에게 전자 메일 보내기

> [!Note]
> Microsoft Teams의 사용자에게 오디오 회의 정보를 보내는 자세한 내용은 [Microsoft Teasms에서](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)오디오 회의 정보를 통해 사용자에게 전자 메일 보내기 를 참조하세요.

경우에 따라 비즈니스용 Skype 사용자가 오디오 회의 정보를 보내야 할 수 있습니다. 비즈니스용 **Skype** 관리 센터를 사용하고 사용자의 속성  아래에서 전자 메일을 통해 회의 정보 보내기 를 클릭하여 이 작업을 할 수 있습니다. 이 전자 메일을 보낼 때 다음을 포함하여 모든 오디오 회의 정보가 포함되어 있습니다.
  
- 사용자의 전화 회의 전화 또는 전화 접속 전화 번호입니다.
    
- 사용자의 회의 ID입니다.
    
   
다음은 전송된 전자 메일의 예입니다.
  
![전화 접속 회의 전자 메일](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>사용자에게 오디오 회의 정보가 있는 전자 메일 보내기

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 페이지 맨 위에 있는 편집을 **클릭합니다.**

3. 오디오 **회의에서** 전자 메일로 **회의 정보 보내기 를 클릭합니다.**

1. 직장 또는 학교 계정으로 로그인합니다.
    
2. 비즈니스용 Skype > 관리 센터로 이동하고 왼쪽 탐색에서 오디오 회의 **를 클릭합니다.**
    
3. 사용자를 클릭한 다음 사용자를 선택합니다.
    
4. 작업 창에서 전자 메일을 통해 **회의 정보 보내기 를 클릭합니다.**
    
> [!TIP]
> 사용자의 속성을 편집한 다음 전자 메일을 통해 회의 정보 보내기 를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을  >  **보낼 수도 있습니다.** 

## <a name="what-else-should-you-know-about-this-email"></a>이 전자 메일에 대해 알아야 할 다른 것은 무엇입니까?

- 오디오 회의를 사용하도록 설정한 후 조직의 사용자에게 전송된 여러 전자 메일이 있습니다.
    
  - 오디오 **회의** 라이선스가 할당되는 경우.
    
  - 사용자의 오디오 회의 PIN을 수동으로 다시 설정하면 됩니다.
    
  - 사용자의 회의 ID를 수동으로 다시 설정하면 됩니다.
    
  - 오디오 **회의** 라이선스가 제거되면
    
  - 사용자에 대한 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 **없음으로** 변경된 경우
    
  - 사용자에 대한 오디오 회의 공급자가 Microsoft로 변경된 경우
    
- 기본적으로 전자 메일의 발신자는 Microsoft 365 또는 Office 365에서 제공되지만 전자 메일 주소 및 표시 이름을 변경할 수 Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet을 사용하여 전자 메일 주소를 변경할 수 있습니다. 사용자에게 전자 메일을 보내는 전자 메일 주소를 변경하려면 다음을 해야 합니다.
    
  - SendEmailFromAddress 매개 변수에 전자 메일 주소를 입력합니다.
    
  - SendEmailOverride 매개 변수를 True로 설정합니다.
    
  - SendEmailFromDisplayName 매개 변수에 전자 메일 표시 이름을 입력합니다.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > 전자 메일 주소 정보를 변경하려면 조직의 인바운드 전자 메일 정책에서 설정된 사용자 지정 전자 메일 주소에서 오는 전자 메일을 허용하는지 확인해야 합니다. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell.

- 시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet을 사용할 수 있습니다.
    
    오디오 회의 정보를 통해 사용자에게 전자 메일을 보내기 위해 다음을 실행합니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 비즈니스용 Windows PowerShell 비즈니스용 Skype Online은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 모두 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 많은 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 비즈니스용 skype Windows PowerShell 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype 온라인용 Windows PowerShell Microsoft 다운로드 센터에서 다운로드할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)