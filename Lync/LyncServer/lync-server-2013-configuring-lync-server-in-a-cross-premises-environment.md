---
title: 'Lync Server 2013: 교차 프레미스 환경에서 Lync 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>교차 프레미스 환경에서 Microsoft Lync Server 2013 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-02-21_

교차 프레미스 구성에서 일부 사용자는 다른 사용자가 Office 365 버전의 Lync Server에 속한 동안 Microsoft Lync Server 2013의 온-프레미스 설치에 설정 됩니다. 교차 프레미스 환경에서 서버 간 인증을 구성 하려면 먼저 Lync Server 2013의 온-프레미스 설치를 구성 하 여 Office 365 권한 부여 서버를 신뢰 해야 합니다. 이 프로세스의 초기 단계는 다음 Lync Server Management Shell 스크립트를 실행 하 여 수행할 수 있습니다.

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

테 넌 트에서 일반적으로 조직 이름과 다른 영역 이름을 사용할 수 있다는 점에 유의 하세요. 실제로 영역 이름은 테 넌 트 ID와 거의 항상 동일 합니다. 이 때문에 스크립트의 첫 번째 줄을 사용 하 여 지정 된 테 넌 트에 대 한 TenantId 속성 값 (이 경우 fabrikam.com)을 반환 하 고 해당 이름을 변수 $TenantId에 할당 합니다.

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

스크립트를 완료 한 후에는 Lync Server 2013 및 권한 부여 서버와 Exchange 2013 및 권한 부여 서버 간의 두 번째 신뢰 관계 간에 신뢰 관계를 구성 해야 합니다. 이 작업은 Microsoft Online Services cmdlet을 사용 하는 경우에만 가능 합니다.

<div>


> [!NOTE]  
> Microsoft Online Services cmdlet을 설치 하지 않은 경우에는 계속 하기 전에 두 가지 작업을 수행 해야 합니다. 먼저 64 비트 버전의 Microsoft Online Services 로그인 도우미를 다운로드 하 여 설치 합니다. 설치가 완료 되 면 64 비트 버전의 Windows PowerShell 용 Microsoft Online Services 모듈을 다운로드 하 여 설치 합니다. Microsoft Online Services 모듈을 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 Office 365 웹 사이트에 나와 있습니다. 이 지침에서는 Office 365와 Active Directory 간의 single sign-on, 페더레이션 및 동기화를 구성 하는 방법에 대해서도 설명 합니다.<BR>이러한 cmdlet을 설치 하지 않은 경우 CsTenant cmdlet을 사용할 수 없으므로 스크립트는 실패 합니다.



</div>

Office 365을 구성한 후 Lync Server 2013 및 Exchange 2013에 대 한 Office 365 서비스 사용자를 만든 후에는 이러한 서비스 사용자에 게 자격 증명을 등록 해야 합니다. 이를 위해서는 먼저로 저장 된 x.509 Base64를 가져와야 합니다. CER 파일. 그러면이 인증서가 Office 365 서비스 사용자에 게 적용 됩니다.

X.509 인증서를 얻었으면 **시작**, **모든 프로그램**, **microsoft 온라인 서비스**를 차례로 클릭 한 다음 **Windows PowerShell 용 microsoft Online Services 모듈**을 클릭 하 여 microsoft online services 모듈을 시작 합니다. 서비스 모듈을 연 후 다음을 입력 하 여 서비스 사용자를 관리 하는 데 사용할 수 있는 cmdlet이 포함 된 Microsoft Online Windows PowerShell 모듈을 가져옵니다.

    Import-Module MSOnlineExtended

모듈을 가져왔으면 다음 명령을 입력 하 고 enter 키를 눌러 Office 365에 연결 합니다.

    Connect-MsolService

Enter 키를 누르면 자격 증명 대화 상자가 표시 됩니다. 대화 상자에 Office 365 사용자 이름 및 암호를 입력 한 다음 확인을 클릭 합니다.

Office 365에 연결 되 자 마자 다음 명령을 실행 하 여 서비스 사용자에 대 한 정보를 반환할 수 있습니다.

    Get-MsolServicePrincipal

모든 서비스 사용자에 대해 다음과 같은 정보가 다시 표시 됩니다.

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

다음 단계는 x.509 인증서를 가져오고, 인코딩하고, 할당 하는 것입니다. 인증서를 가져오고 인코딩하려면 다음 Windows PowerShell 명령을 사용 하 여에 대 한 전체 파일 경로를 지정 해야 합니다. CER 파일에서 가져오기 메서드를 호출 하는 경우:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

인증서를 가져와 인코딩한 후에는 Office 365 서비스 사용자에 게 인증서를 할당할 수 있습니다. 이렇게 하려면 먼저 Get-MsolServicePrincipal를 사용 하 여 Lync Server와 Microsoft Exchange 서비스 사용자 둘 다에 대 한 AppPrincipalId 속성의 값을 검색 합니다. AppPrincipalId 속성 값은 인증서를 할당 하는 서비스 사용자를 식별 하는 데 사용 됩니다. Lync Server 2013에 대 한 AppPrincipalId 속성 값을 사용 하는 경우 다음 명령을 실행 하 여 Lync Server의 Office 365 버전에 인증서를 할당 합니다 (시작 및 EndDate 속성은 인증서의 유효 기간에 해당 해야 함).

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

그런 다음 Exchange 2013에 대 한 AppPrincipalId 속성 값을 사용 하 여이 명령을 반복 해야 합니다.

나중에 해당 인증서를 삭제 해야 하는 경우 먼저 인증서에 대 한 KeyId를 검색 하 여이를 확인할 수 있습니다.

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

해당 명령은 다음과 같은 데이터를 반환 합니다.

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

그러면 다음과 같은 명령을 사용 하 여 인증서를 삭제할 수 있습니다.

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

인증서를 할당 하는 것 외에도 온-프레미스 버전의 Lync Server 2013에 대 한 서버 사용자 이름을 추가 하 여 Exchange Online에 대 한 Office 365 서비스 사용자를 구성 해야 합니다. Microsoft Online Services PowerShell 세션에서 다음 네 가지 줄을 실행 하 여이 작업을 수행할 수 있습니다.

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

