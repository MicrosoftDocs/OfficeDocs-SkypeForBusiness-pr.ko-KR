---
title: Lync Server 2013 풀 오류 발생 시 사용자 환경
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
ms.openlocfilehash: 98429875ce56371248552eddae9cb7db5e511529
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="2e1c6-102">Lync Server 2013에서 풀 오류 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="2e1c6-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e1c6-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2e1c6-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2e1c6-104">풀이 장애 조치(failover)되는 경우 영향을 받는 풀의 모든 사용자는 로그아웃된 후 백업 풀에 로그인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="2e1c6-105">백업 풀에 로그인된 사용자는 잠시 동안 복구 모드에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="2e1c6-106">복구 모드에서는 사용자가 연락처 추가와 같이 Lync Server에 대 한 영구 변경을 수행 하는 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="2e1c6-107">장애 조치가 완료된 후에 모든 사용자는 백업 풀에서 모든 서비스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="2e1c6-108">풀에 장애가 발생할 때 사용자가 참여 중인 세션은 모두 중단되며 사용자는 장애 조치 후에 이러한 세션을 다시 설정해야 세션을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="2e1c6-p102">사용자는 장애 조치 또는 장애 복구 후에 홈으로 복원되지 않습니다. 장애가 발생한 풀에 속한 사용자는 일시적으로 백업 풀에서 서비스를 받게 됩니다. 홈 풀이 복원되면 관리자가 이러한 사용자를 장애 복구하여 원래 홈 풀에서 서비스를 받도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="2e1c6-112">참고 Lync 2013에서 위치 정보 서버 데이터베이스는 백업 풀로 복제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="2e1c6-113">관리자는 LIS 데이터베이스를 백업하여 장애 조치 후 백업 풀에서 LIS 데이터베이스를 복원하는 데 최신 백업 복사본을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="2e1c6-114">장애 조치 시 사용자 경험</span><span class="sxs-lookup"><span data-stu-id="2e1c6-114">User Experience During Failover</span></span>

<span data-ttu-id="2e1c6-p104">장애가 발생한 풀에 있던 사용자는 로그아웃됩니다. 사용자가 참가하고 있던 피어 투 피어 세션은 종료되며 사용자가 구성한 회의도 마찬가지입니다. 등록자 복구 타이머가 만료되거나 관리자가 장애 조치 절차를 시작할 때까지(먼저 도래하는 것) 다시 로그인할 수 없습니다. 사용자가 다시 로그인할 때는 백업 풀에 로그인하게 됩니다. 장애 조치가 완료되기 전에 로그인할 경우 장애 조치가 완료될 때까지 복구 모드에 있게 됩니다. 완료 후에 비로소 사용자는 새 세션을 설정하거나 이전 세션을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="2e1c6-120">장애 복구 시 사용자 경험</span><span class="sxs-lookup"><span data-stu-id="2e1c6-120">User Experience During Failback</span></span>

