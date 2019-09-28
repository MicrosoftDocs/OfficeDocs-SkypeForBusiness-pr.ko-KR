---
title: 비즈니스용 Skype Server 하이브리드 환경에 대 한 서버 대 서버 인증 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '요약: 비즈니스용 Skype 서버 하이브리드 환경에 대 한 서버 대 서버 인증을 구성 합니다.'
ms.openlocfilehash: 2879a1acc35a2c8928a95af913476c26028d6e6c
ms.sourcegitcommit: 1721acdd507591d16a4e766b390b997979d985e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37305774"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="64303-103">비즈니스용 Skype 서버 하이브리드 환경에 대 한 서버 대 서버 인증을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="64303-104">**요약:** 비즈니스용 Skype 서버 하이브리드 환경에 대해 서버 간 인증을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="64303-105">하이브리드 구성에서 일부 사용자는 다른 사용자가 비즈니스용 skype Server의 온-프레미스 설치에 있고 Office 365 버전의 비즈니스용 Skype 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="64303-106">하이브리드 환경에서 서버 간 인증을 구성 하려면 먼저 비즈니스용 Skype Server의 온-프레미스 설치를 구성 하 여 Office 365 권한 부여 서버를 신뢰 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="64303-107">이 프로세스의 초기 단계는 다음 비즈니스용 Skype 서버 관리 셸 스크립트를 실행 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```
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

<span data-ttu-id="64303-108">테 넌 트에서 일반적으로 조직 이름과 다른 영역 이름을 사용할 수 있다는 점에 유의 하세요. 실제로 영역 이름은 테 넌 트 ID와 거의 항상 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-108">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID.</span></span> <span data-ttu-id="64303-109">이 때문에 스크립트의 첫 번째 줄을 사용 하 여 지정 된 테 넌 트에 대 한 TenantId 속성 값 (이 경우 fabrikam.com)을 반환 하 고 해당 이름을 변수 $TenantId에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-109">Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="64303-110">이 스크립트를 실행 하려면 비즈니스용 Skype Online PowerShell 모듈을 설치 하 고이 모듈을 사용 하 여 테 넌 트에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="64303-111">이러한 cmdlet을 설치 하지 않은 경우 CsTenant cmdlet을 사용할 수 없으므로 스크립트는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="64303-112">스크립트를 완료 한 후에는 비즈니스용 Skype 서버와 권한 부여 서버 간의 신뢰 관계와 Exchange 2013/2016와 권한 부여 서버 간의 두 번째 신뢰 관계를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="64303-113">이 작업은 Microsoft Online Services cmdlet을 사용 하는 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="64303-114">Microsoft Online Services cmdlet을 설치 하지 않은 경우에는 cmdlet `install-module MSOnline`을 사용 하 여 PowerShell 리포지토리에서 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="64303-115">Microsoft Online Services 모듈을 설치 하 고 사용 하는 방법에 대 한 자세한 내용은 Office 365 웹 사이트에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="64303-116">이 지침에서는 Office 365와 Active Directory 간의 single sign-on, 페더레이션 및 동기화를 구성 하는 방법에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="64303-117">Office 365을 구성한 후 비즈니스용 Skype 서버 및 Exchange 2013에 대 한 Office 365 서비스 사용자를 만든 후에는 이러한 서비스 사용자에 게 자격 증명을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="64303-118">이를 위해서는 먼저로 저장 된 x.509 Base64 인증서를 가져와야 합니다. CER 파일.</span><span class="sxs-lookup"><span data-stu-id="64303-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="64303-119">그러면이 인증서가 Office 365 서비스 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64303-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="64303-120">X.509 인증서를 가져온 후 PowerShell 콘솔을 열고 서비스 사용자를 관리 하는 데 사용할 수 있는 cmdlet이 포함 된 Microsoft 온라인 Windows PowerShell 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64303-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnline
```

<span data-ttu-id="64303-121">모듈을 가져왔으면 다음 명령을 입력 하 고 enter 키를 눌러 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="64303-122">Enter 키를 누르면 자격 증명 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64303-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="64303-123">대화 상자에 Office 365 사용자 이름 및 암호를 입력 한 다음 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="64303-124">Office 365에 연결 되는 즉시 다음 명령을 실행 하 여 서비스 사용자에 대 한 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="64303-125">모든 서비스 사용자에 대해 다음과 같은 정보가 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64303-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="64303-126">다음 단계는 x.509 인증서를 가져오고, 인코딩하고, 할당 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64303-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="64303-127">인증서를 가져오고 인코딩하려면 다음 Windows PowerShell 명령을 사용 하 여에 대 한 전체 파일 경로를 지정 해야 합니다. CER 파일에서 가져오기 메서드를 호출 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="64303-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="64303-128">인증서를 가져와 인코딩한 후에는 Office 365 서비스 사용자에 게 인증서를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="64303-129">이렇게 하려면 먼저 Get-MsolServicePrincipal을 사용 하 여 비즈니스용 Skype 서버와 Microsoft Exchange 서비스 사용자 둘 다에 대해 AppPrincipalId 속성 값을 검색 합니다. AppPrincipalId 속성 값은 인증서를 할당 하는 서비스 사용자를 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64303-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="64303-130">비즈니스용 Skype Server에 대 한 AppPrincipalId 속성 값을 사용 하는 경우 다음 명령으로 비즈니스용 Skype Online 버전에 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="64303-131">그런 다음 Exchange 2013에 대 한 AppPrincipalId 속성 값을 사용 하 여이 명령을 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="64303-132">나중에 인증서를 삭제 해야 하는 경우 (예: 만료 된 경우) 먼저 인증서에 대 한 KeyId를 검색 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="64303-133">해당 명령은 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="64303-134">그러면 다음과 같은 명령을 사용 하 여 인증서를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-134">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="64303-135">인증서를 할당 하는 것 외에도 Exchange Online 서비스 사용자를 구성 하 고 Office 365 서비스 주체로 온-프레미스 버전의 비즈니스용 Skype 서버 외부 웹 서비스 Url을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="64303-136">다음 두 명령을 실행 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64303-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="64303-137">다음 예제에서 Pool1ExternalWebFQDN.contoso.com는 비즈니스용 Skype 서버 풀의 외부 웹 서비스 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="64303-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="64303-138">배포에 모든 외부 웹 서비스 Url을 추가 하려면이 단계를 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64303-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
