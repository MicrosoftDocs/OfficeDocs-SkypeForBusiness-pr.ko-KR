---
title: Outlook을 사용 하 여 모임에 대 한 콘텐츠 미리 로드 허용 설정 또는 해제
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
description: 'Outlook 모임 초대에서 파일이 나 첨부 파일을 사용 하 여 비즈니스용 Skype 모임에서 미리 로드 된 콘텐츠를 설정 하거나 해제 하는 방법을 알아봅니다. '
ms.openlocfilehash: bee2d4094e1a85db39514e0757e58092544653a1
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164087"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Outlook을 사용 하 여 모임에 대 한 콘텐츠 미리 로드 허용 설정 또는 해제

사용자는 비즈니스용 Skype Online 모임에 Outlook 모임 초대에 연결 된 콘텐츠, 파일 또는 첨부 파일을 미리 로드할 수 있지만, 설정 하거나 해제할 수는 있습니다. 비즈니스용 Skype Online을 사용 하는 모든 조직에서 기본적으로 설정 되어 있습니다. [비즈니스용 Skype 모임에 대 한 첨부 파일을 미리 로드](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)하는 방법에 대해 알아봅니다.
  
> [!NOTE]
> 현재는 비즈니스용 Skype Online에서 _Maxcontentstoragemb_ 및 _MaxUploadFileMB_의 온라인 값을 설정 하거나 볼 수 있는 cmdlet이 없습니다. 온-프레미스 배포에만 사용할 수 있습니다. 첨부 된 콘텐츠가 _MaxUploadFileSizeMB_ 를 초과 하거나 _Maxcontentstoragemb_ 제한에 도달 하는 경우 콘텐츠가 모임에 업로드 되지 않는다는 것을 알아야 합니다.
  
## <a name="to-get-you-started"></a>시작 하기

### 

 **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
  
1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
자세한 정보를 알고 싶은 경우에 [는 단일 Windows PowerShell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.
  
### 

 **Windows PowerShell 세션 시작**
  
1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.
  
## <a name="turning-it-on-or-off"></a>설정 또는 해제

Outlook 모임 초대에 첨부 된 콘텐츠를 비즈니스용 Skype Online 모임에 미리 로드할 수 있지만, 조직의 사용자가 모임에서 콘텐츠를 미리 로드 하지 못하도록 해야 할 수 있습니다.
  
> [!IMPORTANT]
> 이 설정은 조직 전체에 대해 설정 하거나 해제할 수 있습니다. 단일 사용자에 대해이 기능을 설정 하거나 해제할 수 없습니다. 
  
 **해제 하려면 Windows PowerShell을 열고 다음을 수행 합니다.**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **다시 설정 하려면 Windows PowerShell을 열고 다음을 수행 합니다.**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 해야 하는 여섯 가지 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
