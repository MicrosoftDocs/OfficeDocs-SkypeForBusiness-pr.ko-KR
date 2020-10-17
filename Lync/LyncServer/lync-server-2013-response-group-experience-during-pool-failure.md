---
title: 풀 오류 발생 시 Lync Server 2013 응답 그룹 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684d33219bb6146a0c5dc85894c060affd6745a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511645"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="74e96-102">풀 오류 발생 시 Lync Server 2013의 응답 그룹 환경</span><span class="sxs-lookup"><span data-stu-id="74e96-102">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74e96-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="74e96-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="74e96-104">이 섹션에서는 다음 단계에서 응답 그룹 활동에 주는 영향에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="74e96-105">기본 풀에서 중단이 발생하지만 장애 조치(Failover)가 아직 시작되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="74e96-106">서비스가 백업 풀로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="74e96-107">서비스가 기본 풀로 장애 복구(failback)됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="74e96-108">중단 발생 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="74e96-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="74e96-109">풀 또는 사이트 중단이 발생하지만 관리자가 아직 장애 조치(failover)를 시작하지 않은 경우 응답 그룹 활동은 다음 표에 설명된 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74e96-p101">재해 복구 중 통화는 기본 풀 응답 그룹을 복구 중에 백업 풀로 가져왔는지 여부에 따라 다르게 작동합니다. 다음 표에서 가져온 응답 그룹에 대한 참조는 기본 풀 응답 그룹을 재해 복구 모드 중에 백업 풀로 가져왔음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="74e96-112">중단 발생</span><span class="sxs-lookup"><span data-stu-id="74e96-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74e96-113">통화 또는 사용자 작업 유형</span><span class="sxs-lookup"><span data-stu-id="74e96-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="74e96-114">중단 중</span><span class="sxs-lookup"><span data-stu-id="74e96-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74e96-115">에이전트에 연결된 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-116">일반 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-117">익명 통화는 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-118">에이전트에 아직 연결되지 않은 진행 중인 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="74e96-119">통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e96-120">새 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-121">통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-122">응답 그룹을 가져왔으면 백업 풀로 통화가 연결되지만 기본 풀에 있는 에이전트에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-123">응답 그룹을 대신하는 에이전트 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="74e96-124">이 단계 중에는 기능이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e96-125">에이전트 로그인 및 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="74e96-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-126">기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-127">백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-128">가져온 에이전트 그룹은 에이전트 콘솔에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-129">응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="74e96-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-130">기본 풀이 소유하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-131">백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-132">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="74e96-133">장애 조치(Failover) 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="74e96-133">User Experience During Failover</span></span>

<span data-ttu-id="74e96-p102">관리자가 백업 풀에 대한 장애 조치(failover)를 호출할 경우, 장애 조치(failover) 동안 및 이후의 응답 그룹 활동은 다음 표에 설명된 대로 처리됩니다. 첫 번째 열은 발생 가능한 활동 유형에 대해 설명합니다. 가운데 열은 백업 풀로 장애 조치(failover)하는 짧은 시간 동안 각 활동이 처리되는 방법에 대해 설명합니다. 마지막 열은 장애 조치(failover) 프로세스가 완료되고 백업 풀이 기본 풀 대신 작동하는 기간 동안 활동이 처리되는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74e96-p103">재해 복구 중 통화는 기본 풀 응답 그룹을 복구 중에 백업 풀로 가져왔는지 여부에 따라 다르게 작동합니다. 다음 표에서 가져온 응답 그룹에 대한 참조는 기본 풀 응답 그룹을 재해 복구 모드 중에 백업 풀로 가져왔음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="74e96-140">장애 조치(Failover)가 시작됨</span><span class="sxs-lookup"><span data-stu-id="74e96-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74e96-141">통화 또는 사용자 작업 유형</span><span class="sxs-lookup"><span data-stu-id="74e96-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="74e96-142">장애 조치(Failover) 동안</span><span class="sxs-lookup"><span data-stu-id="74e96-142">During Failover</span></span></th>
<th><span data-ttu-id="74e96-143">장애 조치(Failover) 완료 후</span><span class="sxs-lookup"><span data-stu-id="74e96-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74e96-144">에이전트에 연결된 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-145">일반 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-146">익명 통화는 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-147">일반 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-148">가져온 응답 그룹의 경우 백업 풀에 연결된 익명 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-149">에이전트에 아직 연결되지 않은 진행 중인 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="74e96-150">통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-151">응답 그룹을 가져오지 않은 경우 이 상태의 통화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="74e96-152">가져온 응답 그룹의 경우 백업 풀에 연결된 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e96-153">새 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-154">통화 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-155">가져온 응답 그룹의 경우 통화가 백업 풀에 연결되지만 기본 풀에 있는 에이전트에는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-156">응답 그룹을 가져오지 않은 경우 통화의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-157">가져온 응답 그룹의 경우 통화가 백업 풀에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-158">응답 그룹을 대신하는 에이전트 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="74e96-159">이 단계 중에는 기능이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-160">응답 그룹을 가져오지 않은 경우 통화가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="74e96-161">가져온 응답 그룹의 경우 통화가 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e96-162">에이전트 로그인 및 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="74e96-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-163">기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-164">백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-165">가져온 에이전트 그룹이 에이전트 콘솔에 표시되고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-166">기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-167">백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-168">가져온 에이전트 그룹이 에이전트 콘솔에 표시되고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-169">응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="74e96-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-170">기본 풀이 소유하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-171">백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-172">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-173">기본 풀이 소유하는 응답 그룹은 백 엔드 데이터베이스의 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-174">백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-175">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="74e96-176">복구(Failback) 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="74e96-176">User Experience During Failback</span></span>

