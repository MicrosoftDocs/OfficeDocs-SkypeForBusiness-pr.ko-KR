---
title: Lync Server 2013에 대해 온-프레미스 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34b6cd21d781f26ca734effd0c574c016aec3266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517585"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013에 대 한 온-프레미스 파트너 응용 프로그램 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-04_

OAuthTokenIssuer 인증서를 할당 한 후에는 Microsoft Lync Server 2013 파트너 응용 프로그램을 구성 해야 합니다. (설명 하기 위한 절차에는 Microsoft Exchange Server 2013와 Microsoft SharePoint가 파트너 응용 프로그램으로 작동 하도록 구성 됩니다.) 온-프레미스 파트너 응용 프로그램을 구성 하려면 다음 Windows PowerShell 스크립트를 복사 하 여 메모장 (또는 다른 텍스트 편집기)에 코드를 붙여 넣어 시작 해야 합니다.

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
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

코드를 복사한 후에는을 사용 하 여 스크립트를 저장 합니다. PS1 파일 확장명 (예를 들어 C: \\ Scripts \\ServerToServerAuth.ps1)입니다. 이 스크립트를 실행 하기 전에 메타 데이터 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 과 http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx Exchange 2013 및 SharePoint 서버에서 사용 하는 메타 데이터 url을 각각 대체 해야 합니다. 각 제품의 메타 데이터 URL을 식별 하는 방법에 대 한 자세한 내용은 Exchange 2013 및 SharePoint의 제품 설명서를 참조 하세요.

스크립트의 마지막 줄을 살펴보면 다음 구문을 사용 하 여 Set-CsOAuthConfiguration cmdlet을 호출 하는 것을 알 수 있습니다.

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Set-CsOAuthConfiguration를 호출할 때 Realm 매개 변수를 사용 하지 않았으므로 영역이 자동으로 조직의 FQDN (정규화 된 도메인 이름) (예: litwareinc.com)으로 설정 됩니다. 영역 이름이 조직 이름과 다른 경우 다음과 같이 영역 이름을 포함 해야 합니다.

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

이러한 변경을 수행한 후 스크립트를 실행 하 고 Lync Server 2013 관리 셸에서 스크립트 파일을 실행 하 여 Exchange 2013와 SharePoint를 모두 파트너 응용 프로그램으로 구성할 수 있습니다. 예제:

    C:\Scripts\ServerToServerAuth.ps1

Exchange 2013 및 SharePoint Server를 모두 설치 하지 않은 경우에도이 스크립트를 실행할 수 있습니다. SharePoint Server가 설치 되어 있지 않더라도 SharePoint Server를 파트너 응용 프로그램으로 구성 하는 경우에는 문제가 발생 하지 않습니다.

이 스크립트를 실행 하면 다음과 같은 오류 메시지가 표시 될 수 있습니다.

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

이 오류 메시지는 일반적으로 다음 두 가지 중 하나를 의미 합니다. 1) 스크립트에 지정 된 Url 중 하나가 유효 하지 않은 경우 (즉, 메타 데이터 Url 중 하나가 실제 메타 데이터 URL이 아님) 또는, 2) 메타 데이터 Url 중 하나에 연결할 수 없습니다. 이 경우 Url이 올바르고 액세스 가능 하며 스크립트를 다시 실행 하십시오.

Lync Server 2013에 대 한 파트너 응용 프로그램을 만든 후에는 Lync Server를 Exchange 2013에 대 한 파트너 응용 프로그램으로 구성 해야 합니다. 스크립트 Configure-EnterprisePartnerApplication.ps1를 실행 하 여 Exchange 2013에 대 한 파트너 응용 프로그램을 구성할 수 있습니다. Lync Server에 대 한 메타 데이터 URL을 지정 하 고 Lync Server가 새 파트너 응용 프로그램 임을 표시 하기만 하면 됩니다.

Lync Server를 Exchange 용 파트너 응용 프로그램으로 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다.

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

