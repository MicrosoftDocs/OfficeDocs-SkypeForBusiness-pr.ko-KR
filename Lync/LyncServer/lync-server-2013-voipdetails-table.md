---
title: 'Lync Server 2013: VoipDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="ca63d-102">Lync Server 2013의 VoipDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="ca63d-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca63d-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ca63d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ca63d-104">각 레코드는 하나 이상의 사용자가 VoIP 사용자 인 1 2-파티 통화를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca63d-105">열</span><span class="sxs-lookup"><span data-stu-id="ca63d-105">Column</span></span></th>
<th><span data-ttu-id="ca63d-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ca63d-106">Data Type</span></span></th>
<th><span data-ttu-id="ca63d-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="ca63d-107">Key/Index</span></span></th>
<th><span data-ttu-id="ca63d-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="ca63d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca63d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="ca63d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca63d-111">주요한</span><span class="sxs-lookup"><span data-stu-id="ca63d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca63d-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-112">Time of session request.</span></span> <span data-ttu-id="ca63d-113">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ca63d-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca63d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-116">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-116">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-117">주요한</span><span class="sxs-lookup"><span data-stu-id="ca63d-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca63d-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-118">ID number to identify the session.</span></span> <span data-ttu-id="ca63d-119">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ca63d-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca63d-121"><strong>From번호 번호</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-122">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-122">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-123">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-124">발신자의 <strong>PhoneId</strong> .</span><span class="sxs-lookup"><span data-stu-id="ca63d-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="ca63d-125">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ca63d-126">NULL이 아니고 <strong>FromGatewayId</strong> 가 null이 아니면 호출자는 PSTN 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca63d-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-128">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-128">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-129">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-130">통화 수신기의 <strong>PhoneId</strong> .</span><span class="sxs-lookup"><span data-stu-id="ca63d-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="ca63d-131">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ca63d-132">NULL이 아니고 <strong>ToGatewayId</strong> 가 null이 아니면 통화 수신기는 PSTN 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca63d-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-134">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-134">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-135">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-136">통화를 보내는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="ca63d-137">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca63d-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-139">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-139">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-140">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-141">호출 되는 중재 서버.</span><span class="sxs-lookup"><span data-stu-id="ca63d-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="ca63d-142">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca63d-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-144">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-144">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-145">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-146">통화를 보내는 게이트웨이.</span><span class="sxs-lookup"><span data-stu-id="ca63d-146">Gateway the call is coming from.</span></span> <span data-ttu-id="ca63d-147">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca63d-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-149">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-149">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-150">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-151">전화를 받는 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="ca63d-151">Gateway the call is going to.</span></span> <span data-ttu-id="ca63d-152">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca63d-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-154">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-154">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-155">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-156">사용자에 게 URI가 있는 경우 전화를 끊은 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="ca63d-157">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca63d-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="ca63d-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca63d-159">int</span><span class="sxs-lookup"><span data-stu-id="ca63d-159">int</span></span></p></td>
<td><p><span data-ttu-id="ca63d-160">외부</span><span class="sxs-lookup"><span data-stu-id="ca63d-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca63d-161">통화를 끊은 전화의 ID가 휴대폰에서 연결이 끊어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ca63d-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="ca63d-162">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca63d-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

