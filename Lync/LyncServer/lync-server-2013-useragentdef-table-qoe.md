---
title: 'Lync Server 2013: UserAgentDef 테이블 (체감 품질)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adfe05a24d2a45cf5d6d279b29d77b1c7654012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="6e36c-102">Lync Server 2013의 UserAgentDef 테이블 (체감 품질)</span><span class="sxs-lookup"><span data-stu-id="6e36c-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e36c-103">_**마지막으로 수정한 주제:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="6e36c-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="6e36c-104">UserAgentDef 테이블은 사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="6e36c-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="6e36c-105">사용자 에이전트는 Microsoft Lync Server 2013에 연결 하는 데 사용 되는 소프트웨어 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="6e36c-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e36c-106">UAType</span><span class="sxs-lookup"><span data-stu-id="6e36c-106">UAType</span></span></th>
<th><span data-ttu-id="6e36c-107">UAName</span><span class="sxs-lookup"><span data-stu-id="6e36c-107">UAName</span></span></th>
<th><span data-ttu-id="6e36c-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="6e36c-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-109">1</span><span class="sxs-lookup"><span data-stu-id="6e36c-109">1</span></span></p></td>
<td><p><span data-ttu-id="6e36c-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6e36c-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="6e36c-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6e36c-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-112">2</span><span class="sxs-lookup"><span data-stu-id="6e36c-112">2</span></span></p></td>
<td><p><span data-ttu-id="6e36c-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="6e36c-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="6e36c-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="6e36c-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-115">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="6e36c-115">4</span></span></p></td>
<td><p><span data-ttu-id="6e36c-116">OC</span><span class="sxs-lookup"><span data-stu-id="6e36c-116">OC</span></span></p></td>
<td><p><span data-ttu-id="6e36c-117">OC</span><span class="sxs-lookup"><span data-stu-id="6e36c-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-118">20cm(8</span><span class="sxs-lookup"><span data-stu-id="6e36c-118">8</span></span></p></td>
<td><p><span data-ttu-id="6e36c-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6e36c-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="6e36c-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6e36c-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-121">16</span><span class="sxs-lookup"><span data-stu-id="6e36c-121">16</span></span></p></td>
<td><p><span data-ttu-id="6e36c-122">LMC</span><span class="sxs-lookup"><span data-stu-id="6e36c-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="6e36c-123">LMC</span><span class="sxs-lookup"><span data-stu-id="6e36c-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-124">32</span><span class="sxs-lookup"><span data-stu-id="6e36c-124">32</span></span></p></td>
<td><p><span data-ttu-id="6e36c-125">DVT</span><span class="sxs-lookup"><span data-stu-id="6e36c-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="6e36c-126">DVT</span><span class="sxs-lookup"><span data-stu-id="6e36c-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-127">64</span><span class="sxs-lookup"><span data-stu-id="6e36c-127">64</span></span></p></td>
<td><p><span data-ttu-id="6e36c-128">200</span><span class="sxs-lookup"><span data-stu-id="6e36c-128">MM</span></span></p></td>
<td><p><span data-ttu-id="6e36c-129">200</span><span class="sxs-lookup"><span data-stu-id="6e36c-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-130">64</span><span class="sxs-lookup"><span data-stu-id="6e36c-130">64</span></span></p></td>
<td><p><span data-ttu-id="6e36c-131">MC</span><span class="sxs-lookup"><span data-stu-id="6e36c-131">MC</span></span></p></td>
<td><p><span data-ttu-id="6e36c-132">200</span><span class="sxs-lookup"><span data-stu-id="6e36c-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-133">128</span><span class="sxs-lookup"><span data-stu-id="6e36c-133">128</span></span></p></td>
<td><p><span data-ttu-id="6e36c-134">리소스만</span><span class="sxs-lookup"><span data-stu-id="6e36c-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="6e36c-135">리소스만</span><span class="sxs-lookup"><span data-stu-id="6e36c-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-136">256</span><span class="sxs-lookup"><span data-stu-id="6e36c-136">256</span></span></p></td>
<td><p><span data-ttu-id="6e36c-137">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="6e36c-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="6e36c-138">이어지는</span><span class="sxs-lookup"><span data-stu-id="6e36c-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-139">512</span><span class="sxs-lookup"><span data-stu-id="6e36c-139">512</span></span></p></td>
<td><p><span data-ttu-id="6e36c-140">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="6e36c-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="6e36c-141">CAA</span><span class="sxs-lookup"><span data-stu-id="6e36c-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-142">512</span><span class="sxs-lookup"><span data-stu-id="6e36c-142">512</span></span></p></td>
<td><p><span data-ttu-id="6e36c-143">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="6e36c-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="6e36c-144">CAA</span><span class="sxs-lookup"><span data-stu-id="6e36c-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-145">1024</span><span class="sxs-lookup"><span data-stu-id="6e36c-145">1024</span></span></p></td>
<td><p><span data-ttu-id="6e36c-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="6e36c-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="6e36c-147">RGS</span><span class="sxs-lookup"><span data-stu-id="6e36c-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-148">1032</span><span class="sxs-lookup"><span data-stu-id="6e36c-148">1032</span></span></p></td>
<td><p><span data-ttu-id="6e36c-149">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="6e36c-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="6e36c-150">CPS</span><span class="sxs-lookup"><span data-stu-id="6e36c-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-151">1040</span><span class="sxs-lookup"><span data-stu-id="6e36c-151">1040</span></span></p></td>
<td><p><span data-ttu-id="6e36c-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="6e36c-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="6e36c-153">문자열로</span><span class="sxs-lookup"><span data-stu-id="6e36c-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-154">2048</span><span class="sxs-lookup"><span data-stu-id="6e36c-154">2048</span></span></p></td>
<td><p><span data-ttu-id="6e36c-155">Microsoft Rtc. Ccs</span><span class="sxs-lookup"><span data-stu-id="6e36c-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="6e36c-156">CCS</span><span class="sxs-lookup"><span data-stu-id="6e36c-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-157">16386</span><span class="sxs-lookup"><span data-stu-id="6e36c-157">16386</span></span></p></td>
<td><p><span data-ttu-id="6e36c-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="6e36c-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="6e36c-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="6e36c-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-160">16387</span><span class="sxs-lookup"><span data-stu-id="6e36c-160">16387</span></span></p></td>
<td><p><span data-ttu-id="6e36c-161">CWA</span><span class="sxs-lookup"><span data-stu-id="6e36c-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="6e36c-162">CWA</span><span class="sxs-lookup"><span data-stu-id="6e36c-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-163">16388</span><span class="sxs-lookup"><span data-stu-id="6e36c-163">16388</span></span></p></td>
<td><p><span data-ttu-id="6e36c-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="6e36c-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="6e36c-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="6e36c-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-166">16389</span><span class="sxs-lookup"><span data-stu-id="6e36c-166">16389</span></span></p></td>
<td><p><span data-ttu-id="6e36c-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="6e36c-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="6e36c-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="6e36c-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-169">16393</span><span class="sxs-lookup"><span data-stu-id="6e36c-169">16393</span></span></p></td>
<td><p><span data-ttu-id="6e36c-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="6e36c-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="6e36c-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="6e36c-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-172">16395</span><span class="sxs-lookup"><span data-stu-id="6e36c-172">16395</span></span></p></td>
<td><p><span data-ttu-id="6e36c-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="6e36c-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="6e36c-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="6e36c-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-175">16396</span><span class="sxs-lookup"><span data-stu-id="6e36c-175">16396</span></span></p></td>
<td><p><span data-ttu-id="6e36c-176">ST</span><span class="sxs-lookup"><span data-stu-id="6e36c-176">ST</span></span></p></td>
<td><p><span data-ttu-id="6e36c-177">ST</span><span class="sxs-lookup"><span data-stu-id="6e36c-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-178">16397</span><span class="sxs-lookup"><span data-stu-id="6e36c-178">16397</span></span></p></td>
<td><p><span data-ttu-id="6e36c-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="6e36c-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="6e36c-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="6e36c-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-181">16398</span><span class="sxs-lookup"><span data-stu-id="6e36c-181">16398</span></span></p></td>
<td><p><span data-ttu-id="6e36c-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="6e36c-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-184">16399</span><span class="sxs-lookup"><span data-stu-id="6e36c-184">16399</span></span></p></td>
<td><p><span data-ttu-id="6e36c-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="6e36c-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-187">16400</span><span class="sxs-lookup"><span data-stu-id="6e36c-187">16400</span></span></p></td>
<td><p><span data-ttu-id="6e36c-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="6e36c-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-190">16401</span><span class="sxs-lookup"><span data-stu-id="6e36c-190">16401</span></span></p></td>
<td><p><span data-ttu-id="6e36c-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="6e36c-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-193">16402</span><span class="sxs-lookup"><span data-stu-id="6e36c-193">16402</span></span></p></td>
<td><p><span data-ttu-id="6e36c-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="6e36c-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6e36c-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-196">16403</span><span class="sxs-lookup"><span data-stu-id="6e36c-196">16403</span></span></p></td>
<td><p><span data-ttu-id="6e36c-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="6e36c-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="6e36c-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="6e36c-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-199">16404</span><span class="sxs-lookup"><span data-stu-id="6e36c-199">16404</span></span></p></td>
<td><p><span data-ttu-id="6e36c-200">플레이어</span><span class="sxs-lookup"><span data-stu-id="6e36c-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="6e36c-201">플레이어</span><span class="sxs-lookup"><span data-stu-id="6e36c-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-202">16405</span><span class="sxs-lookup"><span data-stu-id="6e36c-202">16405</span></span></p></td>
<td><p><span data-ttu-id="6e36c-203">LWA</span><span class="sxs-lookup"><span data-stu-id="6e36c-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="6e36c-204">LWA</span><span class="sxs-lookup"><span data-stu-id="6e36c-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-205">16406</span><span class="sxs-lookup"><span data-stu-id="6e36c-205">16406</span></span></p></td>
<td><p><span data-ttu-id="6e36c-206">OWA</span><span class="sxs-lookup"><span data-stu-id="6e36c-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="6e36c-207">OWA</span><span class="sxs-lookup"><span data-stu-id="6e36c-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-208">16407</span><span class="sxs-lookup"><span data-stu-id="6e36c-208">16407</span></span></p></td>
<td><p><span data-ttu-id="6e36c-209">AOC</span><span class="sxs-lookup"><span data-stu-id="6e36c-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="6e36c-210">AOC</span><span class="sxs-lookup"><span data-stu-id="6e36c-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-211">16408</span><span class="sxs-lookup"><span data-stu-id="6e36c-211">16408</span></span></p></td>
<td><p><span data-ttu-id="6e36c-212">GCC</span><span class="sxs-lookup"><span data-stu-id="6e36c-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="6e36c-213">GCC</span><span class="sxs-lookup"><span data-stu-id="6e36c-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-214">16409</span><span class="sxs-lookup"><span data-stu-id="6e36c-214">16409</span></span></p></td>
<td><p><span data-ttu-id="6e36c-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="6e36c-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="6e36c-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="6e36c-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-217">16410</span><span class="sxs-lookup"><span data-stu-id="6e36c-217">16410</span></span></p></td>
<td><p><span data-ttu-id="6e36c-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="6e36c-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="6e36c-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="6e36c-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e36c-220">32769</span><span class="sxs-lookup"><span data-stu-id="6e36c-220">32769</span></span></p></td>
<td><p><span data-ttu-id="6e36c-221">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="6e36c-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="6e36c-222">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="6e36c-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e36c-223">32770</span><span class="sxs-lookup"><span data-stu-id="6e36c-223">32770</span></span></p></td>
<td><p><span data-ttu-id="6e36c-224">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="6e36c-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="6e36c-225">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="6e36c-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

