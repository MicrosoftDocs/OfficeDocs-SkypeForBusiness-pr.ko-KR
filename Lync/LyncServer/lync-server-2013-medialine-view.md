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
ms.openlocfilehash: 5c6e5fd3c1afe27bc1baa8790527ee239bdba990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="68915-102">Lync Server 2013의 MediaLine</span><span class="sxs-lookup"><span data-stu-id="68915-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68915-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="68915-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="68915-104">미디어 회선 보기에는 데이터베이스의 각 미디어 회선에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="68915-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="68915-105">하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="68915-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="68915-106">하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68915-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="68915-107">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="68915-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68915-108">열</span><span class="sxs-lookup"><span data-stu-id="68915-108">Column</span></span></th>
<th><span data-ttu-id="68915-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="68915-109">Data Type</span></span></th>
<th><span data-ttu-id="68915-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="68915-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68915-111">Conferencedatetime이 동일할</span><span class="sxs-lookup"><span data-stu-id="68915-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="68915-112">datetime</span><span class="sxs-lookup"><span data-stu-id="68915-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="68915-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68915-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="68915-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="68915-115">int</span><span class="sxs-lookup"><span data-stu-id="68915-115">int</span></span></p></td>
<td><p><span data-ttu-id="68915-116"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68915-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="68915-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="68915-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="68915-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68915-119"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68915-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="68915-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="68915-121">int</span><span class="sxs-lookup"><span data-stu-id="68915-121">int</span></span></p></td>
<td><p><span data-ttu-id="68915-p102">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="68915-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="68915-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="68915-125">int</span><span class="sxs-lookup"><span data-stu-id="68915-125">int</span></span></p></td>
<td><p><span data-ttu-id="68915-p103">수신자에 대해 비트 플래그로 설명되는 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="68915-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-128">보안</span><span class="sxs-lookup"><span data-stu-id="68915-128">Security</span></span></p></td>
<td><p><span data-ttu-id="68915-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="68915-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68915-p104">사용 중인 보안 프로필입니다. 0은 NONE, 1은 SRTP, 2는 V1입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-132">전송</span><span class="sxs-lookup"><span data-stu-id="68915-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="68915-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="68915-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68915-p105">전송 유형입니다. 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="68915-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="68915-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-p106">발신자의 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="68915-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="68915-141">int</span><span class="sxs-lookup"><span data-stu-id="68915-141">int</span></span></p></td>
<td><p><span data-ttu-id="68915-142">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="68915-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="68915-144">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-144">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-p107">발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 발신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 발신자가 네트워크 외부에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-148">CallerMacAddress가)</span><span class="sxs-lookup"><span data-stu-id="68915-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="68915-149">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-150">발신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="68915-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="68915-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-153">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="68915-154">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68915-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="68915-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="68915-156">int</span><span class="sxs-lookup"><span data-stu-id="68915-156">int</span></span></p></td>
<td><p><span data-ttu-id="68915-157">A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="68915-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="68915-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-160">A/V 에지 서비스에서 보고한 발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="68915-161">클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CallerIPAddr과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68915-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="68915-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="68915-163">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-164">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="68915-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="68915-166">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-167">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="68915-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="68915-169">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-170">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="68915-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="68915-172">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-173">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="68915-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="68915-175">varchar (256</span><span class="sxs-lookup"><span data-stu-id="68915-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="68915-176">발신자의 Wi-Fi 드라이버 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="68915-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="68915-178">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-179">발신자의 Wi-Fi 드라이버 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="68915-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="68915-181">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-182">발신자의 네트워크 연결 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-182">Details of caller’s network connection.</span></span> <span data-ttu-id="68915-183">자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013에서 Networkconnectiondetail 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68915-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="68915-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="68915-185">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-186">발신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="68915-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="68915-188">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-188">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-p111">발신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="68915-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="68915-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-193">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-193">IP address of the callee.</span></span> <span data-ttu-id="68915-194">IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68915-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="68915-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="68915-196">int</span><span class="sxs-lookup"><span data-stu-id="68915-196">int</span></span></p></td>
<td><p><span data-ttu-id="68915-197">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="68915-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="68915-199">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-199">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-p113">수신자가 엔터프라이즈 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 수신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 수신자가 네트워크 외부에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="68915-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="68915-203">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-204">수신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="68915-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="68915-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-207">수신자가 사용하는 A/V 에지 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="68915-208">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68915-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="68915-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="68915-210">int</span><span class="sxs-lookup"><span data-stu-id="68915-210">int</span></span></p></td>
<td><p><span data-ttu-id="68915-211">A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-212">Callere과, Iveipaddr</span><span class="sxs-lookup"><span data-stu-id="68915-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="68915-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-214">A/V 에지 서비스에서 보고한 수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="68915-215">클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CalleeIPAddr과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68915-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="68915-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="68915-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="68915-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="68915-218">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="68915-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="68915-220">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-221">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="68915-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="68915-223">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-224">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="68915-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="68915-226">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-227">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="68915-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="68915-229">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-230">수신자의 Wi-Fi 드라이버 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="68915-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="68915-232">varchar (256</span><span class="sxs-lookup"><span data-stu-id="68915-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="68915-233">수신자의 Wi-Fi 드라이버 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="68915-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="68915-235">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-236">수신자의 네트워크 연결 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-236">Details of callee’s network connection.</span></span> <span data-ttu-id="68915-237">자세한 내용은 <a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013에서 Networkconnectiondetail 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68915-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="68915-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="68915-239">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-240">수신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="68915-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="68915-242">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-242">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-p117">수신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="68915-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="68915-246">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="68915-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="68915-247">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="68915-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="68915-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="68915-249">int</span><span class="sxs-lookup"><span data-stu-id="68915-249">int</span></span></p></td>
<td><p><span data-ttu-id="68915-p118">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신 쪽 스트림에 적용되는 실제 대역폭입니다. 대역폭 예상치에 따라 유효 대역폭은 더 낮을 수 있으므로 이 대역폭을 유효 대역폭과 혼동해서는 안 됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="68915-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="68915-254">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="68915-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68915-p119">적용 중인 대역폭의 원본입니다. 이 원본은 대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN 서버" 또는 "형식")를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68915-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-257">최초</span><span class="sxs-lookup"><span data-stu-id="68915-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="68915-258">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-258">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-259">발신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-260">피호출자</span><span class="sxs-lookup"><span data-stu-id="68915-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="68915-261">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-261">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-262">통화 수신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.</span><span class="sxs-lookup"><span data-stu-id="68915-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="68915-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="68915-264">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-264">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-265">보고서가 통화의 일부분에 대한 것인지 전체 통화에 대한 것인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68915-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="68915-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="68915-267">비트만</span><span class="sxs-lookup"><span data-stu-id="68915-267">bit</span></span></p></td>
<td><p><span data-ttu-id="68915-268">통화가 불량 통화(1)로 분류되었는지 양호한 통화(0)로 분류되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68915-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68915-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="68915-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="68915-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="68915-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68915-271">발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68915-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68915-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="68915-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="68915-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="68915-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68915-274">전화를 건 사용자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68915-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

