---
title: 'Lync Server 2013: UserAgentDef 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b378b6d71bb5163d1d2d2e9146cf3877c0d38a19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="b2858-102">Lync Server 2013의 UserAgentDef 테이블</span><span class="sxs-lookup"><span data-stu-id="b2858-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2858-103">_**마지막으로 수정한 주제:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="b2858-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="b2858-104">UserAgentDef 테이블은 사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b2858-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="b2858-105">사용자 에이전트는 Microsoft Lync Server 2013에 연결 하는 데 사용 되는 소프트웨어 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="b2858-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b2858-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2858-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2858-107">UAType</span><span class="sxs-lookup"><span data-stu-id="b2858-107">UAType</span></span></th>
<th><span data-ttu-id="b2858-108">UAName</span><span class="sxs-lookup"><span data-stu-id="b2858-108">UAName</span></span></th>
<th><span data-ttu-id="b2858-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="b2858-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2858-110">1</span><span class="sxs-lookup"><span data-stu-id="b2858-110">1</span></span></p></td>
<td><p><span data-ttu-id="b2858-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="b2858-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="b2858-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="b2858-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-113">2</span><span class="sxs-lookup"><span data-stu-id="b2858-113">2</span></span></p></td>
<td><p><span data-ttu-id="b2858-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="b2858-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="b2858-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="b2858-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-116">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="b2858-116">4</span></span></p></td>
<td><p><span data-ttu-id="b2858-117">OC</span><span class="sxs-lookup"><span data-stu-id="b2858-117">OC</span></span></p></td>
<td><p><span data-ttu-id="b2858-118">OC</span><span class="sxs-lookup"><span data-stu-id="b2858-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-119">20cm(8</span><span class="sxs-lookup"><span data-stu-id="b2858-119">8</span></span></p></td>
<td><p><span data-ttu-id="b2858-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="b2858-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="b2858-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="b2858-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-122">16</span><span class="sxs-lookup"><span data-stu-id="b2858-122">16</span></span></p></td>
<td><p><span data-ttu-id="b2858-123">LMC</span><span class="sxs-lookup"><span data-stu-id="b2858-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="b2858-124">LMC</span><span class="sxs-lookup"><span data-stu-id="b2858-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-125">32</span><span class="sxs-lookup"><span data-stu-id="b2858-125">32</span></span></p></td>
<td><p><span data-ttu-id="b2858-126">DVT</span><span class="sxs-lookup"><span data-stu-id="b2858-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="b2858-127">DVT</span><span class="sxs-lookup"><span data-stu-id="b2858-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-128">64</span><span class="sxs-lookup"><span data-stu-id="b2858-128">64</span></span></p></td>
<td><p><span data-ttu-id="b2858-129">200</span><span class="sxs-lookup"><span data-stu-id="b2858-129">MM</span></span></p></td>
<td><p><span data-ttu-id="b2858-130">200</span><span class="sxs-lookup"><span data-stu-id="b2858-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-131">64</span><span class="sxs-lookup"><span data-stu-id="b2858-131">64</span></span></p></td>
<td><p><span data-ttu-id="b2858-132">MC</span><span class="sxs-lookup"><span data-stu-id="b2858-132">MC</span></span></p></td>
<td><p><span data-ttu-id="b2858-133">200</span><span class="sxs-lookup"><span data-stu-id="b2858-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-134">128</span><span class="sxs-lookup"><span data-stu-id="b2858-134">128</span></span></p></td>
<td><p><span data-ttu-id="b2858-135">리소스만</span><span class="sxs-lookup"><span data-stu-id="b2858-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="b2858-136">리소스만</span><span class="sxs-lookup"><span data-stu-id="b2858-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-137">256</span><span class="sxs-lookup"><span data-stu-id="b2858-137">256</span></span></p></td>
<td><p><span data-ttu-id="b2858-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="b2858-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="b2858-139">이어지는</span><span class="sxs-lookup"><span data-stu-id="b2858-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-140">512</span><span class="sxs-lookup"><span data-stu-id="b2858-140">512</span></span></p></td>
<td><p><span data-ttu-id="b2858-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="b2858-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="b2858-142">CAA</span><span class="sxs-lookup"><span data-stu-id="b2858-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-143">512</span><span class="sxs-lookup"><span data-stu-id="b2858-143">512</span></span></p></td>
<td><p><span data-ttu-id="b2858-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="b2858-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="b2858-145">CAA</span><span class="sxs-lookup"><span data-stu-id="b2858-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-146">1024</span><span class="sxs-lookup"><span data-stu-id="b2858-146">1024</span></span></p></td>
<td><p><span data-ttu-id="b2858-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="b2858-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="b2858-148">RGS</span><span class="sxs-lookup"><span data-stu-id="b2858-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-149">1032</span><span class="sxs-lookup"><span data-stu-id="b2858-149">1032</span></span></p></td>
<td><p><span data-ttu-id="b2858-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="b2858-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="b2858-151">CPS</span><span class="sxs-lookup"><span data-stu-id="b2858-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-152">1040</span><span class="sxs-lookup"><span data-stu-id="b2858-152">1040</span></span></p></td>
<td><p><span data-ttu-id="b2858-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="b2858-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="b2858-154">문자열로</span><span class="sxs-lookup"><span data-stu-id="b2858-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-155">2048</span><span class="sxs-lookup"><span data-stu-id="b2858-155">2048</span></span></p></td>
<td><p><span data-ttu-id="b2858-156">Microsoft Rtc. Ccs</span><span class="sxs-lookup"><span data-stu-id="b2858-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="b2858-157">CCS</span><span class="sxs-lookup"><span data-stu-id="b2858-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-158">16386</span><span class="sxs-lookup"><span data-stu-id="b2858-158">16386</span></span></p></td>
<td><p><span data-ttu-id="b2858-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="b2858-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="b2858-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="b2858-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-161">16387</span><span class="sxs-lookup"><span data-stu-id="b2858-161">16387</span></span></p></td>
<td><p><span data-ttu-id="b2858-162">CWA</span><span class="sxs-lookup"><span data-stu-id="b2858-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="b2858-163">CWA</span><span class="sxs-lookup"><span data-stu-id="b2858-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-164">16388</span><span class="sxs-lookup"><span data-stu-id="b2858-164">16388</span></span></p></td>
<td><p><span data-ttu-id="b2858-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="b2858-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="b2858-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="b2858-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-167">16389</span><span class="sxs-lookup"><span data-stu-id="b2858-167">16389</span></span></p></td>
<td><p><span data-ttu-id="b2858-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="b2858-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="b2858-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="b2858-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-170">16393</span><span class="sxs-lookup"><span data-stu-id="b2858-170">16393</span></span></p></td>
<td><p><span data-ttu-id="b2858-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="b2858-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="b2858-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="b2858-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-173">16395</span><span class="sxs-lookup"><span data-stu-id="b2858-173">16395</span></span></p></td>
<td><p><span data-ttu-id="b2858-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="b2858-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="b2858-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="b2858-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-176">16396</span><span class="sxs-lookup"><span data-stu-id="b2858-176">16396</span></span></p></td>
<td><p><span data-ttu-id="b2858-177">ST</span><span class="sxs-lookup"><span data-stu-id="b2858-177">ST</span></span></p></td>
<td><p><span data-ttu-id="b2858-178">ST</span><span class="sxs-lookup"><span data-stu-id="b2858-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-179">16397</span><span class="sxs-lookup"><span data-stu-id="b2858-179">16397</span></span></p></td>
<td><p><span data-ttu-id="b2858-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="b2858-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="b2858-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="b2858-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-182">16398</span><span class="sxs-lookup"><span data-stu-id="b2858-182">16398</span></span></p></td>
<td><p><span data-ttu-id="b2858-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="b2858-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="b2858-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="b2858-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-185">16399</span><span class="sxs-lookup"><span data-stu-id="b2858-185">16399</span></span></p></td>
<td><p><span data-ttu-id="b2858-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="b2858-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="b2858-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="b2858-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-188">16400</span><span class="sxs-lookup"><span data-stu-id="b2858-188">16400</span></span></p></td>
<td><p><span data-ttu-id="b2858-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="b2858-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="b2858-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="b2858-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-191">16401</span><span class="sxs-lookup"><span data-stu-id="b2858-191">16401</span></span></p></td>
<td><p><span data-ttu-id="b2858-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="b2858-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="b2858-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="b2858-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-194">16402</span><span class="sxs-lookup"><span data-stu-id="b2858-194">16402</span></span></p></td>
<td><p><span data-ttu-id="b2858-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="b2858-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="b2858-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="b2858-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-197">16403</span><span class="sxs-lookup"><span data-stu-id="b2858-197">16403</span></span></p></td>
<td><p><span data-ttu-id="b2858-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="b2858-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="b2858-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="b2858-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-200">16404</span><span class="sxs-lookup"><span data-stu-id="b2858-200">16404</span></span></p></td>
<td><p><span data-ttu-id="b2858-201">플레이어</span><span class="sxs-lookup"><span data-stu-id="b2858-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="b2858-202">플레이어</span><span class="sxs-lookup"><span data-stu-id="b2858-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-203">16405</span><span class="sxs-lookup"><span data-stu-id="b2858-203">16405</span></span></p></td>
<td><p><span data-ttu-id="b2858-204">LWA</span><span class="sxs-lookup"><span data-stu-id="b2858-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="b2858-205">LWA</span><span class="sxs-lookup"><span data-stu-id="b2858-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-206">16406</span><span class="sxs-lookup"><span data-stu-id="b2858-206">16406</span></span></p></td>
<td><p><span data-ttu-id="b2858-207">OWA</span><span class="sxs-lookup"><span data-stu-id="b2858-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="b2858-208">OWA</span><span class="sxs-lookup"><span data-stu-id="b2858-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-209">16407</span><span class="sxs-lookup"><span data-stu-id="b2858-209">16407</span></span></p></td>
<td><p><span data-ttu-id="b2858-210">AOC</span><span class="sxs-lookup"><span data-stu-id="b2858-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="b2858-211">AOC</span><span class="sxs-lookup"><span data-stu-id="b2858-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-212">16408</span><span class="sxs-lookup"><span data-stu-id="b2858-212">16408</span></span></p></td>
<td><p><span data-ttu-id="b2858-213">GCC</span><span class="sxs-lookup"><span data-stu-id="b2858-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="b2858-214">GCC</span><span class="sxs-lookup"><span data-stu-id="b2858-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-215">16409</span><span class="sxs-lookup"><span data-stu-id="b2858-215">16409</span></span></p></td>
<td><p><span data-ttu-id="b2858-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="b2858-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="b2858-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="b2858-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-218">16410</span><span class="sxs-lookup"><span data-stu-id="b2858-218">16410</span></span></p></td>
<td><p><span data-ttu-id="b2858-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="b2858-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="b2858-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="b2858-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2858-221">32769</span><span class="sxs-lookup"><span data-stu-id="b2858-221">32769</span></span></p></td>
<td><p><span data-ttu-id="b2858-222">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="b2858-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="b2858-223">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="b2858-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2858-224">32770</span><span class="sxs-lookup"><span data-stu-id="b2858-224">32770</span></span></p></td>
<td><p><span data-ttu-id="b2858-225">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="b2858-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="b2858-226">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="b2858-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

