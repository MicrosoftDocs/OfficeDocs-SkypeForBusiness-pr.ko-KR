---
title: 풀 실패 중 Lync Server 2013 사용자 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6506ac67415ca19b33ee968d698d0ed574df8d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="38447-102">Lync Server 2013에서 풀 장애가 발생 한 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="38447-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38447-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="38447-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="38447-104">풀이 장애 조치 되는 경우 영향을 받는 풀의 모든 사용자는 강제로 로그 아웃 한 다음 백업 풀에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="38447-105">간단한 기간 동안에는 백업 풀에 로그인 하는 사용자가 복원 가능 모드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="38447-106">복원 모드에서는 사용자가 Lync Server에서 영구 변경 (예: 연락처 추가)을 발생 시키는 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="38447-107">장애 조치를 완료 한 후 모든 사용자가 백업 풀에서 모든 서비스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="38447-108">풀에 장애가 발생할 경우 사용자가 보유 한 모든 세션은 중단 되며 계속 하려면 장애 조치 (failover) 후에 해당 세션을 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="38447-109">장애 조치 또는 장애 복구 시 사용자가 상주 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="38447-110">실패 한 풀에 속한 사용자는 백업 풀에서 일시적으로 서비스를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="38447-111">홈 풀이 복원 되 면 관리자는 해당 사용자가 원래 홈 풀에서 서비스를 받을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="38447-112">참고 Lync 2013에서 위치 정보 서버 데이터베이스는 백업 풀로 복제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="38447-113">모범 사례를 위해 관리자는 정기적으로 LIS 데이터베이스를 백업 하 고 최신 백업 복사본을 사용 하 여 장애 조치 후 백업 풀에 LIS 데이터베이스를 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="38447-114">장애 조치 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="38447-114">User Experience During Failover</span></span>

<span data-ttu-id="38447-115">사용자가 실패 한 풀에 있으면 사용자가 로그 아웃 됩니다. 사용자가 참여 한 모든 피어 투 피어 세션은 해당 사용자가 구성한 컨퍼런스와 같이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="38447-116">레지스트라 복원 타이머가 만료 되거나 관리자가 장애 조치 절차를 시작할 때까지 사용자는 다시 로그인 할 수 없습니다 (먼저 제공 됨).</span><span class="sxs-lookup"><span data-stu-id="38447-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="38447-117">사용자가 다시 로그인 하면 백업 풀에 로그인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="38447-118">장애 조치가 완료 되기 전에 로그인 하는 경우 장애 조치가 완료 될 때까지 복원 모드에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="38447-119">그 다음에만 사용자가 새 세션을 설정 하거나 이전 세션을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="38447-120">장애 복구 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="38447-120">User Experience During Failback</span></span>

