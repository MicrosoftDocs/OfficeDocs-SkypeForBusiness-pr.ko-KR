---
title: 'Lync Server 2013: 재해 복구 중의 그룹 통화 픽업 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="18890-102">Lync Server 2013에서 재해 복구를 수행 하는 동안 그룹 통화 픽업 관리</span><span class="sxs-lookup"><span data-stu-id="18890-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18890-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="18890-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="18890-104">계획 되지 않은 사고 때문에 프런트 엔드 풀을 사용할 수 없게 되 면 서비스가 백업 풀로 장애 조치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18890-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="18890-105">백업 풀로 장애 조치 (failover) 하는 동안 사용자가 복원 모드에 있는 백업 풀로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="18890-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="18890-106">복원 모드에서는 사용자가 다른 사용자의 통화를 선택 하거나 다른 사용자가 통화를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="18890-107">장애 조치가 완료 되 면 사용자는 평소 대로 그룹 통화 픽업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="18890-108">기본 풀로 장애 복구 하는 동안 사용자는 기본 풀로 리디렉션되고 복원 모드에 다시 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="18890-109">사용자가 복원 모드를 벗어나면 그룹 통화 픽업 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="18890-110">이 섹션에서는 장애 복구 중 그룹 통화 픽업에 대 한 몇 가지 고려 사항에 대해 설명 하 고 사용자 환경에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="18890-111">재해 복구 중 그룹 통화 픽업 고려 사항</span><span class="sxs-lookup"><span data-stu-id="18890-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="18890-112">재해 복구 중 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 통화 픽업 그룹 번호에 대 한 백업 풀에서 실행 되는 통화 공원 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="18890-113">따라서 재해 복구 중 그룹 통화 픽업 지원에는 기본 풀과 백업 풀 모두에서 통화 대기 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="18890-114">통화 공원 표 내의 그룹 통화 픽업 번호 범위는 백업 풀에 대 한 장애 조치 프로세스가 완료 된 후 백업 풀로 리디렉션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="18890-115">주 풀에 대 한 장애 복구 프로세스가 완료 되 면 번호 범위를 기본 풀로 다시 리디렉션 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="18890-116">그룹 통화 픽업 범위를 리디렉션하려면 **Set-CsCallParkOrbit** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="18890-117">다른 FQDN (정규화 된 도메인 이름)으로 새 풀을 배포 하 여 기본 풀을 바꾸려면 기본 풀과 연결 된 모든 그룹 통화 픽업 번호 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18890-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="18890-118">숫자 범위를 새 풀에 다시 할당 하려면 **CsCallParkOrbit** cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18890-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="18890-119">**Set-CsCallParkOrbit** cmdlet에 대 한 자세한 내용은 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18890-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="18890-120">풀 오류 중 그룹 통화 픽업 경험</span><span class="sxs-lookup"><span data-stu-id="18890-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="18890-121">다음 표에는 재해 복구의 단계를 통해 그룹 통화 픽업 환경이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="18890-122">재해 복구 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="18890-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18890-123">통화 상태</span><span class="sxs-lookup"><span data-stu-id="18890-123">Call state</span></span></th>
<th><span data-ttu-id="18890-124">백업 풀에 대 한 장애 조치</span><span class="sxs-lookup"><span data-stu-id="18890-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="18890-125">주 풀 장애 복구</span><span class="sxs-lookup"><span data-stu-id="18890-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18890-126">새로운 통화</span><span class="sxs-lookup"><span data-stu-id="18890-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="18890-127"><strong>장애 조치 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-128">복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="18890-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-129"><strong>장애 조치 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-130">회복성 있지 않은 사용자 및 그룹 통화 픽업 번호 범위가 백업 풀로 리디렉션되는 경우 사용할 수 있는 그룹 통화 픽업</span><span class="sxs-lookup"><span data-stu-id="18890-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18890-131"><strong>장애 복구 프로세스가 진행 되는 동안:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-132">복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="18890-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-133"><strong>장애 복구 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-134">회복성 있지 않은 사용자 및 그룹 통화 픽업 번호 범위가 기본 풀로 다시 리디렉션되는 경우 사용할 수 있는 그룹 통화 픽업</span><span class="sxs-lookup"><span data-stu-id="18890-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18890-135">그룹 통화 픽업 대기열의 통화</span><span class="sxs-lookup"><span data-stu-id="18890-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="18890-136"><strong>장애 조치 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-137">큐의 통화는 그룹 통화 픽업을 통해 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-138"><strong>장애 조치 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-139">이 상태의 통화 없음</span><span class="sxs-lookup"><span data-stu-id="18890-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18890-140"><strong>장애 복구 프로세스가 진행 되는 동안:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-141">큐의 통화는 그룹 통화 픽업을 통해 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-142"><strong>장애 복구 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-143">큐의 통화는 그룹 통화 픽업을 통해 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18890-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18890-144">통화 설정</span><span class="sxs-lookup"><span data-stu-id="18890-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="18890-145"><strong>장애 조치 프로세스 중:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-146">통화 연결 유지</span><span class="sxs-lookup"><span data-stu-id="18890-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-147"><strong>장애 조치 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-148">통화 연결 유지</span><span class="sxs-lookup"><span data-stu-id="18890-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18890-149"><strong>장애 복구 프로세스가 진행 되는 동안:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-150">통화 연결 유지</span><span class="sxs-lookup"><span data-stu-id="18890-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="18890-151"><strong>장애 복구 완료 후:</strong></span><span class="sxs-lookup"><span data-stu-id="18890-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="18890-152">통화 연결 유지</span><span class="sxs-lookup"><span data-stu-id="18890-152">Calls stay connected</span></span></p></li>
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

