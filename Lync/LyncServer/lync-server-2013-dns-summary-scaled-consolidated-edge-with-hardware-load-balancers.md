---
title: DNS 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6be703e13ec50eb66ba52c981196df06adc6e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="1c10a-102">Lync Server 2013의 DNS 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</span><span class="sxs-lookup"><span data-stu-id="1c10a-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c10a-103">_**마지막으로 수정한 주제:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="1c10a-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="1c10a-104">Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트에 대 한 것과 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="1c10a-105">또한 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션 사용 여부에 따라 많은 레코드가 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="1c10a-106">Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c10a-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1c10a-107">분할 두뇌 DNS가 구성 되어 있지 않은 경우 Lync 2013 클라이언트의 자동 구성을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 dns 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)의 "두뇌 DNS가 없는 자동 구성" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c10a-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1c10a-108">다음 표에는 확장 된 통합에 지 토폴로지 (하드웨어 부하 분산) 그림을 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="1c10a-109">특정 DNS 레코드는 Lync 클라이언트에 대 한 자동 구성에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="1c10a-110">Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 연결 된 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="1c10a-111">중요: Edge 서버 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c10a-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="1c10a-112">라우팅 문제를 방지 하려면 Edge 서버에 두 개 이상의 네트워크 어댑터가 있고 기본 게이트웨이가 외부 인터페이스와 연결 된 네트워크 어댑터에만 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="1c10a-113">예를 들어 확장 된 통합 가장자리에 표시 되는 것 처럼, [Lync Server 2013의 하드웨어 부하 분산 장치를 사용 하 여 확장 통합 가장자리](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)를 선택 하면 기본 게이트웨이가 외부 방화벽을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="1c10a-114">각 Edge 서버에 다음과 같이 두 개의 네트워크 어댑터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="1c10a-115">**네트워크 어댑터 1 (내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="1c10a-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1c10a-116">172.25.33.10이 할당 된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="1c10a-117">기본 게이트웨이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-117">No default gateway.</span></span>
    
    <span data-ttu-id="1c10a-118">Edge 서버 내부 인터페이스를 포함 하는 네트워크에서 lync server를 실행 하는 네트워크 (예: 172.25.33.0 ~ 192.168.10.0)가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1c10a-119">**네트워크 어댑터 2 (외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="1c10a-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="1c10a-120">이 네트워크 어댑터에 대 한 세 가지 공용 IP 주소 (예: 액세스에 지 서비스용 131.107.155.10, 131.107.155.20 웹 회의 Edge 서비스의 경우), 131.107.155.30 for A/V Edge 서비스에 게 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="1c10a-121">Edge 서버의 실제 외부 네트워크 인터페이스에 할당 된 IP 주소는 선택한 하드웨어 부하 분산 장치에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="1c10a-122">실제 IP 주소 요구 사항을 이해 하려면 하드웨어 로드 균형 조정기에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c10a-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="1c10a-123">세 개의 Edge 서비스 인터페이스에 대해 단일 IP 주소를 사용 하는 것은 권장 되지 않지만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="1c10a-124">이것은 IP 주소를 저장 하지만, 서비스 마다 다른 포트 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="1c10a-125">기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용 하도록 보장 하는 443/TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="1c10a-126">포트 값 (예: 액세스에 지 서비스에 대해 5061/tcp를 변경 하는 경우), A/V Edge 서비스에 대 한 444/TCP는 사용자가 뒤에 있는 방화벽이 5061/tcp 및 444를 통해 트래픽을 허용 하지 않는 원격 사용자에 대해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="1c10a-127">또한 IP 주소에 따라 필터링이 가능 하기 때문에 세 개의 고유한 IP 주소를 통해 문제를 더 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="1c10a-128">액세스에 지 서비스 IP 주소는 기본 게이트웨이가 인터넷 연결 라우터 (131.107.155.1)로 설정 된 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="1c10a-129">웹 회의에 지 서비스 및 A/V Edge 서비스 IP 주소 보조.</span><span class="sxs-lookup"><span data-stu-id="1c10a-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="1c10a-130">두 개의 네트워크 어댑터를 사용 하 여 Edge 서버를 구성 하는 옵션은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="1c10a-131">또 다른 옵션은 Edge 서버의 외부 측면에 대 한 네트워크 어댑터와 내부 측면을 각각 세 개 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="1c10a-132">이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며 문제 해결이 필요할 때 더욱 간결한 데이터 수집을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="1c10a-133">축소 된 통합 모서리, 하드웨어 부하 분산을 위해 필요한 DNS 레코드 (예제)</span><span class="sxs-lookup"><span data-stu-id="1c10a-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c10a-134">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="1c10a-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1c10a-135">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="1c10a-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1c10a-136">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="1c10a-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1c10a-137">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="1c10a-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c10a-138">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c10a-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c10a-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c10a-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="1c10a-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="1c10a-141">액세스에 지 서비스 외부 인터페이스 (Contoso)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="1c10a-142">Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</span><span class="sxs-lookup"><span data-stu-id="1c10a-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c10a-143">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c10a-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c10a-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c10a-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="1c10a-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="1c10a-146">웹 회의에 지 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c10a-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c10a-147">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c10a-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c10a-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c10a-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="1c10a-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="1c10a-150">A/V Edge 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c10a-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c10a-151">외부 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="1c10a-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="1c10a-152">_sip _tls. m m .com</span><span class="sxs-lookup"><span data-stu-id="1c10a-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c10a-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-154">액세스에 지 서비스 외부 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="1c10a-154">Access Edge service external interface.</span></span> <span data-ttu-id="1c10a-155">외부에서 작동 하도록 Lync 2013 및 Lync 2010 클라이언트를 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="1c10a-156">Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c10a-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c10a-157">External DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1c10a-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1c10a-158">_sipfederationtls _tcp. m m .com</span><span class="sxs-lookup"><span data-stu-id="1c10a-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c10a-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c10a-160">"허용 된 SIP 도메인"으로 알려진 페더레이션 파트너의 자동 DNS 검색에는 SIP 액세스에 지 서비스 외부 인터페이스가 필요 합니다 (이전 릴리스의 확장 페더레이션 이라고 함).</span><span class="sxs-lookup"><span data-stu-id="1c10a-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="1c10a-161">푸시 알림 서비스 또는 Apple Push Notification service를 사용 하는 Lync를 사용 하는 사용자 및 Microsoft Lync 모바일 클라이언트가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</span><span class="sxs-lookup"><span data-stu-id="1c10a-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c10a-162">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c10a-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c10a-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1c10a-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1c10a-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="1c10a-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="1c10a-165">통합 된 가장자리 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c10a-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

