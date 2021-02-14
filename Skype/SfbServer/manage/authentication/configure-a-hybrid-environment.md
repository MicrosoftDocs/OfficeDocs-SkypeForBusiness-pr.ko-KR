---
title: 비즈니스용 Skype 서버 하이브리드 환경에 대한 서버 대 서버 인증 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '요약: 비즈니스용 Skype 서버 하이브리드 환경에 대해 서버 간 인증을 구성합니다.'
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828488"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="e638b-103">비즈니스용 Skype 서버 하이브리드 환경에 대해 서버 대 서버 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="e638b-104">**요약:** 비즈니스용 Skype 서버 하이브리드 환경에 대해 서버 대 서버 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="e638b-105">하이브리드 구성에서 일부 사용자는 비즈니스용 Skype 서버의 On-premises 설치에 있는 반면 다른 사용자는 Microsoft 365 또는 비즈니스용 Skype 서버의 Office 365 버전에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="e638b-106">하이브리드 환경에서 서버-서버 인증을 구성하려면 먼저 인증 서버를 신뢰하도록 비즈니스용 Skype 서버의 온라인 프레미스 설치를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="e638b-107">이 프로세스의 초기 단계는 다음 비즈니스용 Skype 서버 관리 셸 스크립트를 실행하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```PowerShell
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
```

<span data-ttu-id="e638b-p102">테넌트의 영역 이름은 일반적으로 조직 이름과 다릅니다. 하지만 실제로 영역 이름은 거의 항상 테넌트 ID와 동일합니다. 이러한 이유로 인해 스크립트의 첫 번째 줄은 지정된 테넌트(이 예의 경우 fabrikam.com)에 대한 TenantId 속성의 값을 반환하고 해당 이름을 $TenantId 변수에 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="e638b-110">이 스크립트를 실행하려면 비즈니스용 Skype Online PowerShell 모듈을 설치하고 이 모듈을 사용하여 테넌트에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="e638b-111">이러한 cmdlet을 설치하지 않은 경우 해당 cmdlet을 사용할 수 Get-CsTenant 수 있기 때문에 스크립트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="e638b-112">스크립트가 완료되면 비즈니스용 Skype 서버와 권한 부여 서버 간의 트러스트 관계와 Exchange 2013/2016과 권한 부여 서버 간의 두 번째 트러스트 관계를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="e638b-113">이 작업은 Microsoft Online Services cmdlet을 사용해서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="e638b-114">Microsoft Online Services cmdlet을 설치하지 않은 경우 이 cmdlet을 통해 PowerShell 리포지토리에서 설치해야 `install-module MSOnline` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="e638b-115">Microsoft Online Services 모듈을 설치하고 사용하는 자세한 정보는 Microsoft 365 웹 사이트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="e638b-116">이러한 지침에서는 Microsoft 365 또는 Office 365와 Active Directory 간에 Single Sign-On, 연결 및 동기화를 구성하는 방법도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="e638b-117">Microsoft 365 또는 Office 365를 구성한 후 비즈니스용 Skype 서버 및 Exchange 2013에 대한 Microsoft 365 또는 Office 365 서비스 계정을 만든 후 이러한 서비스 사용자에 자격 증명을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="e638b-118">이렇게하려면 먼저 . CER 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="e638b-119">이 인증서는 Microsoft 365 또는 Office 365 서비스 주체에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="e638b-120">X.509 인증서를 얻은 경우 PowerShell 콘솔을 열고 서비스 주체 관리에 사용할 수 있는 cmdlet이 Windows PowerShell 포함된 Microsoft Online Windows PowerShell 모듈을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="e638b-121">모듈을 가져온 후 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="e638b-122">Enter를 누르면 자격 증명 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="e638b-123">대화 상자에 Microsoft 365 또는 Office 365 사용자 이름과 암호를 입력한 다음 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="e638b-124">Microsoft 365 또는 Office 365에 연결되는 즉시 다음 명령을 실행하여 서비스 사용자에 대한 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="e638b-125">모든 서비스 계정에 대해 이와 비슷한 정보를 얻으려면</span><span class="sxs-lookup"><span data-stu-id="e638b-125">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="e638b-126">다음 단계에서는 X.509 인증서를 가져오고, 인코딩하고, 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="e638b-127">인증서를 가져오고 인코딩하기 위해 다음 Windows PowerShell 명령을 사용하여 전체 파일 경로를 지정해야 합니다. Import 메서드를 호출할 때 CER 파일:</span><span class="sxs-lookup"><span data-stu-id="e638b-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="e638b-128">인증서를 가져와 인코딩한 후 Microsoft 365 또는 Office 365 서비스 주체에 인증서를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="e638b-129">이를 위해 먼저 Get-MsolServicePrincipal 사용하여 비즈니스용 Skype 서버 및 Microsoft Exchange 서비스 사용자 모두에 대한 AppPrincipalId 속성 값을 검색합니다. AppPrincipalId 속성의 값은 인증서가 할당되는 서비스 주체를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="e638b-130">비즈니스용 Skype 서버의 AppPrincipalId 속성 값이 준비된 경우 다음 명령을 사용하여 비즈니스용 Skype Online 버전에 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="e638b-131">그런 다음 이번에는 Exchange 2013에 대해 AppPrincipalId 속성 값을 사용하여 명령을 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="e638b-132">인증서가 만료된 경우와 같은 나중에 해당 인증서를 삭제해야 하는 경우 먼저 인증서의 KeyId를 검색하여 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="e638b-133">이 명령은 다음과 비슷한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="e638b-134">그런 후 다음과 비슷한 명령을 사용하여 인증서를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="e638b-135">인증서를 할당하는 것 외에도 Exchange Online 서비스 사용자 및 비즈니스용 Skype 서버 외부 웹 서비스 URL의온-프레미스 버전을 Microsoft 365 또는 Office 365 서비스 사용자로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="e638b-136">이 명령은 다음 두 명령을 수행하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="e638b-137">다음 예제에서는 Pool1ExternalWebFQDN.contoso.com 비즈니스용 Skype 서버 풀의 외부 웹 서비스 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="e638b-138">이러한 단계를 반복하여 배포의 모든 외부 웹 서비스 URL을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638b-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
