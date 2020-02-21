---
title: 'Lync Server 2013: CDR 테이블 목록'
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
ms.openlocfilehash: 8ca9fd0b05eba812730c926685fedb244d60a29e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="bc126-102">Lync Server 2013의 CDR 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="bc126-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc126-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="bc126-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="bc126-104">CDR(통화 정보 기록) 데이터베이스 스키마는 다음과 같은 테이블로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="bc126-105">정적 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-106">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-106">Table</span></span></th>
<th><span data-ttu-id="bc126-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 CallPriorities 순위 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-109">응급, 긴급, 정상, 일반 등 가능한 통화 우선 순위 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-111">회의 참가 시간 요약 보고서에서 사용하는 분류 경계를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-113">&quot;&quot; &quot;클라이언트 시작, 등록 만료,&quot; &quot;클라이언트 손상&quot; 등의 가능한 사용자 등록 취소 이유 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013의 MediaList 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-115">데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록(예: IM, 오디오, 비디오 및 파일 전송)을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013의 PurgeSettings 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-117">오래된 통화 정보 기록이 CDR 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013의 역할 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-119">가능한 회의 역할 목록(예: 참석자 및 발표자)을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013의 SIPResponseMetaData 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-121">SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="bc126-122">지원 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-123">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-123">Table</span></span></th>
<th><span data-ttu-id="bc126-124">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 ClientVersions 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-126">이 데이터베이스에서 캡처된 정보와 함께 통화에 포함된 각 클라이언트의 클라이언트 정보(클라이언트 유형 및 버전 번호 모두)를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-128">회의 관련 통화에 사용되는 ConferenceURIs 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 ContentTypes 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-130">피어 투 피어 통화 및 회의 통화에 모두 사용되는 SIP(Session Initiation Protocol) 콘텐츠 유형의 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013의 Devices 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-132">제조업체, 하드웨어 버전 및 MAC 주소를 포함하는 장치 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-134">데이터베이스에 있는 각 세션의 대화 ID에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-136">외부 통화에 사용되는 에지 서버 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-138">VoIP(Voice over Internet Protocol) 통화에 사용되는 게이트웨이 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-140">장치(일반 전화)의 하드웨어 버전 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-142">장치(일반 전화)의 제조업체 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-144">다양한 A/V 회의 서버 및 해당 URL에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 MediationServers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-146">VoIP 통화에 사용되는 중재 서버 목록을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-148">보관된 VoIP 통화에 사용되거나 해당 통화 세부 정보가 기록된 모든 전화 번호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-150">IM 메시지가 캡처되는 풀의 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-152">통화에 연관된 서버 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-154">현재 배포에서 지원되는 테넌트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="bc126-155">엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자 및 익명 사용자를 위한 몇 가지 기본 제공 테넌트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 UserAgentDef 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-157">사용자 에이전트 식별자를 에이전트의 설명이 포함된 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-158"><a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-159">이 데이터베이스에 기록 및 보관된 세션에 참여한 사용자의 사용자 URI를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013의 UserStatistics 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-161">개별 사용자의 시스템 사용에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="bc126-162">회의 CDR 레코드 관련 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-163">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-163">Table</span></span></th>
<th><span data-ttu-id="bc126-164">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-166">ConferenceURI 및 시작/종료 시간을 포함하여 보관된 회의 또는 세부 정보가 기록된 회의에 대한 모든 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013의 ConferenceSessionDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-168">시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 세션에 대한 진단 ID를 포함하여 모든 SIP 기반 회의 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013의 FocusJoinsAndLeaves 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-170">사용자의 역할 및 클라이언트 버전을 포함하여 회의 참가 및 종료에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013의 McuJoinsAndLeaves 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-172">회의에 관련된 A/V 회의 서버 및 사용자의 참가 및 종료 시간에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="bc126-173">IM 회의의 메시지 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-174">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-174">Table</span></span></th>
<th><span data-ttu-id="bc126-175">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013의 ConferenceMessageCount 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-177">각 IM 회의에 대해 각 사용자가 전송한 메시지 수를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013의 IMReportSummary 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-179">조직에서 보관하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="bc126-180">피어 투 피어 세션 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-181">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-181">Table</span></span></th>
<th><span data-ttu-id="bc126-182">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 SessionDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-184">시작 및 종료 시간, 사용자 ID, 응답 코드 및 각 사용자에 대한 메시지 수를 포함하여 모든 피어 투 피어 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013의 FileTransfers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-186">파일 이름 및 결과(수락, 거절 또는 취소)를 포함하여 파일 전송 세션에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-187"><a href="lync-server-2013-media-table.md">Lync Server 2013의 미디어 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-188">피어 투 피어 세션에 포함된 여러 미디어 유형에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="bc126-189">VoIP 통화 세부 정보 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-190">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-190">Table</span></span></th>
<th><span data-ttu-id="bc126-191">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013의 VoipDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-193">각 두 사용자 간 VoIP/PSTN 통화에 대해 VoIP 전화의 전화 ID, 사용된 게이트웨이 및 연결을 해제한 사용자 등 통화에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="bc126-194">통화 시작/종료 시간 및 응답 코드에 대 한 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</a> 을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bc126-195">통화에서 한 사용자가 VoIP 사용자이거나 통화에 중재 서버가 포함된 경우 이 테이블에 레코드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="bc126-196">공중 전화망 (PSTN) 전화와 관련 되지 않은 VoIP/VoIP 통화에 대 한 정보는 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</A>에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="bc126-197">E9-1-1 통화 감사 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-198">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-198">Table</span></span></th>
<th><span data-ttu-id="bc126-199">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013의 위치 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-201">E9-1-1(Enhanced 9-1-1) 통화와 같은 각 긴급 통화에 대해서는 통화에 대한 위치 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="bc126-202">통화 시작/종료 시간 및 응답 코드에 대 한 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</a> 을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bc126-p105">이 테이블에는 E9-1-1 통화에 대한 위치 BLOB만 포함됩니다. 통화에 대한 다른 세부 정보는 SessionDetails 테이블을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc126-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="bc126-205">문제 해결 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-206">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-206">Table</span></span></th>
<th><span data-ttu-id="bc126-207">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-208"><a href="lync-server-2013-application-table.md">Lync Server 2013의 응용 프로그램 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-209">라우팅 및 연결과 관련 된 Lync Server 2013 내의 다양 한 프로세스에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013의 CallType 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-211">"오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유"와 같은 통화 유형에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013의 ErrorCategory 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-213">각 Microsoft Lync Server 2013 진단 분류의 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013의 ErrorDef 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-215">오류 유형 및 정의에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-217">발생한 오류에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013의 ProgressReport 테이블</a></span><span class="sxs-lookup"><span data-stu-id="bc126-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bc126-219">Lync Server 2013 프로세스에 포함 된 다양 한 단계의 진행 상황 보고서에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bc126-220">다음 목록의 표에는 Lync Server에서 내부적으로 사용 하는 테이블이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="bc126-221">이러한 테이블의 세부 정보는 이 문서에서 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="bc126-222">Lync Server 내부용 테이블</span><span class="sxs-lookup"><span data-stu-id="bc126-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc126-223">목차가</span><span class="sxs-lookup"><span data-stu-id="bc126-223">Table</span></span></th>
<th><span data-ttu-id="bc126-224">설명</span><span class="sxs-lookup"><span data-stu-id="bc126-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc126-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-226">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-228">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-230">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-231"><strong>FrontEnd 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-232">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-233"><strong>MSMQProcessing 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-234">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-236">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-237"><strong>Syndicators 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-238">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-239"><strong>SyndicatorsTenantMap 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-240">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-241"><strong>Task 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-242">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-244">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-246">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-248">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-250">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-252">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-254">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-256">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-258">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc126-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-260">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc126-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="bc126-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="bc126-262">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc126-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

