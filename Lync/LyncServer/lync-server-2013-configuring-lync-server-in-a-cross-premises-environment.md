---
title: 'Lync Server 2013: 크로스-프레미스 환경에서 Lync Server 구성'
description: 'Lync Server 2013: 크로스-프레미스 환경에서 Lync Server를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec978cd8e0e34c01c1d5cabb5bba42debd16fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570864"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="bdbdf-103">크로스-프레미스 환경에서 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="bdbdf-103">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdbdf-104">_**마지막으로 수정 된 항목:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="bdbdf-104">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="bdbdf-105">크로스-프레미스 구성에서는 일부 사용자가 microsoft Lync Server 2013의 온-프레미스 설치를 진행 하는 동안 다른 사용자는 Office 365의 Lync Server 버전 365에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-105">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Microsoft 365 or Office 365 version of Lync Server.</span></span> <span data-ttu-id="bdbdf-106">크로스-프레미스 환경에서 서버 간 인증을 구성 하려면 먼저 Microsoft 365 인증 서버를 신뢰 하도록 Lync Server 2013의 온-프레미스 설치를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-106">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Microsoft 365 Authorization server.</span></span> <span data-ttu-id="bdbdf-107">이 프로세스의 초기 단계는 다음 Lync Server 관리 셸 스크립트를 실행 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-107">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="bdbdf-p102">테넌트의 영역 이름은 일반적으로 조직 이름과 다릅니다. 하지만 실제로 영역 이름은 거의 항상 테넌트 ID와 동일합니다. 이러한 이유로 인해 스크립트의 첫 번째 줄은 지정된 테넌트(이 예의 경우 fabrikam.com)에 대한 TenantId 속성의 값을 반환하고 해당 이름을 $TenantId 변수에 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="bdbdf-110">스크립트를 완료 한 후에는 Lync Server 2013 및 권한 부여 서버와 Exchange 2013과 인증 서버 간의 두 번째 트러스트 관계 간에 트러스트 관계를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-110">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="bdbdf-111">이 작업은 Microsoft Online Services cmdlet을 사용해서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdbdf-112">Microsoft Online Services cmdlet을 설치하지 않은 경우 계속하기 전에 두 가지 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-112">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="bdbdf-113">우선 Microsoft Online Services 로그인 도우미의 64비트 버전을 다운로드하고 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="bdbdf-114">설치가 완료 되 면 64 비트 버전의 Windows PowerShell 용 Microsoft Online Services 모듈을 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="bdbdf-115">Microsoft Online Services 모듈을 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 Microsoft 365 또는 Office 365 웹 사이트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 or Office 365 web site.</span></span> <span data-ttu-id="bdbdf-116">이러한 지침에서는 Microsoft 365 또는 Office 36과 Active Directory 간의 single sign-on, 페더레이션 및 동기화를 구성 하는 방법에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 36 and Active Directory.</span></span><BR><span data-ttu-id="bdbdf-117">이러한 cmdlet을 설치 하지 않은 경우에는 Get-CsTenant cmdlet을 사용할 수 없으므로 스크립트에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="bdbdf-118">Microsoft 365를 구성 하 고 Lync Server 2013 및 Exchange 2013 용 Microsoft 365 또는 Office 365 서비스 사용자를 만든 후에는 이러한 서비스 주체에 자격 증명을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-118">After you have configured Microsoft 365, and after you have created Microsoft 365 or Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="bdbdf-119">이렇게 하려면 먼저 .CER 파일로 저장된 X.509 Base64를 구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="bdbdf-120">이 인증서는 Microsoft 365 또는 Office 365 서비스 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-120">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="bdbdf-121">X.509 인증서를 가져온 후에는 Microsoft Online Services 모듈 ( **시작**, **모든 프로그램**, **microsoft online services**를 차례로 클릭 하 고 **Windows PowerShell 용 Microsoft Online services 모듈**을 클릭 합니다.)을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="bdbdf-122">서비스 모듈이 열리면 다음을 입력 하 여 서비스 사용자를 관리 하는 데 사용할 수 있는 cmdlet이 포함 된 Microsoft Online Windows PowerShell 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="bdbdf-123">모듈을 가져왔으면 다음 명령을 입력 하 고 enter 키를 눌러 Microsoft 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-123">When the module has been imported, type the following command and then press ENTER in order to connect to Microsoft 365:</span></span>

    Connect-MsolService

<span data-ttu-id="bdbdf-124">Enter를 누르면 자격 증명 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="bdbdf-125">대화 상자에 Microsoft 365 또는 Office 365 사용자 이름과 암호를 입력 한 다음 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-125">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="bdbdf-126">Microsoft 365에 연결 되는 즉시 서비스 계정에 대 한 정보를 반환 하기 위해 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-126">As soon as you are connected to Microsoft 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="bdbdf-127">모든 서비스 계정에 대해 이와 비슷한 정보를 얻으려면</span><span class="sxs-lookup"><span data-stu-id="bdbdf-127">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="bdbdf-128">다음 단계에서는 X.509 인증서를 가져오고, 인코딩하고, 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="bdbdf-129">인증서를 가져오고 인코딩하려면 다음 Windows PowerShell 명령을 사용 하 여에 대 한 전체 파일 경로를 지정 해야 합니다. CER 파일에서 가져오기 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="bdbdf-130">인증서를 가져오고 인코딩한 후에는 인증서를 Microsoft 365 서비스 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-130">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 service principals.</span></span> <span data-ttu-id="bdbdf-131">이 작업을 수행 하려면 먼저 Get-MsolServicePrincipal를 사용 하 여 Lync Server 및 Microsoft Exchange 서비스 사용자 둘 다에 대 한 AppPrincipalId 속성 값을 검색 합니다. AppPrincipalId 속성 값은 인증서가 할당 되는 서비스 사용자를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="bdbdf-132">Lync Server 2013의 AppPrincipalId 속성 값을 사용 하 여 Microsoft 365 버전의 Lync Server (시작 날짜 및 EndDate 속성은 인증서의 유효 기간에 해당)에 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-132">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Microsoft 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="bdbdf-133">이 때 Exchange 2013에 AppPrincipalId 속성 값을 사용 하 여이 명령을 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="bdbdf-134">해당 인증서를 나중에 삭제해야 할 때는 먼저 인증서의KeyID를 검색하여 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="bdbdf-135">이 명령은 다음과 비슷한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-135">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="bdbdf-136">그런 후 다음과 비슷한 명령을 사용하여 인증서를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-136">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="bdbdf-137">인증서를 할당 하는 것 외에도 온-프레미스 버전의 Lync Server 2013에 대 한 서버 사용자 이름을 추가 하 여 Exchange Online에 대 한 Microsoft 365 서비스 사용자를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-137">In addition to assigning a certificate you must also configure the Microsoft 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="bdbdf-138">이 작업은 Microsoft Online Services PowerShell 세션에서 다음의 네 가지 선을 실행 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdbdf-138">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

