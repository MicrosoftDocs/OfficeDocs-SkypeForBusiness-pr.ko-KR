---
title: Lync Server 2013 IPsec 예외
description: Lync Server 2013 IPsec 예외
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
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575004"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="9b8b0-103">Lync Server 2013의 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="9b8b0-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b8b0-104">_**마지막으로 수정 된 항목:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="9b8b0-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="9b8b0-105">IPsec (인터넷 프로토콜 보안) (IETF RFC 4301-4309 참조)이 배포 된 엔터프라이즈 네트워크의 경우에는 오디오, 비디오 및 파노라마 비디오를 배달 하는 데 사용 되는 포트 범위에서 IPsec을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8b0-105">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="9b8b0-106">권장 사항은 IPsec 협상으로 인 한 미디어 포트 할당의 지연을 방지 해야 하는 경우에의 동기입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8b0-106">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="9b8b0-107">다음 표에서는 권장 되는 IPsec 예외 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8b0-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="9b8b0-108">권장 IPsec 예외</span><span class="sxs-lookup"><span data-stu-id="9b8b0-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="9b8b0-109">규칙 이름</span><span class="sxs-lookup"><span data-stu-id="9b8b0-109">Rule name</span></span></th>
<th><span data-ttu-id="9b8b0-110">원본 IP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-110">Source IP</span></span></th>
<th><span data-ttu-id="9b8b0-111">대상 IP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-111">Destination IP</span></span></th>
<th><span data-ttu-id="9b8b0-112">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="9b8b0-112">Protocol</span></span></th>
<th><span data-ttu-id="9b8b0-113">원본 포트</span><span class="sxs-lookup"><span data-stu-id="9b8b0-113">Source port</span></span></th>
<th><span data-ttu-id="9b8b0-114">대상 포트</span><span class="sxs-lookup"><span data-stu-id="9b8b0-114">Destination port</span></span></th>
<th><span data-ttu-id="9b8b0-115">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b8b0-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-116">A/V에 지 서버 내부 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-117">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-117">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-118">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="9b8b0-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-119">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-120">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-120">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-121">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-121">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-122">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-123">A/V에 지 서버 외부 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-124">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-124">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-125">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="9b8b0-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-126">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-127">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-127">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-128">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-128">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-129">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-130">A/V에 지 서버 내부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-131">A/V에 지 서버 내부</span><span class="sxs-lookup"><span data-stu-id="9b8b0-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-132">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-132">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-133">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-134">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-135">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-135">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-136">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-137">A/V에 지 서버 외부 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-138">A/V에 지 서버 외부</span><span class="sxs-lookup"><span data-stu-id="9b8b0-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-139">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-139">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-140">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-141">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-142">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-142">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-143">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-144">중재 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-145">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-145">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-146">중재</span><span class="sxs-lookup"><span data-stu-id="9b8b0-146">Mediation</span></span></p>
<p><span data-ttu-id="9b8b0-147">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="9b8b0-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-148">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-149">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-149">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-150">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-150">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-151">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-152">중재 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-153">중재</span><span class="sxs-lookup"><span data-stu-id="9b8b0-153">Mediation</span></span></p>
<p><span data-ttu-id="9b8b0-154">서버 (s)</span><span class="sxs-lookup"><span data-stu-id="9b8b0-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-155">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-155">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-156">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-157">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-157">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-158">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-158">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-159">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-160">회의 전화 교환 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-161">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-161">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-162">회의 전화 교환을 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="9b8b0-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-163">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-164">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-164">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-165">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-165">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-166">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-167">회의 전화 교환 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-168">회의 전화 교환을 실행 하는 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="9b8b0-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-169">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-169">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-170">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-171">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-171">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-172">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-172">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-173">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-174">A/V 회의 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-175">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-175">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-176">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="9b8b0-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-177">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-178">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-179">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-179">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-180">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-181">A/V 회의 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-182">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="9b8b0-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-183">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-183">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-184">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-185">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-185">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-186">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-186">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-187">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-188">Exchange 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-189">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-189">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-190">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="9b8b0-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-191">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-192">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-192">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-193">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-193">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-194">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-195">응용 프로그램 공유 서버 인바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-196">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-196">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-197">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="9b8b0-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-198">TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-199">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-199">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-200">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-200">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-201">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-202">응용 프로그램 공유 서버 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-203">응용 프로그램 공유 서버</span><span class="sxs-lookup"><span data-stu-id="9b8b0-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-204">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-204">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-205">TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-206">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-206">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-207">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-207">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-208">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b8b0-209">Exchange 아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="9b8b0-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-210">Exchange 통합 메시징</span><span class="sxs-lookup"><span data-stu-id="9b8b0-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-211">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-211">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-212">UDP 및 TCP</span><span class="sxs-lookup"><span data-stu-id="9b8b0-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-213">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-213">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-214">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-214">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-215">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b8b0-216">클라이언트</span><span class="sxs-lookup"><span data-stu-id="9b8b0-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-217">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-217">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-218">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-218">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-219">P</span><span class="sxs-lookup"><span data-stu-id="9b8b0-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-220">지정 된 미디어 포트 범위</span><span class="sxs-lookup"><span data-stu-id="9b8b0-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-221">모두</span><span class="sxs-lookup"><span data-stu-id="9b8b0-221">Any</span></span></p></td>
<td><p><span data-ttu-id="9b8b0-222">인증 안 함</span><span class="sxs-lookup"><span data-stu-id="9b8b0-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

