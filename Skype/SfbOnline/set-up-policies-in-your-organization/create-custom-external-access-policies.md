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
f1keywords: None
ms.custom:
- Setup
description: 비즈니스용 Skype Online을 통해 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트나 회의 정책과는 달리, 미리 정의 된 세 가지 외부 액세스 정책이 있으며 대부분의 시나리오를 포함할 수 있습니다.
ms.openlocfilehash: 978bad4e87e3e7dbe2a9bac5565aa7a6a45ca2df
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962506"
---
# <a name="create-custom-external-access-policies"></a>사용자 지정 외부 액세스 정책 만들기

비즈니스용 Skype Online을 통해 추가 외부 액세스 정책을 만들 수 있습니다. 여러 조합을 사용할 수 있는 클라이언트나 회의 정책과는 달리, 미리 정의 된 세 가지 외부 액세스 정책이 있으며 대부분의 시나리오를 포함할 수 있습니다. 다음과 같습니다.
  
- 페더레이션 또는 Skype 소비자 액세스 없음 (_태그: NoFederationAndPIC_ )
    
- 페더레이션 액세스만 (_Tag: FederationOnly_ )
    
- 페더레이션 및 소비자 액세스 (_FederationAndPICDefault_)
    
사용자 지정 외부 정책을 사용 하 여 위의 설정에서 다루지 않는 추가 정책을 만들 수 있습니다. 정책을 만들면 필요한 모든 매개 변수를 설정 해야 하며 나중에 변경할 수 없습니다. 새 사용자 지정 정책을 만들면 Skype 소비자 액세스 또는 정책 등의 기능을 제어 하 여 미리 정의 된 설정으로 검사 되지 않은 공용 클라우드 오디오/비디오를 사용 하지 않도록 설정할 수 있습니다. 사용자 지정 외부 액세스 정책은 클라이언트, 이동성, 회의 정책과 동일한 구문을 따릅니다. 이러한 설정에 대 한 자세한 내용은 [여기](https://technet.microsoft.com/library/mt228132.aspx)에서 확인할 수 있습니다.
  
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
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
    자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.
    
- **Windows PowerShell 세션 시작**
    
1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows Powershell 용 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>사용자를 위한 사용자 지정 외부 액세스 정책 만들기

이 작업을 수행 하려면 다음을 실행 합니다.
  
> 
>   ```PowerShell
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```PowerShell
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[점 대 점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)

  
 
