---
title: 'Lync Server 2013: MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="8ac79-102">Lync Server 2013의 MediaLine</span><span class="sxs-lookup"><span data-stu-id="8ac79-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ac79-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8ac79-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8ac79-104">MediaLine는 데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="8ac79-105">일반적으로 하나의 오디오 세션에 오디오 미디어 선이 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="8ac79-106">하나의 오디오 및 비디오 (A/V) 세션에는 일반적으로 오디오 미디어 회선 하 나와 비디오 미디어 라인 하나가 포함 됩니다. 그러나 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우에는 세션에 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="8ac79-107">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ac79-108">열</span><span class="sxs-lookup"><span data-stu-id="8ac79-108">Column</span></span></th>
<th><span data-ttu-id="8ac79-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8ac79-109">Data Type</span></span></th>
<th><span data-ttu-id="8ac79-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="8ac79-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="8ac79-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="8ac79-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="8ac79-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="8ac79-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="8ac79-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="8ac79-115">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-115">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-116"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="8ac79-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="8ac79-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ac79-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ac79-119"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8ac79-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8ac79-121">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-121">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-122">호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="8ac79-123">자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac79-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8ac79-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8ac79-125">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-125">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-126">호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="8ac79-127">자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac79-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-128">보안</span><span class="sxs-lookup"><span data-stu-id="8ac79-128">Security</span></span></p></td>
<td><p><span data-ttu-id="8ac79-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ac79-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ac79-130">사용 중인 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="8ac79-130">Security profile in use.</span></span> <span data-ttu-id="8ac79-131">0은 없음, 1은 SRTP, 2는 V1입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-132">운송</span><span class="sxs-lookup"><span data-stu-id="8ac79-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="8ac79-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ac79-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ac79-134">전송 종류.</span><span class="sxs-lookup"><span data-stu-id="8ac79-134">Transport type.</span></span> <span data-ttu-id="8ac79-135">0은 UDP이 고, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="8ac79-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8ac79-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-138">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-138">IP address of the caller.</span></span> <span data-ttu-id="8ac79-139">IPv4 또는 IPv6 주소 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="8ac79-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="8ac79-141">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-141">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-142">호출자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="8ac79-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="8ac79-144">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-144">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-145">호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="8ac79-146">1은 호출자가 엔터프라이즈 네트워크 내에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="8ac79-147">0은 호출자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="8ac79-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="8ac79-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-150">발신자가 사용 하는 네트워크 인터페이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8ac79-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8ac79-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-153">발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="8ac79-154">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac79-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="8ac79-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8ac79-156">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-156">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-157">호출자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="8ac79-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8ac79-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-160">A/V Edge 서비스에서 보고 한 발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="8ac79-161">이 주소는 클라이언트가 NAT 뒤에 있는 경우 CallerIPAddr와 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8ac79-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8ac79-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-164">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="8ac79-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8ac79-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-167">발신자의 렌더링 장치 이름.</span><span class="sxs-lookup"><span data-stu-id="8ac79-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8ac79-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8ac79-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-170">발신자의 캡처 장치 드라이버 이름.</span><span class="sxs-lookup"><span data-stu-id="8ac79-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="8ac79-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8ac79-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-173">호출자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="8ac79-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="8ac79-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="8ac79-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="8ac79-176">발신자의 Wifi 드라이버 설명.</span><span class="sxs-lookup"><span data-stu-id="8ac79-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="8ac79-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="8ac79-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-179">발신자의 Wifi 드라이버 버전.</span><span class="sxs-lookup"><span data-stu-id="8ac79-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="8ac79-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="8ac79-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-182">호출자의 네트워크 연결에 대 한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-182">Details of caller’s network connection.</span></span> <span data-ttu-id="8ac79-183">자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac79-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="8ac79-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="8ac79-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-186">발신자 WiFi 연결에 사용 되는 기본 서비스 설정 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="8ac79-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="8ac79-188">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-188">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-189">호출자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="8ac79-190">1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="8ac79-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8ac79-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-193">호출 수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-193">IP address of the callee.</span></span> <span data-ttu-id="8ac79-194">IPv4 또는 IPv6 주소 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="8ac79-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="8ac79-196">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-196">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-197">호출 수신자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="8ac79-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="8ac79-199">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-199">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-200">호출 수신자가 엔터프라이즈 네트워크 내에 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="8ac79-201">1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="8ac79-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="8ac79-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-204">호출 수신자가 사용 하는 네트워크 인터페이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8ac79-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8ac79-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-207">호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="8ac79-208">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac79-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="8ac79-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8ac79-210">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-210">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-211">호출 수신자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-212">Callere| Iveipaddr</span><span class="sxs-lookup"><span data-stu-id="8ac79-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8ac79-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-214">A/V Edge 서비스에서 보고 한 호출 수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="8ac79-215">이 주소는 클라이언트가 NAT 뒤에 있는 경우 CalleeIPAddr와 같이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8ac79-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8ac79-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="8ac79-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-218">호출 수신자의 캡처 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="8ac79-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8ac79-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-221">피호출자의 렌더링 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8ac79-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8ac79-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-224">피호출자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="8ac79-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8ac79-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-227">피호출자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="8ac79-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="8ac79-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-230">호출 수신자의 Wifi 드라이버 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="8ac79-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="8ac79-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="8ac79-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="8ac79-233">피호출자의 Wifi 드라이버 버전.</span><span class="sxs-lookup"><span data-stu-id="8ac79-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="8ac79-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="8ac79-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-236">호출 수신자의 네트워크 연결에 대 한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-236">Details of callee’s network connection.</span></span> <span data-ttu-id="8ac79-237">자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 Networkconnectiondetail 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ac79-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="8ac79-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="8ac79-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-240">피호출자의 WiFi 연결에 사용 되는 기본 서비스 집합 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="8ac79-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="8ac79-242">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-242">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-243">호출 수신자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="8ac79-244">1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="8ac79-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="8ac79-246">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8ac79-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-247">오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</span><span class="sxs-lookup"><span data-stu-id="8ac79-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="8ac79-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-249">int</span><span class="sxs-lookup"><span data-stu-id="8ac79-249">int</span></span></p></td>
<td><p><span data-ttu-id="8ac79-250">다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="8ac79-251">대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="8ac79-252">이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="8ac79-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="8ac79-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8ac79-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8ac79-255">적용 되는 대역폭 캡의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="8ac79-256">대역폭 한도가 시작 되는 위치를 설명 합니다 (예: "정책 서버", "서버 설정" 또는 "모달").</span><span class="sxs-lookup"><span data-stu-id="8ac79-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-257">호출인</span><span class="sxs-lookup"><span data-stu-id="8ac79-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="8ac79-258">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-258">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-259">호출자의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, 0은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-260">피호출자</span><span class="sxs-lookup"><span data-stu-id="8ac79-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="8ac79-261">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-261">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-262">통화 수신기의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, 0은 no입니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="8ac79-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="8ac79-264">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-264">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-265">보고서가 통화 일부 인지 또는 전체 통화에 대 한 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="8ac79-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="8ac79-267">다소</span><span class="sxs-lookup"><span data-stu-id="8ac79-267">bit</span></span></p></td>
<td><p><span data-ttu-id="8ac79-268">통화가 불량 통화 (1) 또는 좋은 통화 (0)로 분류 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ac79-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="8ac79-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="8ac79-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ac79-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ac79-271">발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ac79-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="8ac79-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="8ac79-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ac79-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ac79-274">사용자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ac79-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

