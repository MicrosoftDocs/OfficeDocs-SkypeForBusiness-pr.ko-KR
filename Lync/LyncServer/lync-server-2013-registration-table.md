---
title: 'Lync Server 2013: 등록 테이블'
description: 'Lync Server 2013: 등록 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578532"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="d38a6-103">Lync Server 2013의 정합 테이블</span><span class="sxs-lookup"><span data-stu-id="d38a6-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d38a6-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d38a6-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d38a6-105">각 레코드는 한 사용자의 등록 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d38a6-106">열</span><span class="sxs-lookup"><span data-stu-id="d38a6-106">Column</span></span></th>
<th><span data-ttu-id="d38a6-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d38a6-107">Data Type</span></span></th>
<th><span data-ttu-id="d38a6-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="d38a6-108">Key/Index</span></span></th>
<th><span data-ttu-id="d38a6-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d38a6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d38a6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d38a6-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="d38a6-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-113">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-113">Time of session request.</span></span> <span data-ttu-id="d38a6-114"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d38a6-115">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-117">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-117">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="d38a6-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-119">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-119">ID number to identify the session.</span></span> <span data-ttu-id="d38a6-120"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d38a6-121">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-123">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-123">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-124">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-125">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-125">The user ID.</span></span> <span data-ttu-id="d38a6-126">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-128">고유</span><span class="sxs-lookup"><span data-stu-id="d38a6-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-p104">등록 끝점을 식별하기 위한 GUID입니다. 일반적으로 동일 사용자 및 동일 컴퓨터의 등록 이벤트는 동일한 끝점 ID를 갖습니다. 컴퓨터가 다른 경우 서로 다른 끝점 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-133">고유</span><span class="sxs-lookup"><span data-stu-id="d38a6-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-134">같은 사용자 및 끝점을 포함하는 등록을 구분하는 데 사용되는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="d38a6-135">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-137">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-137">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-138">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-139">현재 사용자의 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-139">Client version of current user.</span></span> <span data-ttu-id="d38a6-140">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d38a6-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-142">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-142">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-143">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-144">등록에 사용된 등록자 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="d38a6-145">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-147">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-147">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-148">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-149">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="d38a6-150">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d38a6-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-152">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-152">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-153">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-154">등록이 수행되는 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="d38a6-155">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-157">비트만</span><span class="sxs-lookup"><span data-stu-id="d38a6-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-158">사용자가 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-160">비트만</span><span class="sxs-lookup"><span data-stu-id="d38a6-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-161">UserService를 사용할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-163">비트만</span><span class="sxs-lookup"><span data-stu-id="d38a6-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-164">기본 등록자에 등록할지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-166">비트만</span><span class="sxs-lookup"><span data-stu-id="d38a6-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-167">사용자가 SBA(Survivable Branch Appliance)에 등록되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="d38a6-168">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-170">datetime</span><span class="sxs-lookup"><span data-stu-id="d38a6-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-171">등록 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-173">datetime</span><span class="sxs-lookup"><span data-stu-id="d38a6-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-174">등록 취소 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-176">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-177">등록 요청의 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-179">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-p109">등록 요청의 진단 ID입니다. 이 값은 진단 정보 유형을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-183">int</span><span class="sxs-lookup"><span data-stu-id="d38a6-183">int</span></span></p></td>
<td><p><span data-ttu-id="d38a6-184">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-185">등록 요청이 시작된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-185">The device that the register request is coming from.</span></span> <span data-ttu-id="d38a6-186">자세한 내용은 <a href="lync-server-2013-devices-table.md">Lync Server 2013에서 Devices 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d38a6-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="d38a6-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d38a6-189">외부</span><span class="sxs-lookup"><span data-stu-id="d38a6-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d38a6-190">'사용자 시작', '등록 만료', '클라이언트 오류' 등의 등록 취소 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="d38a6-191">자세한 내용은 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d38a6-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d38a6-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="d38a6-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d38a6-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d38a6-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d38a6-194">사용자가 등록된 끝점의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="d38a6-195">IPv4 주소 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="d38a6-196">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d38a6-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

