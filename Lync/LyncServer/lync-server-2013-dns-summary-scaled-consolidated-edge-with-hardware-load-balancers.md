---
title: DNS 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
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
ms.openlocfilehash: 5625aa9d6211c703853b110b3fec439113cfa48d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="8ed42-102">Lync Server 2013의 DNS 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="8ed42-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ed42-103">_**마지막으로 수정 된 항목:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="8ed42-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="8ed42-104">Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트의 경우와 비교 하는 것이 아주 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="8ed42-105">또한 대부분의 레코드는 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션을 사용 하는지 여부에 따라 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="8ed42-106">Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ed42-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="8ed42-107">분할로 인 한 DNS가 구성 되지 않은 경우 Lync 2013 클라이언트의 자동 구성을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)의 "자동 구성 (분할 되지 않은 dns)" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ed42-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="8ed42-108">다음 표에는 확장된 통합 에지 토폴로지(하드웨어 부하 분산) 그림을 지원하는 데 필요한 DNS 레코드에 대한 요약이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="8ed42-109">특정 DNS 레코드는 Lync 클라이언트에 대 한 자동 구성에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="8ed42-110">Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 관련 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="8ed42-111">중요:에 지 서버 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ed42-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="8ed42-112">라우팅 문제를 방지 하려면에 지 서버에 네트워크 어댑터가 두 개 이상 있는지, 그리고 외부 인터페이스와 연결 된 네트워크 어댑터에만 기본 게이트웨이가 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="8ed42-113">예를 들어, [Lync Server 2013의 하드웨어 부하 분산 장치를 사용 하 여 확장 된 통합](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)에 지에 따라 확장 된 통합에 지 시나리오 그림에 나와 있는 것 처럼 기본 게이트웨이는 외부 방화벽을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="8ed42-114">다음과 같이 각에 지 서버에 두 개의 네트워크 어댑터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="8ed42-115">**네트워크 어댑터 1(내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="8ed42-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="8ed42-116">172.25.33.10이 지정된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="8ed42-117">기본 게이트웨이는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-117">No default gateway.</span></span>
    
    <span data-ttu-id="8ed42-118">에 지 서버 내부 인터페이스를 포함 하는 네트워크에서 lync server를 실행 하는 네트워크 (예: 172.25.33.0에서 192.168.10.0로)에 대 한 경로가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="8ed42-119">**네트워크 어댑터 2(외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="8ed42-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="8ed42-120">이 네트워크 어댑터에는 세 개의 공용 IP 주소가 할당 됩니다 (예: 액세스에 지 서비스의 경우 131.107.155.10, 131.107.155.20에 대 한 웹 회의에 지 서비스의 경우 131.107.155.30 for A/V에 지 서비스의 경우).</span><span class="sxs-lookup"><span data-stu-id="8ed42-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8ed42-121">에 지 서버의 실제 외부 네트워크 인터페이스에 할당 되는 IP 주소는 선택한 하드웨어 부하 분산 장치에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="8ed42-122">실제 IP 주소 요구 사항을 이해 하려면 하드웨어 부하 분산 장치 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ed42-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="8ed42-123">권장되지는 않지만 세 개의 모든 에지 서비스 인터페이스에 대해 단일 IP 주소를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="8ed42-124">이렇게 해서 IP 주소를 절약할 수는 있지만 각 서비스에 대해 서로 다른 포트 번호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="8ed42-125">기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용하도록 보장하는 443/TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="8ed42-126">포트 값을 다음으로 변경 (예: 액세스에 지 서비스의 경우), A/V에 지 서비스의 경우 444/tcp를 사용 하는 경우 원격 사용자에 게 문제가 발생할 수 있는데,이 경우 해당 방화벽에서 들어오는 방화벽이 5061/tcp 및 444/tcp를 통해 트래픽을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="8ed42-127">또한 세 개의 고유 IP 주소를 사용하면 IP 주소로 필터링할 수 있기 때문에 문제 해결에도 더 유리합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="8ed42-128">액세스에 지 서비스 IP 주소는 기본 게이트웨이가 인터넷 연결 라우터 (131.107.155.1)로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="8ed42-129">웹 회의에 지 서비스 및 A/V에 지 서비스 IP 주소 보조입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="8ed42-130">두 개의 네트워크 어댑터를 사용 하 여에 지 서버를 구성 하는 방법은 두 가지 옵션 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="8ed42-131">또 다른 옵션은에 지 서버의 외부에 세 개의 네트워크 어댑터와 내부 측면에 대해 하나의 네트워크 어댑터를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="8ed42-132">이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며, 문제 해결이 필요한 경우 데이터 수집이 더 간결 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="8ed42-133">확장된 통합 에지, 하드웨어 부하 분산에 필요한 DNS 레코드(예제)</span><span class="sxs-lookup"><span data-stu-id="8ed42-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ed42-134">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="8ed42-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8ed42-135">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="8ed42-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="8ed42-136">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="8ed42-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="8ed42-137">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="8ed42-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ed42-138">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ed42-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ed42-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ed42-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="8ed42-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="8ed42-141">액세스에 지 서비스 외부 인터페이스 (Contoso)</span><span class="sxs-lookup"><span data-stu-id="8ed42-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="8ed42-142">Lync를 사용하도록 설정된 사용자가 포함된 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ed42-143">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ed42-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ed42-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ed42-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="8ed42-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="8ed42-146">웹 회의에 지 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ed42-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ed42-147">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ed42-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ed42-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ed42-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="8ed42-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="8ed42-150">A/V에 지 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ed42-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ed42-151">외부 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="8ed42-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="8ed42-152">_sip _tls. contoso.</span><span class="sxs-lookup"><span data-stu-id="8ed42-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ed42-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-154">액세스에 지 서비스 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ed42-154">Access Edge service external interface.</span></span> <span data-ttu-id="8ed42-155">Lync 2013 및 Lync 2010 클라이언트가 외부적으로 작동 하도록 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="8ed42-156">Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ed42-157">외부 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="8ed42-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="8ed42-158">_sipfederationtls _tcp. contoso.</span><span class="sxs-lookup"><span data-stu-id="8ed42-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ed42-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8ed42-160">SIP 액세스에 지 서비스 외부 인터페이스 페더레이션 파트너의 자동 DNS 검색에 필요한 "허용 된 SIP 도메인" (이전 릴리스의 향상 된 페더레이션 이라고 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="8ed42-161">Lync를 사용할 수 있는 모든 SIP 도메인 및 푸시 알림 서비스 또는 Apple 푸시 알림 서비스를 사용 하는 Microsoft Lync 모바일 클라이언트에 대해 필요에 따라 반복</span><span class="sxs-lookup"><span data-stu-id="8ed42-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ed42-162">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="8ed42-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8ed42-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8ed42-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8ed42-164">172.25.33.10이 지정</span><span class="sxs-lookup"><span data-stu-id="8ed42-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="8ed42-165">통합 에지 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ed42-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

