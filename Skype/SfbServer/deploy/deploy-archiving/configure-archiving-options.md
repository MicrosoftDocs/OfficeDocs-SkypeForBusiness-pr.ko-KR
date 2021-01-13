---
title: 비즈니스용 Skype 서버에 대한 보관 옵션 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: '요약: 비즈니스용 Skype 서버에 대한 초기 보관 옵션을 구성하는 방법을 알아보는 이 항목을 읽어 보십시오. 보관을 배포할 때 처음에는 보관 구성을 설정했지만 배포 후에 구성을 변경, 추가 및 삭제할 수 있습니다.'
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815538"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="d3c6c-104">비즈니스용 Skype 서버에 대한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="d3c6c-105">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버에 대한 초기 보관 옵션을 구성하는 방법을 배워 보십시오.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="d3c6c-106">보관을 배포할 때 처음에는 보관 구성을 설정했지만 배포 후에 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="d3c6c-107">초기 보관 구성을 구성하려면 비즈니스용 Skype 서버 제어판을 사용하여 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="d3c6c-108">비즈니스용 Skype 서버를 배포할 때 기본적으로 만들어진 전역 수준 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="d3c6c-109">특정 사이트에 대해 보관을 구현하는 방법을 지정하는 선택적 사이트 수준 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="d3c6c-110">특정 풀에 대해 보관을 구현하는 방법을 지정하는 선택적 풀 수준 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="d3c6c-111">다음에 대한 옵션을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="d3c6c-112">보관을 사용할지 여부</span><span class="sxs-lookup"><span data-stu-id="d3c6c-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="d3c6c-113">IM 세션을 보관할지 여부</span><span class="sxs-lookup"><span data-stu-id="d3c6c-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="d3c6c-114">웹 회의 세션을 보관할지 여부</span><span class="sxs-lookup"><span data-stu-id="d3c6c-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="d3c6c-115">보관을 사용할 수 없는 경우 활동을 차단할지 여부</span><span class="sxs-lookup"><span data-stu-id="d3c6c-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="d3c6c-116">Exchange 통합을 사용할지 여부</span><span class="sxs-lookup"><span data-stu-id="d3c6c-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="d3c6c-117">데이터 제거 및 내보내기를 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="d3c6c-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3c6c-118">보관을 사용하도록 설정하기 전에 적절한 옵션을 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="d3c6c-119">지정할 수 있는 옵션 및 보관 구성 계층 구조를 포함하여 보관 구성을 구현하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버의 보관 계획을 [참조하세요.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="d3c6c-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="d3c6c-120">제어판을 사용하여 또는 제어판을 사용하여 배포 후 구성을 관리하는 방법에 대한 자세한 Windows PowerShell 비즈니스용 Skype 서버에서 보관 옵션 [관리를 참조하세요.](../../manage/archiving/options.md)</span><span class="sxs-lookup"><span data-stu-id="d3c6c-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="d3c6c-121">전역 수준 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-121">Configure global level archiving options</span></span>

<span data-ttu-id="d3c6c-122">토폴로지에 보관을 추가하고 토폴로지 게시할 때 비즈니스용 Skype 서버는 보관에 대한 전역 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="d3c6c-123">기본적으로 전역 구성에서는 보관 옵션이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="d3c6c-124">전역 구성은 전역 구성을 다시 설정하는 사이트 또는 풀 구성을 설정하지 않는 한 전체 배포에 대해 사용하도록 설정된 옵션을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="d3c6c-125">보관 옵션을 전역 수준에서 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="d3c6c-126">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d3c6c-127">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d3c6c-128">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d3c6c-129">**보관 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d3c6c-130">**보관 설정 편집 - 전역** 의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="d3c6c-131">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="d3c6c-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="d3c6c-132">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="d3c6c-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="d3c6c-133">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="d3c6c-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="d3c6c-134">보관 설정 **편집 - 전역** 페이지에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="d3c6c-135">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d3c6c-136">보관 Microsoft Exchange Server 데이터를 저장하려면 Microsoft Exchange 통합 **확인란을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d3c6c-137">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d3c6c-138">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d3c6c-139">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="d3c6c-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="d3c6c-140">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="d3c6c-141">사이트 수준 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-141">Configure site level archiving options</span></span>

<span data-ttu-id="d3c6c-142">특정 사이트에 대한 보관 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="d3c6c-143">사이트 구성은 전역 구성을 무시하지만 사이트 구성에 지정된 사이트로만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="d3c6c-144">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d3c6c-145">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d3c6c-146">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d3c6c-147">**보관 구성** 페이지에서 **새로 만들기** 를 클릭한 다음 **사이트 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="d3c6c-148">**사이트 선택** 에서 보관을 위해 구성할 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="d3c6c-149">**새 보관 설정** 의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="d3c6c-150">IM(인스턴트 메시징) 세션에 대해서만 보관을 사용하도록 설정하려면 **IM 세션 보관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="d3c6c-151">IM 세션 및 회의 모두에 대해 보관을 사용하도록 설정하려면 **IM 및 웹 회의 세션 보관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="d3c6c-152">정책에 대해 보관을 사용하지 않도록 설정하려면 **보관 사용 안 함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="d3c6c-153">또한 **새 보관 설정** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="d3c6c-154">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d3c6c-155">보관 Microsoft Exchange Server 데이터를 저장하려면 Microsoft Exchange 통합 **확인란을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d3c6c-156">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d3c6c-157">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d3c6c-158">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="d3c6c-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="d3c6c-159">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="d3c6c-160">풀 수준 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="d3c6c-160">Configure pool level archiving options</span></span>

<span data-ttu-id="d3c6c-161">특정 풀에 대한 보관 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="d3c6c-162">풀 구성은 풀 구성에 지정된 풀에 한해 전역 구성 및 사이트 구성을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="d3c6c-163">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d3c6c-164">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d3c6c-165">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d3c6c-166">**보관 구성** 페이지에서 **새로 만들기** 를 클릭한 다음 **풀 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="d3c6c-167">**서비스 선택** 에서 보관을 위해 구성할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="d3c6c-168">**새 보관 설정** 의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="d3c6c-169">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="d3c6c-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="d3c6c-170">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="d3c6c-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="d3c6c-171">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="d3c6c-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="d3c6c-172">또한 **새 보관 설정** 페이지에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="d3c6c-173">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관이 실패할 경우 IM(인스턴트 메시징) 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d3c6c-174">보관 Microsoft Exchange Server 데이터를 저장하려면 Microsoft Exchange 통합 **확인란을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d3c6c-175">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d3c6c-176">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d3c6c-177">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="d3c6c-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="d3c6c-178">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3c6c-178">Click **Commit**.</span></span>
    

