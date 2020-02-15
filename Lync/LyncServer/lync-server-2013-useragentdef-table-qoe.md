---
title: 'Lync Server 2013: UserAgentDef 테이블 (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebddb1e0313d0c47acb4171929d12d352f69c260
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="fb04b-102">Lync Server 2013의 UserAgentDef 테이블 (QoE)</span><span class="sxs-lookup"><span data-stu-id="fb04b-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb04b-103">_**마지막으로 수정 된 항목:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="fb04b-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="fb04b-104">UserAgentDef 테이블은 사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fb04b-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="fb04b-105">사용자 에이전트는 Microsoft Lync Server 2013에 연결 하는 데 사용 되는 소프트웨어 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="fb04b-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb04b-106">UAType</span><span class="sxs-lookup"><span data-stu-id="fb04b-106">UAType</span></span></th>
<th><span data-ttu-id="fb04b-107">UAName</span><span class="sxs-lookup"><span data-stu-id="fb04b-107">UAName</span></span></th>
<th><span data-ttu-id="fb04b-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="fb04b-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-109">1 </span><span class="sxs-lookup"><span data-stu-id="fb04b-109">1</span></span></p></td>
<td><p><span data-ttu-id="fb04b-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="fb04b-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="fb04b-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="fb04b-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-112">2 </span><span class="sxs-lookup"><span data-stu-id="fb04b-112">2</span></span></p></td>
<td><p><span data-ttu-id="fb04b-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="fb04b-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="fb04b-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="fb04b-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-115">4 </span><span class="sxs-lookup"><span data-stu-id="fb04b-115">4</span></span></p></td>
<td><p><span data-ttu-id="fb04b-116">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="fb04b-116">OC</span></span></p></td>
<td><p><span data-ttu-id="fb04b-117">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="fb04b-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-118">8 </span><span class="sxs-lookup"><span data-stu-id="fb04b-118">8</span></span></p></td>
<td><p><span data-ttu-id="fb04b-119">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="fb04b-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="fb04b-120">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="fb04b-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-121">16 </span><span class="sxs-lookup"><span data-stu-id="fb04b-121">16</span></span></p></td>
<td><p><span data-ttu-id="fb04b-122">LMC</span><span class="sxs-lookup"><span data-stu-id="fb04b-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="fb04b-123">LMC</span><span class="sxs-lookup"><span data-stu-id="fb04b-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-124">32</span><span class="sxs-lookup"><span data-stu-id="fb04b-124">32</span></span></p></td>
<td><p><span data-ttu-id="fb04b-125">DVT</span><span class="sxs-lookup"><span data-stu-id="fb04b-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="fb04b-126">DVT</span><span class="sxs-lookup"><span data-stu-id="fb04b-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-127">64</span><span class="sxs-lookup"><span data-stu-id="fb04b-127">64</span></span></p></td>
<td><p><span data-ttu-id="fb04b-128">19</span><span class="sxs-lookup"><span data-stu-id="fb04b-128">MM</span></span></p></td>
<td><p><span data-ttu-id="fb04b-129">19</span><span class="sxs-lookup"><span data-stu-id="fb04b-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-130">64</span><span class="sxs-lookup"><span data-stu-id="fb04b-130">64</span></span></p></td>
<td><p><span data-ttu-id="fb04b-131">MC</span><span class="sxs-lookup"><span data-stu-id="fb04b-131">MC</span></span></p></td>
<td><p><span data-ttu-id="fb04b-132">19</span><span class="sxs-lookup"><span data-stu-id="fb04b-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-133">128</span><span class="sxs-lookup"><span data-stu-id="fb04b-133">128</span></span></p></td>
<td><p><span data-ttu-id="fb04b-134">교환</span><span class="sxs-lookup"><span data-stu-id="fb04b-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="fb04b-135">교환</span><span class="sxs-lookup"><span data-stu-id="fb04b-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-136">256</span><span class="sxs-lookup"><span data-stu-id="fb04b-136">256</span></span></p></td>
<td><p><span data-ttu-id="fb04b-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="fb04b-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="fb04b-138">인증</span><span class="sxs-lookup"><span data-stu-id="fb04b-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-139">512</span><span class="sxs-lookup"><span data-stu-id="fb04b-139">512</span></span></p></td>
<td><p><span data-ttu-id="fb04b-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="fb04b-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="fb04b-141">CAA</span><span class="sxs-lookup"><span data-stu-id="fb04b-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-142">512</span><span class="sxs-lookup"><span data-stu-id="fb04b-142">512</span></span></p></td>
<td><p><span data-ttu-id="fb04b-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="fb04b-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="fb04b-144">CAA</span><span class="sxs-lookup"><span data-stu-id="fb04b-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-145">1024</span><span class="sxs-lookup"><span data-stu-id="fb04b-145">1024</span></span></p></td>
<td><p><span data-ttu-id="fb04b-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="fb04b-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="fb04b-147">컴파일하지</span><span class="sxs-lookup"><span data-stu-id="fb04b-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-148">1032</span><span class="sxs-lookup"><span data-stu-id="fb04b-148">1032</span></span></p></td>
<td><p><span data-ttu-id="fb04b-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="fb04b-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="fb04b-150">CPS</span><span class="sxs-lookup"><span data-stu-id="fb04b-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-151">1040</span><span class="sxs-lookup"><span data-stu-id="fb04b-151">1040</span></span></p></td>
<td><p><span data-ttu-id="fb04b-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="fb04b-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="fb04b-153">에</span><span class="sxs-lookup"><span data-stu-id="fb04b-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-154">2048</span><span class="sxs-lookup"><span data-stu-id="fb04b-154">2048</span></span></p></td>
<td><p><span data-ttu-id="fb04b-155">Microsoft Rtc. Ccs</span><span class="sxs-lookup"><span data-stu-id="fb04b-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="fb04b-156">CCS</span><span class="sxs-lookup"><span data-stu-id="fb04b-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-157">16386</span><span class="sxs-lookup"><span data-stu-id="fb04b-157">16386</span></span></p></td>
<td><p><span data-ttu-id="fb04b-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="fb04b-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="fb04b-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="fb04b-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-160">16387</span><span class="sxs-lookup"><span data-stu-id="fb04b-160">16387</span></span></p></td>
<td><p><span data-ttu-id="fb04b-161">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="fb04b-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="fb04b-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="fb04b-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-163">16388</span><span class="sxs-lookup"><span data-stu-id="fb04b-163">16388</span></span></p></td>
<td><p><span data-ttu-id="fb04b-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="fb04b-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="fb04b-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="fb04b-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-166">16389</span><span class="sxs-lookup"><span data-stu-id="fb04b-166">16389</span></span></p></td>
<td><p><span data-ttu-id="fb04b-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="fb04b-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="fb04b-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="fb04b-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-169">16393</span><span class="sxs-lookup"><span data-stu-id="fb04b-169">16393</span></span></p></td>
<td><p><span data-ttu-id="fb04b-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="fb04b-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="fb04b-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="fb04b-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-172">16395</span><span class="sxs-lookup"><span data-stu-id="fb04b-172">16395</span></span></p></td>
<td><p><span data-ttu-id="fb04b-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="fb04b-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="fb04b-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="fb04b-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-175">16396</span><span class="sxs-lookup"><span data-stu-id="fb04b-175">16396</span></span></p></td>
<td><p><span data-ttu-id="fb04b-176">ST</span><span class="sxs-lookup"><span data-stu-id="fb04b-176">ST</span></span></p></td>
<td><p><span data-ttu-id="fb04b-177">ST</span><span class="sxs-lookup"><span data-stu-id="fb04b-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-178">16397</span><span class="sxs-lookup"><span data-stu-id="fb04b-178">16397</span></span></p></td>
<td><p><span data-ttu-id="fb04b-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="fb04b-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="fb04b-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="fb04b-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-181">16398</span><span class="sxs-lookup"><span data-stu-id="fb04b-181">16398</span></span></p></td>
<td><p><span data-ttu-id="fb04b-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="fb04b-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-184">16399</span><span class="sxs-lookup"><span data-stu-id="fb04b-184">16399</span></span></p></td>
<td><p><span data-ttu-id="fb04b-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="fb04b-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-187">16400</span><span class="sxs-lookup"><span data-stu-id="fb04b-187">16400</span></span></p></td>
<td><p><span data-ttu-id="fb04b-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="fb04b-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-190">16401</span><span class="sxs-lookup"><span data-stu-id="fb04b-190">16401</span></span></p></td>
<td><p><span data-ttu-id="fb04b-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="fb04b-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-193">16402</span><span class="sxs-lookup"><span data-stu-id="fb04b-193">16402</span></span></p></td>
<td><p><span data-ttu-id="fb04b-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="fb04b-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="fb04b-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-196">16403</span><span class="sxs-lookup"><span data-stu-id="fb04b-196">16403</span></span></p></td>
<td><p><span data-ttu-id="fb04b-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="fb04b-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="fb04b-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="fb04b-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-199">16404</span><span class="sxs-lookup"><span data-stu-id="fb04b-199">16404</span></span></p></td>
<td><p><span data-ttu-id="fb04b-200">PC</span><span class="sxs-lookup"><span data-stu-id="fb04b-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="fb04b-201">PC</span><span class="sxs-lookup"><span data-stu-id="fb04b-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-202">16405</span><span class="sxs-lookup"><span data-stu-id="fb04b-202">16405</span></span></p></td>
<td><p><span data-ttu-id="fb04b-203">LWA</span><span class="sxs-lookup"><span data-stu-id="fb04b-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="fb04b-204">LWA</span><span class="sxs-lookup"><span data-stu-id="fb04b-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-205">16406</span><span class="sxs-lookup"><span data-stu-id="fb04b-205">16406</span></span></p></td>
<td><p><span data-ttu-id="fb04b-206">OWA</span><span class="sxs-lookup"><span data-stu-id="fb04b-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="fb04b-207">OWA</span><span class="sxs-lookup"><span data-stu-id="fb04b-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-208">16407</span><span class="sxs-lookup"><span data-stu-id="fb04b-208">16407</span></span></p></td>
<td><p><span data-ttu-id="fb04b-209">AOC</span><span class="sxs-lookup"><span data-stu-id="fb04b-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="fb04b-210">AOC</span><span class="sxs-lookup"><span data-stu-id="fb04b-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-211">16408</span><span class="sxs-lookup"><span data-stu-id="fb04b-211">16408</span></span></p></td>
<td><p><span data-ttu-id="fb04b-212">GCC</span><span class="sxs-lookup"><span data-stu-id="fb04b-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="fb04b-213">GCC</span><span class="sxs-lookup"><span data-stu-id="fb04b-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-214">16409</span><span class="sxs-lookup"><span data-stu-id="fb04b-214">16409</span></span></p></td>
<td><p><span data-ttu-id="fb04b-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="fb04b-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="fb04b-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="fb04b-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-217">16410</span><span class="sxs-lookup"><span data-stu-id="fb04b-217">16410</span></span></p></td>
<td><p><span data-ttu-id="fb04b-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="fb04b-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="fb04b-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="fb04b-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb04b-220">32769</span><span class="sxs-lookup"><span data-stu-id="fb04b-220">32769</span></span></p></td>
<td><p><span data-ttu-id="fb04b-221">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="fb04b-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="fb04b-222">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="fb04b-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb04b-223">32770</span><span class="sxs-lookup"><span data-stu-id="fb04b-223">32770</span></span></p></td>
<td><p><span data-ttu-id="fb04b-224">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="fb04b-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="fb04b-225">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="fb04b-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

