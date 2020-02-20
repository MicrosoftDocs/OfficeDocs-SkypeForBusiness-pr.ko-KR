---
title: Lync Server 2013 IPsec 예외
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="c0681-102">Lync Server 2013의 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="c0681-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0681-103">_**마지막으로 수정 된 항목:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="c0681-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="c0681-104">IPsec (인터넷 프로토콜 보안) (IETF RFC 4301-4309 참조)이 배포 된 엔터프라이즈 네트워크의 경우에는 오디오, 비디오 및 파노라마 비디오를 배달 하는 데 사용 되는 포트 범위에서 IPsec을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0681-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="c0681-105">권장 사항은 IPsec 협상으로 인 한 미디어 포트 할당의 지연을 방지 해야 하는 경우에의 동기입니다.</span><span class="sxs-lookup"><span data-stu-id="c0681-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="c0681-106">다음 표에서는 권장 되는 IPsec 예외 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0681-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="c0681-107">권장 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="c0681-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="c0681-108">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="c0681-108">Rule name</span></span></th>
<th><span data-ttu-id="c0681-109">원본 IP</span><span class="sxs-lookup"><span data-stu-id="c0681-109">Source IP</span></span></th>
<th><span data-ttu-id="c0681-110">대상 IP</span><span class="sxs-lookup"><span data-stu-id="c0681-110">Destination IP</span></span></th>
<th><span data-ttu-id="c0681-111">프로토콜로</span><span class="sxs-lookup"><span data-stu-id="c0681-111">Protocol</span></span></th>
<th><span data-ttu-id="c0681-112">원본 포트</span><span class="sxs-lookup"><span data-stu-id="c0681-112">Source port</span></span></th>
<th><span data-ttu-id="c0681-113">대상 포트</span><span class="sxs-lookup"><span data-stu-id="c0681-113">Destination port</span></span></th>
<th><span data-ttu-id="c0681-114">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c0681-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0681-115">A/V에 지 서버 내부 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-116">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-116">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-117">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="c0681-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="c0681-118">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-119">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-119">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-120">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-120">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-121">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-122">A/V에 지 서버 외부 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-123">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-123">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-124">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="c0681-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="c0681-125">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-126">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-126">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-127">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-127">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-128">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-129">A/V에 지 서버 내부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-130">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="c0681-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="c0681-131">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-133">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-133">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-134">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-134">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-135">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-136">A/V에 지 서버 외부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-137">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="c0681-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="c0681-138">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-138">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-139">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-140">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-140">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-141">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-141">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-142">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-143">중재 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-144">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-144">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-145">중재</span><span class="sxs-lookup"><span data-stu-id="c0681-145">Mediation</span></span></p>
<p><span data-ttu-id="c0681-146">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="c0681-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="c0681-147">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-148">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-148">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-149">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-149">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-150">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-151">중재 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-152">중재</span><span class="sxs-lookup"><span data-stu-id="c0681-152">Mediation</span></span></p>
<p><span data-ttu-id="c0681-153">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="c0681-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="c0681-154">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-154">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-155">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-156">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-156">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-157">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-157">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-158">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-159">회의 전화 교환 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-160">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-160">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-161">회의 전화 교환을 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="c0681-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="c0681-162">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-163">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-163">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-164">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-164">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-165">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-166">회의 전화 교환 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-167">회의 전화 교환을 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="c0681-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="c0681-168">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-168">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-169">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-170">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-170">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-171">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-171">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-172">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-173">A/V 회의 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-174">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-174">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-175">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="c0681-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="c0681-176">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-177">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-177">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-178">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-178">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-179">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-180">A/V 회의 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-181">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="c0681-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="c0681-182">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-182">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-183">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-184">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-184">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-185">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-185">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-186">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-187">Exchange 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-188">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-188">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-189">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="c0681-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="c0681-190">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-191">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-191">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-192">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-192">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-193">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-194">응용 프로그램 공유 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-195">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-195">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-196">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="c0681-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="c0681-197">TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-198">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-198">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-199">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-199">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-200">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-201">응용 프로그램 공유 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-202">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="c0681-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="c0681-203">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-203">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-204">TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-205">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-205">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-206">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-206">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-207">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0681-208">Exchange 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="c0681-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="c0681-209">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="c0681-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="c0681-210">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-210">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-211">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="c0681-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="c0681-212">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-212">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-213">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-213">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-214">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0681-215">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c0681-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="c0681-216">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-216">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-217">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-217">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-218">P</span><span class="sxs-lookup"><span data-stu-id="c0681-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="c0681-219">지정 된 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="c0681-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="c0681-220">모두</span><span class="sxs-lookup"><span data-stu-id="c0681-220">Any</span></span></p></td>
<td><p><span data-ttu-id="c0681-221">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="c0681-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

