---
title: 'Lync Server 2013: Registration 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="89c11-102">Lync Server 2013의 Registration 테이블</span><span class="sxs-lookup"><span data-stu-id="89c11-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89c11-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="89c11-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="89c11-104">각 레코드는 하나의 사용자 등록 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89c11-105">열</span><span class="sxs-lookup"><span data-stu-id="89c11-105">Column</span></span></th>
<th><span data-ttu-id="89c11-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="89c11-106">Data Type</span></span></th>
<th><span data-ttu-id="89c11-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="89c11-107">Key/Index</span></span></th>
<th><span data-ttu-id="89c11-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="89c11-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89c11-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="89c11-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="89c11-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="89c11-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-112">Time of session request.</span></span> <span data-ttu-id="89c11-113">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="89c11-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-116">int</span><span class="sxs-lookup"><span data-stu-id="89c11-116">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-117">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="89c11-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-118">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-118">ID number to identify the session.</span></span> <span data-ttu-id="89c11-119">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="89c11-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-122">int</span><span class="sxs-lookup"><span data-stu-id="89c11-122">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-123">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-124">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-124">The user ID.</span></span> <span data-ttu-id="89c11-125">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="89c11-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-128">등록 끝점을 식별 하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="89c11-129">일반적으로 같은 사용자의 동일한 컴퓨터의 register 이벤트는 동일한 끝점 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="89c11-130">다른 컴퓨터에는 다른 끝점 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="89c11-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-133">같은 사용자 및 같은 끝점과 관련 된 등록을 구분 하는 데 사용 되는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="89c11-134">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-136">int</span><span class="sxs-lookup"><span data-stu-id="89c11-136">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-137">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-138">현재 사용자의 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-138">Client version of current user.</span></span> <span data-ttu-id="89c11-139">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-141">int</span><span class="sxs-lookup"><span data-stu-id="89c11-141">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-142">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-143">등록에 사용 되는 등록자 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="89c11-144">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-146">int</span><span class="sxs-lookup"><span data-stu-id="89c11-146">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-147">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-148">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="89c11-149">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-151">int</span><span class="sxs-lookup"><span data-stu-id="89c11-151">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-152">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-153">Edge 서버 등록을 진행 하는 동안.</span><span class="sxs-lookup"><span data-stu-id="89c11-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="89c11-154">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-156">다소</span><span class="sxs-lookup"><span data-stu-id="89c11-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-157">사용자가 내부에서 로그온 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="89c11-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-158"><strong>IsUserServiceAvailable 가능</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-159">다소</span><span class="sxs-lookup"><span data-stu-id="89c11-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-160">UserService를 사용할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="89c11-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-162">다소</span><span class="sxs-lookup"><span data-stu-id="89c11-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-163">기본 등록 기관에 등록할 것인지 여부</span><span class="sxs-lookup"><span data-stu-id="89c11-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-165">다소</span><span class="sxs-lookup"><span data-stu-id="89c11-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-166">사용자가 survivable branch 기기에 등록 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="89c11-167">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-169">dmtf</span><span class="sxs-lookup"><span data-stu-id="89c11-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-170">등록 시간.</span><span class="sxs-lookup"><span data-stu-id="89c11-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-172">dmtf</span><span class="sxs-lookup"><span data-stu-id="89c11-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-173">등록 취소 시간.</span><span class="sxs-lookup"><span data-stu-id="89c11-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-175">int</span><span class="sxs-lookup"><span data-stu-id="89c11-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-176">Register 요청의 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-178">int</span><span class="sxs-lookup"><span data-stu-id="89c11-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-179">Register 요청의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="89c11-180">이는 진단 정보 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-182">int</span><span class="sxs-lookup"><span data-stu-id="89c11-182">int</span></span></p></td>
<td><p><span data-ttu-id="89c11-183">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-184">등록 요청이 들어오는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-184">The device that the register request is coming from.</span></span> <span data-ttu-id="89c11-185">자세한 내용은 <a href="lync-server-2013-devices-table.md">Lync Server 2013의 장치 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89c11-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="89c11-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89c11-188">외부</span><span class="sxs-lookup"><span data-stu-id="89c11-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="89c11-189">' 사용자 시작 ', ' 등록 만료 ', ' 클라이언트 실패 ' 등의 등록을 취소 하는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="89c11-190">자세한 내용은 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89c11-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89c11-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="89c11-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="89c11-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="89c11-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89c11-193">사용자가 등록 한 끝점의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="89c11-194">IPv4 주소 또는 IPv6 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="89c11-195">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89c11-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

