---
title: 'Lync Server 2013: 등록 테이블'
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
ms.openlocfilehash: d56f08db69fab4dfbf8da0c09d5d693bccf76bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="fe30d-102">Lync Server 2013의 정합 테이블</span><span class="sxs-lookup"><span data-stu-id="fe30d-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe30d-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fe30d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fe30d-104">각 레코드는 한 사용자의 등록 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe30d-105">열</span><span class="sxs-lookup"><span data-stu-id="fe30d-105">Column</span></span></th>
<th><span data-ttu-id="fe30d-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fe30d-106">Data Type</span></span></th>
<th><span data-ttu-id="fe30d-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="fe30d-107">Key/Index</span></span></th>
<th><span data-ttu-id="fe30d-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fe30d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fe30d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe30d-111">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="fe30d-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-112">Time of session request.</span></span> <span data-ttu-id="fe30d-113"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fe30d-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-116">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-116">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="fe30d-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-118">ID number to identify the session.</span></span> <span data-ttu-id="fe30d-119"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fe30d-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-122">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-122">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-123">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-124">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-124">The user ID.</span></span> <span data-ttu-id="fe30d-125">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-127">고유</span><span class="sxs-lookup"><span data-stu-id="fe30d-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-p104">등록 끝점을 식별하기 위한 GUID입니다. 일반적으로 동일 사용자 및 동일 컴퓨터의 등록 이벤트는 동일한 끝점 ID를 갖습니다. 컴퓨터가 다른 경우 서로 다른 끝점 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-132">고유</span><span class="sxs-lookup"><span data-stu-id="fe30d-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-133">같은 사용자 및 끝점을 포함하는 등록을 구분하는 데 사용되는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="fe30d-134">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-136">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-136">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-137">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-138">현재 사용자의 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-138">Client version of current user.</span></span> <span data-ttu-id="fe30d-139">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe30d-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-141">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-141">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-142">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-143">등록에 사용된 등록자 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="fe30d-144">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-146">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-146">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-147">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-148">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="fe30d-149">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe30d-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-151">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-151">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-152">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-153">등록이 수행되는 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="fe30d-154">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-156">비트만</span><span class="sxs-lookup"><span data-stu-id="fe30d-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-157">사용자가 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-159">비트만</span><span class="sxs-lookup"><span data-stu-id="fe30d-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-160">UserService를 사용할 수 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-162">비트만</span><span class="sxs-lookup"><span data-stu-id="fe30d-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-163">기본 등록자에 등록할지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-165">비트만</span><span class="sxs-lookup"><span data-stu-id="fe30d-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-166">사용자가 SBA(Survivable Branch Appliance)에 등록되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="fe30d-167">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-169">datetime</span><span class="sxs-lookup"><span data-stu-id="fe30d-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-170">등록 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-172">datetime</span><span class="sxs-lookup"><span data-stu-id="fe30d-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-173">등록 취소 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-175">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-176">등록 요청의 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-178">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-p109">등록 요청의 진단 ID입니다. 이 값은 진단 정보 유형을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-182">int</span><span class="sxs-lookup"><span data-stu-id="fe30d-182">int</span></span></p></td>
<td><p><span data-ttu-id="fe30d-183">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-184">등록 요청이 시작된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-184">The device that the register request is coming from.</span></span> <span data-ttu-id="fe30d-185">자세한 내용은 <a href="lync-server-2013-devices-table.md">Lync Server 2013에서 Devices 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe30d-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe30d-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fe30d-188">외부</span><span class="sxs-lookup"><span data-stu-id="fe30d-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe30d-189">'사용자 시작', '등록 만료', '클라이언트 오류' 등의 등록 취소 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="fe30d-190">자세한 내용은 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013의 DeRegisterType 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe30d-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe30d-191"><strong>Address</strong></span><span class="sxs-lookup"><span data-stu-id="fe30d-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fe30d-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fe30d-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe30d-193">사용자가 등록된 끝점의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="fe30d-194">IPv4 주소 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="fe30d-195">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe30d-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

