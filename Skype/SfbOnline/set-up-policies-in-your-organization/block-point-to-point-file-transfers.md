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
description: 비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point-to-Point) 파일 전송을 제어할 수 있습니다. 그러나 이 기능을 사용하면 파일을 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더리드 사용자로 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단할 수 있습니다. 아래 단계에 따라 페더리드 조직 또는 파트너를 사용하여 P2P 파일 전송을 차단할 수 있습니다.
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100624"
---
# <a name="block-point-to-point-file-transfers"></a>점 대 점 파일 전송 차단

비즈니스용 Skype Online에서는 기존 회의 정책 설정의 일부로 P2P(Point-to-Point) 파일 전송을 제어할 수 있습니다. 그러나 이 기능을 사용하면 파일을 동일한 조직 내에 있는 사용자 또는 다른 조직의 페더리드 사용자로 파일을 전송하는지 여부에 따라 사용자에 대한 파일 전송을 허용하거나 차단할 수 있습니다. 아래 단계에 따라 페더리드 조직 또는 파트너를 사용하여 P2P 파일 전송을 차단할 수 있습니다.
  
 매우 일반적인 시나리오는 내부 사용자가 P2P 파일 전송을 사용할 수 있도록 허용하지만 페더리드 파트너를 사용하여 파일 전송을 차단하려는 경우입니다. 이 시나리오에서는 다음을 해야 합니다.
  
- P2P 파일 전송을 사용하도록 설정된 회의 정책을 _할당합니다(EnableP2PFileTransfer를_ _True로_ 설정) 조직의 사용자에게 할당합니다.
    
- 외부 P2P 파일 전송을 차단하도록 글로벌 외부 사용자 통신 정책 집합을 _만들고(EnableP2PFileTransfer를_ _False로_ 설정) 조직 내 사용자에게 할당합니다. 
    
이러한 설정에 대한 자세한 내용은 여기를 [클릭하세요.](/previous-versions//mt228132(v=technet.10))
  
조직 외부의 페더리드 사용자가 정책이 적용된 사용자에게 파일을 보내고자 하면 전송 실패 오류가 **발생합니다.** 사용자가 파일을 보내면 파일 전송이 **꺼져** 있습니다.
  
이 작업을 실행하려면 사용자가 지원되는 2016년 비즈니스용 Skype 앱의 지원되는 버전을 사용해야 합니다. 비즈니스용 Skype 2016 Click-to-Run 클라이언트의 최소 버전이 필요합니다.
  
|**유형**|**릴리스 날짜**|**버전**|**빌드**|
|:-----|:-----|:-----|:-----|
|현재 채널에 대한 첫 번째 릴리스  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |버전 1611(빌드 7571.2006)  <br/> |
|현재 채널  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |버전 1611(빌드 7571.2072)  <br/> |
|지연 채널  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |버전 1609(빌드 7369.2118)  <br/> |
   
> [!CAUTION]
> 이전 버전의 비즈니스용 Skype Windows 앱 또는 Mac 클라이언트를 사용하는 사용자는 여전히 파일을 전송할 수 있습니다. 
  
## <a name="start-windows-powershell"></a>시작 Windows PowerShell

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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>조직의 P2P 파일 전송을 사용하지 않도록 설정

기본적으로 조직의 전역 정책에서 _EnableP2PFileTransfer를_ 사용하도록 설정됩니다. 이 정책을 만들 때 사용자에게 _BposSAllModality 정책이 할당되었습니다._
  
조직 내에서 P2P 전송을 허용하지만 다른 조직으로의 외부 파일 전송을 차단하려면 전역 수준에서만 변경해야 합니다. 이를 위해 다음을 실행합니다.
    
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

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

- Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
