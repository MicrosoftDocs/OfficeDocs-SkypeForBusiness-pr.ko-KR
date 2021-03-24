---
title: 조직의 클라이언트 정책 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 클라이언트 정책은 사용자가 사용할 수 있도록 비즈니스용 Skype Online의 기능을 결정하는 데 도움이 됩니다. 예를 들어 일부 사용자에게 다른 사용자에게 이 권리가 거부되는 동안 파일을 전송할 수 있는 권리가 주어도 됩니다.
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100534"
---
# <a name="set-up-client-policies-for-your-organization"></a>조직의 클라이언트 정책 설정

클라이언트 정책은 사용자가 사용할 수 있도록 비즈니스용 Skype Online의 기능을 결정하는 데 도움이 됩니다. 예를 들어 일부 사용자에게 다른 사용자에게 이 권리가 거부되는 동안 파일을 전송할 수 있는 권리가 주어도 됩니다.
  
정책을 만들 때 클라이언트 정책 설정을 구성하거나 **Set-CsClientPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.
  
## <a name="set-your-client-policies"></a>클라이언트 정책 설정

> [!NOTE]
> 비즈니스용 Skype Online의 모든 클라이언트 정책 설정의 경우 비즈니스용  Skype Windows PowerShell 비즈니스용 Skype 관리 센터를 사용할 **수 없습니다.** 
  
### <a name="start-windows-powershell"></a>시작 Windows PowerShell

> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.
1. Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)
    
2. 명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다. 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>이모티콘 및 현재 상태 알림을 사용하지 않도록 설정하고 IM 저장을 방지합니다.

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet을 참조합니다.
    
- 조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 참조합니다.
    
정책을 이미 만든 경우 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>URL 또는 하이퍼링크를 IM에서 클릭할 수 있도록 설정

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet을 참조합니다.
    
- 조직의 모든 사용자에게 만든 새 정책을 부여하기 위해 다음을 실행합니다.
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 참조합니다.
    
정책을 이미 만든 경우 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="prevent-showing-recent-contacts"></a>최근 연락처 표시 방지

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet을 참조합니다.
    
- Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 참조합니다.
    
  정책을 이미 만든 경우 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[지점 및 지점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
