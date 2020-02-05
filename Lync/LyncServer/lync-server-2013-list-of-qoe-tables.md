---
title: 'Lync Server 2013: QoE 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="5af26-102">Lync Server 2013의 QoE 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="5af26-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af26-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5af26-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5af26-104">데이터베이스 스키마는 다음 테이블로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="5af26-105">**지원 테이블**</span><span class="sxs-lookup"><span data-stu-id="5af26-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5af26-106"><strong>테이블로</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="5af26-107"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5af26-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013의 AppSharingMetricsThreshold 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-109">응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 대해 최적 및 허용 가능한 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-110"><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-111">고유 코덱 식별자를 해당 하는 코덱에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-112"><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-113">환경 데이터베이스의 다른 위치에서 사용 되는 고유한 IP 주소 식별자에 IP 주소를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013의 NetworkConnectionDetail 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-115">네트워크 연결 형식을 경력 데이터베이스의 다른 곳에 사용 되는 네트워크 연결 식별자에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013의 PurgeSettings 테이블 (체감 품질)</a></span><span class="sxs-lookup"><span data-stu-id="5af26-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-117">오래 된 경력 품질 레코드가 체감 품질 데이터베이스에서 자동으로 삭제 되는지 여부를 지정 하는 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-118"><a href="lync-server-2013-traceroute-table.md">Lync Server 2013의 TraceRoute 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-119">통화에 대 한 라우팅 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 UserAgentDef 테이블 (체감 품질)</a></span><span class="sxs-lookup"><span data-stu-id="5af26-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-121">사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-122"><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013의 VideoMetricsThreshold 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-123">영상 통화에 사용 되는 경험 메트릭의 품질 기준에 대 한 최적 및 허용 가능한 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-124"><a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-125">오디오 및 비디오 세션에 사용 되는 SIP (세션 초기화 프로토콜) 및 ua (Session User Agent) 문자열 및 UA 형식을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-126"><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-127">오디오 및 비디오 세션에 사용 되는 사용자, 회의 및 전화 Uri를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-128"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-129">오디오 및 비디오 세션에 참가 하는 끝점의 FQDN 컴퓨터 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-130"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-131">메트릭 데이터가 속한 풀의 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-132"><a href="lync-server-2013-device-table.md">Lync Server 2013의 Device 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-133">오디오/비디오 통화에 사용 되는 캡처 장치 및 렌더링 장치를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-134"><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013의 DeviceDriver 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-135">캡처 디바이스의 드라이버와 오디오/비디오 통화에 사용 되는 렌더링 장치를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-136"><a href="lync-server-2013-conference-table.md">Lync Server 2013의 Conference 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-137">다른 시나리오의 경우 컨퍼런스 시나리오 또는 DialogID 용 전화 회의 Uri를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-138"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 SessionCorrelation 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-139">PSTN 통화에 대 한 CorrelationID을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-140"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-141">오디오/비디오 통화에 사용 되는 코덱을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013의 AppliedBandwidthSource 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-143">오디오/비디오 통화에 사용 되는 대역폭 원본을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-144"><a href="lync-server-2013-macaddress-table.md">Lync Server 2013의 MacAddress 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-145">오디오 및 비디오 세션에 참가 하는 끝점의 MAC 주소를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-146"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-147">오디오 및 비디오 세션의 대화 상자 ID를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-148"><a href="lync-server-2013-region-table.md">Lync Server 2013의 Region 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-149">NC 설정에 정의 된 네트워크 지역을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-150"><a href="lync-server-2013-usersite-table.md">Lync Server 2013의 UserSite 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-151">NC 설정에 정의 된 네트워크 사이트를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-152"><a href="lync-server-2013-subnet-table.md">Lync Server 2013의 Subnet 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-153">NC 설정에 정의 된 서브넷을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-154"><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013의 MonitoredRegionLink 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-155">NC 설정에 정의 된 지역 링크를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-157">NC 설정에 정의 된 네트워크 사이트 링크를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-158"><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013의 EndpointSubnet 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-159">오디오 및 비디오 세션에 참여 하는 끝점의 서브넷을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-160"><a href="lync-server-2013-server-table.md">Lync Server 2013의 Server 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-161">미디어가 거치는 서버의 FQDN 또는 IP 주소를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5af26-162">**메트릭 데이터 테이블**</span><span class="sxs-lookup"><span data-stu-id="5af26-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5af26-163"><strong>테이블로</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="5af26-164"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5af26-165"><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013의 AppSharingStream 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-166">응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭의 품질 기준을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="5af26-167">응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭의 품질 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-168"><a href="lync-server-2013-session-table.md">Lync Server 2013의 Session 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-169">오디오 또는 오디오/비디오 세션에 대 한 전체 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="5af26-170">세션은 두 끝점 간의 오디오 또는 비디오 SIP 대화 상자로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-171"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 MediaLine 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-172">세션의 각 미디어 라인에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="5af26-173">미디어 선은 하나 이상의 오디오 및 비디오 스트림 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="5af26-174">일반적으로 단일 미디어 회선에는 두 개의 스트림 (오디오 또는 비디오)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-175"><a href="lync-server-2013-audiostream-table.md">Lync Server 2013의 AudioStream 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-176">미디어 라인에 각 오디오 스트림에 대 한 오디오 미디어 품질 메트릭을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-177"><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013의 AudioSignal 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-178">미디어 라인에 오디오 미디어 품질 메트릭을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="5af26-179">여기에는 AEC (음향 반향 제거) 및 AGC (자동 게인 제어) 메트릭이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-180"><a href="lync-server-2013-videostream-table.md">Lync Server 2013의 VideoStream 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-181">미디어 라인의 각 오디오 스트림에 대 한 비디오 미디어 품질 기준을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-182"><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013의 AudioClientEvent 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-183">클라이언트 이벤트에서 수집 된 오디오 미디어 품질 메트릭을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-184"><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013의 VideoClientEvent 테이블</a></span><span class="sxs-lookup"><span data-stu-id="5af26-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5af26-185">클라이언트 이벤트에서 수집 된 비디오 미디어 품질 메트릭을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-186"><strong>DiagnosticData 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-187">내부용 으로만 사용 되는 진단 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5af26-188">**요약 데이터 표**</span><span class="sxs-lookup"><span data-stu-id="5af26-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5af26-189"><strong>테이블로</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="5af26-190"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5af26-191"><strong>ServerSummary 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-192">서버에 대 한 요약 데이터를 저장 하 고, 이러한 데이터는 경력 (체감 품질) 보고용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-193"><strong>UserSummary 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-194">사용자에 대 한 요약 데이터를 저장 하 고, 이러한 데이터는 체감 품질 보고에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-195"><strong>Call유형 Ummary 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-196">통화 형식에 대 한 요약 데이터를 저장 하는 경우 이러한 데이터는 체감 품질 보고에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5af26-197">**모니터링 서버에서 내부용으로 사용 되는 테이블**</span><span class="sxs-lookup"><span data-stu-id="5af26-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5af26-198"><strong>테이블로</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="5af26-199"><strong>설명</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5af26-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-201">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-203">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-204"><strong>프런트 엔드 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-205">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-206"><strong>작업 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-207">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-209">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-211">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-213">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-215">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-217">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-218"><strong>시간대</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-219">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-220"><strong>CallSummary 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-221">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-222"><strong>DeviceCallSumary 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-223">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-224"><strong>테 넌 트 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-225">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af26-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-227">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af26-228"><strong>Ascall요약 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="5af26-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af26-229">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5af26-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

