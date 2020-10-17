---
title: 응답 그룹 마이그레이션
description: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570324"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="a338e-103">응답 그룹 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a338e-103">Migrate response groups</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a338e-104">_**마지막으로 수정 된 항목:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="a338e-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="a338e-105">사용자를 Lync Server 2013 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-105">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="a338e-106">응답 그룹 마이그레이션에는 레거시 배포에서 Lync Server 2013 풀로 에이전트 그룹, 큐, 워크플로, 오디오 파일 및 이동 응답 그룹 대화 상대 개체를 복사 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-106">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="a338e-107">레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 통화가 Lync Server 2013 풀의 응답 그룹 응용 프로그램에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-107">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="a338e-108">응답 그룹에 대한 호출은 더 이상 레거시 풀에서 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-108">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a338e-109">모든 사용자를 Lync Server 2013 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만 모든 사용자를 먼저 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-109">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="a338e-110">특히 응답 그룹 에이전트를 실행 하는 사용자는 Lync Server 2013 풀로 이동할 때까지 새 기능의 전체 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-110">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="a338e-111">응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 Lync Server 2013 풀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-111">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="a338e-112">Enterprise Voice를 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 및 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="a338e-113">**-Csservice** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-113">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a338e-114">레거시 응답 그룹을 마이그레이션하기 전에 Lync Server 2013 풀에서 새 Lync Server 2013 response 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-114">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="a338e-115">이전 풀의 응답 그룹을 Lync Server 2013로 마이그레이션하려면 **export-csrgsconfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-115">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a338e-116">응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-116">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="a338e-117">마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-117">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="a338e-118">응답 그룹을 마이그레이션한 후에는 Lync Server 제어판 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-118">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="a338e-119">응답 그룹을 마이그레이션할 때 Lync Server 2010 응답 그룹은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-119">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="a338e-120">Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 마이그레이션 후에 응답 그룹을 관리 하는 경우 Lync Server 2010 response 그룹과 Lync Server 2013 response 그룹을 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-120">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="a338e-121">Lync Server 2013 response 그룹에만 업데이트를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-121">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="a338e-122">Lync Server 2010 응답 그룹은 롤백 목적 으로만 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-122">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a338e-123">마이그레이션이 완료 되 고 새 응답 그룹이 만들어진 후 Lync server 제어판과 Lync Server 관리 셸에서 각 응답 그룹의 Lync Server 2010 및 Lync Server 2013 버전을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-123">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="a338e-124">Lync server 2010 응답 그룹을 제거 하려면 lync server 제어판 또는 Lync Server 관리 셸을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a338e-124">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="a338e-125">하나를 제거 하면 마이그레이션 중에 만들어진 해당 하는 응답 그룹이 작동을 멈춥니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-125">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="a338e-126">Lync server 2010 풀을 해제 하면 Lync Server 2010 응답 그룹이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-126">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a338e-127">풀을 해제하기 전까지는 이전 배포에서 어떠한 데이터도 제거하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-127">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="a338e-128">또한 마이그레이션 직후 응답 그룹을 내보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-128">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="a338e-129">Lync Server 2010 response 그룹을 제거 해야 하는 경우에는 응답 그룹을 백업에서 복원 하 여 Lync Server 2013 응답 그룹을 다시 실행 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-129">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="a338e-130">Lync Server 2013에서는 **워크플로 유형**이라는 새로운 응답 그룹 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-130">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="a338e-131">**워크플로 유형**은 **관리됨** 또는 **관리되지 않음**일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-131">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="a338e-132">모든 응답 그룹은 **워크플로 유형**이 **관리되지 않음** 상태로 마이그레이션되고 관리자 목록은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-132">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="a338e-133">**Move-CsRgsConfiguration** cmdlet을 실행하면 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 롤백 목적으로 레거시 풀에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-133">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="a338e-134">하지만 레거시 풀로 롤백해야 하는 경우에는 **Move-CsApplicationEndpoint** cmdlet을 실행해서 연락처 개체를 다시 레거시 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-134">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="a338e-135">응답 그룹 구성을 마이그레이션하는 다음 절차에서는 레거시 풀과 Lync Server 2013 풀 간에 일대일 관계를가지고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-135">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="a338e-136">마이그레이션 및 배포 중에 풀을 통합 하거나 분할 하려는 경우에는 Lync Server 2013 풀에 대 한 레거시 풀 맵을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-136">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="a338e-137">응답 그룹 구성을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="a338e-137">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="a338e-138">RTCUniversalServerAdmins 그룹의 구성원이거나 이와 동등한 관리자 권한 및 사용 권한을 가진 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-138">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="a338e-139">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a338e-140">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-140">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="a338e-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-141">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="a338e-142">응답 그룹과 에이전트를 Lync Server 2013 풀로 마이그레이션한 후에는 에이전트가 로그인 및 로그 아웃 하는 데 사용 하는 URL은 Lync Server 2013 URL로, **도구** 메뉴에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-142">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="a338e-143">에이전트가 책갈피와 같은 모든 참조를 새 URL로 업데이트하도록 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-143">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="a338e-144">Lync Server 제어판을 사용하여 응답 그룹 마이그레이션을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a338e-144">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a338e-145">RTCUniversalReadOnlyAdmins 그룹의 구성원이거나 최소한 CsViewOnlyAdministrator 역할의 구성원인 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-145">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="a338e-146">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a338e-147">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a338e-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a338e-148">왼쪽 탐색 창에서 **응답 그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-148">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="a338e-149">**워크플로** 탭에서 Lync Server 2010 환경의 모든 워크플로가 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-149">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="a338e-150">**큐** 탭을 클릭 하 고 Lync Server 2010 환경의 모든 큐가 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-150">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="a338e-151">**그룹** 탭을 클릭 하 고 Lync Server 2010 환경의 모든 에이전트 그룹이 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-151">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="a338e-152">Lync Server 관리 셸을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="a338e-152">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a338e-153">RTCUniversalReadOnlyAdmins 그룹의 구성원이거나 최소한 CsViewOnlyAdministrator 역할의 구성원인 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-153">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="a338e-154">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="a338e-155">다음 cmdlet에 대한 자세한 내용을 보려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-155">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="a338e-156">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-156">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="a338e-157">Lync Server 2010 환경의 모든 에이전트 그룹이 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-157">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="a338e-158">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-158">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="a338e-159">Lync Server 2010 환경의 모든 큐가 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-159">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="a338e-160">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-160">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="a338e-161">Lync Server 2010 환경의 모든 워크플로가 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a338e-161">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

