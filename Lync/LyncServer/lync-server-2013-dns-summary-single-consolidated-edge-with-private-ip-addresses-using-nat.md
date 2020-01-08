---
title: DNS 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156757dbb3afd671d15618e8d3fceb0dfa7a04ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="02207-102">Lync Server 2013의 DNS 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="02207-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02207-103">_**마지막으로 수정한 주제:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="02207-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="02207-104">Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트에 대 한 것과 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="02207-105">또한 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션 사용 여부에 따라 많은 레코드가 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="02207-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="02207-106">Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02207-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="02207-107">분할 두뇌 DNS가 구성 되지 않은 경우 Lync 2013를 실행 하는 클라이언트의 자동 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 dns 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)에서 "분할 되지 않은 dns를 사용 하지 않는 자동 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02207-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="02207-108">다음 표에는 단일 통합 된 Edge 토폴로지 그림에 표시 된 단일 통합 edge 토폴로지를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="02207-109">특정 DNS 레코드는 Lync 2013 및 Lync 2010 클라이언트의 자동 구성에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="02207-110">Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 연결 된 자동 구성 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="02207-111">중요: Edge 서버 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="02207-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="02207-112">라우팅 문제를 방지 하려면 Edge 서버에 두 개 이상의 네트워크 어댑터가 있고 기본 게이트웨이가 외부 인터페이스와 연결 된 네트워크 어댑터에만 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="02207-113">예를 들어 통합 된 단일 edge 토폴로지에서 [Lync Server 2013의 개인 IP 주소와 NAT가 있는 단일 통합 된 가장자리](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)에 표시 되는 것 처럼 기본 게이트웨이는 외부 방화벽 (10.45.16.1)을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="02207-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="02207-114">다음과 같이 Edge 서버에서 두 개의 네트워크 어댑터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="02207-115">**네트워크 어댑터 1 (내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="02207-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="02207-116">172.25.33.10이 할당 된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="02207-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="02207-117">기본 게이트웨이가 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="02207-118">Edge 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버를 포함 하는 네트워크에 대 한 경로가 있는지 확인 합니다 (예: 172.25.33.0에서 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="02207-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="02207-119">**네트워크 어댑터 2 (외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="02207-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="02207-120">이 네트워크 어댑터에는 세 개의 개인 IP 주소가 할당 됩니다 (예: 액세스 Edge 용 10.45.16.10, 10.45.16.20 웹 컨퍼런스 Edge, AV Edge 용 10.45.16.30).</span><span class="sxs-lookup"><span data-stu-id="02207-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="02207-121">세 개의 Edge 서비스 인터페이스에 대해 단일 IP 주소를 사용 하는 것은 권장 되지 않지만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-121">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="02207-122">이것은 IP 주소를 저장 하지만, 서비스 마다 다른 포트 번호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-122">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="02207-123">기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용 하도록 보장 하는 443/TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="02207-123">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="02207-124">포트 값을 (예:) 액세스 Edge에 대해 5061/tcp로 변경 하면, AV Edge에 대 한 444/TCP는 해당 사용자가 뒤에 있는 방화벽이 5061/TCP 및 444를 통해 트래픽을 허용 하지 않는 리모컨에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-124">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="02207-125">또한 IP 주소에 따라 필터링이 가능 하기 때문에 세 개의 고유한 IP 주소를 통해 문제를 더 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-125">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="02207-126">Access Edge IP 주소는 기본 게이트웨이가 통합 라우터 (10.45.16.1)로 설정 된 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="02207-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="02207-127">웹 회의 및 A/V Edge IP 주소 보조.</span><span class="sxs-lookup"><span data-stu-id="02207-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="02207-128">두 개의 네트워크 어댑터를 사용 하 여 Edge 서버를 구성 하는 옵션은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="02207-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="02207-129">또 다른 옵션은 Edge 서버의 외부 측면에 대 한 네트워크 어댑터와 내부 측면을 각각 세 개 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="02207-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="02207-130">이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며 문제 해결이 필요할 때 더욱 간결한 데이터 수집을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="02207-131">NAT를 사용 하 여 개인 IP 주소가 있는 단일 통합 된 가장자리에 대해 필요한 DNS 레코드 (예제)</span><span class="sxs-lookup"><span data-stu-id="02207-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02207-132">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="02207-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="02207-133">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="02207-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="02207-134">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="02207-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="02207-135">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="02207-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02207-136">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="02207-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="02207-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="02207-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="02207-139">Lync를 사용 하는 사용자가 모든 SIP 도메인에 필요한 경우 액세스에 지 외부 인터페이스 (Contoso) 반복</span><span class="sxs-lookup"><span data-stu-id="02207-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02207-140">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="02207-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="02207-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="02207-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="02207-143">웹 회의 가장자리 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02207-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02207-144">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="02207-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="02207-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="02207-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="02207-147">A/V Edge 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02207-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02207-148">외부 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="02207-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="02207-149">_sip _tls. m m .com</span><span class="sxs-lookup"><span data-stu-id="02207-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-151">액세스에 지 외부 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="02207-151">Access Edge external interface.</span></span> <span data-ttu-id="02207-152">외부에서 작동 하도록 Lync 2013 및 Lync 2010 클라이언트를 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="02207-153">Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02207-154">External DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="02207-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="02207-155">_sipfederationtls _tcp. m m .com</span><span class="sxs-lookup"><span data-stu-id="02207-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-157">"허용 된 SIP 도메인" 이라고 알려진 페더레이션 파트너의 자동 DNS 검색에는 SIP 액세스에 지 외부 인터페이스가 필요 합니다 (이전 릴리스의 확장 페더레이션 이라고 함). Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</span><span class="sxs-lookup"><span data-stu-id="02207-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02207-158">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="02207-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="02207-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="02207-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="02207-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="02207-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="02207-161">통합 된 가장자리 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02207-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="02207-162">이전 표에 나열 된 레코드는 <EM>.net</EM> 확장 또는 <EM>.com</EM> 확장명으로 표시 되어 분할 하는 DNS를 사용 하지 않는 경우에는 해당 영역이 있어야 하는 영역을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="02207-163">분할 하는 DNS를 사용 하는 경우에는 모든 레코드가 내부 또는 외부 DNS 영역 버전에 있든 관계 없이 동일한 <EM>.com</EM> 영역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02207-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="02207-164">자세한 내용은 <A href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013의 dns 요구 사항 결정</A>에서 "분할-두뇌 dns"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02207-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="02207-165">페더레이션에 필요한 레코드</span><span class="sxs-lookup"><span data-stu-id="02207-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02207-166">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="02207-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="02207-167">Q</span><span class="sxs-lookup"><span data-stu-id="02207-167">FQDN</span></span></th>
<th><span data-ttu-id="02207-168">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="02207-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="02207-169">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="02207-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02207-170">External DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="02207-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="02207-171">_sipfederationtls _tcp. m m .com</span><span class="sxs-lookup"><span data-stu-id="02207-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-173">SIP 액세스에 지 외부 인터페이스는 다른 잠재적 페더레이션 파트너에 대 한 페더레이션 자동 DNS 검색을 위해 필요 하며, "허용 된 SIP 도메인" (이전 릴리스의 확장 페더레이션 이라고 함) 이라고 합니다. Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 대해 필요한 경우 반복</span><span class="sxs-lookup"><span data-stu-id="02207-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="02207-174">이 SRV 레코드는 이동성 및 푸시 알림 클리어 링 하우스에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="02207-175">확장 가능 메시지 및 현재 상태 프로토콜에 대 한 DNS 요약</span><span class="sxs-lookup"><span data-stu-id="02207-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02207-176">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="02207-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="02207-177">Q</span><span class="sxs-lookup"><span data-stu-id="02207-177">FQDN</span></span></th>
<th><span data-ttu-id="02207-178">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="02207-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="02207-179">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="02207-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02207-180">외부 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="02207-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="02207-181">_xmpp-서버 _tcp. c a m.</span><span class="sxs-lookup"><span data-stu-id="02207-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="02207-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="02207-183">액세스에 지 서비스 또는 Edge 풀의 XMPP 프록시 외부 인터페이스. Lync를 사용 하는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책, 또는에 적용 된 사용자 정책을 통해 외부 액세스 정책의 구성을 통해 XMPP 연락처와의 연결을 허용 하는 사용자가 Lync를 사용할 수 있는 사용자.</span><span class="sxs-lookup"><span data-stu-id="02207-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="02207-184">허용 되는 XMPP 도메인은 XMPP 페더레이션 파트너 정책 에서도 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02207-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="02207-185">자세한 내용은 관련 <strong>항목을 참조 하세요.</strong></span><span class="sxs-lookup"><span data-stu-id="02207-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02207-186">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="02207-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="02207-187">xmpp.contoso.com (예:)</span><span class="sxs-lookup"><span data-stu-id="02207-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="02207-188">XMPP 프록시를 호스팅하는 Edge 서버 또는 Edge 풀에 있는 액세스에 지 서비스의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="02207-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="02207-189">XMPP 프록시 서비스를 호스트 하는 액세스에 지 서비스 또는 Edge 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="02207-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="02207-190">일반적으로 사용자가 만든 SRV 레코드는이 호스트 (A 또는 AAAA) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="02207-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

