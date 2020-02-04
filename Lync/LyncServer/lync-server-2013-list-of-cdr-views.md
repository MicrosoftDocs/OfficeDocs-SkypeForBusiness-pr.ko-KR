---
title: 'Lync Server 2013: CDR 보기 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe2620175c2a706bfb2c48fe7fb380d5fae4c09
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="03eaf-102">Lync Server 2013의 CDR 보기 목록</span><span class="sxs-lookup"><span data-stu-id="03eaf-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03eaf-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="03eaf-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="03eaf-104">뷰는 CDR 데이터베이스에서 데이터를 반환 하는 데 사용 되는 가장 일반적인 시나리오에 대 한 정보에 쉽게 액세스할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="03eaf-105">실제 CDR 데이터베이스 테이블을 사용 하는 대신 사용자 지정 보고서를 빌드하는 데 보기를 사용 하는 것이 좋습니다. 이는 데이터베이스 뷰가 이후 Lync Server의 이전 버전과 호환성을 유지할 가능성이 높기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03eaf-106">이름 보기</span><span class="sxs-lookup"><span data-stu-id="03eaf-106">View Name</span></span></th>
<th><span data-ttu-id="03eaf-107">설명</span><span class="sxs-lookup"><span data-stu-id="03eaf-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-108"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013의 ClientVersions 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-109">통신 세션에 사용 되는 클라이언트 소프트웨어/장치에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-110"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013의 ConferenceMessageCount 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-111">회의 중 사용자가 보낸 메시지 수에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-112"><a href="lync-server-2013-conferences-view.md">Lync Server 2013의 회의 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-113">시작 시간, 종료 시간, 컨퍼런스 이끌이 등 회의 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013의 ConferenceSessionDetails 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-115">시작 및 종료 시간, 사용자 Id, 응답 코드, 진단 Id를 포함 하 여 모든 회의 세션에 대 한 세션 세부 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-116"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013의 ConferenceUris 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-117">회의에 사용 되는 회의 Uri에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-118"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013의 ErrorReport 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-119">세션 중에 발생 한 오류에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-120"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013의 FileTransfers 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-121">파일 이름과 전송 수락, 거부 또는 취소를 포함 하 여 파일 전송 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013의 FocusJoinsAndLeaves 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-123">컨퍼런스 참가 및 탈퇴 활동에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013의 McuJoinsAndLeaves 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-125">컨퍼런스 참가 및 탈퇴 활동에 대 한 통합 된 정보를 반환 합니다 (각 회의 참가는 해당 회의 연결이 유지 됩니다.).</span><span class="sxs-lookup"><span data-stu-id="03eaf-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-126"><a href="lync-server-2013-mcus-view.md">Lync Server 2013의 Mcus 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-127">회의 서버에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-128"><a href="lync-server-2013-media-view.md">Lync Server 2013의 미디어 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-129">피어 투 피어 통신 세션에 사용 되는 미디어 형식에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-130"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013의 ProgressReport 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-131">완료 된 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-132"><a href="lync-server-2013-registration-view.md">Lync Server 2013의 등록 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-133">Lync Server를 사용 하 여 등록에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-134"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 SessionDetails 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-135">VoIP 전화 통화, 2 자리 IM 세션 또는 기타 피어 투 피어 통신 세션을 비롯 한 피어 투 피어 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eaf-136"><a href="lync-server-2013-user-view.md">Lync Server 2013의 사용자 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-137">통신 세션에 참가 한 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eaf-138"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013의 VoIPDetails 보기</a></span><span class="sxs-lookup"><span data-stu-id="03eaf-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="03eaf-139">하나 이상의 VoIP (음성 over IO) 사용자를 포함 하는 피어 투 피어 세션에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03eaf-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

