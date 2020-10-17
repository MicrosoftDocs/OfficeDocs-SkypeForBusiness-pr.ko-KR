---
title: 'Lync Server 2013: Medialofftable'
description: 'Lync Server 2013: Medialofftable'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572114"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="64fc3-103">Lync Server 2013의 Medialofftable</span><span class="sxs-lookup"><span data-stu-id="64fc3-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64fc3-104">_**마지막으로 수정 된 항목:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="64fc3-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="64fc3-105">각 레코드는 하나의 미디어 회선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-105">Each record represents one media line.</span></span> <span data-ttu-id="64fc3-106">일반적으로 오디오 세션에는 하나의 오디오 미디어 회선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="64fc3-107">회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우, A/V (오디오 및 비디오) 세션에는 대개 하나의 오디오 미디어 회선과 하나의 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 회선이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64fc3-108"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="64fc3-109"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="64fc3-110"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="64fc3-111"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-112"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="64fc3-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="64fc3-114">Primary</span><span class="sxs-lookup"><span data-stu-id="64fc3-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="64fc3-115"><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-117">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-117">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-118">Primary</span><span class="sxs-lookup"><span data-stu-id="64fc3-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="64fc3-119"><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="64fc3-122">Primary</span><span class="sxs-lookup"><span data-stu-id="64fc3-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="64fc3-123">0은 기본 오디오이 고 1은 기본 비디오이 고 2는 파노라마 동영상, 3은 응용 프로그램/데스크톱 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="64fc3-124">이 레이블은 단일 세션 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-127">이 열은 제공 되지만 Microsoft Lync Server 2013에서는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="64fc3-128">미디어 회선에 사용 되는 연결에 대 한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에서 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-130">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-131">Bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="64fc3-132">자세한 내용은 다운로드 가능한 <em>Experience Quality Monitoring Server 프로토콜 사양을</em>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64fc3-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-134">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-135">CallerIceWarningFlags와 같으며 수신자 쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="64fc3-136">자세한 내용은 다운로드 가능한 <em>Experience Quality Monitoring Server 프로토콜 사양을</em>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="64fc3-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-137"><strong>보안</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-139">사용 중인 보안 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-139">The security profile in use.</span></span> <span data-ttu-id="64fc3-140">0은 NONE, 1은 SRTP, 2는 V1입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-141"><strong>전송</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-143">0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-145">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-145">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-146">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-147">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-147">IP Address of the caller.</span></span> <span data-ttu-id="64fc3-148">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64fc3-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-150">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-151">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-153">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-153">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-154"> 외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-155">발신자의 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-155">The subnet of the caller.</span></span> <span data-ttu-id="64fc3-156">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64fc3-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-158">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-159">1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-160"><strong>CallerMacAddress가)</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-161">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-161">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-162">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-163"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 하는 발신자의 mac 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-165">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-165">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-166">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-167">발신자가 사용 하는 Lync Server A/V에 지 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="64fc3-168">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64fc3-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-170">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-171">A/V에 지 서비스에서 발신자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-173">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-173">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-174">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-175">발신자가 사용 하는 캡처 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-175">Capture device used by the caller.</span></span> <span data-ttu-id="64fc3-176"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-178">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-178">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-179">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-180">발신자가 사용 하는 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-180">Render device used by caller.</span></span> <span data-ttu-id="64fc3-181"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-183">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-183">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-184">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-185"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 발신자의 캡처 장치용 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-187">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-187">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-188">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-189"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 발신자의 렌더 장치에 대 한 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="64fc3-192">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-193">발신자가 네트워크에 연결 되는 방식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="64fc3-194">값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="64fc3-195">WiFi 연결의 경우 유선 연결의 1에 대 한 일반적인 값은 0입니다. 및 3은 이더넷 연결용입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-197">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-197">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-198">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-199">무선이 사용 되는 경우 발신자의 BSSID입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="64fc3-200"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-202">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-203">발신자의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-203">The caller's link.</span></span> <span data-ttu-id="64fc3-204">1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-206">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="64fc3-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-207">발신자의 끝점에 대 한 네트워크 연결 속도 (bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-209">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-209">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-210">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-211">통화 수신기의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-211">IP Address of the call receiver.</span></span> <span data-ttu-id="64fc3-212">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64fc3-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-214">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-215">통화 수신기에서 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-217">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-217">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-218">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-219">수신자의 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-219">Subnet of callee.</span></span> <span data-ttu-id="64fc3-220">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64fc3-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-222">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-223">1은 통화 수신자가 회사 네트워크 내에 있음을 의미 하 고 0은 통화 수신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-225">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-225">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-226">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-227">수신자 Mac 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-227">Callee Mac address.</span></span> <span data-ttu-id="64fc3-228"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-230">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-230">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-231">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-232">통화 수신기에서 사용 하는 A/V에 지 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="64fc3-233">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64fc3-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-235">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-236">A/V에 지 서비스에서 통화 수신기에 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-238">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-238">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-239">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-240">통화 수신기에서 사용 되는 캡처 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="64fc3-241"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-243">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-243">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-244">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-245">통화 수신기에서 사용 하는 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-245">Render device used by the call receiver.</span></span> <span data-ttu-id="64fc3-246"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-248">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-248">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-249">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-250">통화 수신기의 캡처 장치에 대 한 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="64fc3-251"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-253">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="64fc3-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64fc3-254">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-255">통화 수신기의 렌더 장치에 대 한 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="64fc3-256"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="64fc3-259">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-260">수신자가 네트워크에 연결 된 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="64fc3-261">값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="64fc3-262">WiFi 연결의 경우 유선 연결의 1에 대 한 일반적인 값은 0입니다. 및 3은 이더넷 연결용입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-264">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-264">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-265">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-266">무선이 사용 되는 경우 수신자의 BSSID입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="64fc3-267"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 (</a>~) 테이블에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-269">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-270">통화 수신기의 링크입니다. 1은 VPN (가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-272">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="64fc3-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-273">통화 수신기의 끝점에 대 한 네트워크 연결 속도 (bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-275">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="64fc3-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-276">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="64fc3-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-278">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-279">다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)에 따라 지정 된 보내기 쪽 스트림에 실제 대역폭이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="64fc3-280">이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="64fc3-281">이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-283">smallint</span><span class="sxs-lookup"><span data-stu-id="64fc3-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-284">적용 되는 대역폭 캡의 출처입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="64fc3-285">또한 대역폭 제한이 전송 되는 위치 ("정책 서버", "서버 설정", "모달" 등)를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="64fc3-286"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-287"><strong>최초</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-288">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-289">발신자의 메트릭이 수신 되었는지 여부를 나타냅니다. 1이 예 이면 null 값은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-290"><strong>피호출자</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-291">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="64fc3-292">통화 수신기에서 메트릭을 받았는지 여부를 나타냅니다. 1이 예 이면 null 값은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-294">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-295">보고서가 세션의 일부 또는 전체 세션에 대 한 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="64fc3-296">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-298">비트만</span><span class="sxs-lookup"><span data-stu-id="64fc3-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-299">통화가 불량 통화 (값 1) 또는 정상 통화 (0)로 분류 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="64fc3-300">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="64fc3-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-303">발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="64fc3-304">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="64fc3-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64fc3-307">발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="64fc3-308">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-310">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-310">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-311">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-312">통화를 시작한 사용자의 재귀 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="64fc3-313">NAT (네트워크 주소 변환)를 사용 하는 조직에서는 재귀 IP 주소가 프록시 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="64fc3-314">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-316">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-316">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-317">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-318">통화를 시작한 사용자가 사용한 WiFi 드라이버에 대 한 장치 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="64fc3-319">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-321">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-321">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-322">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-323">통화를 시작한 사용자가 사용한 WiFi 드라이버의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="64fc3-324">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-326">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-326">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-327">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-328">통화를 받은 사용자의 재귀 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="64fc3-329">NAT (네트워크 주소 변환)를 사용 하는 조직에서는 재귀 IP 주소가 프록시 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="64fc3-330">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64fc3-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-332">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-332">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-333">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-334">통화를 받은 사용자가 사용한 WiFi 드라이버에 대 한 장치 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="64fc3-335">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64fc3-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="64fc3-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="64fc3-337">int</span><span class="sxs-lookup"><span data-stu-id="64fc3-337">int</span></span></p></td>
<td><p><span data-ttu-id="64fc3-338">외부</span><span class="sxs-lookup"><span data-stu-id="64fc3-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64fc3-339">통화를 받은 사용자가 사용한 WiFi 드라이버의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="64fc3-340">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64fc3-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

