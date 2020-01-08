---
title: Lync Server 2013 IPsec 예외
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="4bbf9-102">Lync Server 2013의 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="4bbf9-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bbf9-103">_**마지막으로 수정한 주제:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="4bbf9-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="4bbf9-104">IPsec (인터넷 프로토콜 보안) (IETF RFC 4301-4309 참조)이 배포 된 엔터프라이즈 네트워크의 경우 오디오, 비디오, 파노라마 비디오를 제공 하는 데 사용 되는 포트 범위에 대해 IPsec을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf9-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="4bbf9-105">권장 사항은 IPsec 협상으로 인해 미디어 포트를 할당할 때 지연 되지 않도록 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf9-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="4bbf9-106">다음 표에서는 권장 IPsec 예외 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbf9-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="4bbf9-107">권장 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="4bbf9-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bbf9-108">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="4bbf9-108">Rule name</span></span></th>
<th><span data-ttu-id="4bbf9-109">원본 IP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-109">Source IP</span></span></th>
<th><span data-ttu-id="4bbf9-110">대상 IP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-110">Destination IP</span></span></th>
<th><span data-ttu-id="4bbf9-111">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="4bbf9-111">Protocol</span></span></th>
<th><span data-ttu-id="4bbf9-112">원본 포트</span><span class="sxs-lookup"><span data-stu-id="4bbf9-112">Source port</span></span></th>
<th><span data-ttu-id="4bbf9-113">대상 포트</span><span class="sxs-lookup"><span data-stu-id="4bbf9-113">Destination port</span></span></th>
<th><span data-ttu-id="4bbf9-114">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4bbf9-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-115">A/V Edge 서버 내부 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-116">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-116">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-117">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="4bbf9-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-118">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-119">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-119">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-120">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-120">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-121">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-122">A/V Edge 서버 외부 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-123">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-123">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-124">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="4bbf9-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-125">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-126">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-126">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-127">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-127">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-128">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-129">A/V Edge 서버 내부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-130">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="4bbf9-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-131">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-131">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-133">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-133">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-134">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-134">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-135">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-136">A/V Edge 서버 외부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-137">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="4bbf9-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-138">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-139">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-140">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-140">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-141">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-141">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-142">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-143">중재 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-144">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-144">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-145">중재</span><span class="sxs-lookup"><span data-stu-id="4bbf9-145">Mediation</span></span></p>
<p><span data-ttu-id="4bbf9-146">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="4bbf9-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-147">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-148">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-148">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-149">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-149">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-150">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-151">중재 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-152">중재</span><span class="sxs-lookup"><span data-stu-id="4bbf9-152">Mediation</span></span></p>
<p><span data-ttu-id="4bbf9-153">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="4bbf9-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-154">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-154">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-155">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-156">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-156">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-157">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-157">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-158">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-159">회의 전화 교환 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-160">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-160">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-161">회의 수행자를 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="4bbf9-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-162">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-163">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-163">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-164">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-164">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-165">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-166">회의 전화 교환 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-167">회의 수행자를 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="4bbf9-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-168">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-168">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-169">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-170">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-170">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-171">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-171">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-172">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-173">A/V 회의 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-174">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-174">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-175">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="4bbf9-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-176">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-177">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-177">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-178">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-178">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-179">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-180">A/V 회의 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-181">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="4bbf9-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-182">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-182">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-183">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-184">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-184">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-185">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-185">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-186">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-187">Exchange 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-188">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-188">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-189">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="4bbf9-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-190">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-191">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-191">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-192">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-192">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-193">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-194">응용 프로그램 공유 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-195">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-195">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-196">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="4bbf9-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-197">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-198">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-198">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-199">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-199">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-200">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-201">응용 프로그램 공유 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-202">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="4bbf9-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-203">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-203">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-204">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-205">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-205">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-206">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-206">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-207">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bbf9-208">Exchange 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="4bbf9-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-209">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="4bbf9-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-210">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-210">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-211">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-212">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-212">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-213">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-213">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-214">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bbf9-215">클라이언트</span><span class="sxs-lookup"><span data-stu-id="4bbf9-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-216">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-216">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-217">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-217">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-218">UDP</span><span class="sxs-lookup"><span data-stu-id="4bbf9-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-219">지정 된 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="4bbf9-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-220">이상</span><span class="sxs-lookup"><span data-stu-id="4bbf9-220">Any</span></span></p></td>
<td><p><span data-ttu-id="4bbf9-221">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="4bbf9-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

