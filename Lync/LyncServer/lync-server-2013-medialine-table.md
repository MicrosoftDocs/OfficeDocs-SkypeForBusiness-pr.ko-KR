---
title: 'Lync Server 2013: Medialofftable'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84aa652a51934a8b513392869a0875f60689f759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="fe1ba-102">Lync Server 2013의 Medialofftable</span><span class="sxs-lookup"><span data-stu-id="fe1ba-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe1ba-103">_**마지막으로 수정 된 항목:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="fe1ba-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="fe1ba-104">각 레코드는 하나의 미디어 회선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-104">Each record represents one media line.</span></span> <span data-ttu-id="fe1ba-105">일반적으로 오디오 세션에는 하나의 오디오 미디어 회선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="fe1ba-106">회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우, A/V (오디오 및 비디오) 세션에는 대개 하나의 오디오 미디어 회선과 하나의 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 회선이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe1ba-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fe1ba-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fe1ba-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fe1ba-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fe1ba-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fe1ba-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-114"><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-116">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-116">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-117">Primary</span><span class="sxs-lookup"><span data-stu-id="fe1ba-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-118"><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-121">Primary</span><span class="sxs-lookup"><span data-stu-id="fe1ba-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-122">0은 기본 오디오이 고 1은 기본 비디오이 고 2는 파노라마 동영상, 3은 응용 프로그램/데스크톱 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="fe1ba-123">이 레이블은 단일 세션 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-126">이 열은 제공 되지만 Microsoft Lync Server 2013에서는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="fe1ba-127">미디어 회선에 사용 되는 연결에 대 한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에서 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-129">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-130">Bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="fe1ba-131">자세한 내용은 다운로드 가능한 <em>Experience Quality Monitoring Server 프로토콜 사양을</em>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-133">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-134">CallerIceWarningFlags와 같으며 수신자 쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="fe1ba-135">자세한 내용은 다운로드 가능한 <em>Experience Quality Monitoring Server 프로토콜 사양을</em>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-136"><strong>보안</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-138">사용 중인 보안 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-138">The security profile in use.</span></span> <span data-ttu-id="fe1ba-139">0은 NONE, 1은 SRTP, 2는 V1입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-140"><strong>전송</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-142">0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-144">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-144">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-145">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-146">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-146">IP Address of the caller.</span></span> <span data-ttu-id="fe1ba-147">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-149">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-150">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-152">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-152">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-153"> 외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-154">발신자의 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-154">The subnet of the caller.</span></span> <span data-ttu-id="fe1ba-155">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-157">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-158">1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-159"><strong>CallerMacAddress가)</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-160">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-160">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-161">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-162"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 하는 발신자의 mac 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-164">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-164">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-165">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-166">발신자가 사용 하는 Lync Server A/V에 지 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="fe1ba-167">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-169">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-170">A/V에 지 서비스에서 발신자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-172">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-172">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-173">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-174">발신자가 사용 하는 캡처 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-174">Capture device used by the caller.</span></span> <span data-ttu-id="fe1ba-175"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-177">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-177">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-178">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-179">발신자가 사용 하는 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-179">Render device used by caller.</span></span> <span data-ttu-id="fe1ba-180"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-182">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-182">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-183">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-184"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 발신자의 캡처 장치용 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-186">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-186">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-187">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-188"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 발신자의 렌더 장치에 대 한 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-191">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-192">발신자가 네트워크에 연결 되는 방식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="fe1ba-193">값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="fe1ba-194">WiFi 연결의 경우 유선 연결의 1에 대 한 일반적인 값은 0입니다. 및 3은 이더넷 연결용입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-196">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-196">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-197">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-198">무선이 사용 되는 경우 발신자의 BSSID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="fe1ba-199"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-201">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-202">발신자의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-202">The caller's link.</span></span> <span data-ttu-id="fe1ba-203">1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-205">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="fe1ba-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-206">발신자의 끝점에 대 한 네트워크 연결 속도 (bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-208">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-208">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-209">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-210">통화 수신기의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-210">IP Address of the call receiver.</span></span> <span data-ttu-id="fe1ba-211">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-213">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-214">통화 수신기에서 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-216">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-216">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-217">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-218">수신자의 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-218">Subnet of callee.</span></span> <span data-ttu-id="fe1ba-219">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-221">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-222">1은 통화 수신자가 회사 네트워크 내에 있음을 의미 하 고 0은 통화 수신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-224">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-224">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-225">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-226">수신자 Mac 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-226">Callee Mac address.</span></span> <span data-ttu-id="fe1ba-227"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-229">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-229">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-230">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-231">통화 수신기에서 사용 하는 A/V에 지 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="fe1ba-232">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-234">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-235">A/V에 지 서비스에서 통화 수신기에 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-237">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-237">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-238">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-239">통화 수신기에서 사용 되는 캡처 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="fe1ba-240"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-242">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-242">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-243">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-244">통화 수신기에서 사용 하는 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-244">Render device used by the call receiver.</span></span> <span data-ttu-id="fe1ba-245"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-247">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-247">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-248">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-249">통화 수신기의 캡처 장치에 대 한 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="fe1ba-250"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe1ba-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-253">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-254">통화 수신기의 렌더 장치에 대 한 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="fe1ba-255"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-258">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-259">수신자가 네트워크에 연결 된 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="fe1ba-260">값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="fe1ba-261">WiFi 연결의 경우 유선 연결의 1에 대 한 일반적인 값은 0입니다. 및 3은 이더넷 연결용입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-263">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-263">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-264">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-265">무선이 사용 되는 경우 수신자의 BSSID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="fe1ba-266"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-268">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-269">통화 수신기의 링크입니다. 1은 VPN (가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-271">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="fe1ba-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-272">통화 수신기의 끝점에 대 한 네트워크 연결 속도 (bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-274">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe1ba-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-275">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="fe1ba-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-277">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-278">다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)에 따라 지정 된 보내기 쪽 스트림에 실제 대역폭이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="fe1ba-279">이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="fe1ba-280">이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-282">smallint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-283">적용 되는 대역폭 캡의 출처입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="fe1ba-284">또한 대역폭 제한이 전송 되는 위치 ("정책 서버", "서버 설정", "모달" 등)를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="fe1ba-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-286"><strong>최초</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-287">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-288">발신자의 메트릭이 수신 되었는지 여부를 나타냅니다. 1이 예 이면 null 값은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-289"><strong>피호출자</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-290">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe1ba-291">통화 수신기에서 메트릭을 받았는지 여부를 나타냅니다. 1이 예 이면 null 값은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-293">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-294">보고서가 세션의 일부 또는 전체 세션에 대 한 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="fe1ba-295">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-297">비트만</span><span class="sxs-lookup"><span data-stu-id="fe1ba-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-298">통화가 불량 통화 (값 1) 또는 정상 통화 (0)로 분류 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="fe1ba-299">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="fe1ba-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-302">발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="fe1ba-303">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe1ba-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe1ba-306">발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="fe1ba-307">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-309">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-309">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-310">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-311">통화를 시작한 사용자의 재귀 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="fe1ba-312">NAT (네트워크 주소 변환)를 사용 하는 조직에서는 재귀 IP 주소가 프록시 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="fe1ba-313">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-315">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-315">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-316">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-317">통화를 시작한 사용자가 사용한 WiFi 드라이버에 대 한 장치 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="fe1ba-318">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-320">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-320">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-321">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-322">통화를 시작한 사용자가 사용한 WiFi 드라이버의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="fe1ba-323">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-325">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-325">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-326">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-327">통화를 받은 사용자의 재귀 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="fe1ba-328">NAT (네트워크 주소 변환)를 사용 하는 조직에서는 재귀 IP 주소가 프록시 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="fe1ba-329">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe1ba-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-331">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-331">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-332">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-333">통화를 받은 사용자가 사용한 WiFi 드라이버에 대 한 장치 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="fe1ba-334">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe1ba-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fe1ba-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fe1ba-336">int</span><span class="sxs-lookup"><span data-stu-id="fe1ba-336">int</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-337">외부</span><span class="sxs-lookup"><span data-stu-id="fe1ba-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe1ba-338">통화를 받은 사용자가 사용한 WiFi 드라이버의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="fe1ba-339">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe1ba-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

