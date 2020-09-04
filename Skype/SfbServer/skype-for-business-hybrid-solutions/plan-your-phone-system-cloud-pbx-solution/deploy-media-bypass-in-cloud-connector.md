---
title: 클라우드 커넥터 Edition에 미디어 바이패스 배포
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
description: 클라우드 커넥터 버전 2.0 이상으로 미디어 바이패스를 배포 하는 단계에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359314"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="45f50-103">클라우드 커넥터 Edition에 미디어 바이패스 배포</span><span class="sxs-lookup"><span data-stu-id="45f50-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="45f50-104">클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="45f50-105">조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="45f50-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="45f50-106">클라우드 커넥터 버전 2.0 이상으로 미디어 바이패스를 배포 하는 단계에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="45f50-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="45f50-107">미디어 바이패스는 클라이언트가 공중 전화망 (PSTN) 다음 홉 (게이트웨이 또는 세션 경계 컨트롤러)에 미디어를 직접 보낼 수 있도록 허용 하 고 미디어 경로에서 클라우드 커넥터 Edition 구성 요소를 제거 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="45f50-108">[클라우드 커넥터 Edition의 미디어 바이패스 계획을](plan-for-media-bypass-in-cloud-connector-edition.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45f50-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="45f50-109">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="45f50-109">Enable media bypass</span></span>

<span data-ttu-id="45f50-110">미디어 바이패스를 사용 하도록 설정 하려면 미디어 바이패스 웹 서비스의 DNS 이름을 구성 하 고 테 넌 트 구성에서 미디어 바이패스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="45f50-111">미디어 바이패스 웹 서비스는 모든 중재 서버에 자동으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="45f50-112">테 넌 트 관리자는 하이브리드 voice service (사이트)의 이름을 선택 해야 하며,이 이름은 하이브리드 voice에 등록 된 SIP 도메인에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="45f50-113">서비스 이름은 클라이언트 위치에 관계 없이 모든 클라우드 커넥터 기기와 모든 PSTN 사이트에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="45f50-114">웹 서비스는 네트워크 내부 에서만 사용 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="45f50-115">테 넌 트 관리자가 내부 프로덕션 Active Directory에서 DNS A 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="45f50-116">다중 사이트 환경이 복잡 한 경우 [예제 예: 복잡 한 다중 사이트 환경에서 미디어 바이패스 웹 사이트 DNS 레코드](deploy-media-bypass-in-cloud-connector.md#Example)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45f50-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="45f50-117">DNS 레코드는 내부 네트워크 클라이언트에 대해서만 확인 해야 합니다. 외부 네트워크 클라이언트에 대해 확인 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="45f50-118">DNS를 구성한 후 비즈니스용 skype 관리자 자격 증명을 사용 하 여 원격 PowerShell을 온라인으로 Business Online에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="45f50-119">자세한 내용은 [Windows PowerShell을 사용할 컴퓨터 설정을](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45f50-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="45f50-120">PowerShell 세션에서 다음 명령을 입력 하 여 미디어 바이패스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="45f50-121">미디어 바이패스를 사용 하도록 설정 하는 과정은 두 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="45f50-122">새로운 구성은 새 구성을 즉시 저장 하지 않습니다. 메모리의 설정만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="45f50-123">이 cmdlet에 의해 만들어진 개체는 변수에 저장 된 다음 네트워크 구성의 MediaBypassSettings 속성에 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="45f50-124">자세한 내용은 [예제: 미디어 바이패스 웹 사이트 DNS 레코드 (복잡 한 다중 사이트 환경](deploy-media-bypass-in-cloud-connector.md#Example))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45f50-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="45f50-125">온-프레미스 및 온라인 구성 요소 간의 복제에 최대 24 시간이 걸릴 수 있으므로 Microsoft에서는 사용자를 사용 하기 전에 필요한 명령을 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="45f50-126">미디어 바이패스 설정 확인</span><span class="sxs-lookup"><span data-stu-id="45f50-126">Confirm media bypass settings</span></span>

<span data-ttu-id="45f50-127">다음과 같이 미디어 바이패스 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="45f50-128">테 넌 트 풀로 온라인 복제를 확인 하려면 원격 PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="45f50-129">온-프레미스 복제를 확인 하려면 클라우드 커넥터 중재 서버에 연결 하 고 PowerShell에서 다음 명령을 실행 한 후 Enabled = True 및 AlwaysBypass = True를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="45f50-130">클라이언트 설정을 확인 하려면 비즈니스용 Skype 클라이언트에서 로그 아웃 하 고, 클라이언트에서 서비스 URL을 받았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="45f50-131">%Appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 열기</span><span class="sxs-lookup"><span data-stu-id="45f50-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="45f50-132">Hybridconfigserviceinternalurl를 검색 하 고 URL이 정의한 것과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="45f50-133">미디어 바이패스 매개 변수 변경</span><span class="sxs-lookup"><span data-stu-id="45f50-133">Change media bypass parameters</span></span>

<span data-ttu-id="45f50-134">테 넌 트 관리자는 다음 cmdlet을 실행 하 여 웹 서비스의 DNS 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="45f50-135">클라이언트는 로그 아웃 하 고 로그인 하 여 새 서비스 이름을 가져오고 변경 내용을 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="45f50-136">일시적으로 미디어 바이패스를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="45f50-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="45f50-137">이 시나리오는 문제 해결 또는 유지 관리에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="45f50-138">서비스를 사용 하지 않도록 설정 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="45f50-139">변경한 후에는 변경 내용을 모든 클라우드 커넥터에 복제 하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="45f50-140">복제 상태를 확인 하려면 클라우드 커넥터 중재 서버의 PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="45f50-141">변경 내용이 복제 된 후 중재 서버의 웹 서비스는 미디어 바이패스 서비스에 대 한 클라이언트 요청 거부를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="45f50-142">미디어 바이패스를 영구적으로 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="45f50-142">Disable media bypass permanently</span></span>

<span data-ttu-id="45f50-143">미디어 바이패스를 영구적으로 사용 하지 않도록 설정 하려면 테 넌 트 관리자가 다음 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="45f50-144">또한 관리자가 내부 DNS 서버에서 미디어 바이패스에 대 한 웹 주소를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="45f50-145">변경을 수행한 후에는 변경 내용이 모든 클라우드 커넥터 기기에 복제 되는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="45f50-146">예: 복잡 한 다중 사이트 환경에서 미디어 바이패스 웹 사이트 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="45f50-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="45f50-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="45f50-147"><a name="Example"> </a></span></span>

<span data-ttu-id="45f50-148">클라이언트는 내부 DNS 서버에서 미디어 바이패스 웹 서비스의 웹 주소를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="45f50-149">웹 서비스의 이름은 모든 클라우드 커넥터 기기와 클라우드 커넥터 PSTN 사이트에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="45f50-150">복잡 한 다중 사이트 환경에서는 지리적 위치 기반 트래픽 관리에 Windows 2016 DNS 정책을 사용 하는 것이 좋으며, 클라이언트를 네트워크의 로컬 웹 서비스로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="45f50-151">Windows 2016 DNS 정책에 대 한 자세한 내용은 [기본 서버를 사용 하 여 지리적 위치 기반 트래픽 관리에 대 한 DNS 정책 사용](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45f50-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="45f50-152">다음은 지리적 위치 기반 트래픽 관리에 대해 Windows 2016 DNS 정책을 사용 하는 여러 사이트가 있는 회사의 구성 예입니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="45f50-153">바이패스 서비스의 이름은 ' hybridvoice.adatum.biz '입니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="45f50-154">암스테르담의 사이트에는 다음과 같은 중재 서버 IP 주소를 사용 하 여 배포 된 네 개의 클라우드 커넥터 기기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="45f50-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="45f50-155">192.168.1.45</span></span>
    
- <span data-ttu-id="45f50-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="45f50-156">192.168.1.46</span></span>
    
- <span data-ttu-id="45f50-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="45f50-157">192.168.1.47</span></span>
    
- <span data-ttu-id="45f50-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="45f50-158">192.168.1.48</span></span>
    
<span data-ttu-id="45f50-159">시애틀의 사이트에는 다음과 같은 중재 서버 IP 주소를 사용 하 여 배포 된 세 개의 클라우드 커넥터 기기가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="45f50-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="45f50-160">10.10.1.8</span></span>
    
- <span data-ttu-id="45f50-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="45f50-161">10.10.1.9</span></span>
    
- <span data-ttu-id="45f50-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="45f50-162">10.10.1.10</span></span>
    
<span data-ttu-id="45f50-163">지리적 위치 기반 트래픽 관리를 사용 하는 경우 DNS 서버는 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="45f50-164">암스테르담 및 시애틀 서브넷에 대 한 DNS 클라이언트 서브넷을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="45f50-165">Adatum.biz에 대 한 DNS 영역 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="45f50-166">각 DNS 영역 범위에서 DNS 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="45f50-167">암스테르담</span><span class="sxs-lookup"><span data-stu-id="45f50-167">Amsterdam</span></span>
    
   - <span data-ttu-id="45f50-168">형식 A;</span><span class="sxs-lookup"><span data-stu-id="45f50-168">Type A;</span></span>
    
   - <span data-ttu-id="45f50-169">이름: adatum.biz DNS 영역에서 hybridvoice</span><span class="sxs-lookup"><span data-stu-id="45f50-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="45f50-170">대상: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="45f50-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="45f50-171">추가 중재 서버에 대 한 추가 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="45f50-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="45f50-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="45f50-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="45f50-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="45f50-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="45f50-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="45f50-174">192.168.1.48</span></span>
    
     <span data-ttu-id="45f50-175">부산</span><span class="sxs-lookup"><span data-stu-id="45f50-175">Seattle</span></span>
    
   - <span data-ttu-id="45f50-176">를 입력</span><span class="sxs-lookup"><span data-stu-id="45f50-176">Type A</span></span>
    
   - <span data-ttu-id="45f50-177">이름: adatum.biz DNS 영역의 hybridvoice</span><span class="sxs-lookup"><span data-stu-id="45f50-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="45f50-178">대상: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="45f50-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="45f50-179">추가 중재 서버에 대 한 추가 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="45f50-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="45f50-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="45f50-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="45f50-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="45f50-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="45f50-182">원하는 DNS 확인을 위해 클라이언트 서브넷을 적절 한 영역 범위에 연결 하는 DNS 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="45f50-183">이 시점에서 hybridvoice.adatum.biz의 암스테르담 서브넷에서 DNS 쿼리를 수행 하는 클라이언트는 192.168.1.45, 192.168.1.46, 192.168.1.47 및 192.168.1.48 주소를 반환 하지만 같은 쿼리 양식을 만드는 클라이언트는 10.10.1.8, 10.10.1.9 및 10.10.1.10를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="45f50-184">CCE 기기가 업데이트 된 설정을 받지 않는 것 처럼 보이는 경우 기기가 원격 PowerShell을 통해 테 넌 트에 연결할 수 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="45f50-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="45f50-185">원격 PowerShell을 사용 하 여 CsHybridPSTNAppliance에서 기기 상태를 확인 하거나 CCE 호스트에서 PowerShell을 사용 하 여 상태를 Get-CcApplianceStatus으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45f50-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="45f50-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45f50-186">See also</span></span>
<span data-ttu-id="45f50-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="45f50-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="45f50-188">클라우드 커넥터 버전에서 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="45f50-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
