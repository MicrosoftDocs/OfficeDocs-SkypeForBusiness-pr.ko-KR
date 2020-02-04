---
title: 비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
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
description: 비즈니스용 Skype 사용자에 게 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용 하 여 사용자에 게 문제를 보고 하 고 Microsoft에 직접 의견을 제공할 수 있도록 하는 것이 좋습니다.
ms.openlocfilehash: 7d9b94b31e51287f535628c8485d263301ef991b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706293"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제

비즈니스용 Skype Online 사용자에 게 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용 하 여 사용자에 게 문제를 보고 하 고 Microsoft에 직접 의견을 제공할 수 있도록 하는 기능을 사용 하도록 설정 합니다. 
  
![비즈니스용 Skype 클라이언트 보고.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
이 도구를 사용 하면 사용자가 장치에서 앱의 로그를 복사 하 여 Microsoft가 발생할 수 있는 문제를 보다 효율적으로 조사 하 고 해결할 수 있습니다. 
  
![비즈니스용 Skype 클라이언트 보고.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
_EnableOnlineFeedbackScreenshot_ 설정을 사용 하 여 사용자가 자신의 피드백의 일부로 디바이스의 스크린샷을 포함할 수 있도록 할 수도 있습니다.
  
![비즈니스용 Skype 클라이언트 보고 양식](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> 앱의 피드백 도구를 통해 수집 된 로그는 문제를 조사 하는 동안 최대 90 일 동안 해당 지역에 저장 됩니다. 이 때문에 조직의 데이터 보호 정책에 위배 되는 경우이 피드백 도구를 사용 하지 마세요. 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell 확인 및 시작

- **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
    
1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.
    
- **Windows PowerShell 세션 시작**
    
1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.
 
   ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는[Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>조직의 모든 사용자에 대 한 클라이언트 앱 피드백 보고 설정

조직의 사용자에 대 한 피드백 보고 기능을 사용 하도록 설정 하 고 장치 스크린샷 제출 하도록 허용 하려면 다음을 실행 합니다.
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?
- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 데 필요한 여섯 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 주제
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
