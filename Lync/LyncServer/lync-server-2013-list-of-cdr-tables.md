---
title: 'Lync Server 2013: CDR 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="02399-102">Lync Server 2013의 CDR 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="02399-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02399-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="02399-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="02399-104">CDR (통화 정보 기록) 데이터베이스 스키마는 다음 테이블로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="02399-105">정적 테이블</span><span class="sxs-lookup"><span data-stu-id="02399-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-106">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-106">Table</span></span></th>
<th><span data-ttu-id="02399-107">설명</span><span class="sxs-lookup"><span data-stu-id="02399-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 CallPriorities 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-109">긴급, 긴급, 일반, 비 긴급 등의 가능 통화 우선 순위 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-111">컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-113">&quot;&quot; &quot;클라이언트 시작, 등록 만료,&quot; &quot;클라이언트 손상&quot; 등의 사용 가능 사용자 등록 취소의 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013의 MediaList 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-115">데이터베이스에 항목을 생성할 수 있는 미디어 유형 목록 (예: IM, 오디오, 비디오, 파일 전송)을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013의 PurgeSettings 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-117">오래 된 통화 정보 레코드가 CDR 데이터베이스에서 자동으로 삭제 되는지 여부를 지정 하는 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013의 Roles 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-119">가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013의 SIPResponseMetaData 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-121">SIP 응답 코드와 이러한 코드의 분류 및 정의 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="02399-122">지원 테이블</span><span class="sxs-lookup"><span data-stu-id="02399-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-123">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-123">Table</span></span></th>
<th><span data-ttu-id="02399-124">설명</span><span class="sxs-lookup"><span data-stu-id="02399-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 ClientVersions 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-126">이 데이터베이스에서 캡처한 정보를 사용 하 여 호출에 참여 하는 각 클라이언트의 클라이언트 (클라이언트 유형 및 버전 번호)를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-128">전화 회의 관련 통화에 사용 되는 ConferenceURIs 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 ContentTypes 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-130">피어 투 피어 통화와 전화 회의에 사용 되는 SIP (세션 초기화 프로토콜) 콘텐츠 형식 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013의 Devices 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-132">제조업체, 하드웨어 버전, MAC 주소 등 장치 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-134">데이터베이스의 각 세션에 대 한 대화 상자 ID에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-136">외부 통화에 사용 되는 Edge 서버의 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013의 Gateways 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-138">VoIP (Voice over 인터넷 프로토콜) 통화에 사용 되는 게이트웨이 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-140">장치 (일반 전화기)의 하드웨어 버전 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 Manufacturers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-142">장치 제조업체 (일반 전화기) 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-144">다양 한 A/V 회의 서버와 해당 Uri에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 MediationServers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-146">VoIP 통화에 사용 되는 중재 서버 목록을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013의 Phones 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-148">보관 되었거나 통화 정보가 기록 된 VoIP 통화에 사용 된 모든 전화 번호를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013의 Pools 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-150">메신저 대화 메시지가 캡처되는 풀의 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-152">통화에 관련 된 서버의 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013의 Tenants 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-154">현재 배포에서 지원 되는 테 넌 트를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="02399-155">엔터프라이즈 사용자, 페더레이션 사용자, 공용 IM 연결 사용자, 익명 사용자를 위한 일부 빌드 비 테 넌 트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02399-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 UserAgentDef 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-157">사용자 에이전트 식별자를 에이전트의 설명 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-158"><a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-159">이 데이터베이스에 기록 되거나 보관 된 세션에 참가 한 사용자의 사용자 Uri를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013의 UserStatistics 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-161">시스템의 개별 사용자 사용에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="02399-162">컨퍼런스 CDR 레코드에 해당 하는 테이블</span><span class="sxs-lookup"><span data-stu-id="02399-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-163">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-163">Table</span></span></th>
<th><span data-ttu-id="02399-164">설명</span><span class="sxs-lookup"><span data-stu-id="02399-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013의 Conferences 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-166">보관 되었거나 ConferenceURI, 시작 및 종료 시간을 비롯 한 세부 정보가 기록 된 모든 컨퍼런스에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013의 ConferenceSessionDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-168">시작 및 종료 시간, 사용자 ID, 응답 코드, 각 세션에 대 한 진단 ID 등 모든 SIP 기반 회의 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013의 FocusJoinsAndLeaves 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-170">사용자 역할 및 클라이언트 버전을 포함 하 여 컨퍼런스 참가 및 탈퇴에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013의 McuJoinsAndLeaves 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-172">회의와 관련 된 A/V 회의 서버와 사용자 참가 및 종료 시간에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="02399-173">메신저 대화 회의의 메시지 표</span><span class="sxs-lookup"><span data-stu-id="02399-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-174">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-174">Table</span></span></th>
<th><span data-ttu-id="02399-175">설명</span><span class="sxs-lookup"><span data-stu-id="02399-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013의 ConferenceMessageCount 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-177">각 메신저 대화 회의에 대해 각 사용자가 보낸 메시지 수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013의 IMReportSummary 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-179">조직에 보관 된 인스턴트 메시징 세션에 대 한 전체 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="02399-180">피어 투 피어 세션 표</span><span class="sxs-lookup"><span data-stu-id="02399-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-181">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-181">Table</span></span></th>
<th><span data-ttu-id="02399-182">설명</span><span class="sxs-lookup"><span data-stu-id="02399-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 SessionDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-184">시작 및 종료 시간, 사용자 ID, 응답 코드, 각 사용자의 메시지 수 등 모든 피어 투 피어 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013의 FileTransfers 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-186">파일 이름 및 결과 (수락, 거부 또는 취소 됨)를 포함 하 여 파일 전송 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-187"><a href="lync-server-2013-media-table.md">Lync Server 2013의 Media 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-188">피어 투 피어 세션에 관련 된 다양 한 미디어 형식에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="02399-189">VoIP 통화 정보 표</span><span class="sxs-lookup"><span data-stu-id="02399-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-190">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-190">Table</span></span></th>
<th><span data-ttu-id="02399-191">설명</span><span class="sxs-lookup"><span data-stu-id="02399-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013의 VoipDetails 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-193">두 개의 파티 VoIP/PSTN 통화에 대해 VoIP 전화기의 전화 ID, 게이트웨이 사용, 그리고 연결 끊긴 파티와 같은 통화에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="02399-194"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013에서</a> 통화 시작/종료 시간 및 응답 코드에 대 한 sessiondetails 테이블을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="02399-195">한 통화에 대 한 한 자가 VoIP 사용자 이거나 중재 서버가 통화에 참여 하 고 있는 경우에는이 테이블에 레코드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="02399-196">PSTN (공개 전환 전화 네트워크)과 관련 되지 않은 VoIP/VoIP 통화에 대 한 정보는 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013의 Sessiondetails 테이블</A>에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="02399-197">E9-1-1 통화 감사 표</span><span class="sxs-lookup"><span data-stu-id="02399-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-198">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-198">Table</span></span></th>
<th><span data-ttu-id="02399-199">설명</span><span class="sxs-lookup"><span data-stu-id="02399-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013의 Locations 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-201">향상 된 9-1-1 (E9-1) 통화와 같은 각 비상 통화에 대해 통화에 대 한 위치 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="02399-202"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013에서</a> 통화 시작/종료 시간 및 응답 코드에 대 한 sessiondetails 테이블을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="02399-203">이 표에는 E9-1-1 통화에 대 한 위치 blob만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02399-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="02399-204">통화에 대 한 기타 자세한 정보를 보려면 SessionDetails 테이블을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02399-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="02399-205">문제 해결 표</span><span class="sxs-lookup"><span data-stu-id="02399-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-206">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-206">Table</span></span></th>
<th><span data-ttu-id="02399-207">설명</span><span class="sxs-lookup"><span data-stu-id="02399-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-208"><a href="lync-server-2013-application-table.md">Lync Server 2013의 Application 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-209">라우팅 및 연결과 관련 된 Lync Server 2013 내의 다양 한 프로세스에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013의 CallType 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-211">"오디오", "인스턴트 메시징", "오디오 및 비디오" 및 "응용 프로그램 공유"와 같은 통화 유형에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013의 ErrorCategory 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-213">각 Microsoft Lync Server 2013 진단 분류에 대 한 친숙 한 이름을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013의 ErrorDef 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-215">오류 유형과 해당 정의에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-217">발생 한 오류에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013의 ProgressReport 테이블</a></span><span class="sxs-lookup"><span data-stu-id="02399-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="02399-219">Lync Server 2013 프로세스에 포함 된 다양 한 단계의 진행 상황 보고서에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02399-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02399-220">다음 목록의 표는 Lync Server에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="02399-221">세부 정보는이 문서에 설명 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02399-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="02399-222">Lync 서버에서 내부용으로 사용 하는 테이블</span><span class="sxs-lookup"><span data-stu-id="02399-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02399-223">테이블로</span><span class="sxs-lookup"><span data-stu-id="02399-223">Table</span></span></th>
<th><span data-ttu-id="02399-224">설명</span><span class="sxs-lookup"><span data-stu-id="02399-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02399-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="02399-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-226">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="02399-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-228">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="02399-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-230">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-231"><strong>프런트 엔드 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="02399-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-232">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-233"><strong>MSMQProcessing 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="02399-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-234">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="02399-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-236">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-237"><strong>Syndicators 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="02399-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-238">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-239"><strong>SyndicatorsTenantMap 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="02399-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-240">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-241"><strong>작업 테이블</strong></span><span class="sxs-lookup"><span data-stu-id="02399-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-242">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="02399-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-244">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="02399-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-246">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-247"><strong>Usagesmary</strong></span><span class="sxs-lookup"><span data-stu-id="02399-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-248">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="02399-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-250">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="02399-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-252">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-253"><strong>시간대</strong></span><span class="sxs-lookup"><span data-stu-id="02399-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-254">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="02399-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-256">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="02399-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-258">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02399-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="02399-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-260">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02399-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="02399-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="02399-262">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02399-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

