---
title: 'Lync Server 2013: 풀 오류 발생 시 통화 대기 환경'
description: 'Lync Server 2013: 풀 오류 발생 시 통화 대기 환경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565274"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="c94d6-103">풀 오류 발생 시 Lync Server 2013의 통화 대기 환경</span><span class="sxs-lookup"><span data-stu-id="c94d6-103">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c94d6-104">_**마지막으로 수정 된 항목:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c94d6-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c94d6-105">계획 되지 않은 문제로 인해 프런트 엔드 풀을 사용할 수 없는 경우 파킹 되었지만 아직 검색 되지 않은 통화는 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-105">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="c94d6-106">백업 풀로 장애 조치(failover)하는 중에는 사용자가 백업 풀로 리디렉션되고 복구 모드에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-106">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="c94d6-107">복구 모드에서는 사용자가 통화를 대기시킬 수는 없지만 대기 상태로 설정하고 전송할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-107">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="c94d6-108">장애 조치(failover)가 완료되면 통화가 보통 때처럼 다시 대기되었다고 재개될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-108">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="c94d6-109">장애 복구(failback) 중에는 사용자가 복구 모드가 끝날 때까지 통화를 대기시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-109">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="c94d6-110">재해 복구를 수행 하는 동안 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 백업 풀에 배포 된 통화 대기 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="c94d6-111">따라서 백업 풀로 리디렉션되는 사용자는 백업 풀의 통화 대기 응용 프로그램에 대해 구성 된 통화 대기 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-111">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="c94d6-112">다음 표에는 재해 복구 단계를 통해 제공 되는 통화 대기 환경이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-112">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="c94d6-113">재해 복구 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="c94d6-113">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c94d6-114">통화 상태</span><span class="sxs-lookup"><span data-stu-id="c94d6-114">Call state</span></span></th>
<th><span data-ttu-id="c94d6-115">중단이 발생하는 경우</span><span class="sxs-lookup"><span data-stu-id="c94d6-115">When outage occurs</span></span></th>
<th><span data-ttu-id="c94d6-116">장애 조치(failover) 시</span><span class="sxs-lookup"><span data-stu-id="c94d6-116">During failover</span></span></th>
<th><span data-ttu-id="c94d6-117">장애 복구(failback) 시</span><span class="sxs-lookup"><span data-stu-id="c94d6-117">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c94d6-118">통화가 아직 대기되지 않았음</span><span class="sxs-lookup"><span data-stu-id="c94d6-118">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="c94d6-119">통화가 연결되었지만 대기될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-119">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c94d6-120">장애 조치(failover) 중에는 사용자가 복구 모드에 있는 동안 통화를 대기할 수 없지만 대기 상태로 설정하고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-120">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="c94d6-121">장애 조치(failover)가 완료되면 통화를 대기하고 재개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-121">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c94d6-122">장애 복구(failback) 중에는 사용자가 복구 모드에 있는 동안 통화를 대기할 수 없지만, 대기 상태로 설정하고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-122">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="c94d6-123">장애 복구(failback)가 완료되면 통화를 대기하고 재개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-123">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c94d6-124">통화가 대기되었지만 아직 재개되지 않았음</span><span class="sxs-lookup"><span data-stu-id="c94d6-124">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="c94d6-125">통화가 끊어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-125">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="c94d6-126">이 상태의 통화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-126">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="c94d6-127">통화가 대기 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-127">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c94d6-128">대기된 통화가 이미 재개됨</span><span class="sxs-lookup"><span data-stu-id="c94d6-128">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="c94d6-129">통화가 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="c94d6-130">통화가 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-130">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="c94d6-131">통화가 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c94d6-131">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

