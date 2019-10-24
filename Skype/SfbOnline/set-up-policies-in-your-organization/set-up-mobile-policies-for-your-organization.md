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
f1keywords: None
ms.custom:
- Setup
description: 사용자가 휴대폰 번호를 사용 하 여 휴대폰 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 skype 앱에 대 한 skype Online에 연결 하는 방법을 설정할 수 있습니다. mber. 이동성 정책은 전화를 걸거나 받을 때 Wi-fi 연결이 필요한 경우에도 사용할 수 있습니다.
ms.openlocfilehash: 1e5cb04bbd63c91d1302ace41b1c9bdbaa492574
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642991"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>조직의 모바일 정책 설정

사용자가 휴대폰 번호를 사용 하 여 휴대폰 전화를 걸고 받을 수 있는 기능 등 모바일 장치에서 비즈니스용 skype 앱에 대 한 skype Online에 연결 하는 방법을 설정할 수 있습니다. mber. 이동성 정책은 전화를 걸거나 받을 때 Wi-fi 연결이 필요한 경우에도 사용할 수 있습니다.
  
정책을 만들 때 모바일 정책 설정을 구성 하거나, **Set-CsMobilityPolicy** cmdlet을 사용 하 여 기존 정책의 설정을 수정할 수 있습니다.
  
## <a name="set-your-mobile-policies"></a>모바일 정책 설정

> [!NOTE]
> 비즈니스용 Skype Online의 모든 모바일 정책 설정에 대해 Windows PowerShell을 사용 해야 하며 **비즈니스용 skype 관리 센터**를 **사용할 수 없습니다** . 
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell 확인 및 시작

- **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
    
1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
    자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx)을 참조 하세요.
    
- **Windows PowerShell 세션 시작**
    
1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>사용자의 비디오에 대 한 WiFi 연결 필요

- 이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.
  > 
  > ```
  > New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  > ```
  > [새로운 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
- 만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  > ```
  > [CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
  이미 정책을 만든 경우 [CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음[부여-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet을 사용 하 여 사용자에 게 해당 설정을 적용할 수 있습니다.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>사용자가 비즈니스용 Skype 앱을 사용 하지 못하도록 방지

- 이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.
  ```
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  [새로운 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
- 만든 새 정책을 Amos 대리석에 부여 하려면 다음을 실행 합니다.  
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  > ```
  > [CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
  이미 정책을 만든 경우 [CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음 [부여-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet을 사용 하 여 사용자에 게 해당 설정을 적용할 수 있습니다.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>사용자가 모바일 장치를 사용 하 여 IP 통화를 할 수 없도록 설정

- 이러한 설정에 대 한 새 정책을 만들려면 다음을 실행 합니다.
  > 
  > ```
  > New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  > ```
  > [새로운 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
- 만든 새 정책을 조직의 모든 사용자에 게 부여 하려면 다음을 실행 합니다.
  > 
  > ```
  > Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  > ```

  [CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet에 대 한 자세한 내용을 확인 하세요.
    
이미 정책을 만든 경우 [CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet을 사용 하 여 기존 정책을 변경한 다음[부여-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet을 사용 하 여 사용자에 게 해당 설정을 적용할 수 있습니다.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[점 대 점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
 
