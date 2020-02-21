---
title: 'Lync Server 2013: 재해 복구 중 그룹 통화 픽업 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58894a00c853f04d5d4c6f995edc17683b12e9f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="5d6d4-102">Lync Server 2013에서 재해 복구를 수행 하는 동안 그룹 통화 픽업 관리</span><span class="sxs-lookup"><span data-stu-id="5d6d4-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d6d4-103">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5d6d4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5d6d4-104">계획 되지 않은 문제로 인해 프런트 엔드 풀을 사용할 수 없게 되 면 서비스가 백업 풀로 장애 조치 (failover) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="5d6d4-105">백업 풀로 장애 조치 (failover) 중에 사용자가 백업 풀로 리디렉션되어 복원 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="5d6d4-106">복구 모드에서는 사용자가 다른 사용자의 통화를 선택 하거나 전화를 다른 사용자가 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="5d6d4-107">장애 조치 (failover)가 완료 되 면 사용자는 평소와 같이 그룹 통화 픽업을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="5d6d4-108">기본 풀로의 장애 복구 (failback) 중에는 사용자가 기본 풀로 리디렉션되어 복원 모드에서 다시 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="5d6d4-109">사용자가 복구 모드를 해제할 때 까지는 그룹 통화 픽업 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="5d6d4-110">이 섹션에서는 재해 복구 중에 그룹 통화 픽업에 대 한 몇 가지 고려 사항을 설명 하 고 사용자 환경에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="5d6d4-111">재해 복구 시 그룹 통화 픽업 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5d6d4-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="5d6d4-112">재해 복구 중에 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션된 사용자는 통화 픽업 그룹 번호에 대해 백업 풀에서 실행 되는 통화 대기 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="5d6d4-113">따라서 재해 복구 중에 그룹 통화 픽업 지원을 사용 하려면 기본 풀과 백업 풀에서 모두 통화 대기 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="5d6d4-114">통화 대기 번호 테이블의 그룹 통화 픽업 수 범위는 백업 풀에 대 한 장애 조치 (failover) 프로세스가 완료 된 후 백업 풀로 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="5d6d4-115">기본 풀에 대 한 장애 복구 프로세스가 완료 된 후 번호 범위를 주 풀로 다시 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="5d6d4-116">그룹 통화 픽업 범위를 리디렉션하려면 **get-cscallparkorbit** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="5d6d4-117">기본 풀을 대체 하기 위해 다른 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 풀을 배포 하는 경우 기본 풀과 연결 된 모든 그룹 통화 픽업 번호 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="5d6d4-118">번호 범위를 새 풀에 다시 할당 하려면 **get-cscallparkorbit** cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="5d6d4-119">**Get-cscallparkorbit** cmdlet에 대 한 자세한 내용은 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="5d6d4-120">풀 오류 발생 시 그룹 통화 픽업 환경</span><span class="sxs-lookup"><span data-stu-id="5d6d4-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="5d6d4-121">다음 표에서는 재해 복구 단계를 통해 그룹 통화 픽업 경험을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="5d6d4-122">재해 복구 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="5d6d4-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d6d4-123">통화 상태</span><span class="sxs-lookup"><span data-stu-id="5d6d4-123">Call state</span></span></th>
<th><span data-ttu-id="5d6d4-124">백업 풀에 대 한 장애 조치 (Failover)</span><span class="sxs-lookup"><span data-stu-id="5d6d4-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="5d6d4-125">기본 풀 장애 복구 (Failback)</span><span class="sxs-lookup"><span data-stu-id="5d6d4-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d6d4-126">새 통화</span><span class="sxs-lookup"><span data-stu-id="5d6d4-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="5d6d4-127"><strong>장애 조치 (failover) 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-128">복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5d6d4-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5d6d4-129"><strong>장애 조치 (failover) 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-130">그룹 통화 픽업 사용자 복구 및 그룹 통화 픽업 번호 범위가 백업 풀로 리디렉션될 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d6d4-131"><strong>장애 복구 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-132">복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5d6d4-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5d6d4-133"><strong>장애 복구 (failback) 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-134">그룹 통화 픽업 사용자 복구 및 그룹 통화 픽업 번호 범위가 기본 풀로 다시 리디렉션될 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d6d4-135">그룹 통화 픽업 큐의 통화</span><span class="sxs-lookup"><span data-stu-id="5d6d4-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="5d6d4-136"><strong>장애 조치 (failover) 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-137">그룹 통화 픽업를 통해 큐의 통화에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5d6d4-138"><strong>장애 조치 (failover) 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-139">이 상태의 통화 없음</span><span class="sxs-lookup"><span data-stu-id="5d6d4-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d6d4-140"><strong>장애 복구 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-141">그룹 통화 픽업를 통해 큐의 통화에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5d6d4-142"><strong>장애 복구 (failback) 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-143">그룹 통화 픽업를 통해 큐의 통화에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6d4-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d6d4-144">통화 설정</span><span class="sxs-lookup"><span data-stu-id="5d6d4-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="5d6d4-145"><strong>장애 조치 (failover) 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-146">통화를 계속 연결</span><span class="sxs-lookup"><span data-stu-id="5d6d4-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5d6d4-147"><strong>장애 조치 (failover) 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-148">통화를 계속 연결</span><span class="sxs-lookup"><span data-stu-id="5d6d4-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d6d4-149"><strong>장애 복구 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-150">통화를 계속 연결</span><span class="sxs-lookup"><span data-stu-id="5d6d4-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5d6d4-151"><strong>장애 복구 (failback) 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="5d6d4-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d6d4-152">통화를 계속 연결</span><span class="sxs-lookup"><span data-stu-id="5d6d4-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

