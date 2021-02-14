---
title: Outlook을 사용하여 모임에 콘텐츠 미리 로드 허용 설정 또는 해제
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
description: 'Outlook 모임 초대에서 파일 또는 첨부 파일을 사용하여 비즈니스용 Skype 모임에 대해 미리 로드된 콘텐츠를 설정하거나 해제하는 방법을 참조하세요. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814587"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Outlook을 사용하여 모임에 콘텐츠 미리 로드 허용 설정 또는 해제

사용자는 Outlook 모임 초대에 첨부된 콘텐츠, 파일 또는 첨부 파일을 비즈니스용 Skype Online 모임에 미리 로드할 수 있지만 설정하거나 해제할 수 있습니다. 비즈니스용 Skype Online을 사용하는 모든 조직에 대해 기본적으로 설정되어 있습니다. 비즈니스용 Skype 모임에 대한 첨부 파일을 미리 [로드하는 방법을 참조하세요.](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)
  
> [!NOTE]
> 현재  _MaxContentStorageMB_ 및 _MaxUploadFileMB에_ 대한 온라인 값을 설정하거나 보기 위해 비즈니스용 Skype Online에는 사용할 수 있는 cmdlet이 없습니다. 이러한 구성은 프레미스 배포에만 사용할 수 있습니다. 첨부된 콘텐츠가  _MaxUploadFileSizeMB를_ 초과하거나 _MaxContentStorageMB_ 제한에 도달한 경우 콘텐츠가 모임에 업로드되지 않습니다.
  
## <a name="to-get-you-started"></a>시작

### 

 **버전 3.0 Windows PowerShell 실행 중인지 확인**
  
1. 버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.
    
2. 웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 검사합니다.
    
3. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다. 메시지가 표시될 때 컴퓨터를 다시 시작합니다.
    
4. 또한 비즈니스용 Skype Online에 Windows PowerShell 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688) 메시지가 표시될 경우 컴퓨터를 다시 시작합니다.
    
자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)
  
### 

 **세션 Windows PowerShell 시작**
  
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
  
## <a name="turning-it-on-or-off"></a>켜기 또는 끄기

비즈니스용 Skype Online 모임에 Outlook 모임 초대에 첨부된 콘텐츠를 미리 로드할 수 있는 설정은 기본적으로 설정되어 있지만 조직의 사용자가 모임에서 콘텐츠를 미리 로드하지 못하게 해야 할 수도 있습니다.
  
> [!IMPORTANT]
> 이 설정은 전체 조직에 대해 설정하거나 해제할 수 있습니다. 단일 사용자에 대해 설정하거나 해제할 수 없습니다. 
  
 **이 기능을 해제하기 위해 Windows PowerShell 다음을 합니다.**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **다시 설정하려는 경우 다음을 Windows PowerShell 합니다.**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365를 관리하기 위해 Windows PowerShell 사용할 수 있는 6 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
