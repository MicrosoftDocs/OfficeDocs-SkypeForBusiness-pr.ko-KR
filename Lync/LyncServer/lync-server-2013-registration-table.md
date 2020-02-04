---
title: 'Lync Server 2013: Registration 테이블'
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
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="89d2a-102">Lync Server 2013의 Registration 테이블</span><span class="sxs-lookup"><span data-stu-id="89d2a-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89d2a-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="89d2a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="89d2a-104">각 레코드는 하나의 사용자 등록 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d2a-105">열</span><span class="sxs-lookup"><span data-stu-id="89d2a-105">Column</span></span></th>
<th><span data-ttu-id="89d2a-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="89d2a-106">Data Type</span></span></th>
<th><span data-ttu-id="89d2a-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="89d2a-107">Key/Index</span></span></th>
<th><span data-ttu-id="89d2a-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="89d2a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="89d2a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="89d2a-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="89d2a-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-112">Time of session request.</span></span> <span data-ttu-id="89d2a-113">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="89d2a-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-116">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-116">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="89d2a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-118">ID number to identify the session.</span></span> <span data-ttu-id="89d2a-119">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="89d2a-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-122">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-122">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-123">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-124">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-124">The user ID.</span></span> <span data-ttu-id="89d2a-125">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="89d2a-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-128">등록 끝점을 식별 하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="89d2a-129">일반적으로 같은 사용자의 동일한 컴퓨터의 register 이벤트는 동일한 끝점 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="89d2a-130">다른 컴퓨터에는 다른 끝점 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="89d2a-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-133">같은 사용자 및 같은 끝점과 관련 된 등록을 구분 하는 데 사용 되는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="89d2a-134">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-136">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-136">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-137">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-138">현재 사용자의 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-138">Client version of current user.</span></span> <span data-ttu-id="89d2a-139">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-141">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-141">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-142">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-143">등록에 사용 되는 등록자 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="89d2a-144">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-146">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-146">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-147">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-148">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="89d2a-149">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-151">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-151">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-152">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-153">Edge 서버 등록을 진행 하는 동안.</span><span class="sxs-lookup"><span data-stu-id="89d2a-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="89d2a-154">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-156">다소</span><span class="sxs-lookup"><span data-stu-id="89d2a-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-157">사용자가 내부에서 로그온 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="89d2a-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-158"><strong>IsUserServiceAvailable 가능</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-159">다소</span><span class="sxs-lookup"><span data-stu-id="89d2a-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-160">UserService를 사용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="89d2a-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-162">다소</span><span class="sxs-lookup"><span data-stu-id="89d2a-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-163">기본 등록 기관에 등록할 것인지 여부</span><span class="sxs-lookup"><span data-stu-id="89d2a-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-165">다소</span><span class="sxs-lookup"><span data-stu-id="89d2a-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-166">사용자가 survivable branch 기기에 등록 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="89d2a-167">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-169">dmtf</span><span class="sxs-lookup"><span data-stu-id="89d2a-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-170">등록 시간.</span><span class="sxs-lookup"><span data-stu-id="89d2a-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-172">dmtf</span><span class="sxs-lookup"><span data-stu-id="89d2a-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-173">등록 취소 시간.</span><span class="sxs-lookup"><span data-stu-id="89d2a-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-175">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-176">Register 요청의 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-178">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-179">Register 요청의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="89d2a-180">이는 진단 정보 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-182">int</span><span class="sxs-lookup"><span data-stu-id="89d2a-182">int</span></span></p></td>
<td><p><span data-ttu-id="89d2a-183">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-184">등록 요청이 들어오는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-184">The device that the register request is coming from.</span></span> <span data-ttu-id="89d2a-185">자세한 내용은 <a href="lync-server-2013-devices-table.md">Lync Server 2013의 장치 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d2a-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="89d2a-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89d2a-188">외부</span><span class="sxs-lookup"><span data-stu-id="89d2a-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89d2a-189">' 사용자 시작 ', ' 등록 만료 ', ' 클라이언트 실패 ' 등의 등록을 취소 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="89d2a-190">자세한 내용은 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d2a-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d2a-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="89d2a-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="89d2a-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="89d2a-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89d2a-193">사용자가 등록 한 끝점의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="89d2a-194">IPv4 주소 또는 IPv6 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="89d2a-195">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89d2a-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

