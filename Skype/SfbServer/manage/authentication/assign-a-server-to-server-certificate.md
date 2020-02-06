---
title: 비즈니스용 Skype 서버에 서버 간 인증 인증서 할당
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: '요약: 비즈니스용 Skype 서버에 대 한 서버 간 인증 인증서를 할당 합니다.'
ms.openlocfilehash: 4689306e0fb8cd7b7c8ce67f74c6ddb65db44f13
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818860"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="209b8-103">비즈니스용 Skype 서버에 서버 간 인증 인증서 할당</span><span class="sxs-lookup"><span data-stu-id="209b8-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="209b8-104">**요약:** 비즈니스용 Skype Server에 대 한 서버 간 인증 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="209b8-105">서버 간 인증 인증서가 비즈니스용 Skype 서버에 이미 할당 되어 있는지 여부를 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="209b8-106">인증서 정보가 반환 되지 않으면 서버 간 인증을 사용할 수 있으려면 먼저 토큰 발급자 인증서를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="209b8-107">일반적으로 비즈니스용 Skype 서버 인증서는 OAuthTokenIssuer 인증서로 사용할 수 있습니다. 예를 들어 비즈니스용 Skype 서버 기본 인증서를 OAuthTokenIssuer 인증서로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="209b8-108">OAUthTokenIssuer 인증서는 제목 필드에 SIP 도메인의 이름을 포함 하는 웹 서버 인증서 일 수도 있습니다. 서버 간 인증에 사용 되는 인증서에 대 한 기본 두 가지 요구 사항은 다음과 같습니다. 1) 모든 프런트 엔드 서버에서 동일한 인증서를 OAuthTokenIssuer 인증서로 구성 해야 합니다. and, 2) 인증서는 최소 2048 비트 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="209b8-109">서버 간 인증에 사용할 수 있는 인증서가 없는 경우 새 인증서를 얻고 새 인증서를 가져온 다음이 인증서를 서버 간 인증에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="209b8-110">새 인증서를 요청 하 고 얻은 후에는 프런트 엔드 서버 중 하나에 로그온 하 여이 인증서와 유사한 Windows PowerShell 명령을 사용 하 여 해당 인증서를 가져오고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="209b8-111">위의 명령에서 Path 매개 변수는 인증서 파일의 전체 경로를 나타내고 Password 매개 변수는 인증서에 할당 된 암호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="209b8-112">이 절차는 한 번만 실행 되어야 합니다: 비즈니스용 Skype 서버 복제 서비스는 모든 프런트 엔드 서버에 대 한 인증서를 해독 하 고 배포 하는 예약 된 작업 집합을 자동으로 만들기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="209b8-113">또는 기존 인증서를 서버 대 서버 인증 인증서로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="209b8-114">참고로, 기본 인증서는 서버 간 인증 인증서로 사용할 수 있습니다. 다음 쌍의 Windows PowerShell 명령은 기본 인증서의 손도장 속성 값을 검색 한 다음 해당 값을 사용 하 여 기본 인증서를 서버 간 인증 인증서로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="209b8-115">앞의 명령에서 검색 된 인증서는 전역 서버 대 서버 인증 인증서로 작동 하도록 구성 됩니다. 즉, 인증서가 모든 프런트 엔드 서버에 복제 되 고 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="209b8-116">이 명령은 프런트 엔드 서버 중 하나 에서만 한 번만 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="209b8-117">모든 프런트 엔드 서버는 동일한 인증서를 사용 해야 하지만 각 프런트 엔드 서버에서 OAuthTokenIssuer 인증서를 구성 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="209b8-118">대신, 인증서를 한 번 구성한 다음 비즈니스용 Skype 서버 복제 서버가 각 서버에 해당 인증서를 복사 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="209b8-119">CsCertificate cmdlet은 해당 인증서를 가져와 즉시 해당 인증서를 현재 OAuthTokenIssuer 인증서로 작동 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="209b8-120">(비즈니스용 Skype Server에는 인증서 유형의 복사본 두 개 (현재 인증서 및 이전 인증서)가 유지 됩니다.) 새 인증서가 OAuthTokenIssuer 인증서로 바로 작동 하기 시작 해야 하는 경우 CsCertificate cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="209b8-121">Set-CsCertificate cmdlet을 사용 하 여 새 인증서를 "롤 포워드" 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="209b8-122">"롤링"은 사용자가 지정 된 시점에 현재 OAuthTokenIssuer 인증서가 되도록 새 인증서를 구성 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="209b8-123">예를 들어이 명령은 기본 인증서를 검색 한 다음 해당 인증서를 현재 OAuthTokenIssuer 인증서로 구성 하 여 7 월 1 일 (2015)로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="209b8-124">2015 년 7 월 1 일에 새 인증서가 현재 OAuthTokenIssuer 인증서로 구성 되 고 "old" OAuthTokenIssuer 발급자 인증서가 이전 인증서로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="209b8-125">Windows PowerShell을 사용 하지 않으려는 경우 인증서 MMC 콘솔을 사용 하 여 한 프런트 엔드 서버에서 인증서를 내보낸 다음 다른 모든 프런트 엔드 서버에서 동일한 인증서를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="209b8-126">이 작업을 수행 하는 경우 인증서 자체와 함께 개인 키 내보내기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="209b8-127">이 경우 각 프런트 엔드 서버에서 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="209b8-128">이 방법으로 인증서를 내보내고 가져오면 비즈니스용 Skype Server가 각 프런트 엔드 서버에 해당 인증서를 복제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="209b8-129">모든 프런트 엔드 서버로 인증서를 가져온 후에는 Windows PowerShell이 아닌 비즈니스용 Skype 서버 배포 마법사를 사용 하 여 해당 인증서를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="209b8-130">배포 마법사를 사용 하 여 인증서를 할당 하려면 배포 마법사가 설치 된 컴퓨터에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="209b8-131">시작을 클릭 하 고 모든 프로그램을 클릭 한 다음 비즈니스용 **Skype 서버**를 클릭 하 고 비즈니스용 **Skype 서버 배포 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="209b8-132">배포 마법사에서 **비즈니스용 Skype 서버 시스템 설치 또는 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="209b8-133">비즈니스용 Skype 서버 페이지에서 제목 **3 단계: 요청, 인증서 설치 또는 할당**에서 **실행** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="209b8-134">(참고:이 컴퓨터에 이미 인증서를 설치한 경우 **실행** 단추에는 레이블이 **다시 실행**됩니다.)</span><span class="sxs-lookup"><span data-stu-id="209b8-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="209b8-135">인증서 마법사에서 **Oauthtokenissuer** 인증서를 선택 하 고 **할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="209b8-136">인증서 할당 마법사의 **인증서 할당** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="209b8-137">**인증서 저장소** 페이지에서 서버와 서버 간 인증에 사용할 인증서를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="209b8-138">인증서 할당 요약 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="209b8-139">명령 실행 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="209b8-140">인증서 마법사 및 배포 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="209b8-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

