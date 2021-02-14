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
description: 비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point to Point) 파일 전송을 제어할 수 있습니다. 그러나 사용자가 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더링된 사용자에게 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단합니다. 아래 단계에 따라 페더러드 조직 또는 파트너와의 P2P 파일 전송을 차단할 수 있습니다.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814637"
---
# <a name="block-point-to-point-file-transfers"></a>점 대 점 파일 전송 차단

비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point to Point) 파일 전송을 제어할 수 있습니다. 그러나 사용자가 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더링된 사용자에게 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단합니다. 아래 단계에 따라 페더러드 조직 또는 파트너와의 P2P 파일 전송을 차단할 수 있습니다.
  
 매우 일반적인 시나리오는 내부 사용자가 P2P 파일 전송을 사용하지만 페더러드 파트너와의 파일 전송을 차단하려는 경우입니다. 이 시나리오에서는 다음을 해야 합니다.
  
- 조직의 사용자에게 P2P 파일 전송이 _활성화된(EnableP2PFileTransfer가_ _True로_ 설정) 회의 정책을 할당합니다.
    
- 외부 P2P 파일 _전송(EnableP2PFileTransfer가_ _False로_ 설정)을 차단하도록 설정된 전역 외부 사용자 통신 정책을 만들고 조직의 사용자에게 할당합니다. 
    
이러한 설정에 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://technet.microsoft.com/library/mt228132.aspx)
  
조직 외부의 페더러드 사용자가 정책이 적용된 사용자에게 파일을 보내고자 하면 전송 실패 **오류가** 표시됩니다. 사용자가 파일을 보내면 파일 전송이 해제된 **오류가** 표시됩니다.
  
이 작업을 진행하려면 사용자가 지원되는 2016 비즈니스용 Skype 앱의 지원되는 버전을 사용하고 있어야 합니다. 비즈니스용 Skype 2016 Click-to-Run 클라이언트의 최소 버전은 다음과 같습니다.
  
|**유형**|**릴리스 날짜**|**버전**|**빌드**|
|:-----|:-----|:-----|:-----|
|현재 채널의 첫 번째 릴리스  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |버전 1611(빌드 7571.2006)  <br/> |
|현재 채널  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |버전 1611(빌드 7571.2072)  <br/> |
|지연 채널  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |버전 1609(빌드 7369.2118)  <br/> |
   
> [!CAUTION]
> 이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용하는 사용자는 여전히 파일을 전송할 수 있습니다. 
  
## <a name="verify-and-start-windows-powershell"></a>확인 및 Windows PowerShell

- **버전 3.0 Windows PowerShell 실행 중인지 확인**
    
    1. 버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.
        
    2. 웹 창에 _Get-Host를_ 입력하여 **Windows PowerShell** 확인
        
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>조직의 P2P 파일 전송 사용 안

기본적으로 _EnableP2PFileTransfer는_ 조직의 전역 정책에서 사용하도록 설정됩니다. 만들 때 사용자에게 _BposSAllModality 정책이 할당되었습니다._
  
조직 내부에서 P2P 전송을 허용하지만 다른 조직으로의 외부 파일 전송을 차단하려면 전역 수준에서 변경하면 됩니다. 이를 위해 다음을 실행합니다.
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>사용자에 대한 P2P 파일 전송 사용 안 하도록 설정

새 정책을 만들고 해당 사용자에게 부여하여 사용자에게 적용할 수 있습니다. 이를 위해 다음을 실행합니다. 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
 
