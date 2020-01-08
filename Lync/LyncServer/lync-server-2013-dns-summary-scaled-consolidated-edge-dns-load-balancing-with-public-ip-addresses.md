---
title: 'Lync Server 2013: DNS 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 226f0ac1c27b18ea19cc1893300ad3614130c798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="d1040-102">Lync Server 2013의 DNS 요약 - 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="d1040-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1040-103">_**마지막으로 수정한 주제:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="d1040-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="d1040-104">Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트에 대 한 것과 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="d1040-105">또한 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션 사용 여부에 따라 많은 레코드가 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="d1040-106">Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1040-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="d1040-107">분할 두뇌 DNS가 구성 되어 있지 않은 경우 Lync 2013 클라이언트의 자동 구성을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 dns 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)의 "두뇌 DNS가 없는 자동 구성" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1040-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="d1040-108">다음 표에는 단일 통합 된 Edge 토폴로지 그림에 표시 된 단일 통합 edge 토폴로지를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="d1040-109">특정 DNS 레코드는 Lync 2013 클라이언트의 자동 구성에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="d1040-110">Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 연결 된 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="d1040-111">중요: Edge 서버 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1040-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="d1040-112">라우팅 문제를 방지 하려면 Edge 서버에 두 개 이상의 네트워크 어댑터가 있고 기본 게이트웨이가 외부 인터페이스와 연결 된 네트워크 어댑터에만 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="d1040-113">예를 들어 확장 통합 가장자리에 표시 된 것 처럼, [Lync Server 2013의 공용 IP 주소를 사용 하 여 DNS 부하 분산을 확장](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) 하 여 기본 게이트웨이가 외부 방화벽을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="d1040-114">각 Edge 서버에 다음과 같이 두 개의 네트워크 어댑터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="d1040-115">**네트워크 어댑터 1-노드 1 (내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="d1040-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="d1040-116">172.25.33.10이 할당 된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="d1040-117">기본 게이트웨이가 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="d1040-118">Edge 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버를 포함 하는 네트워크에 대 한 경로가 있는지 확인 합니다 (예: 172.25.33.0에서 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="d1040-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="d1040-119">**네트워크 어댑터 1-노드 2 (내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="d1040-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="d1040-120">172.25.33.11이 할당 된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="d1040-121">기본 게이트웨이가 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="d1040-122">Edge 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버를 포함 하는 네트워크에 대 한 경로가 있는지 확인 합니다 (예: 172.25.33.0에서 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="d1040-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="d1040-123">**네트워크 어댑터 2 노드 1 (외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="d1040-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="d1040-124">이 네트워크 어댑터에는 세 개의 개인 IP 주소가 할당 됩니다 (예: 액세스 Edge 서비스의 131.107.155.10, 131.107.155.20 for Web 컨퍼런스 Edge 서비스의 경우 131.107.155.30, A/V Edge 서비스).</span><span class="sxs-lookup"><span data-stu-id="d1040-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="d1040-125">액세스에 지 서비스 공용 IP 주소는 기본 게이트웨이가 공용 라우터 (131.107.155.1)로 설정 된 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="d1040-126">웹 회의 Edge 서비스 및 A/V Edge 서비스 개인 IP 주소는 Windows Server에서 **로컬 영역 연결 속성** 의 **인터넷 프로토콜 버전 4 (Tcp/ip)** 및 **ipv6(인터넷 프로토콜 버전 6 (tcp/ip)** 의 속성에 대 한 **고급** 섹션에 있는 추가 ip 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1040-127">세 개의 Edge 서비스 인터페이스에 대해 단일 IP 주소를 사용 하는 것은 권장 되지 않지만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="d1040-128">이것은 IP 주소를 저장 하지만, 서비스 마다 다른 포트 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="d1040-129">기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용 하도록 보장 하는 443/TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="d1040-130">포트 값 (예: 액세스에 지 서비스에 대해 5061/tcp를 변경 하는 경우), A/V Edge 서비스에 대 한 444/TCP는 사용자가 뒤에 있는 방화벽이 5061/tcp 및 444를 통해 트래픽을 허용 하지 않는 원격 사용자에 대해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="d1040-131">또한 IP 주소에 따라 필터링이 가능 하기 때문에 세 개의 고유한 IP 주소를 통해 문제를 더 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="d1040-132">**네트워크 어댑터 2 노드 2 (외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="d1040-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="d1040-133">이 네트워크 어댑터에는 세 개의 개인 IP 주소가 할당 됩니다 (예: 액세스 Edge 서비스의 131.107.155.11, 131.107.155.21 for Web 컨퍼런스 Edge 서비스의 경우 131.107.155.31, A/V Edge 서비스).</span><span class="sxs-lookup"><span data-stu-id="d1040-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="d1040-134">액세스에 지 서비스 공용 IP 주소는 기본 게이트웨이가 공용 라우터 (131.107.155.1)로 설정 된 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="d1040-135">웹 회의 Edge 서비스 및 A/V Edge 서비스 개인 IP 주소는 Windows Server에서 **로컬 영역 연결 속성** 의 **인터넷 프로토콜 버전 4 (Tcp/ip)** 및 **ipv6(인터넷 프로토콜 버전 6 (tcp/ip)** 의 속성에 대 한 **고급** 섹션에 있는 추가 ip 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d1040-136">두 개의 네트워크 어댑터를 사용 하 여 Edge 서버를 구성 하는 옵션은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="d1040-137">또 다른 옵션은 Edge 서버의 외부 측면에 대 한 네트워크 어댑터와 내부 측면을 각각 세 개 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="d1040-138">이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며 문제 해결이 필요할 때 더욱 간결한 데이터 수집을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="d1040-139">공용 IP 주소를 사용 하 여 확장 된 통합 된 Edge DNS 부하 분산에 필요한 DNS 레코드 (예)</span><span class="sxs-lookup"><span data-stu-id="d1040-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1040-140">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="d1040-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1040-141">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="d1040-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="d1040-142">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="d1040-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="d1040-143">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="d1040-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1040-144">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1040-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1040-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-146">131.107.155.10 및 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="d1040-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="d1040-147">Lync를 사용 하는 사용자가 모든 SIP 도메인에 필요한 경우 액세스에 지 서비스 외부 인터페이스 (Contoso) 반복</span><span class="sxs-lookup"><span data-stu-id="d1040-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1040-148">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1040-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1040-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-150">131.107.155.20 및 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="d1040-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="d1040-151">웹 회의에 지 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1040-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1040-152">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1040-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1040-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-154">131.107.155.30 및 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="d1040-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="d1040-155">A/V Edge 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1040-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1040-156">외부 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="d1040-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="d1040-157">_sip _tls. m m .com</span><span class="sxs-lookup"><span data-stu-id="d1040-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-159">액세스에 지 서비스 외부 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="d1040-159">Access Edge service external interface.</span></span> <span data-ttu-id="d1040-160">외부에서 작동 하도록 Lync 2013 및 Lync 2010 클라이언트를 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="d1040-161">Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1040-162">External DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="d1040-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="d1040-163">_sipfederationtls _tcp. m m .com</span><span class="sxs-lookup"><span data-stu-id="d1040-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-165">"허용 된 SIP 도메인" 이라고 알려진 페더레이션 파트너의 자동 DNS 검색에는 액세스 경계 서비스 외부 인터페이스가 필요 합니다 (이전 릴리스의 확장 페더레이션 이라고 함).</span><span class="sxs-lookup"><span data-stu-id="d1040-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="d1040-166">Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</span><span class="sxs-lookup"><span data-stu-id="d1040-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1040-167">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1040-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1040-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d1040-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d1040-169">172.25.33.10 및 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="d1040-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="d1040-170">통합 된 가장자리 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1040-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="d1040-171">페더레이션에 필요한 레코드</span><span class="sxs-lookup"><span data-stu-id="d1040-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1040-172">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="d1040-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1040-173">Q</span><span class="sxs-lookup"><span data-stu-id="d1040-173">FQDN</span></span></th>
<th><span data-ttu-id="d1040-174">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="d1040-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="d1040-175">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="d1040-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1040-176">External DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="d1040-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="d1040-177">_sipfederationtls _tcp. m m .com</span><span class="sxs-lookup"><span data-stu-id="d1040-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-179">다른 잠재적인 페더레이션 파트너로의 페더레이션에 대 한 자동 DNS 검색을 위해 SIP 액세스에 지 서비스 외부 인터페이스가 필요 하며, "허용 된 SIP 도메인" 이라고 합니다 (이전 릴리스의 확장 페더레이션 이라고 함).</span><span class="sxs-lookup"><span data-stu-id="d1040-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d1040-180">푸시 알림 서비스 또는 Apple Push Notification service를 사용 하는 Lync를 사용 하는 사용자 및 Microsoft Lync 모바일 클라이언트가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</span><span class="sxs-lookup"><span data-stu-id="d1040-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d1040-181">확장 가능 메시지 및 현재 상태 프로토콜에 대 한 DNS 요약</span><span class="sxs-lookup"><span data-stu-id="d1040-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1040-182">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="d1040-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1040-183">Q</span><span class="sxs-lookup"><span data-stu-id="d1040-183">FQDN</span></span></th>
<th><span data-ttu-id="d1040-184">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="d1040-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="d1040-185">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="d1040-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1040-186">외부 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="d1040-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="d1040-187">_xmpp-서버 _tcp. c a m.</span><span class="sxs-lookup"><span data-stu-id="d1040-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1040-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1040-189">액세스에 지 서비스 또는 Edge 풀의 XMPP 프록시 외부 인터페이스. Lync를 사용 하는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책, 또는에 적용 된 사용자 정책을 통해 외부 액세스 정책의 구성을 통해 XMPP 연락처와의 연결을 허용 하는 사용자가 Lync를 사용할 수 있는 사용자.</span><span class="sxs-lookup"><span data-stu-id="d1040-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="d1040-190">허용 되는 XMPP 도메인은 XMPP 페더레이션 파트너 정책 에서도 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="d1040-191">자세한 내용은 관련 <strong>항목을 참조 하세요.</strong></span><span class="sxs-lookup"><span data-stu-id="d1040-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1040-192">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1040-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1040-193">xmpp.contoso.com (예:)</span><span class="sxs-lookup"><span data-stu-id="d1040-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="d1040-194">XMPP 프록시를 호스팅하는 Edge 서버 또는 Edge 풀에 있는 액세스에 지 서비스의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1040-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="d1040-195">XMPP 프록시 서비스를 호스트 하는 액세스에 지 서비스 또는 Edge 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="d1040-196">일반적으로 사용자가 만든 SRV 레코드는이 호스트 (A 또는 AAAA) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="d1040-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

