---
title: 사용자에 대해 프레미스 파트너 응용 프로그램을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '요약: 사용자에 대해 프레미스 파트너 응용 프로그램을 비즈니스용 Skype 서버.'
ms.openlocfilehash: c3ad8184d7a63afa5b481c62901be13a7c5915e2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392610"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>사용자에 대해 프레미스 파트너 응용 프로그램을 비즈니스용 Skype 서버
 
**요약:** 사용자에 대해 프레미스 파트너 응용 프로그램을 비즈니스용 Skype 서버.
  
OAuthTokenIssuer 인증서를 할당한 후 파트너 응용 프로그램을 비즈니스용 Skype 서버 합니다. 설명할 절차는 Microsoft Exchange Server 2013과 SharePoint 응용 프로그램(선택 사항)으로 구성됩니다. 프레미스 파트너 응용 프로그램을 구성하려면 먼저 다음 Windows PowerShell 스크립트를 복사하고 코드를 메모장 다른 텍스트 편집기로 붙여넣아야 합니다.
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

코드를 복사한 후 파일 확장명(예: .PS1)을 사용하여 스크립트를 C:\Scripts\ServerToServerAuth.ps1. 이 스크립트 `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` `http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1` 를 실행하기 전에 메타데이터 URL 및 Exchange 2013 및 SharePoint 서버에서 사용하는 메타데이터 URL로 바꾸야 합니다. 각 제품의 메타데이터 URL을 식별하는 Exchange 방법에 대한 자세한 내용은 Exchange 2013 및 SharePoint 설명서를 참조하세요.
  
스크립트의 마지막 줄을 보면 다음 구문을 사용하여 Set-CsOAuthConfiguration cmdlet이 호출됩니다.
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Realm 매개 변수를 호출할 때 사용되지 Set-CsOAuthConfiguration 영역은 조직의 FQDN(FQDN)(예: litwareinc.com)으로 자동 설정됩니다. 사용자 이름이 조직 이름과 다른 경우 다음과 같이 실제 이름을 포함해야 합니다.
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

이러한 변경 내용을 적용한 후 Exchange 관리 셸 내에서 스크립트 파일을 실행하여 Exchange 2013 및 SharePoint 파일을 파트너 응용 프로그램으로 구성할 비즈니스용 Skype 서버 있습니다. 예제:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Exchange 2013 및 SharePoint Server가 모두 설치되어 있지 않은 경우에도 이 스크립트를 실행할 수 있습니다. 즉, SharePoint Server를 파트너 응용 프로그램으로 구성하는 경우 SharePoint Server를 설치하지 않은 경우에도 문제가 발생하지 않습니다.
  
이 스크립트를 실행하면 다음과 같은 오류 메시지가 표시될 수 있습니다.
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

이 오류 메시지는 일반적으로 두 가지 중 하나를 의미합니다. 1) 스크립트에 지정된 URL 중 하나가 유효하지 않습니다(즉, 메타데이터 URL 중 하나는 실제 메타데이터 URL이 아 아닐 수 있습니다). 또는 2) 메타데이터 URL 중 하나에 연결하지 못합니다. 이 경우 URL이 올바른지와 액세스가 가능한지 확인하고 스크립트를 다시 실행합니다.
  
비즈니스용 파트너 응용 프로그램을 비즈니스용 Skype 서버 2013의 파트너 비즈니스용 Skype 서버 응용 프로그램으로 구성해야 Exchange 합니다. 스크립트 Configure-EnterprisePartnerApplication.ps1 실행하여 Exchange 2013에 대한 파트너 응용 프로그램을 구성할 수 있습니다. 비즈니스용 Skype 서버 메타데이터 URL을 지정하고 비즈니스용 Skype 서버 새 파트너 응용 프로그램으로 지정하기만하면 됩니다. 
  
비즈니스용 Skype 서버 파트너 응용 프로그램으로 Exchange 관리 셸을 Exchange 다음 명령을 실행합니다.
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


