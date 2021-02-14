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
description: 비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 세 가지 미리 정의된 외부 액세스 정책이 있습니다.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814197"
---
# <a name="create-custom-external-access-policies"></a>사용자 지정 외부 액세스 정책 만들기

비즈니스용 Skype Online을 사용하면 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트 또는 회의 정책과 달리, 대부분의 시나리오를 다를 수 있는 세 가지 미리 정의된 외부 액세스 정책이 있습니다. 다음은
  
- 페더레드 또는 Skype 소비자 액세스 _없음(Tag:NoFederationAndPIC)_
    
- 페더리된 액세스 _전용(Tag:FederationOnly)_
    
- 페더레이드 및 소비자 _액세스(FederationAndPICDefault)_
    
사용자 지정 외부 정책을 사용하면 위의 설정에서 다루지 않는 추가 정책을 만들 수 있습니다. 정책을 만들 때 필요한 모든 매개 변수를 설정해야 하며 나중에 변경할 수 없습니다. 새 사용자 지정 정책을 만들면 Skype 소비자 액세스 또는 공용 클라우드 오디오/비디오를 사용하지 않도록 설정하는 정책과 같은 기능을 제어할 수 있습니다. 이 기능은 미리 정의되어 있는 설정에서 다루지 않습니다. 사용자 지정 외부 액세스 정책은 클라이언트, 이동성 및 회의 정책과 동일한 구문을 따르고 있습니다. 이러한 설정에 대한 자세한 내용은 여기에서 찾을 수 [있습니다.](https://technet.microsoft.com/library/mt228132.aspx)
  
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
    
2. 웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인
    
3. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://www.microsoft.com/download/details.aspx?id=40855) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다. 메시지가 표시될 때 컴퓨터를 다시 시작합니다.
    
4. 또한 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 Teams용 Windows PowerShell 모듈을 설치해야 합니다.
    
    자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)
    
- **세션 Windows PowerShell 시작**
    
1. 시작 **메뉴에서**  >  **Windows PowerShell.**
    
2. 다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.
    
  > [!NOTE]
  > 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
  >
  > 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Windows PowerShell 시작에 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>사용자에 대한 사용자 지정 외부 액세스 정책 만들기

이를 위해 다음을 실행합니다.
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[지점 및 지점 및 지점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
 