<span data-ttu-id="74e96-177">관리자가 기본 풀로 복구(failback)를 호출할 경우, 복구(failback) 동안 및 이후의 응답 그룹 활동은 다음 표에 설명된 대로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74e96-p104">재해 복구 중 통화는 기본 풀 응답 그룹을 복구 중에 백업 풀로 가져왔는지 여부에 따라 다르게 작동합니다. 다음 표에서 가져온 응답 그룹에 대한 참조는 기본 풀 응답 그룹을 재해 복구 모드 중에 백업 풀로 가져왔음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="74e96-180">복구(Failback) 중 통화 처리</span><span class="sxs-lookup"><span data-stu-id="74e96-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74e96-181">통화 또는 사용자 작업 유형</span><span class="sxs-lookup"><span data-stu-id="74e96-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="74e96-182">복구(Failback) 동안</span><span class="sxs-lookup"><span data-stu-id="74e96-182">During Failback</span></span></th>
<th><span data-ttu-id="74e96-183">복구(Failback) 완료 후</span><span class="sxs-lookup"><span data-stu-id="74e96-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74e96-184">에이전트에 연결된 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-185">일반 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-186">응답 그룹을 가져오지 않은 경우 이 상태의 익명 통화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="74e96-187">가져온 응답 그룹의 경우 익명 통화가 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-188">일반 통화는 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="74e96-189">응답 그룹을 가져오지 않은 경우 이 상태의 익명 통화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="74e96-190">가져온 응답 그룹의 경우 익명 통화가 연결된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-191">에이전트에 아직 연결되지 않은 진행 중인 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-192">응답 그룹을 가져오지 않은 경우 이 상태의 통화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="74e96-193">가져온 응답 그룹의 경우 통화의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-194">응답 그룹을 가져오지 않은 경우 이 상태의 통화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="74e96-195">가져온 응답 그룹의 경우 통화의 연결이 끊어집니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e96-196">새 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="74e96-197">통화가 기본 풀에 연결되지만 기본 풀에 있는 에이전트에는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="74e96-198">통화가 기본 풀에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-199">응답 그룹을 대신하는 에이전트 통화</span><span class="sxs-lookup"><span data-stu-id="74e96-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="74e96-200">이 단계 중에는 기능이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="74e96-201">통화가 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74e96-202">에이전트 로그인 및 에이전트 정보</span><span class="sxs-lookup"><span data-stu-id="74e96-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-203">기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-204">백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-205">가져온 에이전트 그룹이 에이전트 콘솔에 표시되고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-206">기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-207">백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="74e96-208">가져온 에이전트 그룹은 에이전트 콘솔에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74e96-209">응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="74e96-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="74e96-210">기본 풀이 소유하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-211">백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-212">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="74e96-213">기본 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-214">백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="74e96-215">가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74e96-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

