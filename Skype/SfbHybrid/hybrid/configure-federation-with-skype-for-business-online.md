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
description: '요약: 프레미스 배포와 프레미스 배포 간의 상호 Teams.'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305972"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="2c489-103">비즈니스용 Skype 하이브리드 구성하기</span><span class="sxs-lookup"><span data-stu-id="2c489-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="2c489-104">비즈니스용 Skype 하이브리드를 구성하기 위해서는 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="2c489-105">[을(를) 페더에](#configure-your-on-premises-edge-service-to-federate-with-teams)연결하도록 프레미스 에지 서비스를 Teams.</span><span class="sxs-lookup"><span data-stu-id="2c489-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="2c489-106">공유 SIP 주소 공간을 사용하도록 Teams [구성합니다.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)</span><span class="sxs-lookup"><span data-stu-id="2c489-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="2c489-107">[조직에서 공유 SIP 주소 공간을 Teams.](#enable-shared-sip-address-space-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="2c489-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="2c489-108">Exchange 있는 경우 Exchange 및 온라인 환경 간에 OAuth를 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="2c489-109">자세한 내용은 [Manage server-to-server authentication in 비즈니스용 Skype 서버](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate 비즈니스용 Skype and [Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="2c489-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="2c489-110">프레미스 에지 서비스에서 사용자와 페더러가 연결하도록 Teams</span><span class="sxs-lookup"><span data-stu-id="2c489-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="2c489-111">페더ation을 사용하면 조직 내 온라인 사용자 및 Teams 비즈니스용 Skype 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="2c489-112">페더ation을 구성하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="2c489-113">'-EnablePartnerDiscovery' 값이 $True 비즈니스용 Skype 서버 DNS 레코드를 사용하여 AllowedDomains 목록에 나열되지 않은 파트너 도메인을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="2c489-114">이 값을 0으로 $False 비즈니스용 Skype 서버 허용Domains 목록에 있는 도메인과만 페더화합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="2c489-115">이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="2c489-116">프레미스 비즈니스용 Skype 배포의 사용자와 Microsoft 365 조직의 사용자 간에 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 Microsoft 365 고객에 대한 페더링 지원 구성을 [비즈니스용 Skype 서버.](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)</span><span class="sxs-lookup"><span data-stu-id="2c489-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="2c489-117">프레미스 환경에서 공유 SIP 주소 공간을 사용하도록 Teams</span><span class="sxs-lookup"><span data-stu-id="2c489-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="2c489-118">또한 공유 SIP 주소 공간을 사용하도록 Teams 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="2c489-119">이 구성은 Teams 환경과 동일한 SIP 도메인 집합에 대한 사용자 계정을 잠재적으로 호스트할 수 있으며, 메시지를 프레미스 및 온라인에서 호스팅되는 사용자 간에 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="2c489-120">아래 설명된 바와 같이 ProxyFqdn=sipfed.online.lync.com을 사용하여 호스팅 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="2c489-121">먼저 ProxyFqdn=sipfed.online.lync.com을 사용하는 호스팅 공급자가 이미 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c489-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="2c489-122">하나만 있는 경우 관리 셸의 다음 명령을 사용하여 비즈니스용 Skype 서버 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="2c489-123">그런 다음 다음과 같이 New-CsHostingProvider cmdlet을 사용하여 새 호스팅 공급자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="2c489-124">조직에서 공유 SIP 주소 공간 사용</span><span class="sxs-lookup"><span data-stu-id="2c489-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="2c489-125">사내 배포에서 변경한 변경 외에도 Teams 조직에서 해당 변경을 통해 공유 SIP 주소 공간을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="2c489-126">조직에서 공유 SIP 주소 공간을 사용하도록 설정하려면 조직에서 원격 PowerShell 세션을 Teams 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="2c489-127">SharedSipAddressSpace 특성은 온라인으로의 이동이 최종적으로 진행될 때까지 "True"로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="2c489-128">Teams(또는 비즈니스용 Skype Online)를 사용하여 원격 PowerShell 세션을 설정하려면 먼저 [PowerShell](/microsoftteams/teams-powershell-install)모듈 을 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="2c489-129">이 Teams PowerShell 모듈은 사용 중지된 Busines Online 커넥터 모듈의 Skype 모듈을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="2c489-130">모듈을 설치한 후 다음 cmdlet을 사용하여 원격 세션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c489-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="2c489-131">Teams 사용하여 원격 PowerShell 세션을 설정하는 방법 및 Teams PowerShell 모듈을 사용하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2c489-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="2c489-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c489-132">See also</span></span>

[<span data-ttu-id="2c489-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="2c489-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
