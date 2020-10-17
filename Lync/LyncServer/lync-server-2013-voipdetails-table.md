---
title: 'Lync Server 2013: VoipDetails 테이블'
description: 'Lync Server 2013: VoipDetails 테이블'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566284"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="aae1c-103">Lync Server 2013의 VoipDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="aae1c-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aae1c-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="aae1c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="aae1c-105">각 레코드는 적어도 한 명의 사용자가 VoIP 사용자인 하나의 두 사용자 간 통화를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aae1c-106">열</span><span class="sxs-lookup"><span data-stu-id="aae1c-106">Column</span></span></th>
<th><span data-ttu-id="aae1c-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aae1c-107">Data Type</span></span></th>
<th><span data-ttu-id="aae1c-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="aae1c-108">Key/Index</span></span></th>
<th><span data-ttu-id="aae1c-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="aae1c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aae1c-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="aae1c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="aae1c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="aae1c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="aae1c-113">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-113">Time of session request.</span></span> <span data-ttu-id="aae1c-114"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="aae1c-115">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae1c-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-117">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-117">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-118">Primary</span><span class="sxs-lookup"><span data-stu-id="aae1c-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="aae1c-119">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-119">ID number to identify the session.</span></span> <span data-ttu-id="aae1c-120"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="aae1c-121">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aae1c-122"><strong>From번호 번호</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-123">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-123">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-124">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-125">발신자의 <strong>PhoneId</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="aae1c-126">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="aae1c-127">NULL이 아니고 <strong>FromGatewayId</strong>가 NULL이 아니면 발신자가 PSTN 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae1c-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-129">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-129">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-130">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-131">통화 수신자의 <strong>PhoneId</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="aae1c-132">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="aae1c-133">NULL이 아니고 <strong>ToGatewayId</strong>가 NULL이 아니면 통화 수신자가 PSTN 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aae1c-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-135">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-135">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-136">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-137">통화의 발신측 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="aae1c-138">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae1c-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-140">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-140">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-141">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-142">통화의 수신측 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="aae1c-143">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aae1c-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-145">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-145">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-146">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-147">통화의 발신측 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-147">Gateway the call is coming from.</span></span> <span data-ttu-id="aae1c-148">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae1c-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-150">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-150">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-151">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-152">통화의 수신측 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-152">Gateway the call is going to.</span></span> <span data-ttu-id="aae1c-153">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aae1c-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-155">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-155">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-156">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-157">사용자가 URI를 갖고 있는 경우 통화 연결을 끊은 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="aae1c-158">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aae1c-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="aae1c-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="aae1c-160">int</span><span class="sxs-lookup"><span data-stu-id="aae1c-160">int</span></span></p></td>
<td><p><span data-ttu-id="aae1c-161">외부</span><span class="sxs-lookup"><span data-stu-id="aae1c-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aae1c-162">전화에서 연결을 끊은 경우 통화 연결을 끊은 전화의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="aae1c-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="aae1c-163">자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aae1c-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

