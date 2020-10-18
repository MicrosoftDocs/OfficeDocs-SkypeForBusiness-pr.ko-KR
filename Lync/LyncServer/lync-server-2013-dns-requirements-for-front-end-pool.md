---
title: 'Lync Server 2013: 프런트 엔드 풀에 대 한 DNS 요구 사항'
description: 'Lync Server 2013: 프런트 엔드 풀에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574334"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="78c64-103">Lync Server 2013의 프런트 엔드 풀에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="78c64-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78c64-104">_**마지막으로 수정 된 항목:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="78c64-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="78c64-105">이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="78c64-106">토폴로지 작성기에 토폴로지를 게시 하기 전에 필요한 DNS (Domain Name System) 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="78c64-107">또한 Lync Server 2013 배포의 구성에 사용 되는 Fqdn (정규화 된 도메인 이름) 중 일부는 논리적 서버 Fqdn이 아니며, 게시 하기 전에 추가 DNS를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="78c64-108">Lync Server 2013에서는 단일 레이블 도메인을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="78c64-109">예를 들어 <STRONG>contoso.local</STRONG>이라는 루트 도메인으로 구성된 포리스트는 지원되지만 <STRONG>local</STRONG>이라는 루트 도메인은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="78c64-110">자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름을 사용 하 여 Windows 구성에 대 한 정보, <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp kbid = 300684</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="78c64-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78c64-111">지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="78c64-112">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="78c64-113">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="78c64-114">Lync Server, Edge 서버 및 풀을 실행 하는 서버의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9 및 하이픈 포함) <STRONG>만 사용</STRONG> 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="78c64-115">유니코드 문자나 밑줄은 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="78c64-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="78c64-116">FQDN의 비표준 문자는 외부 DNS 및 공용 CA(인증 기관)에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="78c64-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="78c64-117">토폴로지를 배포한 후 작동 하기 전에 특정 기능에 대 한 필요에 따라 다음과 같은 Active Directory 및 DNS 레코드가 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="78c64-118">토폴로지에 있는 각 서버 역할은 Active Directory 개체로 게시 됩니다 (도메인에 컴퓨터를 가입 하면이 작업을 수행 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="78c64-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="78c64-119">각 서버에 대한 DNS A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="78c64-120">\_Sipinternaltls tcp의 형태로 클라이언트에 대해 자동 로그온을 사용 하려는 경우 각 SIP 도메인에 대해 DNS SRV 레코드가 존재 합니다 \_ \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="78c64-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="78c64-121">클라이언트에 대해 수동 구성을 사용하려는 경우에는 이 레코드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="78c64-122">구성된 각 단순 URL(모임 및 전화 접속)에 대한 DNS A 레코드가 있어야 합니다(일반적으로 meet, dialin, lwa, scheduler의 4가지).</span><span class="sxs-lookup"><span data-stu-id="78c64-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="78c64-123">또한 Lync Server 2013 제어판에 액세스 하기 위한 특수 URL 인 관리자 단순 URL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="78c64-124">SQL Server를 실행 하는 서버는 도메인에 가입 되어야 하며 토폴로지 작성기가 게시 하는 컴퓨터에서 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="78c64-125">아래 표는 계획 섹션에 설명된 참조 아키텍처를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="78c64-126">자세한 내용은 계획 설명서에서 [Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="78c64-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="78c64-127">프런트 엔드 풀에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="78c64-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78c64-128">위치</span><span class="sxs-lookup"><span data-stu-id="78c64-128">Location</span></span></th>
<th><span data-ttu-id="78c64-129">타이핑</span><span class="sxs-lookup"><span data-stu-id="78c64-129">Type</span></span></th>
<th><span data-ttu-id="78c64-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="78c64-130">FQDN</span></span></th>
<th><span data-ttu-id="78c64-131">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="78c64-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78c64-132">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-133">A</span><span class="sxs-lookup"><span data-stu-id="78c64-133">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="78c64-135">Pool01(DNS 부하 분산).</span><span class="sxs-lookup"><span data-stu-id="78c64-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="78c64-136">풀에 있는 각 프런트 엔드 서버의 IP 주소에 대 한 DNS A 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78c64-137">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-138">A</span><span class="sxs-lookup"><span data-stu-id="78c64-138">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="78c64-140">Pool01(하드웨어 부하 분산 장치의 VIP(가상 IP))</span><span class="sxs-lookup"><span data-stu-id="78c64-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78c64-141">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-142">A</span><span class="sxs-lookup"><span data-stu-id="78c64-142">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="78c64-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="78c64-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="78c64-146">…</span><span class="sxs-lookup"><span data-stu-id="78c64-146">…</span></span></p></td>
<td><p><span data-ttu-id="78c64-147">Pool01 프런트 엔드 서버 (노드 1)</span><span class="sxs-lookup"><span data-stu-id="78c64-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="78c64-148">Pool01 프런트 엔드 서버 (노드 2)</span><span class="sxs-lookup"><span data-stu-id="78c64-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="78c64-149">Pool01 프런트 엔드 서버 (노드 3)</span><span class="sxs-lookup"><span data-stu-id="78c64-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="78c64-150">…</span><span class="sxs-lookup"><span data-stu-id="78c64-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78c64-151">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-152">A</span><span class="sxs-lookup"><span data-stu-id="78c64-152">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="78c64-154">Pool01 프런트 엔드 서버 (노드 2)</span><span class="sxs-lookup"><span data-stu-id="78c64-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78c64-155">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-156">A</span><span class="sxs-lookup"><span data-stu-id="78c64-156">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="78c64-158">클라이언트-서버 웹 트래픽용 Pool01(VIP)</span><span class="sxs-lookup"><span data-stu-id="78c64-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78c64-159">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-160">A</span><span class="sxs-lookup"><span data-stu-id="78c64-160">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="78c64-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="78c64-162">SQL Server 2008 R2를 실행 하는 Pool01 백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="78c64-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78c64-163">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-164">A</span><span class="sxs-lookup"><span data-stu-id="78c64-164">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78c64-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-166">Lync Phone Edition 또는 DNS SRV 레코드가 없는 클라이언트의 자동 로그온 및 엄격한 도메인 일치에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="78c64-167">모든 경우에 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78c64-168">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-169">A</span><span class="sxs-lookup"><span data-stu-id="78c64-169">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="78c64-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-171">두 번째 SIP 도메인을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="78c64-172">Lync Phone Edition, DNS SRV 레코드가 없는 클라이언트의 자동 로그온 및 엄격한 도메인 일치에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="78c64-173">모든 경우에 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78c64-174">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-175">A</span><span class="sxs-lookup"><span data-stu-id="78c64-175">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78c64-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-177">내부적으로 게시 된 전화 접속 회의에 대 한 단순 URL-프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 단순 URL 쿼리에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78c64-178">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-179">A</span><span class="sxs-lookup"><span data-stu-id="78c64-179">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78c64-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-181">내부적으로 게시 된 회의에 대 한 단순 URL-프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 단순 URL 쿼리에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78c64-182">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-183">A</span><span class="sxs-lookup"><span data-stu-id="78c64-183">A</span></span></p></td>
<td><p><span data-ttu-id="78c64-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78c64-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="78c64-185">관리자로</span><span class="sxs-lookup"><span data-stu-id="78c64-185">admin</span></span></p></td>
<td><p><span data-ttu-id="78c64-186">선택적 레코드, Lync Server 2013 제어판에 게시 된 내부-프런트 엔드 서버 (또는 설치 된 경우 디렉터)가 단순 URL 쿼리에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="78c64-187">도메인 이름 없이 호스트 이름만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="78c64-188">VIP = 하드웨어 부하 분산 장치의 가상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="78c64-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="78c64-189">프런트 엔드 풀에 대 한 DNS SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="78c64-189">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="78c64-190">위치</span><span class="sxs-lookup"><span data-stu-id="78c64-190">Location</span></span></th>
<th><span data-ttu-id="78c64-191">타이핑</span><span class="sxs-lookup"><span data-stu-id="78c64-191">Type</span></span></th>
<th><span data-ttu-id="78c64-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="78c64-192">FQDN</span></span></th>
<th><span data-ttu-id="78c64-193">대상 FQDN</span><span class="sxs-lookup"><span data-stu-id="78c64-193">Target FQDN</span></span></th>
<th><span data-ttu-id="78c64-194">포트</span><span class="sxs-lookup"><span data-stu-id="78c64-194">Port</span></span></th>
<th><span data-ttu-id="78c64-195">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="78c64-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78c64-196">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-197">SRV</span><span class="sxs-lookup"><span data-stu-id="78c64-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="78c64-198">_sipinternaltls _sipinternaltls._tcp</span><span class="sxs-lookup"><span data-stu-id="78c64-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78c64-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-200">5061</span><span class="sxs-lookup"><span data-stu-id="78c64-200">5061</span></span></p></td>
<td><p><span data-ttu-id="78c64-201">내부적으로 작동 하도록 Lync 2013 클라이언트를 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78c64-202">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-203">SRV</span><span class="sxs-lookup"><span data-stu-id="78c64-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="78c64-204">_sipinternaltls _sipinternaltls._tcp</span><span class="sxs-lookup"><span data-stu-id="78c64-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="78c64-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-206">5061</span><span class="sxs-lookup"><span data-stu-id="78c64-206">5061</span></span></p></td>
<td><p><span data-ttu-id="78c64-207">내부적으로 작동 하도록 Lync 2013 클라이언트를 자동으로 구성 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78c64-208">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="78c64-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="78c64-209">SRV</span><span class="sxs-lookup"><span data-stu-id="78c64-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="78c64-210">_ntp _ntp._udp</span><span class="sxs-lookup"><span data-stu-id="78c64-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78c64-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="78c64-212">123</span><span class="sxs-lookup"><span data-stu-id="78c64-212">123</span></span></p></td>
<td><p><span data-ttu-id="78c64-213">Lync Phone Edition을 실행 하는 장치에 필요한 NTP (네트워크 시간 프로토콜) 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="78c64-214">내부적으로 도메인 컨트롤러를 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="78c64-215">도메인 컨트롤러가 정의되어 있지 않은 경우에는 NTP 서버 time.windows.com을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78c64-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

