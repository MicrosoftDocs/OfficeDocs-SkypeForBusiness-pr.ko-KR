---
title: 'Lync Server 2013: UserAgentDef 테이블 (QoE)'
description: 'Lync Server 2013: UserAgentDef 테이블 (QoE)'
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
ms.openlocfilehash: 8546a33e607524b23755e9abf3edb2d5e2e417d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547344"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="45173-103">Lync Server 2013의 UserAgentDef 테이블 (QoE)</span><span class="sxs-lookup"><span data-stu-id="45173-103">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45173-104">_**마지막으로 수정 된 항목:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="45173-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="45173-105">UserAgentDef 테이블은 사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="45173-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="45173-106">사용자 에이전트는 Microsoft Lync Server 2013에 연결 하는 데 사용 되는 소프트웨어 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="45173-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45173-107">UAType</span><span class="sxs-lookup"><span data-stu-id="45173-107">UAType</span></span></th>
<th><span data-ttu-id="45173-108">UAName</span><span class="sxs-lookup"><span data-stu-id="45173-108">UAName</span></span></th>
<th><span data-ttu-id="45173-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="45173-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45173-110">1 </span><span class="sxs-lookup"><span data-stu-id="45173-110">1</span></span></p></td>
<td><p><span data-ttu-id="45173-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="45173-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="45173-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="45173-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-113">2</span><span class="sxs-lookup"><span data-stu-id="45173-113">2</span></span></p></td>
<td><p><span data-ttu-id="45173-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="45173-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="45173-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="45173-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-116">4 </span><span class="sxs-lookup"><span data-stu-id="45173-116">4</span></span></p></td>
<td><p><span data-ttu-id="45173-117">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="45173-117">OC</span></span></p></td>
<td><p><span data-ttu-id="45173-118">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="45173-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-119">8 </span><span class="sxs-lookup"><span data-stu-id="45173-119">8</span></span></p></td>
<td><p><span data-ttu-id="45173-120">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="45173-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="45173-121">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="45173-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-122">16 </span><span class="sxs-lookup"><span data-stu-id="45173-122">16</span></span></p></td>
<td><p><span data-ttu-id="45173-123">LMC</span><span class="sxs-lookup"><span data-stu-id="45173-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="45173-124">LMC</span><span class="sxs-lookup"><span data-stu-id="45173-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-125">32</span><span class="sxs-lookup"><span data-stu-id="45173-125">32</span></span></p></td>
<td><p><span data-ttu-id="45173-126">DVT</span><span class="sxs-lookup"><span data-stu-id="45173-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="45173-127">DVT</span><span class="sxs-lookup"><span data-stu-id="45173-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-128">64</span><span class="sxs-lookup"><span data-stu-id="45173-128">64</span></span></p></td>
<td><p><span data-ttu-id="45173-129">19</span><span class="sxs-lookup"><span data-stu-id="45173-129">MM</span></span></p></td>
<td><p><span data-ttu-id="45173-130">19</span><span class="sxs-lookup"><span data-stu-id="45173-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-131">64</span><span class="sxs-lookup"><span data-stu-id="45173-131">64</span></span></p></td>
<td><p><span data-ttu-id="45173-132">MC</span><span class="sxs-lookup"><span data-stu-id="45173-132">MC</span></span></p></td>
<td><p><span data-ttu-id="45173-133">19</span><span class="sxs-lookup"><span data-stu-id="45173-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-134">128</span><span class="sxs-lookup"><span data-stu-id="45173-134">128</span></span></p></td>
<td><p><span data-ttu-id="45173-135">도우미</span><span class="sxs-lookup"><span data-stu-id="45173-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="45173-136">도우미</span><span class="sxs-lookup"><span data-stu-id="45173-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-137">256</span><span class="sxs-lookup"><span data-stu-id="45173-137">256</span></span></p></td>
<td><p><span data-ttu-id="45173-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="45173-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="45173-139">인증</span><span class="sxs-lookup"><span data-stu-id="45173-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-140">512</span><span class="sxs-lookup"><span data-stu-id="45173-140">512</span></span></p></td>
<td><p><span data-ttu-id="45173-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="45173-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="45173-142">CAA</span><span class="sxs-lookup"><span data-stu-id="45173-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-143">512</span><span class="sxs-lookup"><span data-stu-id="45173-143">512</span></span></p></td>
<td><p><span data-ttu-id="45173-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="45173-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="45173-145">CAA</span><span class="sxs-lookup"><span data-stu-id="45173-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-146">1024</span><span class="sxs-lookup"><span data-stu-id="45173-146">1024</span></span></p></td>
<td><p><span data-ttu-id="45173-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="45173-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="45173-148">컴파일하지</span><span class="sxs-lookup"><span data-stu-id="45173-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-149">1032</span><span class="sxs-lookup"><span data-stu-id="45173-149">1032</span></span></p></td>
<td><p><span data-ttu-id="45173-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="45173-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="45173-151">CPS</span><span class="sxs-lookup"><span data-stu-id="45173-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-152">1040</span><span class="sxs-lookup"><span data-stu-id="45173-152">1040</span></span></p></td>
<td><p><span data-ttu-id="45173-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="45173-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="45173-154">에</span><span class="sxs-lookup"><span data-stu-id="45173-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-155">2048</span><span class="sxs-lookup"><span data-stu-id="45173-155">2048</span></span></p></td>
<td><p><span data-ttu-id="45173-156">Microsoft Rtc. Ccs</span><span class="sxs-lookup"><span data-stu-id="45173-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="45173-157">CCS</span><span class="sxs-lookup"><span data-stu-id="45173-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-158">16386</span><span class="sxs-lookup"><span data-stu-id="45173-158">16386</span></span></p></td>
<td><p><span data-ttu-id="45173-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="45173-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="45173-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="45173-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-161">16387</span><span class="sxs-lookup"><span data-stu-id="45173-161">16387</span></span></p></td>
<td><p><span data-ttu-id="45173-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="45173-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="45173-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="45173-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-164">16388</span><span class="sxs-lookup"><span data-stu-id="45173-164">16388</span></span></p></td>
<td><p><span data-ttu-id="45173-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="45173-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="45173-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="45173-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-167">16389</span><span class="sxs-lookup"><span data-stu-id="45173-167">16389</span></span></p></td>
<td><p><span data-ttu-id="45173-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="45173-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="45173-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="45173-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-170">16393</span><span class="sxs-lookup"><span data-stu-id="45173-170">16393</span></span></p></td>
<td><p><span data-ttu-id="45173-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="45173-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="45173-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="45173-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-173">16395</span><span class="sxs-lookup"><span data-stu-id="45173-173">16395</span></span></p></td>
<td><p><span data-ttu-id="45173-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="45173-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="45173-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="45173-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-176">16396</span><span class="sxs-lookup"><span data-stu-id="45173-176">16396</span></span></p></td>
<td><p><span data-ttu-id="45173-177">ST</span><span class="sxs-lookup"><span data-stu-id="45173-177">ST</span></span></p></td>
<td><p><span data-ttu-id="45173-178">ST</span><span class="sxs-lookup"><span data-stu-id="45173-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-179">16397</span><span class="sxs-lookup"><span data-stu-id="45173-179">16397</span></span></p></td>
<td><p><span data-ttu-id="45173-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="45173-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="45173-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="45173-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-182">16398</span><span class="sxs-lookup"><span data-stu-id="45173-182">16398</span></span></p></td>
<td><p><span data-ttu-id="45173-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="45173-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="45173-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="45173-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-185">16399</span><span class="sxs-lookup"><span data-stu-id="45173-185">16399</span></span></p></td>
<td><p><span data-ttu-id="45173-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="45173-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="45173-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="45173-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-188">16400</span><span class="sxs-lookup"><span data-stu-id="45173-188">16400</span></span></p></td>
<td><p><span data-ttu-id="45173-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="45173-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="45173-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="45173-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-191">16401</span><span class="sxs-lookup"><span data-stu-id="45173-191">16401</span></span></p></td>
<td><p><span data-ttu-id="45173-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="45173-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="45173-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="45173-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-194">16402</span><span class="sxs-lookup"><span data-stu-id="45173-194">16402</span></span></p></td>
<td><p><span data-ttu-id="45173-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="45173-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="45173-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="45173-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-197">16403</span><span class="sxs-lookup"><span data-stu-id="45173-197">16403</span></span></p></td>
<td><p><span data-ttu-id="45173-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="45173-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="45173-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="45173-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-200">16404</span><span class="sxs-lookup"><span data-stu-id="45173-200">16404</span></span></p></td>
<td><p><span data-ttu-id="45173-201">PC</span><span class="sxs-lookup"><span data-stu-id="45173-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="45173-202">PC</span><span class="sxs-lookup"><span data-stu-id="45173-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-203">16405</span><span class="sxs-lookup"><span data-stu-id="45173-203">16405</span></span></p></td>
<td><p><span data-ttu-id="45173-204">LWA</span><span class="sxs-lookup"><span data-stu-id="45173-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="45173-205">LWA</span><span class="sxs-lookup"><span data-stu-id="45173-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-206">16406</span><span class="sxs-lookup"><span data-stu-id="45173-206">16406</span></span></p></td>
<td><p><span data-ttu-id="45173-207">OWA</span><span class="sxs-lookup"><span data-stu-id="45173-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="45173-208">OWA</span><span class="sxs-lookup"><span data-stu-id="45173-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-209">16407</span><span class="sxs-lookup"><span data-stu-id="45173-209">16407</span></span></p></td>
<td><p><span data-ttu-id="45173-210">AOC</span><span class="sxs-lookup"><span data-stu-id="45173-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="45173-211">AOC</span><span class="sxs-lookup"><span data-stu-id="45173-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-212">16408</span><span class="sxs-lookup"><span data-stu-id="45173-212">16408</span></span></p></td>
<td><p><span data-ttu-id="45173-213">GCC</span><span class="sxs-lookup"><span data-stu-id="45173-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="45173-214">GCC</span><span class="sxs-lookup"><span data-stu-id="45173-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-215">16409</span><span class="sxs-lookup"><span data-stu-id="45173-215">16409</span></span></p></td>
<td><p><span data-ttu-id="45173-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="45173-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="45173-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="45173-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-218">16410</span><span class="sxs-lookup"><span data-stu-id="45173-218">16410</span></span></p></td>
<td><p><span data-ttu-id="45173-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="45173-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="45173-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="45173-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45173-221">32769</span><span class="sxs-lookup"><span data-stu-id="45173-221">32769</span></span></p></td>
<td><p><span data-ttu-id="45173-222">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="45173-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="45173-223">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="45173-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45173-224">32770</span><span class="sxs-lookup"><span data-stu-id="45173-224">32770</span></span></p></td>
<td><p><span data-ttu-id="45173-225">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="45173-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="45173-226">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="45173-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

