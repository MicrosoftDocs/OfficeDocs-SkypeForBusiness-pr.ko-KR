---
title: 클라우드 커넥터 버전에서 미디어 우회 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 이 항목을 통해 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 배포하는 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119367"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="8a360-103">클라우드 커넥터 버전에서 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="8a360-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="8a360-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="8a360-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="8a360-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="8a360-106">이 항목을 통해 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 배포하는 단계에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="8a360-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="8a360-107">미디어 우회를 통해 클라이언트는 PSTN(Public Switched Telephone Network) 다음 홉(게이트웨이 또는 SBC(Session Border Controller))으로 직접 미디어를 보내고 미디어 경로에서 Cloud Connector Edition 구성 요소를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="8a360-108">Cloud [Connector Edition의 미디어 우회 계획을 참조합니다.](plan-for-media-bypass-in-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="8a360-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="8a360-109">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="8a360-109">Enable media bypass</span></span>

<span data-ttu-id="8a360-110">미디어 우회를 사용하도록 설정하려면 미디어 우회 웹 서비스의 DNS 이름을 구성하고 테넌트 구성에서 미디어 우회를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="8a360-111">미디어 우회 웹 서비스는 모든 중재 서버에 자동으로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="8a360-112">테넌트 관리자는 하이브리드 음성 서비스(사이트)의 이름을 선택해야 합니다. 이 이름은 하이브리드 음성에 등록된 SIP 도메인에서 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="8a360-113">서비스 이름은 클라이언트 위치에 관계없이 모든 클라우드 커넥터 어플라이언스 및 모든 PSTN 사이트에서 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="8a360-114">웹 서비스는 네트워크에서 내부적으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="8a360-115">테넌트 관리자는 내부 프로덕션 Active Directory에서 DNS A 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="8a360-116">복잡한 다중 사이트 환경이 있는 경우 예제: 복잡한 다중 사이트 환경의 미디어 우회 웹 [사이트 DNS 레코드를 참조하세요.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="8a360-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="8a360-117">DNS 레코드는 내부 네트워크 클라이언트에 한해 확인해야 합니다. 외부 네트워크 클라이언트에 대해 확인하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="8a360-118">DNS를 구성한 후 비즈니스용 Skype 관리자 자격 증명과 함께 원격 PowerShell을 사용하여 비즈니스용 Skype Online에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="8a360-119">자세한 내용은 [Set up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8a360-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="8a360-120">PowerShell 세션에서 미디어 우회를 사용하도록 설정하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="8a360-121">미디어 우회를 사용하도록 설정하는 과정은 2단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="8a360-122">이 New-CsNetworkMedia 새 구성을 즉시 저장하지는 않습니다. 메모리에 설정만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="8a360-123">이 cmdlet에서 만든 개체는 변수에 저장한 다음 네트워크 구성의 MediaBypassSettings 속성에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="8a360-124">자세한 내용은 예: 복잡한 다중 사이트 환경에서 미디어 우회 웹 사이트 [DNS 레코드를 참조하세요.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="8a360-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="8a360-125">프레미스 구성 요소와 온라인 구성 요소 간의 복제에는 최대 24시간이 걸릴 수 있으므로 사용자를 사용하도록 설정하기 전에 필요한 명령을 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="8a360-126">미디어 우회 설정 확인</span><span class="sxs-lookup"><span data-stu-id="8a360-126">Confirm media bypass settings</span></span>

<span data-ttu-id="8a360-127">미디어 우회 설정을 다음과 같이 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="8a360-128">테넌트 풀에 대한 온라인 복제를 확인하기 위해 원격 PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="8a360-129">클라우드 커넥터 중재 서버에 연결하고 PowerShell에서 다음 명령을 실행하여 Enabled=True 및 AlwaysBypass=True를 확인한 다음, 사내 복제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="8a360-130">클라이언트 설정을 확인하려면 비즈니스용 Skype 클라이언트에서 로그인하고 다시 로그인하고 클라이언트가 다음과 같이 서비스 URL을 수신한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="8a360-131">%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="8a360-132">hybridconfigserviceinternalurl을 검색하고 URL이 정의한 URL과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="8a360-133">미디어 우회 매개 변수 변경</span><span class="sxs-lookup"><span data-stu-id="8a360-133">Change media bypass parameters</span></span>

<span data-ttu-id="8a360-134">테넌트 관리자는 다음 cmdlet을 실행하여 웹 서비스의 DNS 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="8a360-135">클라이언트는 새 서비스 이름을 입력하고 변경을 인식하려면 로그인하여 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="8a360-136">미디어 우회를 일시적으로 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8a360-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="8a360-137">이 시나리오는 문제 해결 또는 유지 관리에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="8a360-138">서비스를 사용하지 않도록 설정하기 위해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="8a360-139">변경한 후 변경 내용을 모든 클라우드 커넥터에 복제하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="8a360-140">복제 상태를 확인하기 위해 클라우드 커넥터 중재 서버의 PowerShell에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="8a360-141">변경 내용이 복제된 후 중재 서버의 웹 서비스가 미디어 우회 서비스에 대한 클라이언트 요청을 거부하기 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="8a360-142">미디어 우회를 영구적으로 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8a360-142">Disable media bypass permanently</span></span>

<span data-ttu-id="8a360-143">미디어 우회를 영구적으로 사용하지 않도록 설정하기 위해 테넌트 관리자는 다음 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="8a360-144">관리자는 또한 내부 DNS 서버에서 미디어 우회에 대한 웹 주소를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="8a360-145">변경한 후 변경 내용을 모든 클라우드 커넥터 어플라이언스에 복제하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="8a360-146">예: 복잡한 다중 사이트 환경에서 미디어 우회 웹 사이트 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="8a360-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="8a360-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="8a360-147"><a name="Example"> </a></span></span>

<span data-ttu-id="8a360-148">클라이언트는 내부 DNS 서버에서 미디어 우회 웹 서비스의 웹 주소를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="8a360-149">웹 서비스의 이름은 모든 클라우드 커넥터 어플라이언스 및 클라우드 커넥터 PSTN 사이트에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="8a360-150">복잡한 다중 사이트 환경에서는 클라이언트를 네트워크의 로컬 웹 서비스로 리디렉션할 수 있도록 Geo-Location 기반 트래픽 관리에 Windows 2016 DNS 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="8a360-151">Windows 2016 DNS 정책에 대한 자세한 내용은 [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers을 참조하십시오.](/windows-server/networking/dns/deploy/primary-geo-location)</span><span class="sxs-lookup"><span data-stu-id="8a360-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="8a360-152">다음은 Windows 2016 DNS 정책을 사용하여 사이트가 여러 개 있는 회사의 구성 예입니다Geo-Location 기반 트래픽 관리.</span><span class="sxs-lookup"><span data-stu-id="8a360-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="8a360-153">우회 서비스의 이름은 'hybridvoice.adatum.biz.'입니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="8a360-154">암스테르담 사이트에는 다음 중재 서버 IP 주소와 함께 배포된 4개의 클라우드 커넥터 어플라이언스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="8a360-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="8a360-155">192.168.1.45</span></span>
    
- <span data-ttu-id="8a360-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="8a360-156">192.168.1.46</span></span>
    
- <span data-ttu-id="8a360-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="8a360-157">192.168.1.47</span></span>
    
- <span data-ttu-id="8a360-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="8a360-158">192.168.1.48</span></span>
    
<span data-ttu-id="8a360-159">시애틀의 사이트에는 다음 중재 서버 IP 주소와 함께 배포된 3개의 클라우드 커넥터 어플라이언스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="8a360-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="8a360-160">10.10.1.8</span></span>
    
- <span data-ttu-id="8a360-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="8a360-161">10.10.1.9</span></span>
    
- <span data-ttu-id="8a360-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="8a360-162">10.10.1.10</span></span>
    
<span data-ttu-id="8a360-163">Geo-Location 기반 트래픽 관리를 사용하는 경우 DNS 서버는 다음과 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="8a360-164">암스테르담 및 시애틀 서브넷 모두에 대한 DNS 클라이언트 서브넷을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="8a360-165">암스테르담 및 시애틀에 adatum.biz DNS 영역 범위를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="8a360-166">각 DNS 영역 범위에서 DNS 레코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="8a360-167">암스테르담</span><span class="sxs-lookup"><span data-stu-id="8a360-167">Amsterdam</span></span>
    
   - <span data-ttu-id="8a360-168">A를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-168">Type A;</span></span>
    
   - <span data-ttu-id="8a360-169">이름 : adatum.biz DNS 영역의 hybridvoice</span><span class="sxs-lookup"><span data-stu-id="8a360-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="8a360-170">대상: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="8a360-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="8a360-171">추가 중재 서버에 대한 추가 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="8a360-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="8a360-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="8a360-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="8a360-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="8a360-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="8a360-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="8a360-174">192.168.1.48</span></span>
    
     <span data-ttu-id="8a360-175">시애틀</span><span class="sxs-lookup"><span data-stu-id="8a360-175">Seattle</span></span>
    
   - <span data-ttu-id="8a360-176">A 입력</span><span class="sxs-lookup"><span data-stu-id="8a360-176">Type A</span></span>
    
   - <span data-ttu-id="8a360-177">이름 : adatum.biz DNS 영역의 hybridvoice</span><span class="sxs-lookup"><span data-stu-id="8a360-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="8a360-178">대상: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="8a360-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="8a360-179">추가 중재 서버에 대한 추가 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="8a360-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="8a360-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="8a360-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="8a360-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="8a360-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="8a360-182">클라이언트 서브넷을 적절한 영역 범위에 연결하는 DNS 정책을 만들어 원하는 DNS 확인을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="8a360-183">이때 클라이언트가 암스테르담 서브넷에서 DNS 쿼리를 hybridvoice.adatum.biz 192.168.1.45가 반환됩니다. 192.168.1.46, 192.168.1.47 및 192.168.1.48 주소가 있는 반면 시애틀에서 동일한 쿼리 양식을 만드는 클라이언트는 10.10.1.8, 10.10.1.9 및 10.10.1.10을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="8a360-184">CCE 어플라이언스가 업데이트된 설정을 받고 있는 것 같지 않은 경우 어플라이언스가 원격 PowerShell을 통해 테넌트에 연락할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="8a360-185">원격 PowerShell을 사용하여 응용 Get-CsHybridPSTNAppliance 상태 확인 또는 CCE 호스트의 PowerShell을 사용하여 Get-CcApplianceStatus의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a360-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="8a360-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a360-186">See also</span></span>
<span data-ttu-id="8a360-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="8a360-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="8a360-188">클라우드 커넥터 버전에서 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="8a360-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)