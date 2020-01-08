---
title: Lync Server 2013 풀 오류 발생 시 응답 그룹 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="25eac-102">풀 오류 발생 시 Lync Server 2013의 응답 그룹 환경</span><span class="sxs-lookup"><span data-stu-id="25eac-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25eac-103">_**마지막으로 수정한 주제:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="25eac-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="25eac-104">이 섹션에서는 응답 그룹 활동이 다음 단계에서 영향을 받는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="25eac-105">기본 풀에서 작동 중지가 발생 하지만 장애 조치는 아직 시작 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="25eac-106">서비스가 백업 풀로 장애 조치 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="25eac-107">서비스가 기본 풀로 장애 복구 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="25eac-108">중단 발생 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="25eac-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="25eac-109">풀 또는 사이트 중단이 발생 하지만 관리자가 아직 장애 조치를 시작 하지 않은 경우 응답 그룹 활동은 다음 표에 설명 된 대로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25eac-110">재해 복구 중에는 복구 중에 기본 풀 응답 그룹을 백업 풀로 가져왔는지 여부에 따라 호출이 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="25eac-111">다음 표에서는 재해 복구 모드 중에 주 풀 응답 그룹을 백업 풀로 가져왔는지 평균 응답 그룹을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="25eac-112">중단 발생</span><span class="sxs-lookup"><span data-stu-id="25eac-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25eac-113">통화 유형 또는 사용자 작업</span><span class="sxs-lookup"><span data-stu-id="25eac-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="25eac-114">비활성 동안</span><span class="sxs-lookup"><span data-stu-id="25eac-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25eac-115">에이전트에 연결 된 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-116">일반 통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-117">익명 통화는 연결이 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-118">아직 에이전트에 연결 되지 않은 진행 중인 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="25eac-119">통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25eac-120">새로운 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-121">통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-122">응답 그룹을 가져온 경우 백업 풀에 연결을 호출 하지만 기본 풀에 있는 에이전트는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-123">응답 그룹을 대신 하 여 에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="25eac-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="25eac-124">이 단계에서는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25eac-125">에이전트 로그인 및 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="25eac-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-126">주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-127">에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-128">가져온 에이전트 그룹은 에이전트 콘솔에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-129">응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="25eac-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-130">기본 풀에서 소유 하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-131">백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-132">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="25eac-133">장애 조치 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="25eac-133">User Experience During Failover</span></span>

<span data-ttu-id="25eac-134">관리자가 백업 풀로 장애 조치 (failover)를 호출 하면 다음 표에 설명 된 대로 응답 그룹 활동이 장애 조치 중에 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="25eac-135">첫 번째 열은 수행할 수 있는 활동 유형을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="25eac-136">중간 열에서는 백업 풀로 장애 조치 하는 데 걸리는 짧은 시간 동안 각 활동이 처리 되는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="25eac-137">마지막 열은 장애 조치 프로세스가 완료 되 고 백업 풀이 기본 풀에 대해 발생 한 후 해당 기간 동안 활동이 처리 되는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25eac-138">재해 복구 중에는 복구 중에 기본 풀 응답 그룹을 백업 풀로 가져왔는지 여부에 따라 호출이 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="25eac-139">다음 표에서는 재해 복구 모드 중에 주 풀 응답 그룹을 백업 풀로 가져왔는지 평균 응답 그룹을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="25eac-140">장애 조치 시작 됨</span><span class="sxs-lookup"><span data-stu-id="25eac-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25eac-141">통화 유형 또는 사용자 작업</span><span class="sxs-lookup"><span data-stu-id="25eac-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="25eac-142">장애 조치 동안</span><span class="sxs-lookup"><span data-stu-id="25eac-142">During Failover</span></span></th>
<th><span data-ttu-id="25eac-143">장애 조치 완료 후</span><span class="sxs-lookup"><span data-stu-id="25eac-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25eac-144">에이전트에 연결 된 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-145">일반 통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-146">익명 통화는 연결이 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-147">일반 통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-148">가져온 응답 그룹의 경우 백업 풀에 도달한 익명 호출은 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-149">아직 에이전트에 연결 되지 않은 진행 중인 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="25eac-150">통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-151">응답 그룹을 가져오지 못한 경우에는 모든 호출이이 상태에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="25eac-152">가져온 응답 그룹의 경우 백업 풀에 도달 하는 호출은 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25eac-153">새로운 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-154">통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-155">가져온 응답 그룹의 경우 백업 풀에 연결을 호출 하지만 기본 풀에 있는 에이전트는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-156">응답 그룹을 가져오지 못한 경우에는 통화가 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-157">가져온 응답 그룹의 경우 백업 풀에 연결을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-158">응답 그룹을 대신 하 여 에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="25eac-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="25eac-159">이 단계에서 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-160">응답 그룹을 가져오지 못한 경우에는 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="25eac-161">가져온 응답 그룹의 경우 호출이 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25eac-162">에이전트 로그인 및 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="25eac-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-163">주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-164">에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-165">가져온 에이전트 그룹은 에이전트 콘솔에 표시 되 고, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-166">주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-167">에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-168">가져온 에이전트 그룹은 에이전트 콘솔에 표시 되 고, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-169">응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="25eac-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-170">기본 풀에서 소유 하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-171">백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-172">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-173">백 엔드 데이터베이스의 가용성에 따라 주 풀에서 소유 하는 응답 그룹을 볼 수는 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-174">백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-175">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="25eac-176">장애 복구 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="25eac-176">User Experience During Failback</span></span>

