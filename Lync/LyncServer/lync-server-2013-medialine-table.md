---
title: 'Lync Server 2013: MediaLine 테이블'
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
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="62fc5-102">Lync Server 2013의 MediaLine 테이블</span><span class="sxs-lookup"><span data-stu-id="62fc5-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62fc5-103">_**마지막으로 수정한 주제:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="62fc5-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="62fc5-104">각 레코드는 하나의 미디어 회선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-104">Each record represents one media line.</span></span> <span data-ttu-id="62fc5-105">(하나의 오디오 세션에는 일반적으로 하나의 오디오 미디어 회선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="62fc5-106">회의 장치를 사용 하는 경우 또는 갤러리 보기를 사용 하는 경우 한 오디오 및 비디오 (A/V) 세션에는 일반적으로 하나의 오디오 미디어 회선 및 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62fc5-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="62fc5-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="62fc5-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="62fc5-110"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="62fc5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="62fc5-113">주요한</span><span class="sxs-lookup"><span data-stu-id="62fc5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="62fc5-114"><a href="lync-server-2013-session-table.md">Lync Server 2013의 세션 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-116">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-116">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-117">주요한</span><span class="sxs-lookup"><span data-stu-id="62fc5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="62fc5-118"><a href="lync-server-2013-session-table.md">Lync Server 2013의 세션 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="62fc5-121">주요한</span><span class="sxs-lookup"><span data-stu-id="62fc5-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="62fc5-122">0은 기본 오디오, 1은 기본 비디오, 2는 파노라마 비디오, 3은 응용 프로그램/데스크톱 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="62fc5-123">이 레이블은 단일 세션 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-126">이 열은 현재 있지만 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="62fc5-127">미디어 줄에 사용 되는 연결에 대 한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-129">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-130">Bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="62fc5-131">자세한 내용은 다운로드 가능한 <em>경험 치 모니터링 서버 프로토콜 사양을</em>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-133">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-134">CallerIceWarningFlags와 동일 하지만 호출 수신자 측에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="62fc5-135">자세한 내용은 다운로드 가능한 <em>경험 치 모니터링 서버 프로토콜 사양을</em>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-136"><strong>보안</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-138">사용 중인 보안 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-138">The security profile in use.</span></span> <span data-ttu-id="62fc5-139">0은 없음, 1은 SRTP, 2는 V1입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-140"><strong>운송</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-142">0은 UDP이 고, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-144">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-144">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-145">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-146">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-146">IP Address of the caller.</span></span> <span data-ttu-id="62fc5-147">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-149">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-150">호출자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-152">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-152">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-153"> 외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-154">호출자의 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-154">The subnet of the caller.</span></span> <span data-ttu-id="62fc5-155">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-157">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-158">1은 발신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 발신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-160">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-160">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-161">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-162"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의</a>로이 테이블에서 참조 하는 발신자의 mac 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-164">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-164">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-165">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-166">발신자가 사용 하는 Lync Server A/V Edge 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="62fc5-167">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-169">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-170">발신자에의 한 A/V Edge 서비스에 사용 되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-172">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-172">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-173">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-174">호출자가 사용 하는 캡처 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-174">Capture device used by the caller.</span></span> <span data-ttu-id="62fc5-175"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-177">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-177">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-178">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-179">발신자에 사용 된 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-179">Render device used by caller.</span></span> <span data-ttu-id="62fc5-180"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-182">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-182">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-183">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-184"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 되는 호출자 캡처 디바이스의 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-186">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-186">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-187">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-188"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 Devicedriver 테이블</a>에서 참조 하는 호출자의 렌더 디바이스 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="62fc5-191">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-192">발신자가 네트워크에 연결 되는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="62fc5-193">값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="62fc5-194">WiFi 연결에 대 한 유선 연결의 경우 일반적으로 값은 0이 고, 그렇지 않으면-1입니다. 이더넷 연결의 경우 3.</span><span class="sxs-lookup"><span data-stu-id="62fc5-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-196">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-196">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-197">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-198">무선이 사용 되는 경우 발신자의 BSSID입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="62fc5-199"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의</a>로이 테이블에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-201">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-202">호출자의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-202">The caller's link.</span></span> <span data-ttu-id="62fc5-203">1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-205">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="62fc5-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-206">호출자 끝점에 대 한 bps의 네트워크 링크 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-208">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-208">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-209">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-210">통화 수신기의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-210">IP Address of the call receiver.</span></span> <span data-ttu-id="62fc5-211">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-213">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-214">전화 수신기에서 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-215"><strong>Calleesnet</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-216">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-216">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-217">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-218">호출 수신자의 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-218">Subnet of callee.</span></span> <span data-ttu-id="62fc5-219">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-221">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-222">1은 통화 수신기가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 전화 수신기가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-224">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-224">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-225">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-226">호출 수신자 Mac 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-226">Callee Mac address.</span></span> <span data-ttu-id="62fc5-227"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의로이 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-229">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-229">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-230">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-231">통화 수신기에서 사용 하는 A/V Edge 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="62fc5-232">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="62fc5-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-234">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-235">전화 수신기에 의해 A/V에 지 서비스에 사용 되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-237">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-237">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-238">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-239">호출 수신자가 사용 하는 캡처 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="62fc5-240"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-242">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-242">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-243">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-244">통화 수신기에 사용 되는 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-244">Render device used by the call receiver.</span></span> <span data-ttu-id="62fc5-245"><a href="lync-server-2013-device-table.md">Lync Server 2013의 장치 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-247">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-247">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-248">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-249">전화 수화기 캡처 장치용 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="62fc5-250"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013에서 Devicedriver 테이블</a>에서 참조 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-252">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="62fc5-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="62fc5-253">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-254">통화 수신기의 렌더링 장치 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="62fc5-255"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013에서 Devicedriver 테이블</a>에서 참조 했습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="62fc5-258">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-259">호출 수신자가 네트워크에 연결 되는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="62fc5-260">값은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a>에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="62fc5-261">WiFi 연결에 대 한 유선 연결의 경우 일반적으로 값은 0이 고, 그렇지 않으면-1입니다. 이더넷 연결의 경우 3.</span><span class="sxs-lookup"><span data-stu-id="62fc5-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-263">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-263">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-264">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-265">무선이 사용 되는 경우 피호출자의 BSSID입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="62fc5-266"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의</a>로이 테이블에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-268">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-269">전화 수화기의 링크입니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-271">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="62fc5-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-272">통화 수신기의 끝점에 대 한 bps의 네트워크 링크 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-274">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="62fc5-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-275">오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</span><span class="sxs-lookup"><span data-stu-id="62fc5-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-277">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-278">다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)이 지정 된 지정 된 보내기 쪽 스트림에 적용 되는 실제 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="62fc5-279">대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="62fc5-280">이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-282">smallint</span><span class="sxs-lookup"><span data-stu-id="62fc5-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-283">적용 되는 대역폭 cap의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="62fc5-284">이는 대역폭 한도가 어디에서 오는지 ("정책 서버", "서버 켜기", "모달" 등)를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="62fc5-285"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-286"><strong>호출인</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-287">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-288">호출자의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, null 값은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-289"><strong>피호출자</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-290">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="62fc5-291">통화 수신기의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, null 값은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-293">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-294">보고서가 세션의 일부 인지 또는 전체 세션에 대 한 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="62fc5-295">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-297">다소</span><span class="sxs-lookup"><span data-stu-id="62fc5-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-298">통화가 불량 통화 (값 1) 또는 좋은 통화 (0)로 분류 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="62fc5-299">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="62fc5-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-302">발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="62fc5-303">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="62fc5-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62fc5-306">발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="62fc5-307">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-309">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-309">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-310">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-311">통화를 설정한 사용자의 재귀 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="62fc5-312">NAT (네트워크 주소 변환)를 사용 하는 조직에서 재귀 IP 주소는 프록시 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="62fc5-313">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-315">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-315">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-316">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-317">통화를 설정한 사용자가 사용 하는 WiFi 드라이버에 대 한 디바이스 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="62fc5-318">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-320">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-320">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-321">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-322">통화를 설정한 사용자가 사용 하는 WiFi 드라이버의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="62fc5-323">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-325">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-325">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-326">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-327">통화를 받은 사용자의 재귀 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="62fc5-328">NAT (네트워크 주소 변환)를 사용 하는 조직에서 재귀 IP 주소는 프록시 서버의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="62fc5-329">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62fc5-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-331">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-331">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-332">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-333">통화를 받은 사용자가 사용 하는 WiFi 드라이버에 대 한 디바이스 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="62fc5-334">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62fc5-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="62fc5-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="62fc5-336">int</span><span class="sxs-lookup"><span data-stu-id="62fc5-336">int</span></span></p></td>
<td><p><span data-ttu-id="62fc5-337">외부</span><span class="sxs-lookup"><span data-stu-id="62fc5-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62fc5-338">통화를 받은 사용자가 사용 하는 WiFi 드라이버의 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="62fc5-339">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62fc5-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

