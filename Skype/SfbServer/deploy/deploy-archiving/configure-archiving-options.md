---
title: 비즈니스용 Skype 서버에 대 한 보관 옵션 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: '요약: 비즈니스용 Skype 서버에 대 한 초기 보관 옵션을 구성 하는 방법을 알아보려면이 항목을 읽으십시오. 보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다.'
ms.openlocfilehash: f663b310d4c82594976f2f0fc99b8ddd9baf035f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769201"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="03a88-104">비즈니스용 Skype 서버에 대 한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="03a88-105">**요약:** 비즈니스용 Skype 서버에 대 한 초기 보관 옵션을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03a88-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="03a88-106">보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="03a88-107">초기 보관 구성을 구성 하려면 비즈니스용 Skype Server 제어판을 사용 하 여 다음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="03a88-108">비즈니스용 Skype 서버를 배포할 때 기본적으로 만들어지는 전역 수준 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="03a88-109">특정 사이트에 대해 보관을 구현 하는 방법을 지정 하는 선택적 사이트 수준 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="03a88-110">특정 풀에 대해 보관을 구현 하는 방법을 지정 하는 선택적 풀 수준 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="03a88-111">다음에 대 한 옵션을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="03a88-112">보관 설정 또는 해제 여부</span><span class="sxs-lookup"><span data-stu-id="03a88-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="03a88-113">IM 세션 보관 여부</span><span class="sxs-lookup"><span data-stu-id="03a88-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="03a88-114">웹 회의 세션을 보관할지 여부</span><span class="sxs-lookup"><span data-stu-id="03a88-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="03a88-115">보관을 사용할 수 없는 경우 활동을 차단할지 여부</span><span class="sxs-lookup"><span data-stu-id="03a88-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="03a88-116">Exchange 통합 사용 여부</span><span class="sxs-lookup"><span data-stu-id="03a88-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="03a88-117">데이터 제거 및 내보내기 설정 방법</span><span class="sxs-lookup"><span data-stu-id="03a88-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="03a88-118">보관을 사용 하도록 설정 하기 전에 모든 적절 한 옵션을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="03a88-119">보관 구성의 구현 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03a88-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="03a88-120">제어판을 사용 하거나 Windows PowerShell을 사용 하 여 배포한 후 구성을 관리 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 보관 옵션 관리](../../manage/archiving/options.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03a88-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="03a88-121">전역 수준 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-121">Configure global level archiving options</span></span>

<span data-ttu-id="03a88-122">토폴로지에 보관을 추가 하 고 토폴로지를 게시 하면 비즈니스용 Skype 서버에서 보관을 위한 전역 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="03a88-123">기본적으로 전역 구성에서는 보관 옵션이 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="03a88-124">전역 구성은 전역 구성을 재정의 하는 사이트 또는 풀 구성을 설정 하지 않는 한 전체 배포에 대해 사용할 수 있는 옵션을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="03a88-125">전역 수준에서 보관 옵션을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="03a88-126">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="03a88-127">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="03a88-128">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="03a88-129">**보관 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="03a88-130">**보관 설정 편집-Global**의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="03a88-131">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="03a88-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="03a88-132">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="03a88-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="03a88-133">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="03a88-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="03a88-134">또한 **보관 설정 편집-글로벌** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="03a88-135">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="03a88-136">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="03a88-137">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="03a88-138">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="03a88-139">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="03a88-140">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="03a88-141">사이트 수준 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-141">Configure site level archiving options</span></span>

<span data-ttu-id="03a88-142">특정 사이트에 대 한 보관 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="03a88-143">사이트 구성은 사이트 구성에 지정 된 사이트에 대해서만 전역 구성 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="03a88-144">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="03a88-145">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="03a88-146">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="03a88-147">**보관 구성** 페이지에서 **새로 만들기**를 클릭 한 다음 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="03a88-148">**사이트 선택**에서 보관을 위해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="03a88-149">**새 보관 설정**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="03a88-150">IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="03a88-151">IM 세션과 회의 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 웹 회의 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="03a88-152">정책 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="03a88-153">또한 **새 보관 설정**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="03a88-154">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="03a88-155">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="03a88-156">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="03a88-157">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="03a88-158">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="03a88-159">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="03a88-160">풀 수준 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="03a88-160">Configure pool level archiving options</span></span>

<span data-ttu-id="03a88-161">특정 풀에 대 한 보관 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="03a88-162">풀 구성은 전역 구성 및 사이트 구성 보다 우선 하지만 풀 구성에 지정 된 풀에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="03a88-163">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="03a88-164">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="03a88-165">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="03a88-166">**보관 구성** 페이지에서 **새로 만들기**를 클릭 한 다음 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="03a88-167">**서비스 선택**에서 보관을 위해 구성할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="03a88-168">**새 보관 설정**의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="03a88-169">**보관 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="03a88-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="03a88-170">**IM 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="03a88-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="03a88-171">**IM 및 웹 회의 세션 보관**</span><span class="sxs-lookup"><span data-stu-id="03a88-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="03a88-172">또한 **새 보관 설정** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="03a88-173">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="03a88-174">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="03a88-175">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="03a88-176">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="03a88-177">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="03a88-178">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03a88-178">Click **Commit**.</span></span>
    