<span data-ttu-id="38447-121">풀 장애 복구는 영향을 받는 사용자가 백업 풀에 로그온 하는 동안 발생할 수 있으며, 장애 복구 중에 사용자가 로그인 하 여 작동 하는 것으로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="38447-122">장애 복구 프로세스가 완료 되기까지 몇 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="38447-123">참조용으로 2만 사용자 풀에 대해 최대 60 분이 소요 될 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="38447-124">다음 표에서는 장애가 있는 사용자가 Lync 2013 클라이언트 또는 Microsoft Lync 2010 클라이언트를 사용 하는 방법에 대 한 자세한 정보를 보여 줍니다. 또한 다른 풀의 사용자가 장애 복구 되는 풀의 사용자를 보고 상호 작용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="38447-125">Microsoft Office Communicator 2007 R2 클라이언트가 있는 사용자는 프런트 엔드 풀이 완전히 장애 복구 될 때까지 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="38447-126">*영향을 받는 사용자* 는 홈 풀에서 장애 조치를 수행한 사용자를 참조 하 고 백업 풀에서 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="38447-127">정의에 따라 백업 풀에서 원래 설정한 사용자는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="38447-128">장애 복구 시 풀의 영향을 받는 사용자에 대 한 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="38447-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38447-129">사용자 상태 또는 작업</span><span class="sxs-lookup"><span data-stu-id="38447-129">User state or task</span></span></th>
<th><span data-ttu-id="38447-130">장애 복구 중</span><span class="sxs-lookup"><span data-stu-id="38447-130">During failback</span></span></th>
<th><span data-ttu-id="38447-131">장애 복구 완료 후</span><span class="sxs-lookup"><span data-stu-id="38447-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38447-132">사용자의 사용자 상태가 이미 로그인 되어 있음</span><span class="sxs-lookup"><span data-stu-id="38447-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="38447-133">사용자가 로그인 되어 있고 백업 풀에 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="38447-134">일부 시점에서는 사용자가 로그 아웃 하 고 원래 홈 풀 (복원 모드)에 다시 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="38447-135">사용자는 로그인 상태를 유지 하 고 일반 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38447-136">새 사용자 로그인</span><span class="sxs-lookup"><span data-stu-id="38447-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="38447-137">사용자는 복원 모드에서 홈 풀에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="38447-138">사용자는 일반 모드에서 원래 홈 풀에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38447-139">영향을 받는 사용자가 구성한 지속적인 회의</span><span class="sxs-lookup"><span data-stu-id="38447-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="38447-140">모든 컨퍼런스 형식을 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="38447-141">다시 참가 단추가 표시 되지만, 영향을 받는 사용자가 복원 모드에 있는 동안에는 사용자가 다시 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="38447-142">이제 모든 형식을 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-142">All modalities now work.</span></span> <span data-ttu-id="38447-143">모든 참가자가 회의에 다시 참가 하려면을 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38447-144">영향을 받지 않는 사용자가 구성한 지속적인 컨퍼런스</span><span class="sxs-lookup"><span data-stu-id="38447-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="38447-145">회의가 계속 되며 영향을 받는 사용자는 회의에 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="38447-146">영향을 받는 사용자는 복원 모드에서 수행할 수 있는 작업으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="38447-147">회의가 계속 되며, 사용자가 복원 모드를 종료 한 후에도 영향을 받는 사용자가 회의 및 모든 형식을 작업에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38447-148">예약 된 모임 예약 또는 수정, 특별 컨퍼런스 만들기</span><span class="sxs-lookup"><span data-stu-id="38447-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="38447-149">사용자가 복원 모드에 있는 동안에는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="38447-150">모든 형식을에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38447-151">같은 풀의 다른 사용자가 표시 한 상태</span><span class="sxs-lookup"><span data-stu-id="38447-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="38447-152">현재 상태를 알 수 없음 복원 모드 동안 사용자가 백업 풀에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="38447-153">사용자가 설정한 마지막 현재 상태를 표시 하 고 현재 존재 변경 내용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38447-154">연락처 목록 및 주소록 서비스 사용 가능성</span><span class="sxs-lookup"><span data-stu-id="38447-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="38447-155">사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="38447-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="38447-156">공간이</span><span class="sxs-lookup"><span data-stu-id="38447-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38447-157">모든 피어 투 피어 세션 및 형식을</span><span class="sxs-lookup"><span data-stu-id="38447-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="38447-158">공간이</span><span class="sxs-lookup"><span data-stu-id="38447-158">Available</span></span></p></td>
<td><p><span data-ttu-id="38447-159">공간이</span><span class="sxs-lookup"><span data-stu-id="38447-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="38447-160">다른 풀의 장애 복구를 수행 하는 동안 영향을 받지 않는 풀에 속한 사용자의 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="38447-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38447-161">사용자 작업</span><span class="sxs-lookup"><span data-stu-id="38447-161">User task</span></span></th>
<th><span data-ttu-id="38447-162">장애 복구 중</span><span class="sxs-lookup"><span data-stu-id="38447-162">During failback</span></span></th>
<th><span data-ttu-id="38447-163">장애 복구 완료 후</span><span class="sxs-lookup"><span data-stu-id="38447-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38447-164">영향을 받는 사용자의 현재 상태 보기</span><span class="sxs-lookup"><span data-stu-id="38447-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="38447-165">영향을 받는 사용자가 설정한 마지막 현재 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="38447-166">중.</span><span class="sxs-lookup"><span data-stu-id="38447-166">Working.</span></span> <span data-ttu-id="38447-167">영향을 받지 않는 사용자는 해당 사용자가 수행한 업데이트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38447-168">영향을 받는 사용자가 구성한 지속적인 회의</span><span class="sxs-lookup"><span data-stu-id="38447-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="38447-169">모든 컨퍼런스 형식을 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38447-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="38447-170">이제 모든 형식을 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-170">All modalities now work.</span></span> <span data-ttu-id="38447-171">모든 참가자가 회의에 다시 참가 하려면을 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38447-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38447-172">영향을 받지 않는 사용자가 구성한 지속적인 컨퍼런스</span><span class="sxs-lookup"><span data-stu-id="38447-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="38447-173">회의가 계속 되 고, 영향을 받는 사용자가 회의 및 모든 형식을 작업에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="38447-174">회의가 계속 되 고, 영향을 받는 사용자가 회의 및 모든 형식을 작업에 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38447-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38447-175">모든 피어 투 피어 세션 및 형식을</span><span class="sxs-lookup"><span data-stu-id="38447-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="38447-176">공간이</span><span class="sxs-lookup"><span data-stu-id="38447-176">Available</span></span></p></td>
<td><p><span data-ttu-id="38447-177">공간이</span><span class="sxs-lookup"><span data-stu-id="38447-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

