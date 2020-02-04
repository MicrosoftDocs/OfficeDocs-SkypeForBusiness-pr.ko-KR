---
title: 'Lync Server 2013: 풀 오류 발생 시 통화 대기 환경'
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
ms.openlocfilehash: 59de3b7cc7490c84536cfbc1457c6486af52c33a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="c7f9c-102">풀 오류 발생 시 Lync Server 2013의 통화 대기 환경</span><span class="sxs-lookup"><span data-stu-id="c7f9c-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7f9c-103">_**마지막으로 수정한 주제:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c7f9c-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c7f9c-104">계획 되지 않은 사고 때문에 프런트 엔드 풀을 사용할 수 없게 되 면 파킹 되었지만 아직 검색 되지 않은 통화는 연결이 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="c7f9c-105">백업 풀로 장애 조치 하는 동안 사용자는 백업 풀로 리디렉션되고 복원 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="c7f9c-106">복원 모드에서는 사용자가 통화를 보류할 수 없지만 통화를 대기 상태로 전환 하 고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="c7f9c-107">장애 조치가 완료 되 면 통화가 다시 파킹 되 고 평소와 같이 검색 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="c7f9c-108">장애 복구 중에는 사용자가 복원 모드에서 끝날 때까지 통화를 파킹 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="c7f9c-109">재해 복구 중 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 백업 풀에 배포 된 통화 대기 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="c7f9c-110">따라서 백업 풀로 리디렉션되는 사용자는 백업 풀의 통화 공원 응용 프로그램에 대해 구성 된 통화 대기 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="c7f9c-111">다음 표에는 재해 복구의 단계를 통해 호출 공원 환경이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="c7f9c-112">재해 복구 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="c7f9c-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7f9c-113">통화 상태</span><span class="sxs-lookup"><span data-stu-id="c7f9c-113">Call state</span></span></th>
<th><span data-ttu-id="c7f9c-114">중단 발생 시기</span><span class="sxs-lookup"><span data-stu-id="c7f9c-114">When outage occurs</span></span></th>
<th><span data-ttu-id="c7f9c-115">장애 조치 동안</span><span class="sxs-lookup"><span data-stu-id="c7f9c-115">During failover</span></span></th>
<th><span data-ttu-id="c7f9c-116">장애 복구 중</span><span class="sxs-lookup"><span data-stu-id="c7f9c-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7f9c-117">통화가 아직 파킹 되지 않음</span><span class="sxs-lookup"><span data-stu-id="c7f9c-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-118">통화는 계속 연결 되어 있지만 파킹 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7f9c-119">장애 조치 중에는 사용자가 복원 모드에 있는 동안에는 통화를 파킹 할 수 없지만 보류 하 고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="c7f9c-120">장애 조치가 완료 되 면 통화를 파킹 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c7f9c-121">장애 복구 중에는 사용자가 복원 모드에 있는 동안 통화를 파킹 할 수 없지만 보류 하 고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="c7f9c-122">장애 복구를 완료 하면 통화를 파킹 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7f9c-123">파킹 된 통화 (아직 검색 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c7f9c-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-124">통화가 끊겼습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-125">이 상태의 통화는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-126">통화는 계속 파킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7f9c-127">파킹 통화가 이미 검색 됨</span><span class="sxs-lookup"><span data-stu-id="c7f9c-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-128">통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-129">통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="c7f9c-130">통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7f9c-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

