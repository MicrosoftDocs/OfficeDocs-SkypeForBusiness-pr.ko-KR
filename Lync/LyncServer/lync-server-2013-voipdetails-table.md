---
title: 'Lync Server 2013: VoipDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d41021016d6d6e21e7112597bb6206dc46d95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="8fa4a-102">Lync Server 2013의 VoipDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="8fa4a-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fa4a-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8fa4a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8fa4a-104">각 레코드는 적어도 한 명의 사용자가 VoIP 사용자인 하나의 두 사용자 간 통화를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fa4a-105">열</span><span class="sxs-lookup"><span data-stu-id="8fa4a-105">Column</span></span></th>
<th><span data-ttu-id="8fa4a-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8fa4a-106">Data Type</span></span></th>
<th><span data-ttu-id="8fa4a-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="8fa4a-107">Key/Index</span></span></th>
<th><span data-ttu-id="8fa4a-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8fa4a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fa4a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8fa4a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8fa4a-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-112">Time of session request.</span></span> <span data-ttu-id="8fa4a-113"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8fa4a-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa4a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-116">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-116">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8fa4a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-118">ID number to identify the session.</span></span> <span data-ttu-id="8fa4a-119"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8fa4a-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fa4a-121"><strong>From번호 번호</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-122">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-122">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-123">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-124">발신자의 <strong>PhoneId</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="8fa4a-125">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="8fa4a-126">NULL이 아니고 <strong>FromGatewayId</strong>가 NULL이 아니면 발신자가 PSTN 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa4a-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-128">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-128">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-129">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-130">통화 수신자의 <strong>PhoneId</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="8fa4a-131">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="8fa4a-132">NULL이 아니고 <strong>ToGatewayId</strong>가 NULL이 아니면 통화 수신자가 PSTN 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fa4a-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-134">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-134">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-135">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-136">통화의 발신측 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="8fa4a-137">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa4a-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-139">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-139">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-140">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-141">통화의 수신측 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="8fa4a-142">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fa4a-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-144">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-144">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-145">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-146">통화의 발신측 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-146">Gateway the call is coming from.</span></span> <span data-ttu-id="8fa4a-147">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa4a-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-149">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-149">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-150">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-151">통화의 수신측 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-151">Gateway the call is going to.</span></span> <span data-ttu-id="8fa4a-152">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fa4a-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-154">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-154">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-155">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-156">사용자가 URI를 갖고 있는 경우 통화 연결을 끊은 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="8fa4a-157">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fa4a-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="8fa4a-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fa4a-159">int</span><span class="sxs-lookup"><span data-stu-id="8fa4a-159">int</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-160">외부</span><span class="sxs-lookup"><span data-stu-id="8fa4a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fa4a-161">전화에서 연결을 끊은 경우 통화 연결을 끊은 전화의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="8fa4a-162">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

