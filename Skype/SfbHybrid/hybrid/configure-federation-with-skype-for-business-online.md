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
description: '요약: 사내 배포와 비즈니스용 Skype Online 간의 상호 연동성을 구성하는 방법을 설명합니다.'
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118947"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="d4d4e-103">비즈니스용 Skype 하이브리드 구성하기</span><span class="sxs-lookup"><span data-stu-id="d4d4e-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="d4d4e-104">비즈니스용 Skype 하이브리드를 구성하기 위해서는 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="d4d4e-105">[Microsoft 365 또는 Office 365와 페더에 연결하도록](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)프레미스 에지 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="d4d4e-106">[Microsoft 365 또는 Office 365를](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)신뢰하고 공유 SIP 주소 공간을 사용하도록 사내 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="d4d4e-107">[Microsoft 365 또는 Office 365](#enable-shared-sip-address-space-in-your-organization)조직에서 공유 SIP 주소 공간을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d4d4e-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="d4d4e-108">Exchange온-프레미스가 있는 경우 Exchange온-프레미스와 비즈니스용 Skype Online 환경 간에 OAuth를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="d4d4e-109">자세한 내용은 [비즈니스용 Skype](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 서버에서 서버 대 서버 인증 관리 및 비즈니스용 Skype 및 Exchange 통합 계획을 [참조하세요.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="d4d4e-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="d4d4e-110">Microsoft 365 또는 Office 365와 페더에 연결하도록 프레미스 에지 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="d4d4e-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="d4d4e-111">페더ation을 사용하면 조직의 Microsoft 365 또는 Office 365 사용자와의 통신을 프레미스 배포의 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="d4d4e-112">페더전을 구성하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="d4d4e-113">'-EnablePartnerDiscovery' 값을 $True 경우 비즈니스용 Skype 서버는 DNS 레코드를 사용하여 AllowedDomains 목록에 나열되지 않은 파트너 도메인을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="d4d4e-114">이 값을 $False 경우 비즈니스용 Skype 서버는 AllowedDomains 목록에 있는 도메인과만 페더러입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="d4d4e-115">이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="d4d4e-116">비즈니스용 Skype 배포 사용자와 비즈니스용 Skype Online 조직의 사용자 간에 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 [비즈니스용 Skype](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)서버에서 비즈니스용 Skype Online 고객에 대한 페더링 지원 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="d4d4e-117">Microsoft 365 또는 Office 365와의 공유 SIP 주소 공간을 사용하도록 사내 환경 구성</span><span class="sxs-lookup"><span data-stu-id="d4d4e-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="d4d4e-118">또한 Microsoft 365 또는 Office 365를 신뢰하고 공유 SIP 주소 공간을 사용하도록 사내 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="d4d4e-119">즉, Microsoft 365 또는 Office 365는 잠재적으로 사용자 계정을 사내 환경과 동일한 SIP 도메인 집합에 호스트할 수 있으며, 메시지는 프레미스에서 호스트된 사용자와 온라인 사용자 간에 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="d4d4e-120">아래 설명된 바와 같이 ProxyFqdn=sipfed.online.lync.com을 사용하여 호스팅 공급자를 구성하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="d4d4e-121">먼저 ProxyFqdn=sipfed.online.lync.com을 사용하는 호스팅 공급자가 이미 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="d4d4e-122">이 명령이 있는 경우 다음 명령을 사용하여 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="d4d4e-123">그런 다음 새 호스팅 공급자를 만들고 다음과 New-CsHostingProvider cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="d4d4e-124">조직에서 공유 SIP 주소 공간 사용</span><span class="sxs-lookup"><span data-stu-id="d4d4e-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="d4d4e-125">Microsoft 365 또는 Office 365 조직에서 변경한 변경 외에도, Microsoft 365 또는 Office 365 조직에서 해당 변경을 통해 공유 SIP 주소 공간을 사내 배포와 함께 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="d4d4e-126">조직에서 공유 SIP 주소 공간을 사용하도록 설정하려면 비즈니스용 Skype Online을 사용하여 원격 PowerShell 세션을 설정한 후 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="d4d4e-127">SharedSipAddressSpace 특성은 온라인으로의 이동이 최종적으로 진행될 때까지 "True"로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="d4d4e-128">Teams 또는 비즈니스용 Skype Online과 원격 PowerShell 세션을 설정하려면 먼저 [Teams PowerShell 모듈을 설치해야 합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="d4d4e-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="d4d4e-129">모듈을 설치한 후 다음 cmdlet을 사용하여 원격 세션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d4e-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="d4d4e-130">비즈니스용 Skype Online을 사용하여 원격 PowerShell 세션을 설정하는 방법 및 비즈니스용 Skype Online 커넥터 모듈을 사용하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d4d4e-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="d4d4e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4d4e-131">See also</span></span>

[<span data-ttu-id="d4d4e-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="d4d4e-132">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)