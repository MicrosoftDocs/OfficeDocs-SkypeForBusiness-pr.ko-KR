---
title: 조직의 모바일 정책 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: 사용자가 휴대폰 번호 대신 직장 전화 번호를 사용하여 휴대폰으로 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 Skype 앱을 사용하여 비즈니스용 Skype Online에 연결하는 방법을 설정할 수 있습니다. 모바일 정책을 사용하여 호출을 걸거나 받을 Wi-Fi 연결을 요구할 수도 있습니다.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814747"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>조직의 모바일 정책 설정

사용자가 휴대폰 번호 대신 직장 전화 번호를 사용하여 휴대폰으로 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 Skype 앱을 사용하여 비즈니스용 Skype Online에 연결하는 방법을 설정할 수 있습니다. 모바일 정책을 사용하여 호출을 걸거나 받을 Wi-Fi 연결을 요구할 수도 있습니다.
  
정책을 만들 때 모바일 정책 설정을 구성하거나 **Set-CsMobilityPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.
  
## <a name="set-your-mobile-policies"></a>모바일 정책 설정

> [!NOTE]
> 비즈니스용 Skype Online의 모든 모바일 정책 설정에 대해 Windows PowerShell 비즈니스용 Skype 관리 **센터를** 사용할 **수 없습니다.** 
  
### <a name="verify-and-start-windows-powershell"></a>확인 및 Windows PowerShell

- **버전 3.0 Windows PowerShell 실행 중인지 확인**
    
    1. 버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.
        
    2. 웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인
        
    3. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다. 메시지가 표시될 때 컴퓨터를 다시 시작합니다.
        
    4. 또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.
    
    자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)
    
- **세션 Windows PowerShell 시작**
    
    1. 시작 **메뉴에서**  >  **Windows PowerShell.**
        
    2. 다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.
        
       > [!NOTE]
       > 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.
       >
       > 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>사용자의 비디오에 WiFi 연결 필요

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
- 만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
  이미 정책을 만든 경우 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>사용자가 비즈니스용 Skype 앱을 사용하지 못하도록 방지

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
- Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
  이미 정책을 만든 경우 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>사용자가 모바일 장치를 사용하여 IP 통화를 통해 음성을 걸지 못하도록 방지

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
- 만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
이미 정책을 만든 경우 [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[지점 및 지점 및 지점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
 
