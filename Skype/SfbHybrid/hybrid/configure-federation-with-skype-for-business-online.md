---
title: 비즈니스용 Skype 하이브리드 구성하기
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 온-프레미스 배포와 비즈니스용 Skype Online 간의 상호 운용성을 구성 하는 방법을 알아봅니다.'
ms.openlocfilehash: 1b36a25674c3d6690b7490d0cd0793f05131cc12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726788"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="202af-103">비즈니스용 Skype 하이브리드 구성하기</span><span class="sxs-lookup"><span data-stu-id="202af-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="202af-104">비즈니스용 Skype 하이브리드를 구성하기 위해서는 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="202af-105">[Office 365와 페더레이션 할 온-프레미스 환경 서비스를 구성](#configure-your-on-premises-edge-service-to-federate-with-office-365)합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-105">[Configure your on-premises environment service to federate with Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span></span>
- <span data-ttu-id="202af-106">[Office 365을 신뢰 하도록 온-프레미스 환경을 구성 하 고 office 365와 공유 SIP 주소 공간을 사용 하도록 설정](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="202af-107">[Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정](#enable-shared-sip-address-space-in-your-office-365-tenant)합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="202af-108">Exchange 온-프레미스를 사용 하는 경우 Exchange 온-프레미스 및 비즈니스용 Skype 온라인 환경 간에 OAuth를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202af-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="202af-109">자세한 내용은 [비즈니스용 Skype 서버에서 서버 간 인증 관리](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) 및 [비즈니스용 skype 및 Exchange 통합 계획](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="202af-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="202af-110">Office 365와 페더레이션 할 온-프레미스에 지 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="202af-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="202af-111">페더레이션을 사용 하면 온-프레미스 배포의 사용자가 조직의 Office 365 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202af-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="202af-112">페더레이션을 구성 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

<span data-ttu-id="202af-113">'-EnablePartnerDiscovery ' 값이 1로 설정 된 경우 비즈니스용 Skype 서버는 DNS 레코드를 사용 하 여 AllowedDomains 목록에 나열 되지 않은 파트너 도메인을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-113">If '-EnablePartnerDiscovery' value set to 1, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="202af-114">값이 0으로 설정 되 면 비즈니스용 Skype 서버가 AllowedDomains 목록에 있는 도메인과만 페더레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-114">If the value set to 0, Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="202af-115">이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-115">This parameter is required if you use DNS service routing.</span></span>



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="202af-116">Office 365에서 공유 SIP 주소 공간을 사용 하도록 온-프레미스 환경을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-116">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="202af-117">또한 Office 365를 신뢰하고 Office 365와 공유 SIP 주소 공간을 사용하도록 온-프레미스 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-117">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="202af-118">즉, Office 365은 온-프레미스 환경과 동일한 SIP 도메인 집합에 대해 사용자 계정을 잠재적으로 호스트할 수 있으며, 메시지를 온-프레미스와 온라인으로 호스트 되는 사용자 간에 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202af-118">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="202af-119">아래 설명 된 대로 ProxyFqdn = sipfed.online.lync.com>을 사용 하 여 호스팅 공급자를 구성 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-119">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="202af-120">먼저 ProxyFqdn = sipfed.online.lync.com>을 사용 하는 호스팅 공급자가 이미 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-120">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="202af-121">하나가 있으면 다음 명령을 사용 하 여 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-121">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="202af-122">그런 다음 새 호스팅 공급자를 만들려면 다음과 같이 새-CsHostingProvider cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-122">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="202af-123">Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="202af-123">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="202af-124">온-프레미스 배포에서 수행한 변경 사항 외에도 Office 365 테 넌 트에서 해당 변경 사항을 사용 하 여 온-프레미스 배포와 공유 SIP 주소 공간을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-124">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="202af-125">Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정 하려면 비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정한 후 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="202af-125">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="202af-126">SharedSipAddressSpace 특성은 온라인으로 전환할 때까지 "True"로 유지 되어야 하며, 사용자는 온-프레미스에 남아 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="202af-126">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="202af-127">팀 또는 비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정 하려면 먼저 비즈니스용 Skype Online 커넥터 모듈 for Windows PowerShell을 설치 해야 [합니다.](https://go.microsoft.com/fwlink/p/?LinkId=391911)</span><span class="sxs-lookup"><span data-stu-id="202af-127">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="202af-128">모듈을 설치한 후에는 다음 cmdlet을 사용 하 여 원격 세션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202af-128">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="202af-129">비즈니스용 Skype Online에서 원격 PowerShell 세션을 설정 하는 방법과 비즈니스용 Skype Online 커넥터 모듈을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell에 대 한 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="202af-129">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="202af-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="202af-130">See also</span></span>

[<span data-ttu-id="202af-131">새-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="202af-131">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

