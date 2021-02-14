---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로, 오디오 파일 복사, 레거시 배포에서 비즈니스용 Skype 서버 2019 풀로 응답 그룹 연락처 개체 이동이 포함됩니다. 레거시 응답 그룹을 마이그레이션한 후 응답 그룹에 대한 통화는 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에 의해 처리됩니다. 응답 그룹에 대한 호출은 더 이상 레거시 풀에서 처리되지 않습니다.
ms.openlocfilehash: 03b0ffd900b5d7c23dd6ff680d56c0c4db53d8dc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752680"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="1d71c-106">응답 그룹 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1d71c-106">Migrate response groups</span></span>

<span data-ttu-id="1d71c-107">사용자를 비즈니스용 Skype 서버 2019 풀로 이동한 후 응답 그룹을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="1d71c-108">응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로, 오디오 파일 복사, 레거시 배포에서 비즈니스용 Skype 서버 2019 풀로 응답 그룹 연락처 개체 이동이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="1d71c-109">레거시 응답 그룹을 마이그레이션한 후 응답 그룹에 대한 통화는 비즈니스용 Skype 서버 2019 풀의 응답 그룹 응용 프로그램에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="1d71c-110">응답 그룹에 대한 호출은 더 이상 레거시 풀에서 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d71c-111">모든 사용자를 비즈니스용 Skype 서버 2019 풀로 이동하기 전에 응답 그룹을 마이그레이션할 수 있습니다. 그러나 모든 사용자를 먼저 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="1d71c-112">특히 응답 그룹 에이전트인 사용자는 비즈니스용 Skype 서버 2019 풀로 이동하기 전까지는 새로운 기능의 전체 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="1d71c-113">응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램을 포함하는 비즈니스용 Skype 서버 2019 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="1d71c-114">응답 그룹 응용 프로그램은 배포할 때 기본적으로 설치되고 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1d71c-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="1d71c-115">**Get-CsService -ApplicationServer** cmdlet을 실행하여 응답 그룹 응용 프로그램이 설치되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1d71c-116">레거시 응답 그룹을 마이그레이션하기 전에 비즈니스용 Skype 서버 2019 풀에서 새 비즈니스용 Skype 서버 2019 응답 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="1d71c-117">응답 그룹을 레거시 풀에서 비즈니스용 Skype 서버 2019로 마이그레이션하려면 **Move-CsRgsConfiguration** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1d71c-118">응답 그룹 마이그레이션 cmdlet은 전체 풀에 대한 응답 그룹 구성을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="1d71c-119">마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="1d71c-120">응답 그룹을 마이그레이션한 후 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동된지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="1d71c-121">응답 그룹을 마이그레이션할 때 레거시 응답 그룹은 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="1d71c-122">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 마이그레이션 후 응답 그룹을 관리하는 경우 레거시 응답 그룹과 비즈니스용 Skype 서버 2019 응답 그룹을 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="1d71c-123">비즈니스용 Skype 서버 2019 응답 그룹에만 업데이트를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="1d71c-124">레거시 응답 그룹은 롤백 목적으로만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1d71c-125">마이그레이션이 완료되고 새 응답 그룹이 만들어진 후 비즈니스용 Skype 서버 제어판과 비즈니스용 Skype 서버 관리 셸에는 각 응답 그룹의 레거시 및 비즈니스용 Skype 서버 2019 버전이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="1d71c-126">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 레거시 응답 그룹을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="1d71c-127">하나를 제거하면 마이그레이션 중에 만들어진 해당 응답 그룹이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="1d71c-128">레거시 풀을 해제하면 레거시 응답 그룹이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1d71c-129">풀을 해제하기 전까지는 이전 배포에서 어떠한 데이터도 제거하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="1d71c-130">또한 마이그레이션 직후 응답 그룹을 내보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="1d71c-131">레거시 응답 그룹을 제거해야 하는 경우 백업에서 응답 그룹을 복원하여 비즈니스용 Skype 서버 2019 응답 그룹을 다시 실행하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="1d71c-132">비즈니스용 Skype 서버 2019에는 워크플로 유형이라는 새로운 응답 **그룹 기능이 도입됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1d71c-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="1d71c-133">**워크플로 유형** 은 **관리됨** 또는 **관리되지 않음** 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="1d71c-134">모든 응답 그룹은 **워크플로 유형** 이 **관리되지 않음** 상태로 마이그레이션되고 관리자 목록은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="1d71c-135">**Move-CsRgsConfiguration** cmdlet을 실행하면 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 롤백 목적으로 레거시 풀에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="1d71c-136">하지만 레거시 풀로 롤백해야 하는 경우에는 **Move-CsApplicationEndpoint** cmdlet을 실행해서 연락처 개체를 다시 레거시 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="1d71c-137">다음 응답 그룹 구성 마이그레이션 절차에서는 레거시 풀과 비즈니스용 Skype 서버 2019 풀 간에 일대일 관계가 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="1d71c-138">마이그레이션 및 배포 중에 풀을 통합하거나 분할하려는 경우 비즈니스용 Skype 서버 2019 풀에 매핑되는 레거시 풀을 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="1d71c-139">응답 그룹 구성을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="1d71c-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="1d71c-140">RTCUniversalServerAdmins 그룹의 구성원이거나 이와 동등한 관리자 권한 및 사용 권한을 가진 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="1d71c-141">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버 2019,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d71c-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1d71c-142">실행:</span><span class="sxs-lookup"><span data-stu-id="1d71c-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="1d71c-143">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="1d71c-144">응답 그룹 및 에이전트를 비즈니스용 Skype 서버 2019 풀로 마이그레이션한 후 에이전트가 로그인 및 로그인하는 데 사용하는 URL은 비즈니스용 Skype  서버 2019 URL로 도구 메뉴에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="1d71c-145">에이전트가 책갈피와 같은 모든 참조를 새 URL로 업데이트하도록 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1d71c-146">비즈니스용 Skype 서버 제어판을 사용하여 응답 그룹 마이그레이션을 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="1d71c-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1d71c-147">RTCUniversalReadOnlyAdmins 그룹의 구성원이거나 최소한 CsViewOnlyAdministrator 역할의 구성원인 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="1d71c-148">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="1d71c-149">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 비즈니스용 [Skype 서버 2019 관리 도구 열기를 참조하세요.](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)</span><span class="sxs-lookup"><span data-stu-id="1d71c-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="1d71c-150">왼쪽 탐색 창에서 **응답 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="1d71c-151">워크플로 **탭에서** 레거시 환경의 모든 워크플로가 목록에 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="1d71c-152">큐 **탭을** 클릭하고 레거시 환경의 모든 큐가 목록에 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="1d71c-153">그룹 **탭을** 클릭하고 레거시 환경의 모든 에이전트 그룹이 목록에 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1d71c-154">비즈니스용 Skype 서버 관리 셸을 사용하여 응답 그룹 마이그레이션을 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="1d71c-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1d71c-155">RTCUniversalReadOnlyAdmins 그룹의 구성원이거나 최소한 CsViewOnlyAdministrator 역할의 구성원인 계정을 사용하여 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="1d71c-156">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버 2019,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d71c-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="1d71c-157">다음 cmdlet에 대한 자세한 내용을 보려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="1d71c-158">실행:</span><span class="sxs-lookup"><span data-stu-id="1d71c-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="1d71c-159">레거시 환경의 모든 에이전트 그룹이 목록에 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d71c-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="1d71c-160">실행:</span><span class="sxs-lookup"><span data-stu-id="1d71c-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="1d71c-161">레거시 환경의 모든 큐가 목록에 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="1d71c-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="1d71c-162">실행:</span><span class="sxs-lookup"><span data-stu-id="1d71c-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="1d71c-163">레거시 환경의 모든 워크플로가 목록에 포함되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="1d71c-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

