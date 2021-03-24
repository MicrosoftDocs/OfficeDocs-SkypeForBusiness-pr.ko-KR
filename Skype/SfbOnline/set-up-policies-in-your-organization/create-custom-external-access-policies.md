---
title: 사용자 지정 외부 액세스 정책 만들기
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: 비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 미리 정의된 세 가지 외부 액세스 정책이 있습니다.
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100614"
---
# <a name="create-custom-external-access-policies"></a>사용자 지정 외부 액세스 정책 만들기

비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 미리 정의된 세 가지 외부 액세스 정책이 있습니다. 다음은 다음 사항일 수 있습니다.
  
- 페더리드 또는 Skype 소비자 액세스 _없음(Tag:NoFederationAndPIC)_
    
- 페더리드 액세스 _전용(Tag:FederationOnly)_
    
- 페더레이드 및 소비자 _액세스(페더리게이트AndPICDefault)_
    
사용자 지정 외부 정책을 사용하면 위의 설정에서 다루지 않는 추가 정책을 만들 수 있습니다. 정책을 만들 때 필요한 모든 매개 변수를 설정해야 하며 나중에 변경할 수 없습니다. 새 사용자 지정 정책을 만들면 Skype 소비자 액세스 또는 공용 클라우드 오디오/비디오를 사용하지 않도록 설정하는 정책과 같은 기능을 제어할 수 있습니다. 이는 미리 정의된 설정으로 다루지 않은 것입니다. 사용자 지정 외부 액세스 정책은 클라이언트, 이동성 및 회의 정책과 동일한 구문을 따르고 있습니다. 이러한 설정에 대한 자세한 내용은 여기를 [클릭하세요.](/previous-versions//mt228132(v=technet.10))
  
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
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>사용자에 대한 사용자 지정 외부 액세스 정책 만들기

이렇게 하여 다음을 실행합니다.
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[지점 및 지점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
