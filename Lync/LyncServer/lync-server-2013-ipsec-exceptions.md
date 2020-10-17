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
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514155"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="d697f-102">Lync Server 2013의 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="d697f-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d697f-103">_**마지막으로 수정 된 항목:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="d697f-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="d697f-104">IPsec (인터넷 프로토콜 보안) (IETF RFC 4301-4309 참조)이 배포 된 엔터프라이즈 네트워크의 경우에는 오디오, 비디오 및 파노라마 비디오를 배달 하는 데 사용 되는 포트 범위에서 IPsec을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d697f-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="d697f-105">권장 사항은 IPsec 협상으로 인 한 미디어 포트 할당의 지연을 방지 해야 하는 경우에의 동기입니다.</span><span class="sxs-lookup"><span data-stu-id="d697f-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="d697f-106">다음 표에서는 권장 되는 IPsec 예외 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d697f-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="d697f-107">권장 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="d697f-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="d697f-108">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="d697f-108">Rule name</span></span></th>
<th><span data-ttu-id="d697f-109">원본 IP</span><span class="sxs-lookup"><span data-stu-id="d697f-109">Source IP</span></span></th>
<th><span data-ttu-id="d697f-110">대상 IP</span><span class="sxs-lookup"><span data-stu-id="d697f-110">Destination IP</span></span></th>
<th><span data-ttu-id="d697f-111">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="d697f-111">Protocol</span></span></th>
<th><span data-ttu-id="d697f-112">원본 포트</span><span class="sxs-lookup"><span data-stu-id="d697f-112">Source port</span></span></th>
<th><span data-ttu-id="d697f-113">대상 포트</span><span class="sxs-lookup"><span data-stu-id="d697f-113">Destination port</span></span></th>
<th><span data-ttu-id="d697f-114">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d697f-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d697f-115">A/V에 지 서버 내부 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-116">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-116">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-117">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="d697f-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="d697f-118">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-119">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-119">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-120">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-120">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-121">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-122">A/V에 지 서버 외부 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-123">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-123">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-124">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="d697f-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="d697f-125">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-126">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-126">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-127">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-127">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-128">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-129">A/V에 지 서버 내부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-130">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="d697f-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="d697f-131">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-131">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-133">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-133">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-134">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-134">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-135">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-136">A/V에 지 서버 외부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-137">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="d697f-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="d697f-138">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-138">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-139">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-140">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-140">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-141">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-141">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-142">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-143">중재 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-144">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-144">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-145">중재</span><span class="sxs-lookup"><span data-stu-id="d697f-145">Mediation</span></span></p>
<p><span data-ttu-id="d697f-146">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="d697f-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="d697f-147">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-148">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-148">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-149">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-149">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-150">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-151">중재 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-152">중재</span><span class="sxs-lookup"><span data-stu-id="d697f-152">Mediation</span></span></p>
<p><span data-ttu-id="d697f-153">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="d697f-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="d697f-154">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-154">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-155">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-156">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-156">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-157">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-157">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-158">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-159">회의 전화 교환 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-160">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-160">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-161">회의 전화 교환을 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="d697f-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="d697f-162">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-163">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-163">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-164">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-164">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-165">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-166">회의 전화 교환 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-167">회의 전화 교환을 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="d697f-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="d697f-168">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-168">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-169">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-170">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-170">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-171">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-171">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-172">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-173">A/V 회의 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-174">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-174">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-175">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="d697f-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d697f-176">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-177">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-177">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-178">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-178">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-179">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-180">A/V 회의 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-181">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="d697f-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="d697f-182">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-182">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-183">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-184">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-184">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-185">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-185">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-186">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-187">Exchange 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-188">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-188">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-189">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="d697f-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="d697f-190">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-191">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-191">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-192">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-192">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-193">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-194">응용 프로그램 공유 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-195">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-195">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-196">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="d697f-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="d697f-197">TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-198">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-198">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-199">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-199">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-200">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-201">응용 프로그램 공유 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-202">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="d697f-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="d697f-203">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-203">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-204">TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-205">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-205">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-206">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-206">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-207">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d697f-208">Exchange 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="d697f-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="d697f-209">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="d697f-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="d697f-210">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-210">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-211">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="d697f-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="d697f-212">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-212">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-213">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-213">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-214">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d697f-215">클라이언트</span><span class="sxs-lookup"><span data-stu-id="d697f-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="d697f-216">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-216">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-217">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-217">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-218">P</span><span class="sxs-lookup"><span data-stu-id="d697f-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="d697f-219">지정 된 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="d697f-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="d697f-220">모두</span><span class="sxs-lookup"><span data-stu-id="d697f-220">Any</span></span></p></td>
<td><p><span data-ttu-id="d697f-221">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="d697f-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

