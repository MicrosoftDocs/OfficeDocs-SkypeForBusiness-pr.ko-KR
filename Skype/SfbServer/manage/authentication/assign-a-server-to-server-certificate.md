---
title: 비즈니스용 Skype 서버에 서버 대 서버 인증 인증서 할당
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
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '요약: 비즈니스용 Skype 서버에 대해 서버 간 인증 인증서를 할당합니다.'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828508"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="3c2e0-103">비즈니스용 Skype 서버에 서버 대 서버 인증 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="3c2e0-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="3c2e0-104">**요약:** 비즈니스용 Skype 서버에 대한 서버 대 서버 인증 인증서를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="3c2e0-105">서버 대 서버 인증 인증서가 비즈니스용 Skype 서버에 이미 할당되어 있는지 여부를 확인하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="3c2e0-106">반환되는 인증서 정보가 없으면 토큰 발급자 인증서를 먼저 할당해야 서버 간 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="3c2e0-107">일반적으로 비즈니스용 Skype 서버 인증서는 OAuthTokenIssuer 인증서로 사용할 수 있습니다. 예를 들어 비즈니스용 Skype 서버 기본 인증서를 OAuthTokenIssuer 인증서로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="3c2e0-108">(OAUthTokenIssuer 인증서는 주체 필드에 SIP 도메인 이름이 포함된 모든 웹 서버 인증서일 수도 있습니다.) 서버 대 서버 인증에 사용되는 인증서의 기본 두 요구 사항은 1)모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서로 구성해야 합니다. 2) 인증서는 2048비트 이상이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="3c2e0-p102">서버 간 인증에 사용할 수 있는 인증서가 없는 경우 새로운 인증서를 받아 가져온 다음 서버 간 인증의 인증서로 사용해야 합니다. 새 인증서를 요청하여 받으면 새 인증서로 프런트 엔드 서버 중 하나에 로그온할 수 있으며, 다음과 유사한 Windows PowerShell 명령을 사용하여 인증서를 가져오고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="3c2e0-111">위의 명령에서 Path 매개 변수는 인증서 파일의 전체 경로를 나타내고 Password 매개 변수는 인증서에 할당된 암호를 나타내며,</span><span class="sxs-lookup"><span data-stu-id="3c2e0-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="3c2e0-112">이 절차는 한 번만 실행해야 합니다. 그러면 비즈니스용 Skype 서버 복제 서비스가 인증서의 암호를 해독하고 모든 프런트 엔드 서버에 배포하는 예약된 작업 집합을 자동으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="3c2e0-p104">또는, 기존 인증서를 서버 간 인증 인증서로 사용할 수 있습니다. 앞에서 언급한 것과 같이 기본 인증서도 서버 간 인증 인증서로 사용할 수 있습니다. 다음 Windows PowerShell 명령 쌍을 실행하면 기본 인증서의 Thumbprint 속성 값을 검색한 후 해당 값을 사용하여 기본 인증서를 서버 간 인증 인증서로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="3c2e0-115">위의 명령에서 검색된 인증서는 전역 서버 대 서버 인증 인증서로 작동하도록 구성됩니다. 즉, 인증서가 모든 프런트 엔드 서버로 복제 및 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="3c2e0-116">이 명령은 프런트 엔드 서버 중 하나에서만 한 번만 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="3c2e0-117">모든 프런트 엔드 서버에서 동일한 인증서를 사용해야 하지만 각 프런트 엔드 서버에서 OAuthTokenIssuer 인증서를 구성하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="3c2e0-118">대신 인증서를 한 번 구성한 다음 비즈니스용 Skype 서버 복제 서버가 해당 인증서를 각 서버에 복사하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="3c2e0-119">이 Set-CsCertificate 인증서를 사용하며 현재 OAuthTokenIssuer 인증서로 사용할 인증서를 즉시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="3c2e0-120">비즈니스용 Skype 서버는 인증서 유형의 두 복사본( 현재 인증서 및 이전 인증서)을 보관합니다. 새 인증서가 OAuthTokenIssuer 인증서 역할을 즉시 시작해야 하는 경우 해당 cmdlet을 Set-CsCertificate 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="3c2e0-121">또한 Set-CsCertificate cmdlet을 사용하여 새 인증서를 "롤링"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="3c2e0-122">인증서를 "롤링"한다는 것은 단순히, 지정된 시점에 새 인증서를 현재 OAuthTokenIssuer 인증서로 사용하도록 구성한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="3c2e0-123">예를 들어 다음 명령은 기본 인증서를 검색한 다음 2015년 7월 1일을 현재 OAuthTokenIssuer 인증서로 인계하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="3c2e0-124">2015년 7월 1일에는 새 인증서가 현재 OAuthTokenIssuer 인증서로 구성되고 "이전" OAuthTokenIssuer 인증서가 이전 인증서로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="3c2e0-p108">Windows PowerShell을 사용하지 않으려는 경우 인증서 MMC 콘솔을 사용하여 인증서를 단일 프런트 엔드 서버에서 내보내어 동일한 인증서를 다른 모든 프런트 엔드 서버로 가져올 수도 있습니다. 이를 수행하는 경우 반드시 인증서 자체와 함께 개인 키를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3c2e0-127">이러한 경우 절차는 각 프런트 엔드 서버에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="3c2e0-128">이러한 방식으로 인증서를 내보내고 가져올 때 비즈니스용 Skype 서버는 해당 인증서를 각 프런트 엔드 서버에 복제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="3c2e0-129">인증서를 모든 프런트 엔드 서버로 가져온 후 해당 인증서는 모든 프런트 엔드 서버가 아닌 비즈니스용 Skype 서버 배포 마법사를 사용하여 할당할 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="3c2e0-130">배포 마법사를 사용하여 인증서를 할당하려면 배포 마법사가 설치된 컴퓨터에서 다음 단계를 완료하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="3c2e0-131">시작, 모든 프로그램, 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 배포 마법사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c2e0-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="3c2e0-132">배포 마법사에서 **비즈니스용 Skype** 서버 시스템 설치 또는 업데이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="3c2e0-133">비즈니스용 Skype 서버 페이지에서 **3단계:** 인증서 요청, 설치 또는 할당 제목 아래에서 실행 단추를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="3c2e0-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="3c2e0-134">참고: 이 컴퓨터에서 인증서를 이미 설치한 경우 **실행** 단추 대신 **다시 실행** 이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="3c2e0-135">인증서 마법사에서 **OAuthTokenIssuer** 인증서를 선택한 후 **지정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="3c2e0-136">인증서 할당 마법사의 **인증서 할당** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="3c2e0-137">**인증서 저장소** 페이지에서 서버 간 인증에 사용할 인증서를 선택한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="3c2e0-138">인증서 할당 요약 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="3c2e0-139">명령 실행 페이지에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="3c2e0-140">인증서 마법사와 배포 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

