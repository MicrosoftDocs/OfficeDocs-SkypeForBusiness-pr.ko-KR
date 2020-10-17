---
title: 'Lync Server 2013: CDR 테이블 목록'
description: 'Lync Server 2013: CDR 테이블 목록입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558704"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="171c0-103">Lync Server 2013의 CDR 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="171c0-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="171c0-104">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="171c0-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="171c0-105">CDR(통화 정보 기록) 데이터베이스 스키마는 다음과 같은 테이블로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="171c0-106">정적 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-107">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-107">Table</span></span></th>
<th><span data-ttu-id="171c0-108">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-109"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 CallPriorities 순위 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-110">응급, 긴급, 정상, 일반 등 가능한 통화 우선 순위 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-112">회의 참가 시간 요약 보고서에서 사용하는 분류 경계를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-113"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-114">&quot;클라이언트 시작, &quot; &quot; 등록 만료, &quot; &quot; 클라이언트 손상 &quot; 등의 가능한 사용자 등록 취소 이유 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-115"><a href="lync-server-2013-medialist-table.md">Lync Server 2013의 MediaList 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-116">데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록(예: IM, 오디오, 비디오 및 파일 전송)을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-117"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013의 PurgeSettings 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-118">오래된 통화 정보 기록이 CDR 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-119"><a href="lync-server-2013-roles-table.md">Lync Server 2013의 역할 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-120">가능한 회의 역할 목록(예: 참석자 및 발표자)을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013의 SIPResponseMetaData 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-122">SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="171c0-123">지원 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-124">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-124">Table</span></span></th>
<th><span data-ttu-id="171c0-125">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-126"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 ClientVersions 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-127">이 데이터베이스에서 캡처된 정보와 함께 통화에 포함된 각 클라이언트의 클라이언트 정보(클라이언트 유형 및 버전 번호 모두)를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-128"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-129">회의 관련 통화에 사용되는 ConferenceURIs 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-130"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 ContentTypes 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-131">피어 투 피어 통화 및 회의 통화에 모두 사용되는 SIP(Session Initiation Protocol) 콘텐츠 유형의 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-132"><a href="lync-server-2013-devices-table.md">Lync Server 2013의 Devices 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-133">제조업체, 하드웨어 버전 및 MAC 주소를 포함하는 장치 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-134"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-135">데이터베이스에 있는 각 세션의 대화 ID에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-136"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-137">외부 통화에 사용되는 에지 서버 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-138"><a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-139">VoIP(Voice over Internet Protocol) 통화에 사용되는 게이트웨이 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-140"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-141">장치(일반 전화)의 하드웨어 버전 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-142"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-143">장치(일반 전화)의 제조업체 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-144"><a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-145">다양한 A/V 회의 서버 및 해당 URL에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-146"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 MediationServers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-147">VoIP 통화에 사용되는 중재 서버 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-148"><a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-149">보관된 VoIP 통화에 사용되거나 해당 통화 세부 정보가 기록된 모든 전화 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-150"><a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-151">IM 메시지가 캡처되는 풀의 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-152"><a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-153">통화에 연관된 서버 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-154"><a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-155">현재 배포에서 지원되는 테넌트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="171c0-156">엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자 및 익명 사용자를 위한 몇 가지 기본 제공 테넌트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-157"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 UserAgentDef 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-158">사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-159"><a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-160">이 데이터베이스에 기록 및 보관된 세션에 참여한 사용자의 사용자 URI를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-161"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013의 UserStatistics 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-162">개별 사용자의 시스템 사용에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="171c0-163">회의 CDR 레코드 관련 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-164">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-164">Table</span></span></th>
<th><span data-ttu-id="171c0-165">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-166"><a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-167">ConferenceURI 및 시작/종료 시간을 포함하여 보관된 회의 또는 세부 정보가 기록된 회의에 대한 모든 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013의 ConferenceSessionDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-169">시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 세션에 대한 진단 ID를 포함하여 모든 SIP 기반 회의 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013의 FocusJoinsAndLeaves 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-171">사용자의 역할 및 클라이언트 버전을 포함하여 회의 참가 및 종료에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013의 McuJoinsAndLeaves 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-173">회의에 관련된 A/V 회의 서버 및 사용자의 참가 및 종료 시간에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="171c0-174">IM 회의의 메시지 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-175">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-175">Table</span></span></th>
<th><span data-ttu-id="171c0-176">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-177"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013의 ConferenceMessageCount 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-178">각 IM 회의에 대해 각 사용자가 전송한 메시지 수를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-179"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013의 IMReportSummary 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-180">조직에서 보관하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="171c0-181">피어 투 피어 세션 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-182">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-182">Table</span></span></th>
<th><span data-ttu-id="171c0-183">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-184"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 SessionDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-185">시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 사용자에 대한 메시지 수를 포함하여 모든 피어 투 피어 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-186"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013의 FileTransfers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-187">파일 이름 및 결과(수락, 거절 또는 취소)를 포함하여 파일 전송 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-188"><a href="lync-server-2013-media-table.md">Lync Server 2013의 미디어 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-189">피어 투 피어 세션에 포함된 여러 미디어 유형에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="171c0-190">VoIP 통화 세부 정보 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-191">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-191">Table</span></span></th>
<th><span data-ttu-id="171c0-192">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-193"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013의 VoipDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-194">각 두 사용자 간 VoIP/PSTN 통화에 대해 VoIP 전화의 전화 ID, 사용된 게이트웨이 및 연결을 해제한 사용자 등 통화에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="171c0-195">통화 시작/종료 시간 및 응답 코드에 대 한 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</a> 을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="171c0-196">통화에서 한 사용자가 VoIP 사용자이거나 통화에 중재 서버가 포함된 경우 이 테이블에 레코드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="171c0-197">공중 전화망 (PSTN) 전화와 관련 되지 않은 VoIP/VoIP 통화에 대 한 정보는 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</A>에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="171c0-198">E9-1-1 통화 감사 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-199">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-199">Table</span></span></th>
<th><span data-ttu-id="171c0-200">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-201"><a href="lync-server-2013-locations-table.md">Lync Server 2013의 위치 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-202">E9-1-1(Enhanced 9-1-1) 통화와 같은 각 긴급 통화에 대해서는 통화에 대한 위치 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="171c0-203">통화 시작/종료 시간 및 응답 코드에 대 한 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</a> 을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="171c0-p105">이 테이블에는 E9-1-1 통화에 대한 위치 BLOB만 포함됩니다. 통화에 대한 다른 세부 정보는 SessionDetails 테이블을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="171c0-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="171c0-206">문제 해결 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-207">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-207">Table</span></span></th>
<th><span data-ttu-id="171c0-208">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-209"><a href="lync-server-2013-application-table.md">Lync Server 2013의 응용 프로그램 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-210">라우팅 및 연결과 관련 된 Lync Server 2013 내의 다양 한 프로세스에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-211"><a href="lync-server-2013-calltype-table.md">Lync Server 2013의 CallType 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-212">"오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유"와 같은 통화 유형에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-213"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013의 ErrorCategory 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-214">각 Microsoft Lync Server 2013 진단 분류의 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-215"><a href="lync-server-2013-errordef-table.md">Lync Server 2013의 ErrorDef 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-216">오류 유형 및 정의에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-217"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-218">발생한 오류에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-219"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013의 ProgressReport 테이블</a></span><span class="sxs-lookup"><span data-stu-id="171c0-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="171c0-220">Lync Server 2013 프로세스에 포함 된 다양 한 단계의 진행 상황 보고서에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="171c0-221">다음 목록의 표에는 Lync Server에서 내부적으로 사용 하는 테이블이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="171c0-222">이러한 테이블의 세부 정보는 이 문서에서 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="171c0-223">Lync Server 내부용 테이블</span><span class="sxs-lookup"><span data-stu-id="171c0-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="171c0-224">목차가</span><span class="sxs-lookup"><span data-stu-id="171c0-224">Table</span></span></th>
<th><span data-ttu-id="171c0-225">설명</span><span class="sxs-lookup"><span data-stu-id="171c0-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="171c0-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-227">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-229">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-231">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-232"><strong>FrontEnd 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-233">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-234"><strong>MSMQProcessing 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-235">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-237">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-238"><strong>Syndicators 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-239">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-240"><strong>SyndicatorsTenantMap 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-241">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-242"><strong>Task 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-243">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-245">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-247">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-249">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-251">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-253">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-255">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-257">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-259">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="171c0-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-261">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="171c0-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="171c0-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="171c0-263">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="171c0-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

