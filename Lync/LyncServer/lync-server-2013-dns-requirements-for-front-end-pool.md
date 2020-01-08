---
title: 'Lync Server 2013: 프런트 엔드 풀에 대한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="c4ba8-102">Lync Server 2013의 프런트 엔드 풀에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4ba8-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ba8-103">_**마지막으로 수정한 주제:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="c4ba8-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="c4ba8-104">이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="c4ba8-105">토폴로지 작성기에 토폴로지를 게시 하기 전에 필수 DNS (Domain Name System) 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="c4ba8-106">또한 Lync Server 2013 배포의 구성에 사용 되는 Fqdn (정규화 된 도메인 이름) 중 일부는 논리적이 고 비 실제 서버 Fqdn 이므로 게시 하기 전에 추가 DNS 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c4ba8-107">Lync Server 2013는 단일 레이블이 지정 된 도메인을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="c4ba8-108">예를 들어, <STRONG>contoso. local</STRONG> 이라는 루트 도메인이 있는 포리스트는 지원 되지만 <STRONG>local</STRONG> 이라는 루트 도메인은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="c4ba8-109">자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름을 사용 하 여 Windows 구성에 대 한 정보" <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp, kbid = 300684</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c4ba8-110">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="c4ba8-111">기본적으로 도메인에 가입 되어 있지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="c4ba8-112">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="c4ba8-113">Lync Server, Edge 서버 및 풀을 실행 하는 서버의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함) <STRONG>만 사용</STRONG> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="c4ba8-114">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="c4ba8-115">FQDN의 비표준 문자는 외부 DNS 및 Ca (공개 인증 기관)에서 지원 되지 않습니다 (FQDN을 인증서의 SN에 할당 해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="c4ba8-116">토폴로지를 배포한 후에 작동 하기 전에 다음 Active Directory 및 DNS 레코드가 만들어졌는지 확인 하세요 (특정 기능에 대 한 요구 사항에 따라 결정).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="c4ba8-117">토폴로지에 존재 하는 각 서버 역할은 Active Directory 개체로 게시 됩니다 (도메인에 컴퓨터를 참가 하면이를 수행 하 게 됩니다).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="c4ba8-118">각 서버에 대 한 DNS A 레코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="c4ba8-119">\_Sipinternaltls\_tcp 형식의 클라이언트에 대 한 자동 로그온을 사용 하려는 경우 각 SIP 도메인에 대 한 DNS SRV 레코드가 있습니다. \<SIP 도메인\>.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="c4ba8-120">클라이언트에 수동 구성을 사용 하는 경우에는이 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="c4ba8-121">일반적으로 모임, 전화 접속, lwa, 스케줄러 등의 구성 된 각 단순 URL에 대 한 DNS A 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="c4ba8-122">또한 Lync Server 2013 제어판에 대 한 액세스를 위한 특별 한 URL 인 관리 간단한 URL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="c4ba8-123">SQL Server를 실행 하는 서버는 도메인에 가입 하 고 토폴로지 작성기가 게시 하는 컴퓨터에서 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="c4ba8-124">테이블은 계획 섹션에 제시 된 참조 아키텍처를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="c4ba8-125">자세한 내용은 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="c4ba8-126">프런트 엔드 풀에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="c4ba8-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba8-127">위치</span><span class="sxs-lookup"><span data-stu-id="c4ba8-127">Location</span></span></th>
<th><span data-ttu-id="c4ba8-128">유형</span><span class="sxs-lookup"><span data-stu-id="c4ba8-128">Type</span></span></th>
<th><span data-ttu-id="c4ba8-129">Q</span><span class="sxs-lookup"><span data-stu-id="c4ba8-129">FQDN</span></span></th>
<th><span data-ttu-id="c4ba8-130">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="c4ba8-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-131">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-132">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-132">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-134">Pool01 (DNS 로드 균형 조정).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="c4ba8-135">풀에 속한 각 프런트 엔드 서버의 IP 주소에 대 한 DNS A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba8-136">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-137">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-137">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-139">Pool01 (하드웨어 로드 균형 조정기의 VIP (가상 IP)).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-140">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-141">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-141">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="c4ba8-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="c4ba8-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="c4ba8-145">…</span><span class="sxs-lookup"><span data-stu-id="c4ba8-145"></span></span></p></td>
<td><p><span data-ttu-id="c4ba8-146">Pool01 프런트 엔드 서버 (노드 1).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="c4ba8-147">Pool01 프런트 엔드 서버 (노드 2).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="c4ba8-148">Pool01 프런트 엔드 서버 (노드 3).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="c4ba8-149">…</span><span class="sxs-lookup"><span data-stu-id="c4ba8-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba8-150">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-151">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-151">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-153">Pool01 프런트 엔드 서버 (노드 2).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-154">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-155">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-155">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-157">클라이언트 대 서버 웹 트래픽에 대 한 Pool01 (VIP).</span><span class="sxs-lookup"><span data-stu-id="c4ba8-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba8-158">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-159">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-159">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c4ba8-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-161">SQL Server 2008 R2를 실행 하는 Pool01 백 엔드 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-162">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-163">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-163">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-165">Lync Phone Edition 또는 DNS SRV 레코드가 없는 클라이언트의 자동 로그온과 엄격한 도메인 일치에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="c4ba8-166">모든 경우에 필요 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba8-167">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-168">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-168">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-170">두 번째 SIP 도메인으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="c4ba8-171">Lync Phone Edition, DNS SRV 레코드가 없는 클라이언트의 자동 로그온, 엄격한 도메인 일치에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="c4ba8-172">모든 경우에 필요 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-173">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-174">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-174">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-176">내부적으로 게시 된 전화 접속 회의에 대 한 간단한 URL – 프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 간단한 URL 쿼리에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba8-177">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-178">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-178">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-180">내부적으로 게시 되는 회의에 대 한 간단한 URL – 프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 간단한 URL 쿼리에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-181">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-182">에서</span><span class="sxs-lookup"><span data-stu-id="c4ba8-182">A</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="c4ba8-184">관리자</span><span class="sxs-lookup"><span data-stu-id="c4ba8-184">admin</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-185">선택적 레코드, Lync 2013 Server 용 간단한 URL-프런트 엔드 서버 (또는 설치 되어 있는 경우)가 단순 URL 쿼리에 응답 하 여이를 내부적으로 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="c4ba8-186">호스트 이름만 (도메인 이름 없음) 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c4ba8-187">VIP = 하드웨어 부하 분산 장치에 대 한 가상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="c4ba8-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="c4ba8-188">프런트 엔드 풀에 대 한 DNS SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="c4ba8-188">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4ba8-189">위치</span><span class="sxs-lookup"><span data-stu-id="c4ba8-189">Location</span></span></th>
<th><span data-ttu-id="c4ba8-190">유형</span><span class="sxs-lookup"><span data-stu-id="c4ba8-190">Type</span></span></th>
<th><span data-ttu-id="c4ba8-191">Q</span><span class="sxs-lookup"><span data-stu-id="c4ba8-191">FQDN</span></span></th>
<th><span data-ttu-id="c4ba8-192">대상 FQDN</span><span class="sxs-lookup"><span data-stu-id="c4ba8-192">Target FQDN</span></span></th>
<th><span data-ttu-id="c4ba8-193">포트</span><span class="sxs-lookup"><span data-stu-id="c4ba8-193">Port</span></span></th>
<th><span data-ttu-id="c4ba8-194">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="c4ba8-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-195">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-196">SRV</span><span class="sxs-lookup"><span data-stu-id="c4ba8-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-197">_sipinternaltls _tcp. m m .com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-199">5061</span><span class="sxs-lookup"><span data-stu-id="c4ba8-199">5061</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-200">내부적으로 작업 하도록 Lync 2013 클라이언트를 자동 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4ba8-201">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-202">SRV</span><span class="sxs-lookup"><span data-stu-id="c4ba8-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-203">_sipinternaltls _tcp. c a m</span><span class="sxs-lookup"><span data-stu-id="c4ba8-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-205">5061</span><span class="sxs-lookup"><span data-stu-id="c4ba8-205">5061</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-206">내부적으로 작업 하도록 Lync 2013 클라이언트를 자동 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4ba8-207">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="c4ba8-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-208">SRV</span><span class="sxs-lookup"><span data-stu-id="c4ba8-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-209">_ntp _udp. m m .com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4ba8-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-211">123</span><span class="sxs-lookup"><span data-stu-id="c4ba8-211">123</span></span></p></td>
<td><p><span data-ttu-id="c4ba8-212">Lync Phone Edition을 실행 하는 장치에 필요한 NTP (네트워크 시간 프로토콜) 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="c4ba8-213">내부적으로이는 도메인 컨트롤러를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="c4ba8-214">도메인 컨트롤러가 정의 되지 않은 경우에는 NTP 서버 time.windows.com를 사용 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ba8-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