<span data-ttu-id="2e1c6-p105">영향을 받은 사용자가 백업 풀에 로그온해 있는 동안 풀 장애 복구가 이루어질 수 있으며, 사용자는 장애 복구 동안 로그온 및 작동 상태로 유지됩니다. 장애 복구 프로세스가 완료되는 데는 몇 분 정도 걸립니다.  참고로 20,000명의 사용자가 있는 풀의 경우 최대 60분이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="2e1c6-124">다음 표에는 장애 복구 중 및 후에 Lync 2013 클라이언트나 Microsoft Lync 2010 클라이언트의 사용자가 영향을 받는 방법에 대 한 자세한 내용이 나와 있고, 다른 풀의 사용자가 장애가 발생 한 풀에서 사용자를 보고 상호 작용 하는 방법에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="2e1c6-125">Microsoft Office Communicator 2007 R2 클라이언트를 사용 하는 사용자는 프런트 엔드 풀이 완전히 장애 복구 될 때까지 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="2e1c6-p107">*영향을 받는 사용자*라는 용어는 홈 풀에서 장애 조치되어 백업 풀에서 서비스를 받고 있는 사용자를 가리킵니다. 정의에 따라, 원래 백업 풀에 배치된 사용자는 영향을 받는 사용자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="2e1c6-128">장애 복구 시 풀에 있는 영향을 받는 사용자의 사용자 경험</span><span class="sxs-lookup"><span data-stu-id="2e1c6-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e1c6-129">사용자 상태 또는 작업</span><span class="sxs-lookup"><span data-stu-id="2e1c6-129">User state or task</span></span></th>
<th><span data-ttu-id="2e1c6-130">장애 복구 시</span><span class="sxs-lookup"><span data-stu-id="2e1c6-130">During failback</span></span></th>
<th><span data-ttu-id="2e1c6-131">장애 복구 완료 후</span><span class="sxs-lookup"><span data-stu-id="2e1c6-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e1c6-132">이미 로그인된 사용자의 사용자 상태</span><span class="sxs-lookup"><span data-stu-id="2e1c6-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-p108">사용자는 로그인된 상태로 유지되며 백업 풀에 연결되어 있습니다. 특정 시점에 사용자는 로그아웃되었다가 다시 원래 홈 풀로 로그인되어 복구 모드에 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-135">사용자는 로그인된 상태로 유지되며 일반 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e1c6-136">새 사용자 로그인</span><span class="sxs-lookup"><span data-stu-id="2e1c6-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-137">사용자는 홈 풀에 복구 모드로 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-138">사용자는 원래 홈 풀에 일반 모드로 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e1c6-139">영향을 받는 사용자가 구성한 진행 중인 회의</span><span class="sxs-lookup"><span data-stu-id="2e1c6-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-p109">모든 형식의 회의가 종료됩니다. 다시 참가 단추가 나타나지만 영향을 받는 사용자가 복구 모드에 있는 동안에는 아무 사용자도 다시 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-p110">모든 형식의 회의가 다시 작동합니다. 모든 참가자는 클릭하여 회의에 다시 참가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e1c6-144">영향을 받지 않는 사용자가 구성한 진행 중인 회의</span><span class="sxs-lookup"><span data-stu-id="2e1c6-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-p111">회의가 계속되며 영향을 받는 사용자가 회의에서 유지될 수 있습니다. 영향을 받는 사용자는 복구 모드에서 할 수 있는 작업으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-147">회의가 계속되며 영향을 받는 사용자가 회의에서 유지될 수 있습니다. 사용자가 복구 모드에서 전환되면 모든 형식이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e1c6-148">모임 예약 또는 예약된 모임 수정, 임시 회의 만들기</span><span class="sxs-lookup"><span data-stu-id="2e1c6-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-149">사용자가 복구 모드에 있는 동안 불가능</span><span class="sxs-lookup"><span data-stu-id="2e1c6-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-150">모든 형식에서 가능</span><span class="sxs-lookup"><span data-stu-id="2e1c6-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e1c6-151">같은 풀에 있는 다른 사용자가 현재 상태 확인</span><span class="sxs-lookup"><span data-stu-id="2e1c6-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-152">사용자가 백업 풀에 로그인되어 복구 모드에 있는 동안에는 현재 상태를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-153">사용자가 설정한 마지막 현재 상태 설정이 표시되고 이제 현재 상태 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e1c6-154">대화 상대 목록 및 주소록 서비스 사용 가능성</span><span class="sxs-lookup"><span data-stu-id="2e1c6-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-155">사용 불가</span><span class="sxs-lookup"><span data-stu-id="2e1c6-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-156">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="2e1c6-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e1c6-157">모든 피어 투 피어 세션 및 형식</span><span class="sxs-lookup"><span data-stu-id="2e1c6-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-158">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="2e1c6-158">Available</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-159">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="2e1c6-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="2e1c6-160">다른 풀의 장애 복구 시 영향을 받지 않는 풀에 배치된 사용자의 사용자 경험</span><span class="sxs-lookup"><span data-stu-id="2e1c6-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e1c6-161">사용자 작업</span><span class="sxs-lookup"><span data-stu-id="2e1c6-161">User task</span></span></th>
<th><span data-ttu-id="2e1c6-162">장애 복구 시</span><span class="sxs-lookup"><span data-stu-id="2e1c6-162">During failback</span></span></th>
<th><span data-ttu-id="2e1c6-163">장애 복구 완료 후</span><span class="sxs-lookup"><span data-stu-id="2e1c6-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e1c6-164">영향을 받는 사용자의 현재 상태 보기</span><span class="sxs-lookup"><span data-stu-id="2e1c6-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-165">영향을 받는 사용자가 설정한 마지막 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-p112">작동. 영향을 받지 않는 사용자는 영향을 받는 사용자가 수행한 업데이트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e1c6-168">영향을 받는 사용자가 구성한 진행 중인 회의</span><span class="sxs-lookup"><span data-stu-id="2e1c6-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-169">모든 형식의 회의가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-p113">모든 형식의 회의가 다시 작동합니다. 모든 참가자는 클릭하여 회의에 다시 참가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e1c6-172">영향을 받지 않는 사용자가 구성한 진행 중인 회의</span><span class="sxs-lookup"><span data-stu-id="2e1c6-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-173">회의가 계속되며 영향을 받는 사용자가 회의에서 유지되고 모든 형식이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-174">회의가 계속되며 영향을 받는 사용자가 회의에서 유지되고 모든 형식이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2e1c6-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e1c6-175">모든 피어 투 피어 세션 및 형식</span><span class="sxs-lookup"><span data-stu-id="2e1c6-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-176">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="2e1c6-176">Available</span></span></p></td>
<td><p><span data-ttu-id="2e1c6-177">사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="2e1c6-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

