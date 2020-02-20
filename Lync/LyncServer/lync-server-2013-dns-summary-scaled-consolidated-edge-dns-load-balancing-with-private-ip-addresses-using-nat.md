---
title: 'Lync Server 2013: DNS 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3edaa813751af0cb833688d9f36f8447a32baced
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="61417-102">Lync Server 2013의 DNS 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="61417-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61417-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="61417-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="61417-104">Lync Server 2013에 대 한 원격 액세스에 대 한 DNS 레코드 요구 사항은 인증서 및 포트의 경우와 비교 하는 것이 아주 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="61417-105">또한 대부분의 레코드는 Lync 2013를 실행 하는 클라이언트를 구성 하는 방법과 페더레이션을 사용 하는지 여부에 따라 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="61417-106">Lync 2013 DNS 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="61417-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="61417-107">분할로 인 한 DNS가 구성 되지 않은 경우 Lync 2013 클라이언트의 자동 구성을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)의 "자동 구성 (분할 되지 않은 dns)" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="61417-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="61417-108">다음 표에는 단일 통합 에지 토폴로지 그림에 표시된 단일 통합 에지 토폴로지를 지원하는 데 필요한 DNS 레코드가 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="61417-109">특정 DNS 레코드는 Lync 2013 클라이언트를 자동으로 구성 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="61417-110">Gpo (그룹 정책 개체)를 사용 하 여 Lync 클라이언트를 구성 하려는 경우에는 관련 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="61417-111">중요:에 지 서버 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="61417-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="61417-112">라우팅 문제를 방지 하려면에 지 서버에 네트워크 어댑터가 두 개 이상 있는지, 그리고 외부 인터페이스와 연결 된 네트워크 어댑터에만 기본 게이트웨이가 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="61417-113">예를 들어 확장 통합에 지 시나리오 그림에 표시 된 것 처럼, [Lync Server 2013에서 NAT를 사용 하는 개인 IP 주소를 사용한 DNS 부하 분산](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)에 따라 기본 게이트웨이가 외부 방화벽을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="61417-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="61417-114">다음과 같이 각 에지 서버에 네트워크 어댑터 두 개를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="61417-115">**네트워크 어댑터 1 - 노드 1(내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="61417-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="61417-116">172.25.33.10이 할당된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="61417-117">기본 게이트웨이가 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="61417-118">에 지 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="61417-119">**네트워크 어댑터 1 - 노드 2(내부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="61417-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="61417-120">172.25.33.11이 할당된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="61417-121">기본 게이트웨이가 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="61417-122">에 지 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 2013 또는 Lync Server 2013 클라이언트를 실행 하는 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="61417-123">**네트워크 어댑터 2 - 노드 1(외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="61417-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="61417-124">이 네트워크 어댑터에는 개인 IP 주소 3개가 할당됩니다(예: 액세스 에지용 10.45.16.10, 웹 회의 에지용 10.45.16.20, A/V 에지용 10.45.16.30).</span><span class="sxs-lookup"><span data-stu-id="61417-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61417-p104">3개 에지 서비스 인터페이스에 대해 모두 단일 IP 주소를 사용할 수는 있지만 이렇게 하지 않는 것이 좋습니다. 이렇게 하면 IP 주소 수는 줄일 수 있지만 각 서비스에 대해 서로 다른 포트 번호가 필요합니다. 기본 포트 번호는 443/TCP이며, 이 번호를 사용하는 경우 대부분의 원격 방화벽이 트래픽을 허용합니다. 예를 들어 포트 값을 액세스 에지에 대해서는 5061/TCP, 웹 회의 에지에 대해서는 444/TCP, 그리고 A/V 에지에 대해서는 443/TCP로 변경하면 원격 사용자를 보호하는 방화벽이 5061/TCP 및 444/TCP를 통과하는 방화벽을 허용하지 않는 문제가 발생할 수 있습니다. 또한 고유한 IP 주소 3개를 사용하는 경우 IP 주소에서 필터링을 할 수 있으므로 문제를 더 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="61417-130">액세스 에지 공용 IP 주소는 기본 게이트웨이가 통합 라우터로 설정된 기본 IP 주소입니다(10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="61417-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="61417-131">웹 회의 및 A/V 에지 개인 IP 주소는 Windows Server에서 **로컬 영역 연결 속성**의 **인터넷 프로토콜 버전 4(TCP/IPv4)** 및 **인터넷 프로토콜 버전 6(TCP/IPv6)** 속성 **고급** 섹션에 있는 추가 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="61417-132">**네트워크 어댑터 2 - 노드 2(외부 인터페이스)**</span><span class="sxs-lookup"><span data-stu-id="61417-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="61417-133">이 네트워크 어댑터에는 개인 IP 주소 3개가 할당됩니다(예: 액세스 에지용 10.45.16.11, 웹 회의 에지용 10.45.16.21, A/V 에지용 10.45.16.31).</span><span class="sxs-lookup"><span data-stu-id="61417-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="61417-134">액세스 에지 공용 IP 주소는 기본 게이트웨이가 통합 라우터로 설정된 기본 IP 주소입니다(10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="61417-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="61417-135">웹 회의 및 A/V 에지 개인 IP 주소는 Windows Server에서 **로컬 영역 연결 속성**의 **인터넷 프로토콜 버전 4(TCP/IPv4)** 및 **인터넷 프로토콜 버전 6(TCP/IPv6)** 속성 **고급** 섹션에 있는 추가 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="61417-136">두 개의 네트워크 어댑터를 사용 하 여에 지 서버를 구성 하는 방법은 두 가지 옵션 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="61417-137">또 다른 옵션은에 지 서버의 외부에 세 개의 네트워크 어댑터와 내부 측면에 대해 하나의 네트워크 어댑터를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="61417-138">이 옵션의 주요 이점은 각에 지 서버 서비스에 대 한 고유한 네트워크 어댑터 이며, 문제 해결이 필요한 경우 데이터 수집이 더 간결 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61417-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="61417-139">확장된 통합 에지에 필요한 DNS 레코드 - NAT를 사용하는 개인 IP 주소로 DNS 부하 분산됨(예제)</span><span class="sxs-lookup"><span data-stu-id="61417-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61417-140">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="61417-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="61417-141">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="61417-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="61417-142">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="61417-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="61417-143">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="61417-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61417-144">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="61417-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="61417-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-146">131.107.155.10 및 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="61417-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="61417-147">액세스 에지 외부 인터페이스(Contoso). Lync를 사용하도록 설정된 사용자가 포함된 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61417-148">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="61417-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="61417-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-150">131.107.155.20 및 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="61417-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="61417-151">웹 회의 에지 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61417-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61417-152">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="61417-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="61417-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-154">131.107.155.30 및 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="61417-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="61417-155">A/V 에지 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61417-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61417-156">외부 DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="61417-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="61417-157">_sip _tls. contoso.</span><span class="sxs-lookup"><span data-stu-id="61417-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-159">액세스 에지 외부 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="61417-159">Access Edge external interface.</span></span> <span data-ttu-id="61417-160">Lync 2013 및 Lync 2010 클라이언트가 외부적으로 작동 하도록 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="61417-161">Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61417-162">외부 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="61417-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="61417-163">_sipfederationtls _tcp. contoso.</span><span class="sxs-lookup"><span data-stu-id="61417-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-p107">SIP 액세스 에지 외부 인터페이스. "허용 SIP 도메인"(이전 버전에서는 확장 페더레이션이라고 함)이라는 페더레이션 파트너의 자동 DNS 검색에 필요합니다. Lync를 사용하도록 설정된 사용자가 포함된 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61417-168">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="61417-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="61417-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="61417-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="61417-170">172.25.33.10 및 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="61417-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="61417-171">통합 에지 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61417-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="61417-172">페더레이션에 필요한 레코드</span><span class="sxs-lookup"><span data-stu-id="61417-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61417-173">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="61417-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="61417-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="61417-174">FQDN</span></span></th>
<th><span data-ttu-id="61417-175">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="61417-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="61417-176">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="61417-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61417-177">외부 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="61417-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="61417-178">_sipfederationtls _tcp. contoso.</span><span class="sxs-lookup"><span data-stu-id="61417-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-180">SIP 액세스 에지 외부 인터페이스. 다른 잠재적인 페더레이션 파트너에 대한 사용자의 페더레이션의 자동 DNS 검색을 위해 필요하며 "허용된 SIP 도메인"으로 알려져 있습니다(이전 릴리스의 향상된 페더레이션). Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="61417-181">이 SRV 레코드는 모바일 및 푸시 알림 클리어링 하우스에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="61417-182">DNS 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="61417-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61417-183">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="61417-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="61417-184">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="61417-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="61417-185">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="61417-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="61417-186">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="61417-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61417-187">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="61417-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="61417-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-189">액세스에 지 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61417-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="61417-190">액세스 에지 외부 인터페이스(Contoso). Lync가 설정된 사용자의 모든 SIP 도메인에 대해 필요한 만큼 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="61417-191">XMPP(Extensible Messaging and Presence Protocol)의 DNS 요약</span><span class="sxs-lookup"><span data-stu-id="61417-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61417-192">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="61417-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="61417-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="61417-193">FQDN</span></span></th>
<th><span data-ttu-id="61417-194">IP 주소/FQDN 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="61417-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="61417-195">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="61417-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61417-196">외부 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="61417-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="61417-197">_xmpp-.com. _tcp</span><span class="sxs-lookup"><span data-stu-id="61417-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61417-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="61417-199">액세스에 지 서비스 또는에 지 풀의 XMPP 프록시 외부 인터페이스 Lync 사용 가능 사용자가 있는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책 또는 도메인에 적용 되는 사용자 정책을 통해 외부 액세스 정책을 구성 하 여 XMPP 대화 상대와의 연결을 허용 합니다. Lync 사용 가능 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="61417-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="61417-200">XMPP 페더레이션 파트너 정책 에서도 허용 되는 XMPP 도메인을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61417-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="61417-201">자세한 내용은 관련 <strong>항목을 참조</strong> 하십시오.</span><span class="sxs-lookup"><span data-stu-id="61417-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61417-202">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="61417-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="61417-203">xmpp.contoso.com(예제)</span><span class="sxs-lookup"><span data-stu-id="61417-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="61417-204">XMPP 프록시를 호스팅하는에 지 서버 또는에 지 풀에 있는 액세스에 지 서비스의 IP 주소</span><span class="sxs-lookup"><span data-stu-id="61417-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="61417-205">XMPP 프록시 서비스를 호스팅하는 액세스에 지 서비스 또는에 지 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="61417-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="61417-206">일반적으로 사용자가 만드는 SRV 레코드는 이 호스트(A 또는 AAAA) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="61417-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

