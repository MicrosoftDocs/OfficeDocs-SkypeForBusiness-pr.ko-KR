---
title: 'Lync Server 2013: MediaLine'
description: 'Lync Server 2013: 미디어 보기입니다.'
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568684"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="1122c-103">Lync Server 2013의 MediaLine</span><span class="sxs-lookup"><span data-stu-id="1122c-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1122c-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1122c-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1122c-105">미디어 회선 보기에는 데이터베이스의 각 미디어 회선에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="1122c-106">하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="1122c-107">하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="1122c-108">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1122c-109">열</span><span class="sxs-lookup"><span data-stu-id="1122c-109">Column</span></span></th>
<th><span data-ttu-id="1122c-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1122c-110">Data Type</span></span></th>
<th><span data-ttu-id="1122c-111">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1122c-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1122c-112">Conferencedatetime이 동일할</span><span class="sxs-lookup"><span data-stu-id="1122c-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="1122c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1122c-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="1122c-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="1122c-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="1122c-116">int</span><span class="sxs-lookup"><span data-stu-id="1122c-116">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="1122c-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="1122c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="1122c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1122c-120"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="1122c-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="1122c-122">int</span><span class="sxs-lookup"><span data-stu-id="1122c-122">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-p102">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122c-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="1122c-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="1122c-126">int</span><span class="sxs-lookup"><span data-stu-id="1122c-126">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-p103">수신자에 대해 비트 플래그로 설명되는 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122c-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-129">보안</span><span class="sxs-lookup"><span data-stu-id="1122c-129">Security</span></span></p></td>
<td><p><span data-ttu-id="1122c-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="1122c-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1122c-p104">사용 중인 보안 프로필입니다. 0은 NONE, 1은 SRTP, 2는 V1입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-133">전송</span><span class="sxs-lookup"><span data-stu-id="1122c-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="1122c-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="1122c-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1122c-p105">전송 유형입니다. 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="1122c-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1122c-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-p106">발신자의 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="1122c-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="1122c-142">int</span><span class="sxs-lookup"><span data-stu-id="1122c-142">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-143">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="1122c-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="1122c-145">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-145">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-p107">발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 발신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 발신자가 네트워크 외부에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-149">CallerMacAddress가)</span><span class="sxs-lookup"><span data-stu-id="1122c-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="1122c-150">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-151">발신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="1122c-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1122c-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-154">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="1122c-155">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1122c-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="1122c-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="1122c-157">int</span><span class="sxs-lookup"><span data-stu-id="1122c-157">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-158">A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="1122c-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1122c-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-161">A/V 에지 서비스에서 보고한 발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="1122c-162">클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CallerIPAddr과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="1122c-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="1122c-164">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-165">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="1122c-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="1122c-167">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-168">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="1122c-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1122c-170">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-171">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="1122c-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1122c-173">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-174">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="1122c-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="1122c-176">varchar (256</span><span class="sxs-lookup"><span data-stu-id="1122c-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="1122c-177">발신자의 Wi-Fi 드라이버 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="1122c-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="1122c-179">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-180">발신자의 Wi-Fi 드라이버 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="1122c-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="1122c-182">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-183">발신자의 네트워크 연결 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-183">Details of caller’s network connection.</span></span> <span data-ttu-id="1122c-184">자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013에서 Networkconnectiondetail 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122c-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="1122c-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="1122c-186">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-187">발신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="1122c-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="1122c-189">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-189">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-p111">발신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="1122c-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1122c-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-194">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-194">IP address of the callee.</span></span> <span data-ttu-id="1122c-195">IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="1122c-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="1122c-197">int</span><span class="sxs-lookup"><span data-stu-id="1122c-197">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-198">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="1122c-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="1122c-200">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-200">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-p113">수신자가 엔터프라이즈 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 수신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 수신자가 네트워크 외부에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="1122c-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="1122c-204">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-205">수신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="1122c-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1122c-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-208">수신자가 사용하는 A/V 에지 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="1122c-209">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1122c-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="1122c-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="1122c-211">int</span><span class="sxs-lookup"><span data-stu-id="1122c-211">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-212">A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-213">Callere과, Iveipaddr</span><span class="sxs-lookup"><span data-stu-id="1122c-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="1122c-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-215">A/V 에지 서비스에서 보고한 수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="1122c-216">클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CalleeIPAddr과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="1122c-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="1122c-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="1122c-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="1122c-219">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="1122c-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="1122c-221">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-222">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="1122c-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1122c-224">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-225">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="1122c-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="1122c-227">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-228">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="1122c-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="1122c-230">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-231">수신자의 Wi-Fi 드라이버 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="1122c-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="1122c-233">varchar (256</span><span class="sxs-lookup"><span data-stu-id="1122c-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="1122c-234">수신자의 Wi-Fi 드라이버 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="1122c-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="1122c-236">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-237">수신자의 네트워크 연결 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-237">Details of callee’s network connection.</span></span> <span data-ttu-id="1122c-238">자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013에서 Networkconnectiondetail 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1122c-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="1122c-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="1122c-240">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-241">수신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="1122c-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="1122c-243">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-243">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-p117">수신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="1122c-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="1122c-247">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="1122c-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="1122c-248">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="1122c-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="1122c-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="1122c-250">int</span><span class="sxs-lookup"><span data-stu-id="1122c-250">int</span></span></p></td>
<td><p><span data-ttu-id="1122c-p118">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신 쪽 스트림에 적용되는 실제 대역폭입니다. 대역폭 예상치에 따라 유효 대역폭은 더 낮을 수 있으므로 이 대역폭을 유효 대역폭과 혼동해서는 안 됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="1122c-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="1122c-255">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1122c-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1122c-p119">적용 중인 대역폭의 원본입니다. 이 원본은 대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN 서버" 또는 "형식")를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-258">최초</span><span class="sxs-lookup"><span data-stu-id="1122c-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="1122c-259">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-259">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-260">발신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-261">피호출자</span><span class="sxs-lookup"><span data-stu-id="1122c-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="1122c-262">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-262">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-263">통화 수신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="1122c-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="1122c-265">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-265">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-266">보고서가 통화의 일부분에 대한 것인지 전체 통화에 대한 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="1122c-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="1122c-268">비트만</span><span class="sxs-lookup"><span data-stu-id="1122c-268">bit</span></span></p></td>
<td><p><span data-ttu-id="1122c-269">통화가 불량 통화(1)로 분류되었는지 양호한 통화(0)로 분류되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1122c-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="1122c-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="1122c-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="1122c-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1122c-272">발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1122c-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="1122c-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="1122c-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="1122c-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1122c-275">전화를 건 사용자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1122c-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

