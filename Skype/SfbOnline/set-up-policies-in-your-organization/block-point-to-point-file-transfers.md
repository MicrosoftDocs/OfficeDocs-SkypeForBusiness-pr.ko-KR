---
title: 점 대 점 파일 전송 차단
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 서 지점간 (P2P) 파일 전송을 제어할 수 있습니다. 그러나이 방법을 사용 하면 사용자가 같은 조직 내에 있거나 다른 조직의 페더레이션 사용자에 게 파일을 전송 하는지 여부에 관계 없이 파일 전송을 허용 하거나 차단할 수 있습니다. 아래 단계에 따라 페더레이션된 조직이 나 파트너와의 P2P 파일 전송을 차단할 수 있습니다.
ms.openlocfilehash: 773feaa97a888bd2063710de9e72f8c7b465a813
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164727"
---
# <a name="block-point-to-point-file-transfers"></a>점 대 점 파일 전송 차단

비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 서 지점간 (P2P) 파일 전송을 제어할 수 있습니다. 그러나이 방법을 사용 하면 사용자가 같은 조직 내에 있거나 다른 조직의 페더레이션 사용자에 게 파일을 전송 하는지 여부에 관계 없이 파일 전송을 허용 하거나 차단할 수 있습니다. 아래 단계에 따라 페더레이션된 조직이 나 파트너와의 P2P 파일 전송을 차단할 수 있습니다.
  
 일반적으로 내부 사용자는 P2P 파일 전송을 사용할 수 있지만 페더레이션 파트너와 파일 전송을 차단 하는 경우가 있습니다. 이 시나리오에서는 다음을 수행 해야 합니다.
  
- P2P 파일 전송 기능을 사용 하는 회의 정책 (_EnableP2PFileTransfer_ 설정 _)을_조직의 사용자에 게 할당 합니다.
    
- 전역 외부 사용자 통신 정책 만들기 (_EnableP2PFileTransfer_ 를 _False_로 설정)로 차단 하 고 조직의 사용자에 게 해당 파일을 할당 하도록 설정 합니다. 
    
이러한 설정에 대 한 자세한 내용은 [여기](https://technet.microsoft.com/library/mt228132.aspx)에서 확인할 수 있습니다.
  
조직 외부의 페더레이션 사용자가 정책이 적용 된 사용자에 게 파일을 보내려고 하면 **전송 실패** 오류가 표시 됩니다. 사용자가 파일을 보내려고 하면 **파일 전송이 해제** 오류 메시지가 표시 됩니다.
  
이 작업을 수행 하려면 사용자가 지원 되는 버전의 2016 간편 실행 비즈니스용 Skype 앱을 사용 해야 합니다. 다음의 최소 버전의 비즈니스용 Skype 2016 간편 실행 클라이언트를 선택 해야 합니다.
  
|**유형**|**릴리스 날짜**|**버전**|**빌드한**|
|:-----|:-----|:-----|:-----|
|현재 채널의 첫 번째 릴리스  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |버전 1611 (빌드 7571.2006)  <br/> |
|현재 채널  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |버전 1611 (빌드 7571.2072)  <br/> |
|지연 채널  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |버전 1609 (빌드 7369.2118)  <br/> |
   
> [!CAUTION]
> 이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용 하는 사용자는 계속 파일을 전송할 수 있습니다. 
  
## <a name="verify-and-start-windows-powershell"></a>Windows PowerShell 확인 및 시작

- **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
    
    1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
        
    2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
        
    3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
        
    4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
    자세한 정보를 알고 싶은 경우에 [는 단일 Windows PowerShell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.
    
- **Windows PowerShell 세션 시작**
    
    1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
        
    2. **Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.
    
        > [!NOTE]
        > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Microsoft 365 또는 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>조직에서 P2P 파일 전송을 사용 하지 않도록 설정

기본적으로 _EnableP2PFileTransfer_ 는 조직의 글로벌 정책에 따라 사용 하도록 설정 됩니다. 이 파일을 만든 후에는 사용자에 게 _BposSAllModality_ 정책이 할당 되었습니다.
  
조직 내부에 대 한 P2P 전송을 허용 하지만 다른 조직에 대 한 외부 파일 전송을 차단 하는 경우 전역 수준 에서만 변경 해야 합니다. 이 작업을 수행 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>사용자에 대해 P2P 파일 전송을 사용 하지 않도록 설정

새 정책을 만들고 해당 사용자에 게 부여 하 여 사용자에 게 적용할 수 있습니다. 이 작업을 수행 하려면 다음을 실행 합니다. 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
 
