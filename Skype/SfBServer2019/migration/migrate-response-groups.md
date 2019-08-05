---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 레거시 배포에서 비즈니스용 Skype Server 2019 풀로 에이전트 그룹, 큐, 워크플로, 오디오 파일, 응답 그룹 연락처 개체 복사 등이 포함 됩니다. 레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에서 처리 됩니다. 응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.
ms.openlocfilehash: cba50526748ca15c04513013e484b0e279410c1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196958"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="b7b0f-106">응답 그룹 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b7b0f-106">Migrate response groups</span></span>

<span data-ttu-id="b7b0f-107">사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="b7b0f-108">응답 그룹 마이그레이션에는 레거시 배포에서 비즈니스용 Skype Server 2019 풀로 에이전트 그룹, 큐, 워크플로, 오디오 파일, 응답 그룹 연락처 개체 복사 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b7b0f-109">레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b7b0f-110">응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7b0f-111">모든 사용자를 비즈니스용 Skype Server 2019 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만, 모든 사용자를 먼저 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="b7b0f-112">특히 응답 그룹 에이전트를 사용 하는 사용자는 비즈니스용 Skype Server 2019 풀로 이동할 때까지 새로운 기능을 완전히 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="b7b0f-113">응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 비즈니스용 Skype 서버 2019 풀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="b7b0f-114">엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b7b0f-115">**Get CsService-ApplicationServer** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b7b0f-116">레거시 응답 그룹을 마이그레이션하기 전에 비즈니스용 Skype Server 2019 풀에서 새로운 비즈니스용 Skype 서버 2019 응답 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="b7b0f-117">레거시 풀의 응답 그룹을 비즈니스용 Skype 서버 2019로 마이그레이션하려면 **Move-CsRgsConfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b7b0f-118">응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="b7b0f-119">마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="b7b0f-120">응답 그룹을 마이그레이션한 후 비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="b7b0f-121">응답 그룹을 마이그레이션하면 레거시 응답 그룹이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="b7b0f-122">비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 마이그레이션 후에 응답 그룹을 관리 하는 경우 레거시 응답 그룹과 비즈니스용 Skype 서버 2019 응답 그룹을 둘 다 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b7b0f-123">비즈니스용 Skype Server 2019 응답 그룹에만 업데이트를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b7b0f-124">레거시 응답 그룹은 롤백 용도로만 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b7b0f-125">마이그레이션이 완료 되 고 새 응답 그룹이 만들어졌으면 비즈니스용 Skype Server 제어판 및 비즈니스용 Skype 서버 관리 셸에서는 각 응답의 레거시 및 비즈니스용 Skype server 2019 버전이 표시 됩니다. 그룹과.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="b7b0f-126">Skype for Business Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 레거시 응답 그룹을 제거 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="b7b0f-127">제거 하는 경우 마이그레이션 중에 만든 해당 응답 그룹의 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="b7b0f-128">레거시 풀을 해제할 때 레거시 응답 그룹이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b7b0f-129">풀을 해제할 때까지 이전 배포에서 데이터를 제거 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="b7b0f-130">또한 마이그레이션한 후 즉시 응답 그룹을 내보낼 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="b7b0f-131">레거시 응답 그룹을 제거 해야 하는 경우 백업에서 응답 그룹을 복원 하 여 비즈니스용 Skype Server 2019 응답 그룹을 다시 실행 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="b7b0f-132">비즈니스용 Skype 서버 2019에는 **워크플로 유형**이라는 새 응답 그룹 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="b7b0f-133">**워크플로 유형은** **관리** 또는 **비관리형**일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="b7b0f-134">모든 응답 그룹은 **워크플로 유형이** **비관리형** 으로 설정 되 고 빈 관리자 목록이 있는 상태로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="b7b0f-135">**CsRgsConfiguration** cmdlet을 실행 하는 경우 롤백 목적으로 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 레거시 풀에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="b7b0f-136">그러나 레거시 풀로 롤백해야 하는 경우에는 요청 **이동 Applicationendpoint** cmdlet을 실행 하 여 연락처 개체를 레거시 풀로 다시 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="b7b0f-137">응답 그룹 구성을 마이그레이션하는 다음 절차에서는 레거시 풀과 비즈니스용 Skype Server 2019 풀 간에 일대일 관계를 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="b7b0f-138">마이그레이션 및 배포 중에 풀을 통합 하거나 분할 하려는 경우 비즈니스용 Skype 서버 2019 풀에 매핑되는 레거시 풀을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="b7b0f-139">응답 그룹 구성을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="b7b0f-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="b7b0f-140">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 관리자 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="b7b0f-141">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b7b0f-142">런</span><span class="sxs-lookup"><span data-stu-id="b7b0f-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="b7b0f-143">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="b7b0f-144">응답 그룹 및 에이전트를 비즈니스용 Skype 서버 2019 풀로 마이그레이션한 후에는 에이전트가 로그인 하 고 로그 아웃 하는 데 사용 하는 URL이 비즈니스용 Skype Server 2019 URL 이며 **도구** 메뉴에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="b7b0f-145">상담원에 게 책갈피 등의 모든 참조를 새 URL로 업데이트 하도록 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b7b0f-146">비즈니스용 Skype Server 제어판을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="b7b0f-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b7b0f-147">RTCUniversalReadOnlyAdmins 그룹의 구성원 이거나 적어도 Csviewis 관리자 역할의 구성원 인 계정으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b7b0f-148">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="b7b0f-149">비즈니스용 Skype Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2019 관리 도구 열기](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="b7b0f-150">왼쪽 탐색 창에서 **응답 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="b7b0f-151">**워크플로** 탭에서 레거시 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="b7b0f-152">**대기열** 탭을 클릭 하 고 레거시 환경의 모든 대기열이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="b7b0f-153">**그룹** 탭을 클릭 하 고 레거시 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b7b0f-154">비즈니스용 Skype Server Management Shell을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="b7b0f-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b7b0f-155">RTCUniversalReadOnlyAdmins 그룹의 구성원 이거나 적어도 Csviewis 관리자 역할의 구성원 인 계정으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b7b0f-156">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="b7b0f-157">다음 cmdlet에 대 한 자세한 내용을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="b7b0f-158">런</span><span class="sxs-lookup"><span data-stu-id="b7b0f-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="b7b0f-159">레거시 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="b7b0f-160">런</span><span class="sxs-lookup"><span data-stu-id="b7b0f-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="b7b0f-161">레거시 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="b7b0f-162">런</span><span class="sxs-lookup"><span data-stu-id="b7b0f-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="b7b0f-163">레거시 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b0f-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

