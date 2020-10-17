---
title: 'Lync Server 2013: UserAgentDef 테이블'
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
ms.openlocfilehash: 2ef005350d5ed9a4dee3f108a4cf9e3349389d1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530075"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="c7901-102">Lync Server 2013의 UserAgentDef 테이블</span><span class="sxs-lookup"><span data-stu-id="c7901-102">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7901-103">_**마지막으로 수정 된 항목:** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="c7901-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="c7901-104">UserAgentDef 테이블은 사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c7901-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="c7901-105">사용자 에이전트는 Microsoft Lync Server 2013에 연결 하는 데 사용 되는 소프트웨어 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="c7901-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c7901-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7901-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7901-107">UAType</span><span class="sxs-lookup"><span data-stu-id="c7901-107">UAType</span></span></th>
<th><span data-ttu-id="c7901-108">UAName</span><span class="sxs-lookup"><span data-stu-id="c7901-108">UAName</span></span></th>
<th><span data-ttu-id="c7901-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="c7901-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7901-110">1 </span><span class="sxs-lookup"><span data-stu-id="c7901-110">1</span></span></p></td>
<td><p><span data-ttu-id="c7901-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="c7901-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="c7901-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="c7901-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-113">2</span><span class="sxs-lookup"><span data-stu-id="c7901-113">2</span></span></p></td>
<td><p><span data-ttu-id="c7901-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="c7901-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="c7901-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="c7901-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-116">4 </span><span class="sxs-lookup"><span data-stu-id="c7901-116">4</span></span></p></td>
<td><p><span data-ttu-id="c7901-117">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="c7901-117">OC</span></span></p></td>
<td><p><span data-ttu-id="c7901-118">NM-OC-14-2ND</span><span class="sxs-lookup"><span data-stu-id="c7901-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-119">8 </span><span class="sxs-lookup"><span data-stu-id="c7901-119">8</span></span></p></td>
<td><p><span data-ttu-id="c7901-120">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="c7901-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="c7901-121">Cpe-ocphone</span><span class="sxs-lookup"><span data-stu-id="c7901-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-122">16 </span><span class="sxs-lookup"><span data-stu-id="c7901-122">16</span></span></p></td>
<td><p><span data-ttu-id="c7901-123">LMC</span><span class="sxs-lookup"><span data-stu-id="c7901-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="c7901-124">LMC</span><span class="sxs-lookup"><span data-stu-id="c7901-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-125">32</span><span class="sxs-lookup"><span data-stu-id="c7901-125">32</span></span></p></td>
<td><p><span data-ttu-id="c7901-126">DVT</span><span class="sxs-lookup"><span data-stu-id="c7901-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="c7901-127">DVT</span><span class="sxs-lookup"><span data-stu-id="c7901-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-128">64</span><span class="sxs-lookup"><span data-stu-id="c7901-128">64</span></span></p></td>
<td><p><span data-ttu-id="c7901-129">19</span><span class="sxs-lookup"><span data-stu-id="c7901-129">MM</span></span></p></td>
<td><p><span data-ttu-id="c7901-130">19</span><span class="sxs-lookup"><span data-stu-id="c7901-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-131">64</span><span class="sxs-lookup"><span data-stu-id="c7901-131">64</span></span></p></td>
<td><p><span data-ttu-id="c7901-132">MC</span><span class="sxs-lookup"><span data-stu-id="c7901-132">MC</span></span></p></td>
<td><p><span data-ttu-id="c7901-133">19</span><span class="sxs-lookup"><span data-stu-id="c7901-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-134">128</span><span class="sxs-lookup"><span data-stu-id="c7901-134">128</span></span></p></td>
<td><p><span data-ttu-id="c7901-135">도우미</span><span class="sxs-lookup"><span data-stu-id="c7901-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="c7901-136">도우미</span><span class="sxs-lookup"><span data-stu-id="c7901-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-137">256</span><span class="sxs-lookup"><span data-stu-id="c7901-137">256</span></span></p></td>
<td><p><span data-ttu-id="c7901-138">Conferencing_Announcement_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="c7901-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7901-139">인증</span><span class="sxs-lookup"><span data-stu-id="c7901-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-140">512</span><span class="sxs-lookup"><span data-stu-id="c7901-140">512</span></span></p></td>
<td><p><span data-ttu-id="c7901-141">Conferencing_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="c7901-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7901-142">CAA</span><span class="sxs-lookup"><span data-stu-id="c7901-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-143">512</span><span class="sxs-lookup"><span data-stu-id="c7901-143">512</span></span></p></td>
<td><p><span data-ttu-id="c7901-144">Conference_Auto_Attendant_1 0</span><span class="sxs-lookup"><span data-stu-id="c7901-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7901-145">CAA</span><span class="sxs-lookup"><span data-stu-id="c7901-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-146">1024</span><span class="sxs-lookup"><span data-stu-id="c7901-146">1024</span></span></p></td>
<td><p><span data-ttu-id="c7901-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="c7901-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="c7901-148">컴파일하지</span><span class="sxs-lookup"><span data-stu-id="c7901-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-149">1032</span><span class="sxs-lookup"><span data-stu-id="c7901-149">1032</span></span></p></td>
<td><p><span data-ttu-id="c7901-150">Call_Park_Service_1 0</span><span class="sxs-lookup"><span data-stu-id="c7901-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="c7901-151">CPS</span><span class="sxs-lookup"><span data-stu-id="c7901-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-152">1040</span><span class="sxs-lookup"><span data-stu-id="c7901-152">1040</span></span></p></td>
<td><p><span data-ttu-id="c7901-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="c7901-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="c7901-154">에</span><span class="sxs-lookup"><span data-stu-id="c7901-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-155">2048</span><span class="sxs-lookup"><span data-stu-id="c7901-155">2048</span></span></p></td>
<td><p><span data-ttu-id="c7901-156">Microsoft Rtc. Ccs</span><span class="sxs-lookup"><span data-stu-id="c7901-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="c7901-157">CCS</span><span class="sxs-lookup"><span data-stu-id="c7901-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-158">16386</span><span class="sxs-lookup"><span data-stu-id="c7901-158">16386</span></span></p></td>
<td><p><span data-ttu-id="c7901-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="c7901-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="c7901-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="c7901-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-161">16387</span><span class="sxs-lookup"><span data-stu-id="c7901-161">16387</span></span></p></td>
<td><p><span data-ttu-id="c7901-162">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="c7901-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="c7901-163">NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="c7901-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-164">16388</span><span class="sxs-lookup"><span data-stu-id="c7901-164">16388</span></span></p></td>
<td><p><span data-ttu-id="c7901-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="c7901-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="c7901-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="c7901-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-167">16389</span><span class="sxs-lookup"><span data-stu-id="c7901-167">16389</span></span></p></td>
<td><p><span data-ttu-id="c7901-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="c7901-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="c7901-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="c7901-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-170">16393</span><span class="sxs-lookup"><span data-stu-id="c7901-170">16393</span></span></p></td>
<td><p><span data-ttu-id="c7901-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="c7901-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="c7901-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="c7901-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-173">16395</span><span class="sxs-lookup"><span data-stu-id="c7901-173">16395</span></span></p></td>
<td><p><span data-ttu-id="c7901-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="c7901-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="c7901-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="c7901-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-176">16396</span><span class="sxs-lookup"><span data-stu-id="c7901-176">16396</span></span></p></td>
<td><p><span data-ttu-id="c7901-177">ST</span><span class="sxs-lookup"><span data-stu-id="c7901-177">ST</span></span></p></td>
<td><p><span data-ttu-id="c7901-178">ST</span><span class="sxs-lookup"><span data-stu-id="c7901-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-179">16397</span><span class="sxs-lookup"><span data-stu-id="c7901-179">16397</span></span></p></td>
<td><p><span data-ttu-id="c7901-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c7901-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="c7901-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="c7901-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-182">16398</span><span class="sxs-lookup"><span data-stu-id="c7901-182">16398</span></span></p></td>
<td><p><span data-ttu-id="c7901-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="c7901-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="c7901-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="c7901-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-185">16399</span><span class="sxs-lookup"><span data-stu-id="c7901-185">16399</span></span></p></td>
<td><p><span data-ttu-id="c7901-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="c7901-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="c7901-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="c7901-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-188">16400</span><span class="sxs-lookup"><span data-stu-id="c7901-188">16400</span></span></p></td>
<td><p><span data-ttu-id="c7901-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="c7901-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="c7901-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="c7901-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-191">16401</span><span class="sxs-lookup"><span data-stu-id="c7901-191">16401</span></span></p></td>
<td><p><span data-ttu-id="c7901-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="c7901-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="c7901-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="c7901-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-194">16402</span><span class="sxs-lookup"><span data-stu-id="c7901-194">16402</span></span></p></td>
<td><p><span data-ttu-id="c7901-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="c7901-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="c7901-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="c7901-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-197">16403</span><span class="sxs-lookup"><span data-stu-id="c7901-197">16403</span></span></p></td>
<td><p><span data-ttu-id="c7901-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="c7901-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="c7901-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="c7901-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-200">16404</span><span class="sxs-lookup"><span data-stu-id="c7901-200">16404</span></span></p></td>
<td><p><span data-ttu-id="c7901-201">PC</span><span class="sxs-lookup"><span data-stu-id="c7901-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="c7901-202">PC</span><span class="sxs-lookup"><span data-stu-id="c7901-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-203">16405</span><span class="sxs-lookup"><span data-stu-id="c7901-203">16405</span></span></p></td>
<td><p><span data-ttu-id="c7901-204">LWA</span><span class="sxs-lookup"><span data-stu-id="c7901-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="c7901-205">LWA</span><span class="sxs-lookup"><span data-stu-id="c7901-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-206">16406</span><span class="sxs-lookup"><span data-stu-id="c7901-206">16406</span></span></p></td>
<td><p><span data-ttu-id="c7901-207">OWA</span><span class="sxs-lookup"><span data-stu-id="c7901-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="c7901-208">OWA</span><span class="sxs-lookup"><span data-stu-id="c7901-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-209">16407</span><span class="sxs-lookup"><span data-stu-id="c7901-209">16407</span></span></p></td>
<td><p><span data-ttu-id="c7901-210">AOC</span><span class="sxs-lookup"><span data-stu-id="c7901-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="c7901-211">AOC</span><span class="sxs-lookup"><span data-stu-id="c7901-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-212">16408</span><span class="sxs-lookup"><span data-stu-id="c7901-212">16408</span></span></p></td>
<td><p><span data-ttu-id="c7901-213">GCC</span><span class="sxs-lookup"><span data-stu-id="c7901-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="c7901-214">GCC</span><span class="sxs-lookup"><span data-stu-id="c7901-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-215">16409</span><span class="sxs-lookup"><span data-stu-id="c7901-215">16409</span></span></p></td>
<td><p><span data-ttu-id="c7901-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="c7901-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="c7901-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="c7901-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-218">16410</span><span class="sxs-lookup"><span data-stu-id="c7901-218">16410</span></span></p></td>
<td><p><span data-ttu-id="c7901-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="c7901-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="c7901-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="c7901-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7901-221">32769</span><span class="sxs-lookup"><span data-stu-id="c7901-221">32769</span></span></p></td>
<td><p><span data-ttu-id="c7901-222">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="c7901-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="c7901-223">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="c7901-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7901-224">32770</span><span class="sxs-lookup"><span data-stu-id="c7901-224">32770</span></span></p></td>
<td><p><span data-ttu-id="c7901-225">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="c7901-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="c7901-226">게이트웨이 미디어</span><span class="sxs-lookup"><span data-stu-id="c7901-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

