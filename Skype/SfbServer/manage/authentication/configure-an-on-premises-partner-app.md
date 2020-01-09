---
title: 비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: '요약: 비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램을 구성 합니다.'
ms.openlocfilehash: 8f735de5c988dfea0da1adacdc4a77200d3a663d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992345"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램 구성
 
**요약:** 비즈니스용 Skype 서버에 대 한 온-프레미스 파트너 응용 프로그램을 구성 합니다.
  
OAuthTokenIssuer 인증서를 할당 한 후에는 비즈니스용 Skype 서버 파트너 응용 프로그램을 구성 해야 합니다. (논의에 대 한 절차에 따라 Microsoft Exchange Server 2013 및 SharePoint가 파트너 응용 프로그램 역할을 하는 것으로 구성 되며, 선택 사항입니다.) 온-프레미스 파트너 응용 프로그램을 구성 하려면 먼저 다음 Windows PowerShell 스크립트를 복사 하 여 코드를 메모장 (또는 기타 텍스트 편집기)에 붙여 넣어야 합니다.
  
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

코드를 복사한 후를 사용 하 여 스크립트를 저장 합니다. PS1 파일 확장명 (예: C:\Scripts\ServerToServerAuth.ps1). 이 스크립트를 실행 하기 전에 먼저 Exchange 2013 및 SharePoint 서버에서 사용 하 https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 는 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 메타 데이터 Url과 메타 데이터 url을 바꿔야 합니다. 각 제품의 메타 데이터 URL을 식별 하는 방법에 대 한 자세한 내용은 Exchange 2013 및 SharePoint의 제품 설명서를 참조 하세요.
  
스크립트의 마지막 줄을 보면이 구문을 사용 하 여 Set CsOAuthConfiguration cmdlet이 호출 된다는 사실을 알게 됩니다.
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Set-CsOAuthConfiguration을 호출할 때 Realm 매개 변수를 사용 하지 않았으므로 영역이 조직의 FQDN (정규화 된 도메인 이름) (예: litwareinc.com)으로 자동 설정 됩니다. 영역 이름이 조직 이름과 다른 경우 다음과 같이 영역 이름을 포함 해야 합니다.
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

이러한 변경 작업을 수행한 후에는 스크립트를 실행 하 고 비즈니스용 Skype 서버 관리 셸에서 스크립트 파일을 실행 하 여 Exchange 2013와 SharePoint를 파트너 응용 프로그램으로 구성할 수 있습니다. 예를 들면 다음과 같습니다.
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Exchange 2013 및 SharePoint Server가 설치 되어 있지 않은 경우에도이 스크립트를 실행할 수 있습니다. SharePoint Server가 설치 되어 있지 않은 경우에도 파트너 응용 프로그램으로 SharePoint Server를 구성 하는 경우에는 문제가 발생 하지 않습니다.
  
이 스크립트를 실행 하면 다음과 같은 오류 메시지가 나타날 수 있습니다.
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

이 오류 메시지는 일반적으로 스크립트에 지정 된 Url 중 하나가 유효 하지 않은 경우 (즉, 메타 데이터 Url 중 하나가 실제 메타 데이터 URL이 아닌 경우)에 해당 하는 두 가지 중 하나를 의미 합니다. 또는 2) 메타 데이터 Url 중 하나에 연결할 수 없습니다. 이 문제가 발생 하면 Url이 올바르며 액세스할 수 있는지 확인 하 고 스크립트를 다시 실행 합니다.
  
비즈니스용 Skype Server 용 파트너 응용 프로그램을 만든 후에는 비즈니스용 Skype 서버를 Exchange 2013 파트너 응용 프로그램으로 구성 해야 합니다. Configure-EnterprisePartnerApplication 스크립트를 실행 하 여 Exchange 2013에 대 한 파트너 응용 프로그램을 구성할 수 있습니다. 비즈니스용 Skype 서버용 메타 데이터 URL을 지정 하 고 비즈니스용 Skype 서버가 새 파트너 응용 프로그램 임을 표시 하기만 하면 됩니다. 
  
비즈니스용 Skype 서버를 Exchange 용 파트너 응용 프로그램으로 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다.
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


