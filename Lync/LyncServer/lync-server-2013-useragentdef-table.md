---
title: 'Lync Server 2013: UserAgentDef 테이블'
description: 'Lync Server 2013: UserAgentDef 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b12239d0d6ba6e04a708708a1740dbf02c0e07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548644"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="751f8-103">Lync Server 2013의 UserAgentDef 테이블</span><span class="sxs-lookup"><span data-stu-id="751f8-103">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="751f8-104">_**마지막으로 수정 된 항목:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="751f8-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="751f8-105">UserAgentDef 테이블은 사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="751f8-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="751f8-106">사용자 에이전트는 Microsoft Lync Server 2013에 연결 하는 데 사용 되는 소프트웨어 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="751f8-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="751f8-107">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="751f8-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="751f8-108">UAType</span><span class="sxs-lookup"><span data-stu-id="751f8-108">UAType</span></span></th>
<th><span data-ttu-id="751f8-109">UAName</span><span class="sxs-lookup"><span data-stu-id="751f8-109">UAName</span></span></th>
<th><span data-ttu-id="751f8-110">UACategory</span><span class="sxs-lookup"><span data-stu-id="751f8-110">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="751f8-111">1 </span><span class="sxs-lookup"><span data-stu-id="751f8-111">1</span></span></p></td>
<td><p><span data-ttu-id="751f8-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="751f8-112">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="751f8-113">MediationServer</span><span class="sxs-lookup"><span data-stu-id="751f8-113">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-114">2</span><span class="sxs-lookup"><span data-stu-id="751f8-114">2</span></span></p></td>
<td><p><span data-ttu-id="751f8-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="751f8-115">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="751f8-116">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="751f8-116">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-117">4 </span><span class="sxs-lookup"><span data-stu-id="751f8-117">4</span></span></p></td>
<td><p><span data-ttu-id="751f8-118">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="751f8-118">OC</span></span></p></td>
<td><p><span data-ttu-id="751f8-119">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="751f8-119">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-120">8 </span><span class="sxs-lookup"><span data-stu-id="751f8-120">8</span></span></p></td>
<td><p><span data-ttu-id="751f8-121">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="751f8-121">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="751f8-122">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="751f8-122">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-123">16 </span><span class="sxs-lookup"><span data-stu-id="751f8-123">16</span></span></p></td>
<td><p><span data-ttu-id="751f8-124">LMC</span><span class="sxs-lookup"><span data-stu-id="751f8-124">LMC</span></span></p></td>
<td><p><span data-ttu-id="751f8-125">LMC</span><span class="sxs-lookup"><span data-stu-id="751f8-125">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-126">32</span><span class="sxs-lookup"><span data-stu-id="751f8-126">32</span></span></p></td>
<td><p><span data-ttu-id="751f8-127">DVT</span><span class="sxs-lookup"><span data-stu-id="751f8-127">DVT</span></span></p></td>
<td><p><span data-ttu-id="751f8-128">DVT</span><span class="sxs-lookup"><span data-stu-id="751f8-128">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-129">64</span><span class="sxs-lookup"><span data-stu-id="751f8-129">64</span></span></p></td>
<td><p><span data-ttu-id="751f8-130">19</span><span class="sxs-lookup"><span data-stu-id="751f8-130">MM</span></span></p></td>
<td><p><span data-ttu-id="751f8-131">19</span><span class="sxs-lookup"><span data-stu-id="751f8-131">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-132">64</span><span class="sxs-lookup"><span data-stu-id="751f8-132">64</span></span></p></td>
<td><p><span data-ttu-id="751f8-133">MC</span><span class="sxs-lookup"><span data-stu-id="751f8-133">MC</span></span></p></td>
<td><p><span data-ttu-id="751f8-134">19</span><span class="sxs-lookup"><span data-stu-id="751f8-134">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-135">128</span><span class="sxs-lookup"><span data-stu-id="751f8-135">128</span></span></p></td>
<td><p><span data-ttu-id="751f8-136">도우미</span><span class="sxs-lookup"><span data-stu-id="751f8-136">Attendant</span></span></p></td>
<td><p><span data-ttu-id="751f8-137">도우미</span><span class="sxs-lookup"><span data-stu-id="751f8-137">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-138">256</span><span class="sxs-lookup"><span data-stu-id="751f8-138">256</span></span></p></td>
<td><p><span data-ttu-id="751f8-139">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="751f8-139">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="751f8-140">인증</span><span class="sxs-lookup"><span data-stu-id="751f8-140">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-141">512</span><span class="sxs-lookup"><span data-stu-id="751f8-141">512</span></span></p></td>
<td><p><span data-ttu-id="751f8-142">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="751f8-142">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="751f8-143">CAA</span><span class="sxs-lookup"><span data-stu-id="751f8-143">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-144">512</span><span class="sxs-lookup"><span data-stu-id="751f8-144">512</span></span></p></td>
<td><p><span data-ttu-id="751f8-145">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="751f8-145">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="751f8-146">CAA</span><span class="sxs-lookup"><span data-stu-id="751f8-146">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-147">1024</span><span class="sxs-lookup"><span data-stu-id="751f8-147">1024</span></span></p></td>
<td><p><span data-ttu-id="751f8-148">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="751f8-148">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="751f8-149">컴파일하지</span><span class="sxs-lookup"><span data-stu-id="751f8-149">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-150">1032</span><span class="sxs-lookup"><span data-stu-id="751f8-150">1032</span></span></p></td>
<td><p><span data-ttu-id="751f8-151">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="751f8-151">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="751f8-152">CPS</span><span class="sxs-lookup"><span data-stu-id="751f8-152">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-153">1040</span><span class="sxs-lookup"><span data-stu-id="751f8-153">1040</span></span></p></td>
<td><p><span data-ttu-id="751f8-154">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="751f8-154">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="751f8-155">에</span><span class="sxs-lookup"><span data-stu-id="751f8-155">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-156">2048</span><span class="sxs-lookup"><span data-stu-id="751f8-156">2048</span></span></p></td>
<td><p><span data-ttu-id="751f8-157">Microsoft Rtc. Ccs</span><span class="sxs-lookup"><span data-stu-id="751f8-157">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="751f8-158">CCS</span><span class="sxs-lookup"><span data-stu-id="751f8-158">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-159">16386</span><span class="sxs-lookup"><span data-stu-id="751f8-159">16386</span></span></p></td>
<td><p><span data-ttu-id="751f8-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="751f8-160">CoMo</span></span></p></td>
<td><p><span data-ttu-id="751f8-161">CoMo</span><span class="sxs-lookup"><span data-stu-id="751f8-161">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-162">16387</span><span class="sxs-lookup"><span data-stu-id="751f8-162">16387</span></span></p></td>
<td><p><span data-ttu-id="751f8-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="751f8-163">CWA</span></span></p></td>
<td><p><span data-ttu-id="751f8-164">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="751f8-164">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-165">16388</span><span class="sxs-lookup"><span data-stu-id="751f8-165">16388</span></span></p></td>
<td><p><span data-ttu-id="751f8-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="751f8-166">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="751f8-167">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="751f8-167">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-168">16389</span><span class="sxs-lookup"><span data-stu-id="751f8-168">16389</span></span></p></td>
<td><p><span data-ttu-id="751f8-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="751f8-169">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="751f8-170">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="751f8-170">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-171">16393</span><span class="sxs-lookup"><span data-stu-id="751f8-171">16393</span></span></p></td>
<td><p><span data-ttu-id="751f8-172">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="751f8-172">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="751f8-173">ExUM</span><span class="sxs-lookup"><span data-stu-id="751f8-173">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-174">16395</span><span class="sxs-lookup"><span data-stu-id="751f8-174">16395</span></span></p></td>
<td><p><span data-ttu-id="751f8-175">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="751f8-175">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="751f8-176">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="751f8-176">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-177">16396</span><span class="sxs-lookup"><span data-stu-id="751f8-177">16396</span></span></p></td>
<td><p><span data-ttu-id="751f8-178">ST</span><span class="sxs-lookup"><span data-stu-id="751f8-178">ST</span></span></p></td>
<td><p><span data-ttu-id="751f8-179">ST</span><span class="sxs-lookup"><span data-stu-id="751f8-179">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-180">16397</span><span class="sxs-lookup"><span data-stu-id="751f8-180">16397</span></span></p></td>
<td><p><span data-ttu-id="751f8-181">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="751f8-181">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="751f8-182">ASMCU</span><span class="sxs-lookup"><span data-stu-id="751f8-182">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-183">16398</span><span class="sxs-lookup"><span data-stu-id="751f8-183">16398</span></span></p></td>
<td><p><span data-ttu-id="751f8-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="751f8-184">WPLync</span></span></p></td>
<td><p><span data-ttu-id="751f8-185">WPLync</span><span class="sxs-lookup"><span data-stu-id="751f8-185">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-186">16399</span><span class="sxs-lookup"><span data-stu-id="751f8-186">16399</span></span></p></td>
<td><p><span data-ttu-id="751f8-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="751f8-187">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="751f8-188">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="751f8-188">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-189">16400</span><span class="sxs-lookup"><span data-stu-id="751f8-189">16400</span></span></p></td>
<td><p><span data-ttu-id="751f8-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="751f8-190">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="751f8-191">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="751f8-191">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-192">16401</span><span class="sxs-lookup"><span data-stu-id="751f8-192">16401</span></span></p></td>
<td><p><span data-ttu-id="751f8-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="751f8-193">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="751f8-194">iPadLync</span><span class="sxs-lookup"><span data-stu-id="751f8-194">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-195">16402</span><span class="sxs-lookup"><span data-stu-id="751f8-195">16402</span></span></p></td>
<td><p><span data-ttu-id="751f8-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="751f8-196">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="751f8-197">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="751f8-197">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-198">16403</span><span class="sxs-lookup"><span data-stu-id="751f8-198">16403</span></span></p></td>
<td><p><span data-ttu-id="751f8-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="751f8-199">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="751f8-200">LyncImm</span><span class="sxs-lookup"><span data-stu-id="751f8-200">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-201">16404</span><span class="sxs-lookup"><span data-stu-id="751f8-201">16404</span></span></p></td>
<td><p><span data-ttu-id="751f8-202">PC</span><span class="sxs-lookup"><span data-stu-id="751f8-202">PCS</span></span></p></td>
<td><p><span data-ttu-id="751f8-203">PC</span><span class="sxs-lookup"><span data-stu-id="751f8-203">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-204">16405</span><span class="sxs-lookup"><span data-stu-id="751f8-204">16405</span></span></p></td>
<td><p><span data-ttu-id="751f8-205">LWA</span><span class="sxs-lookup"><span data-stu-id="751f8-205">LWA</span></span></p></td>
<td><p><span data-ttu-id="751f8-206">LWA</span><span class="sxs-lookup"><span data-stu-id="751f8-206">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-207">16406</span><span class="sxs-lookup"><span data-stu-id="751f8-207">16406</span></span></p></td>
<td><p><span data-ttu-id="751f8-208">OWA</span><span class="sxs-lookup"><span data-stu-id="751f8-208">OWA</span></span></p></td>
<td><p><span data-ttu-id="751f8-209">OWA</span><span class="sxs-lookup"><span data-stu-id="751f8-209">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-210">16407</span><span class="sxs-lookup"><span data-stu-id="751f8-210">16407</span></span></p></td>
<td><p><span data-ttu-id="751f8-211">AOC</span><span class="sxs-lookup"><span data-stu-id="751f8-211">AOC</span></span></p></td>
<td><p><span data-ttu-id="751f8-212">AOC</span><span class="sxs-lookup"><span data-stu-id="751f8-212">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-213">16408</span><span class="sxs-lookup"><span data-stu-id="751f8-213">16408</span></span></p></td>
<td><p><span data-ttu-id="751f8-214">GCC</span><span class="sxs-lookup"><span data-stu-id="751f8-214">GCC</span></span></p></td>
<td><p><span data-ttu-id="751f8-215">GCC</span><span class="sxs-lookup"><span data-stu-id="751f8-215">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-216">16409</span><span class="sxs-lookup"><span data-stu-id="751f8-216">16409</span></span></p></td>
<td><p><span data-ttu-id="751f8-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="751f8-217">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="751f8-218">IMMCU</span><span class="sxs-lookup"><span data-stu-id="751f8-218">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-219">16410</span><span class="sxs-lookup"><span data-stu-id="751f8-219">16410</span></span></p></td>
<td><p><span data-ttu-id="751f8-220">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="751f8-220">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="751f8-221">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="751f8-221">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751f8-222">32769</span><span class="sxs-lookup"><span data-stu-id="751f8-222">32769</span></span></p></td>
<td><p><span data-ttu-id="751f8-223">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="751f8-223">Gateway</span></span></p></td>
<td><p><span data-ttu-id="751f8-224">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="751f8-224">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751f8-225">32770</span><span class="sxs-lookup"><span data-stu-id="751f8-225">32770</span></span></p></td>
<td><p><span data-ttu-id="751f8-226">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="751f8-226">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="751f8-227">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="751f8-227">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