<span data-ttu-id="25eac-177">관리자가 기본 풀로 장애 복구 (failback)를 호출 하면 다음 표에 설명 된 대로 응답 그룹 활동이 장애 복구 중 및 이후 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25eac-178">재해 복구 중에는 복구 중에 기본 풀 응답 그룹을 백업 풀로 가져왔는지 여부에 따라 호출이 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="25eac-179">다음 표에서는 재해 복구 모드 중에 주 풀 응답 그룹을 백업 풀로 가져왔는지 평균 응답 그룹을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="25eac-180">장애 복구 시 통화 처리</span><span class="sxs-lookup"><span data-stu-id="25eac-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25eac-181">통화 유형 또는 사용자 작업</span><span class="sxs-lookup"><span data-stu-id="25eac-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="25eac-182">장애 복구 중</span><span class="sxs-lookup"><span data-stu-id="25eac-182">During Failback</span></span></th>
<th><span data-ttu-id="25eac-183">장애 복구 완료 후</span><span class="sxs-lookup"><span data-stu-id="25eac-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25eac-184">에이전트에 연결 된 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-185">일반 통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-186">응답 그룹을 가져오지 못한 경우에는 익명 호출이이 상태에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="25eac-187">가져온 응답 그룹의 경우 익명 통화가 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-188">일반 통화는 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="25eac-189">응답 그룹을 가져오지 못한 경우에는 익명 호출이이 상태에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="25eac-190">가져온 응답 그룹의 경우 익명 통화가 연결 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-191">아직 에이전트에 연결 되지 않은 진행 중인 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-192">응답 그룹을 가져오지 못한 경우에는 모든 호출이이 상태에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="25eac-193">가져온 응답 그룹의 경우 통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-194">응답 그룹을 가져오지 못한 경우에는 모든 호출이이 상태에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="25eac-195">가져온 응답 그룹의 경우 통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25eac-196">새로운 통화</span><span class="sxs-lookup"><span data-stu-id="25eac-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="25eac-197">기본 풀에 연결 하는 호출이 있지만 기본 풀에 있는 에이전트에는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="25eac-198">기본 풀에 연결을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-199">응답 그룹을 대신 하 여 에이전트 호출</span><span class="sxs-lookup"><span data-stu-id="25eac-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="25eac-200">이 단계에서는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="25eac-201">통화에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25eac-202">에이전트 로그인 및 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="25eac-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-203">주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-204">에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-205">가져온 에이전트 그룹은 에이전트 콘솔에 표시 되 고, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-206">주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-207">에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="25eac-208">가져온 에이전트 그룹은 에이전트 콘솔에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25eac-209">응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="25eac-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25eac-210">기본 풀에서 소유 하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-211">백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-212">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="25eac-213">기본 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-214">백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="25eac-215">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25eac-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

