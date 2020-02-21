---
title: DNS 요약-공용 IP 주소의 단일 통합에 지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 622cb9811e33762bf40c05dfa5e5f0ab644b51aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="30401-102">Lync Server 2013의 DNS 요약-공용 IP 주소를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="30401-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30401-103">_**마지막으로 수정 된 항목:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="30401-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="30401-104">Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트의 경우와 비교 하는 것이 아주 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="30401-105">또한 대부분의 레코드는 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션을 사용 하는지 여부에 따라 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="30401-106">Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30401-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="30401-107">분할로 인 한 DNS가 구성 되지 않은 경우 Lync 2013을 실행 하는 클라이언트의 자동 구성에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 결정](lync-server-2013-determine-dns-requirements.md)에서 "분할 되지 않은 dns를 사용 하지 않는 자동 구성"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30401-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="30401-108">다음 표에는 단일 통합 에지 토폴로지 그림에 표시된 단일 통합 에지 토폴로지를 지원하는 데 필요한 DNS 레코드가 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30401-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="30401-109">특정 DNS 레코드는 Lync 2013 및 Lync 2010 클라이언트를 자동으로 구성 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="30401-110">Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 연결 된 자동 구성 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30401-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="30401-111">중요:에 지 서버 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="30401-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="30401-112">라우팅 문제를 방지 하려면에 지 서버에 네트워크 어댑터가 두 개 이상 있는지, 그리고 외부 인터페이스와 연결 된 네트워크 어댑터에만 기본 게이트웨이가 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="30401-113">예를 들어 공용 ip 주소를 포함 하는 단일 통합에 지 토폴로지에서 공용 ip 주소를 포함 하는 단일 통합에 지 토폴로지를 [Lync Server 2013에](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)표시 된 것 처럼 기본 게이트웨이는 공용 ip 주소를 제공할 수 있는 인터넷 경계 또는 방화벽에서 외부 라우터를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="30401-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="30401-114">에 지 서버 인터페이스에 대 한 네트워크 관계는 NAT 관계가 아닌 경로 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="30401-115">다음과 같이 에지 서버에 네트워크 어댑터 두 개를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30401-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="30401-116">**네트워크 어댑터 1(내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="30401-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="30401-117">172.25.33.10이 지정된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="30401-118">기본 게이트웨이가 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30401-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="30401-119">에 지 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="30401-120">**네트워크 어댑터 2(외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="30401-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="30401-121">이 네트워크 어댑터에는 3개의 공용 IP 주소가 지정됩니다. 예를 들어 액세스 에지에는 131.107.155.10이 지정되고, 웹 회의 에지에는 131.107.155.20이 지정되고, AV 에지에는 131.107.155.30이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="30401-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="30401-p104">권장되지는 않지만 세 개의 모든 에지 서비스 인터페이스에 대해 단일 IP 주소를 사용할 수도 있습니다. 이렇게 해서 IP 주소를 절약할 수는 있지만 각 서비스에 대해 서로 다른 포트 번호가 필요합니다. 기본 포트 번호는 대부분의 원격 방화벽에서 트래픽을 허용하도록 보장하는 443/TCP입니다. 하지만 예를 들어 포트 값을 액세스 에지의 경우 5061/TCP로 변경하고, 웹 회의 에지의 경우 444/TCP로 변경하고, AV 에지의 경우 443/TCP로 변경하면 뒤에 있는 방화벽이 5061/TCP 및 444/TCP에 대한 트래픽을 허용하지 않아서 원격 사용자에게 문제가 발생할 수 있습니다. 또한 세 개의 고유 IP 주소를 사용하면 IP 주소로 필터링할 수 있기 때문에 문제 해결에도 더 유리합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="30401-127">액세스 에지 공용 IP 주소는 기본 게이트웨이가 공용 라우터로 설정된 기본 IP 주소입니다(131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="30401-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="30401-128">웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server에서 **로컬 영역 연결 속성**의 **인터넷 프로토콜 버전 4(TCP/IPv4)** 및 **인터넷 프로토콜 버전 6(TCP/IPv6)** 에 대한 속성의 **고급** 섹션에 추가된 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="30401-129">두 개의 네트워크 어댑터를 사용 하 여에 지 서버를 구성 하는 방법은 두 가지 옵션 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="30401-130">또 다른 옵션은에 지 서버의 외부에 세 개의 네트워크 어댑터와 내부 측면에 대해 하나의 네트워크 어댑터를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="30401-131">이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며, 문제 해결이 필요한 경우 데이터 수집이 더 간결 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30401-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="30401-132">공용 IP 주소가 포함된 단일 통합 에지에 필요한 DNS 레코드(예제)</span><span class="sxs-lookup"><span data-stu-id="30401-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30401-133">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="30401-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="30401-134">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="30401-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="30401-135">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="30401-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="30401-136">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="30401-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30401-137">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="30401-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="30401-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="30401-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="30401-140">액세스 에지 외부 인터페이스(Contoso). Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30401-141">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="30401-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="30401-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="30401-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="30401-144">웹 회의 에지 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30401-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30401-145">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="30401-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="30401-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="30401-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="30401-148">A/V 에지 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30401-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30401-149">외부 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="30401-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="30401-150">_sip _tls. contoso.</span><span class="sxs-lookup"><span data-stu-id="30401-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-152">액세스 에지 외부 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="30401-152">Access Edge external interface.</span></span> <span data-ttu-id="30401-153">Lync 2013 및 Lync 2010 클라이언트가 외부적으로 작동 하도록 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="30401-154">Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30401-155">외부 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="30401-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="30401-156">_sipfederationtls _tcp. contoso.</span><span class="sxs-lookup"><span data-stu-id="30401-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-158">SIP 액세스 에지 외부 인터페이스. "허용된 SIP 도메인"(이전 버전의 향상된 페더레이션)으로 알려진 페더레이션 파트너의 자동 DNS 검색을 위해 필요합니다. Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30401-159">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="30401-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="30401-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="30401-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="30401-161">172.25.33.10이 지정</span><span class="sxs-lookup"><span data-stu-id="30401-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="30401-162">통합 에지 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30401-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="30401-163">앞의 표에 나열되어 있는 레코드는 분할 DNS를 사용하지 않을 경우 레코드가 있어야 할 영역을 강조하기 위해 <EM>.net</EM> 확장명 또는 <EM>.com</EM> 확장명으로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30401-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="30401-164">분할 DNS를 사용하는 경우에는 모든 레코드가 같은 영역에 있으므로 내부 버전인지 아니면 외부 버전인지만 구분하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30401-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="30401-165">자세한 내용은 <A href="lync-server-2013-determine-dns-requirements.md">Lync Server 2013에 대 한 DNS 요구 사항 결정</A>에서 "분할-두뇌 DNS"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30401-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="30401-166">페더레이션에 필요한 레코드</span><span class="sxs-lookup"><span data-stu-id="30401-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30401-167">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="30401-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="30401-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="30401-168">FQDN</span></span></th>
<th><span data-ttu-id="30401-169">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="30401-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="30401-170">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="30401-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30401-171">외부 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="30401-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="30401-172">_sipfederationtls _tcp. contoso.</span><span class="sxs-lookup"><span data-stu-id="30401-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-174">SIP 액세스 에지 외부 인터페이스. 다른 잠재적인 페더레이션 파트너에 대한 사용자의 페더레이션의 자동 DNS 검색을 위해 필요하며 "허용된 SIP 도메인"으로 알려져 있습니다(이전 릴리스의 향상된 페더레이션). Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="30401-175">이 SRV 레코드는 모바일 및 푸시 알림 클리어링 하우스에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="30401-176">XMPP(Extensible Messaging and Presence Protocol)의 DNS 요약</span><span class="sxs-lookup"><span data-stu-id="30401-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30401-177">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="30401-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="30401-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="30401-178">FQDN</span></span></th>
<th><span data-ttu-id="30401-179">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="30401-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="30401-180">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="30401-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30401-181">외부 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="30401-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="30401-182">_xmpp-.com. _tcp</span><span class="sxs-lookup"><span data-stu-id="30401-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="30401-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="30401-184">액세스에 지 서비스 또는에 지 풀의 XMPP 프록시 외부 인터페이스 Lync 사용 가능 사용자가 있는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책 또는 도메인에 적용 되는 사용자 정책을 통해 외부 액세스 정책을 구성 하 여 XMPP 대화 상대와의 연결을 허용 합니다. Lync 사용 가능 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="30401-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="30401-185">XMPP 페더레이션 파트너 정책 에서도 허용 되는 XMPP 도메인을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30401-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="30401-186">자세한 내용은 관련 <strong>항목을 참조</strong> 하십시오.</span><span class="sxs-lookup"><span data-stu-id="30401-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30401-187">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="30401-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="30401-188">xmpp.contoso.com(예제)</span><span class="sxs-lookup"><span data-stu-id="30401-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="30401-189">XMPP 프록시를 호스팅하는에 지 서버 또는에 지 풀에 있는 액세스에 지 서비스의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="30401-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="30401-190">XMPP 프록시 서비스를 호스팅하는 액세스에 지 서비스 또는에 지 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="30401-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="30401-191">일반적으로 사용자가 만드는 SRV 레코드는 이 호스트(A 또는 AAAA) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="30401-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

