---
title: 'Lync Server 2013: 프런트 엔드 풀에 대 한 DNS 요구 사항'
description: 'Lync Server 2013: 프런트 엔드 풀에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0369e82bd8ed2ea63e2156728b41f9942b0148
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574324"
---
# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="2b649-103">Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b649-103">DNS requirements for Front End pools in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b649-104">_**마지막으로 수정 된 항목:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="2b649-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="2b649-105">이 섹션에서는 프런트 엔드 풀을 배포하는 데 필요한 DNS(도메인 이름 시스템) 레코드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-105">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="2b649-106">프런트 엔드 풀에 대한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="2b649-106">DNS Records for Front End Pools</span></span>

<span data-ttu-id="2b649-107">다음 표에서는 Lync Server 2013 프런트 엔드 풀 배포에 대 한 DNS 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-107">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="2b649-108">프런트 엔드 풀에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b649-108">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b649-109">배포 시나리오</span><span class="sxs-lookup"><span data-stu-id="2b649-109">Deployment scenario</span></span></th>
<th><span data-ttu-id="2b649-110">DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b649-110">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b649-111">여러 프런트 엔드 서버 및 하나의 하드웨어 분산 장치가 포함된 프런트 엔드 풀(DNS 부하 분산이 해당 풀에 배포되었는지 여부는 상관없음)</span><span class="sxs-lookup"><span data-stu-id="2b649-111">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="2b649-112">DNS 부하 분산과 하드웨어 부하 분산 장치를 모두 사용하는 경우 호스트(A) 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-112">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="2b649-113">DNS 부하 분산을 위한 프런트 엔드 풀의 FQDN(정규화된 도메인 이름)으로 확인되는 내부 A 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-113">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="2b649-114">부하 분산 장치의 VIP(가상 IP 주소)를 가리키는 내부 웹 서비스의 내부 호스트(A) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-114">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="2b649-115">토폴로지 작성기에 정의 된 대로 내부 웹 서비스 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-115">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="2b649-116">예를 들어 DNS 부하 분산 및 하드웨어 부하 분산을 모두 사용 하는 경우 DNS 부하 분산을 위해 풀의 각 프런트 엔드 서버에 대 한 A 레코드와 하드웨어 부하 분산 장치의 가상 IP를 가리키는 내부 웹 서비스에 대 한 A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-116">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b649-117">DNS 부하 분산:   Pool01.contoso.net   풀의 IP 주소   10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="2b649-117">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="2b649-118">각 프런트 엔드 서버에는 다음과 같은 고유한 A 레코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-118">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="2b649-119">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="2b649-119">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="2b649-120">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="2b649-120">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="2b649-121">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="2b649-121">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="2b649-122">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="2b649-122">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="2b649-123">하드웨어 부하 분산:   WebInternal.contoso.net   HLB의 IP 주소(VIP)   192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="2b649-123">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="2b649-p102">HTTP/HTTPS 트래픽을 제외한 모든 트래픽은 Pool01.contoso.net 레코드를 사용합니다. HTTP/HTTPS 트래픽은 정의된 내부 웹 서비스 주소인 192.168.10.5를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-p102">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record. HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b649-126">DNS 부하 분산이 배포된 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="2b649-126">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="2b649-p103">풀의 FQDN을 풀에 있는 각 서버의 IP 주소로 확인하는 내부 A 레코드 집합. 풀에는 서버당 하나의 A 레코드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b649-129">DNS 부하 분산이 배포된 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="2b649-129">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="2b649-130">풀의 각 서버에 대한 FQDN을 해당 서버의 IP 주소로 확인하는 내부 A 레코드 집합.</span><span class="sxs-lookup"><span data-stu-id="2b649-130">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="2b649-131">자세한 내용은 계획 설명서에서 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013의 DNS 부하 분산</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b649-131">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b649-132">단일 프런트 엔드 서버와 전용 백 엔드 데이터베이스를 포함하지만 부하 분산 장치는 포함하지 않는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="2b649-132">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="2b649-133">프런트 엔드 풀의 FQDN을 단일 Enterprise Edition 프런트 엔드 서버의 IP 주소로 확인하는 내부 A 레코드</span><span class="sxs-lookup"><span data-stu-id="2b649-133">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b649-134">자동 클라이언트 로그인</span><span class="sxs-lookup"><span data-stu-id="2b649-134">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="2b649-135">지원 되는 각 SIP 도메인에 대해 _sipinternaltls에 대 한 SRV 레코드 _tcp. &gt;로그인 하는 클라이언트 요청을 인증 하 고 리디렉션하는 프런트 엔드 풀의 FQDN에 매핑되는 포트 5061의 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-135">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="2b649-136">자세한 내용은 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항을</a>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b649-136">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b649-137">UC(통합 통신) 장치를 통한 장치 업데이트 웹 서비스 검색</span><span class="sxs-lookup"><span data-stu-id="2b649-137">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="2b649-138">이름이 &lt; c s p 2 인 내부 A 레코드 &gt; 장치 업데이트 웹 서비스를 호스트 하는 프런트 엔드 풀의 IP 주소로 확인 되는 SIP 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-138">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="2b649-139">UC 장치가 설정되었지만 사용자가 장치에 로그인하지 않은 상황에서 A 레코드를 사용하면 장치가 장치 업데이트 웹 서비스를 호스팅하는 프런트 엔드 풀을 검색하고 업데이트를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-139">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="2b649-140">그렇지 않으면 장치는 사용자가 처음 로그인할 때 인밴드 구축을 통해 이 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-140">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2b649-141">Lync Server 2010에 기존에 장치 업데이트 웹 서비스가 배포 되어 있는 경우에는 이름이 c s e r e r e r 있는 내부 A 레코드를 이미 만든 것입니다. &lt; SIP 도메인 &gt;</span><span class="sxs-lookup"><span data-stu-id="2b649-141">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="2b649-142">Microsoft Office Communications Server 2007 r 2의 경우에는 이름 다중 업데이트-2와 함께 추가 DNS A 레코드를 만들어야 합니다. &lt; SIP 도메인 &gt;</span><span class="sxs-lookup"><span data-stu-id="2b649-142">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b649-143">HTTP 트래픽을 지원하는 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="2b649-143">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="2b649-144">외부 웹 팜 FQDN을 역방향 프록시의 외부 IP 주소로 확인하는 외부 A 레코드.</span><span class="sxs-lookup"><span data-stu-id="2b649-144">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="2b649-145">클라이언트와 UC 장치는 이 레코드를 사용하여 역방향 프록시에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-145">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="2b649-146">자세한 내용은 계획 설명서에서 <a href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b649-146">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2b649-147">다음 표에서는 내부 웹 팜 FQDN에 필요한 DNS 레코드의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-147">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="2b649-148">내부 웹 팜 FQDN에 필요한 DNS 레코드의 예</span><span class="sxs-lookup"><span data-stu-id="2b649-148">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b649-149">내부 웹 팜 FQDN</span><span class="sxs-lookup"><span data-stu-id="2b649-149">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="2b649-150">풀 FQDN</span><span class="sxs-lookup"><span data-stu-id="2b649-150">Pool FQDN</span></span></th>
<th><span data-ttu-id="2b649-151">DNS A 레코드</span><span class="sxs-lookup"><span data-stu-id="2b649-151">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b649-152">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b649-152">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b649-153">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b649-153">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b649-154">프런트 엔드 서버가 사용하는 부하 분산 장치의 VIP 주소로 확인되는 ee-pool.contoso.com에 대한 DNS A 레코드</span><span class="sxs-lookup"><span data-stu-id="2b649-154">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="2b649-155">프런트 엔드 서버가 사용하는 부하 분산 장치의 VIP 주소로 확인되는 webcon.contoso.com에 대한 DNS A 레코드</span><span class="sxs-lookup"><span data-stu-id="2b649-155">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b649-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b649-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b649-157">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b649-157">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2b649-158">프런트 엔드 풀에서 Enterprise Edition 프런트 엔드 서버가 사용하는 부하 분산 장치의 VIP(가상 IP) 주소로 확인되는 ee-pool.contoso.com에 대한 DNS A 레코드</span><span class="sxs-lookup"><span data-stu-id="2b649-158">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="2b649-159">이 풀에서 DNS 부하 분산을 사용하는 경우에는 프런트 엔드 풀과 내부 웹 팜의 FQDN이 동일할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b649-159">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

