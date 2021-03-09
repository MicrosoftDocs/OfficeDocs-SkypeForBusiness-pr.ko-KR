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
description: 비즈니스용 Skype 사용자가 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용하여 사용자가 문제를 보고하고 해당 경험에 대한 피드백을 Microsoft에 직접 제공할 수 있도록 설정할 수 있습니다.
ms.openlocfilehash: 9b9134f857be540a528ca12b51a4793c01f70fa4
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569004"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>비즈니스용 Skype 클라이언트 피드백 보고 설정 또는 해제

비즈니스용 Skype Online 사용자가 기본 제공 비즈니스용 Skype 앱 피드백 도구를 사용하여 사용자가 문제를 보고하고 해당 경험에 대한 피드백을 Microsoft에 직접 제공할 수 있도록 설정할 수 있습니다. 
  
![피드백 제공 아이콘](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
이 도구를 사용하면 사용자가 디바이스의 앱에서 로그를 복사하여 Microsoft에서 발생할 수 있는 문제를 더 잘 조사하고 해결할 수 있습니다. 
  
![설정 아이콘을 사용하여 문제 보고](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
사용자가 피드백의 일부로 디바이스 스크린샷을 포함할 수 있도록  _EnableOnlineFeedbackScreenshot_ 설정을 사용할 수 있습니다.
  
![비즈니스용 Skype 클라이언트 보고 양식입니다.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> 앱의 피드백 도구에서 수집한 로그는 문제가 조사되는 동안 미국에서 최대 90일 동안 저장됩니다. 이 때문에 조직의 데이터 보호 정책을 위반하는 경우 이 피드백 도구를 사용하도록 설정하지 않습니다. 
  
## <a name="start-windows-powershell"></a>시작 Windows PowerShell

> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다. 최신 Teams PowerShell 공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.
1. Teams [PowerShell 모듈을 설치합니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. 명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다. 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>조직의 모든 사용자에 대한 클라이언트 앱 피드백 보고 설정

조직의 사용자에 대한 피드백 보고를 사용하도록 설정하고 디바이스 스크린샷을 제출할 수 있도록 허용하려면 다음을 실행합니다.
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?
- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365를 Windows PowerShell 사용하려는 6 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
