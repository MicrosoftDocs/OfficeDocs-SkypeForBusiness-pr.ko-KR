---
title: 조직의 회의 정책 설정
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: 회의는 비즈니스용 Skype Online의 중요한 부분입니다. 회의를 사용하면 사용자 그룹이 온라인으로 모여 슬라이드와 비디오를 보고, 응용 프로그램을 공유하고, 파일을 교환하고, 통신 및 공동 작업을 할 수 있습니다.
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814757"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>조직의 회의 정책 설정

회의는 비즈니스용 Skype Online의 중요한 부분입니다. 회의를 사용하면 사용자 그룹이 온라인으로 모여 슬라이드와 비디오를 보고, 응용 프로그램을 공유하고, 파일을 교환하고, 통신 및 공동 작업을 할 수 있습니다.
  
회의 및 회의 설정을 제어하는 것이 중요합니다. 경우에 따라 보안 문제가 있을 수 있습니다. 기본적으로, 비인식 사용자를 포함한 모든 사용자는 모임에 참가하고 해당 모임 중에 배포된 슬라이드 또는 유인물 중 일부를 저장할 수 있습니다. 또한 경우에 따라 법적 문제가 있을 수 있습니다. 예를 들어 기본적으로 모임 참가자는 공유 콘텐츠에 대한 주석을 만들 수 있습니다. 그러나 이러한 주석은 모임이 보관될 때 저장되지 않습니다. 조직에서 모든 전자 통신의 기록을 유지해야 하는 경우 주석을 사용하지 않도록 설정할 수 있습니다. 
  
비즈니스용 Skype Online에서는 회의 정책을 사용하여 회의를 관리합니다. 회의 정책은 회의에 IP 오디오 및 비디오를 포함할 수 있는지 여부부터 모임에 참가할 수 있는 최대 사용자 수에 대한 모든 것을 포함하여 회의에 사용할 수 있는 기능 및 기능을 결정합니다. 회의 정책은 전역 범위 또는 사용자당 범위에서 구성할 수 있습니다. 이렇게 하면 관리자가 어떤 사용자가 사용할 수 있게 될 기능을 결정해야 하는지 결정하기에 많은 유연성이 제공됩니다.
  
정책을 만들 때 정책 설정을 구성하거나 **Set-CsConferencingPolicy** cmdlet을 사용하여 기존 정책의 설정을 수정할 수 있습니다.
  
## <a name="set-your-conferencing-policies"></a>회의 정책 설정

> [!NOTE]
> 비즈니스용 Skype Online의 모든 회의 정책 설정에 대해 Windows PowerShell 비즈니스용 Skype  관리 센터를 사용할 **수 없습니다.** 
  
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
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>모임 중에 파일 전송 및 데스크톱 공유 차단

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
- 만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
  이미 정책을 만든 경우 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>회의 기록 차단 및 익명 모임 참가자 방지

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다. 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
- Amos Marble에 만든 새 정책을 부여하기 위해 다음을 실행합니다.
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
이미 정책을 만든 경우 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음 [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>익명 참가자가 모임을 녹음/녹화하지 않습니다. 외부 사용자가 모임 콘텐츠를 저장하지 않습니다.

- 이러한 설정에 대한 새 정책을 만들하려면 다음을 실행합니다.  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
- 만든 새 정책을 조직의 모든 사용자에게 부여하기 위해 다음을 실행합니다.
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet에 대한 자세한 내용은 다음을 참조합니다.
    
이미 정책을 만든 경우 [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet을 사용하여 기존 정책을 변경한 다음[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet을 사용하여 사용자에게 설정을 적용할 수 있습니다.
  
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

  
 
