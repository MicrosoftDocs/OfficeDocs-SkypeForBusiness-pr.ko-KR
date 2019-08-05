---
title: 비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 비즈니스용 Skype 서버에서 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷 연결을 만들거나 수정 합니다. 이러한 모든 기능은 고급 엔터프라이즈 음성 기능 (미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅)에 사용 됩니다.
ms.openlocfilehash: 3ce0f4dcf011f57e25c4741c34135bc4ba62085a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36197848"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="c95d6-104">비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="c95d6-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="c95d6-105">비즈니스용 Skype 서버에서 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷 연결을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="c95d6-106">이러한 모든 기능은 고급 엔터프라이즈 음성 기능 (미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="c95d6-107">고급 엔터프라이즈 음성 기능으로는 [통화 허용 제어](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [미디어 바이패스](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [위치 기반 라우팅](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)및 [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="c95d6-108">이러한 기능을 모두 위해서는 네트워크 지역, 네트워크 사이트 및 서브넷을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="c95d6-109">예를 들어 이러한 모든 기능을 사용 하려면 토폴로지의 각 서브넷을 특정 네트워크 사이트와 연결 하 고 각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="c95d6-110">이러한 용어에 대 한 자세한 내용은 [비즈니스용 Skype 서버의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정을](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c95d6-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="c95d6-111">통화 허용 제어 및 E9-1-1에는 네트워크 사이트에 대 한 추가 구성 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="c95d6-112">호출 허용 제어는 WAN 대역폭 제한에 의해 제한 된 각 사이트에 대해 대역폭 정책 프로필을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="c95d6-113">통화 허용 제어를 배포 하려는 경우에는 네트워크 사이트를 구성 하기 전에 비즈니스용 [Skype 서버에서 대역폭 정책 프로필을 만들어야](create-bandwidth-policy-profiles.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="c95d6-114">E9-1-1은 각 사이트에 대해 위치 정책을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="c95d6-115">E9-1-1을 배포 하려는 경우 네트워크 사이트를 구성 하기 전에 [비즈니스용 Skype 서버에서 위치 정책을 만들어야](create-location-policies.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="c95d6-116">네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c95d6-116">Create or modify a Network Region</span></span>

<span data-ttu-id="c95d6-117">이러한 기능 중 하나에 대해 이미 네트워크 지역을 만든 경우에는 새 네트워크 지역을 만들 필요가 없습니다. 그 밖의 고급 엔터프라이즈 음성 기능으로는 동일한 네트워크 지역을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="c95d6-118">그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="c95d6-119">예를 들어 E9 (연결 된 중앙 사이트가 필요 하지 않음)에 대 한 네트워크 지역을 만든 다음 통화 허용 제어를 배포 하는 경우에는 네트워크 지역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c95d6-120">비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 지역 만들기</span><span class="sxs-lookup"><span data-stu-id="c95d6-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c95d6-121">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c95d6-122">새-CsNetworkRegion cmdlet을 실행 하 여 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="c95d6-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-123">For example:</span></span>

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="c95d6-124">이 예제에서는 사이트 ID 시카고를 사용 하 여 중앙 사이트와 연결 되는 "NorthAmerica" 라는 네트워크 영역을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="c95d6-125">토폴로지에 대 한 네트워크 영역 만들기를 마치려면 각 네트워크 영역에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c95d6-126">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c95d6-127">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c95d6-128">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="c95d6-129">**지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-129">Click **Region**.</span></span>

4. <span data-ttu-id="c95d6-130">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-130">Click **New**.</span></span>

5. <span data-ttu-id="c95d6-131">**새 지역** 페이지에서 **이름을** 클릭 한 다음 네트워크 영역의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="c95d6-132">**중앙 사이트**를 클릭 한 다음 목록에서 중앙 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="c95d6-133">필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="c95d6-134">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-134">Click **Commit**.</span></span>

9. <span data-ttu-id="c95d6-135">토폴로지에 대 한 네트워크 영역 만들기를 완료 하려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 8 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c95d6-136">비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 지역 수정</span><span class="sxs-lookup"><span data-stu-id="c95d6-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c95d6-137">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c95d6-138">집합-CsNetworkRegion cmdlet을 실행 하 여 기존 네트워크 지역을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="c95d6-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-139">For example:</span></span>

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="c95d6-140">이 예제에서는 설명을 변경 하 여 "NorthAmerica" (이 항목의 앞부분에 있는 절차를 사용 하 여 만들어짐) 라는 기존 네트워크 영역을 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="c95d6-141">"NorthAmerica" 영역에 대 한 설명이 있는 경우이 명령은이 값으로 덮어씁니다. 설명이 설정 되어 있지 않으면이 명령으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="c95d6-142">다른 네트워크 지역을 수정 하려면 다른 지역에 대 한 설정으로 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c95d6-143">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c95d6-144">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c95d6-145">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="c95d6-146">**지역** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="c95d6-147">표에서 수정 하려는 네트워크 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="c95d6-148">**편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="c95d6-149">**지역 편집** 페이지에서이 네트워크 지역 설정의 값을 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="c95d6-150">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-150">Click **Commit**.</span></span>

8. <span data-ttu-id="c95d6-151">네트워크 지역 수정을 완료 하려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 7 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="c95d6-152">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c95d6-152">Create or modify a network site</span></span>

<span data-ttu-id="c95d6-153">이러한 기능 중 하나에 대해 네트워크 사이트를 이미 만든 경우 새 네트워크 사이트를 만들 필요가 없습니다. 다른 고급 엔터프라이즈 음성 기능은 동일한 네트워크 사이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="c95d6-154">그러나 기능별 설정을 적용 하려면 기존 네트워크 사이트 정의를 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="c95d6-155">예를 들어 E9-1에 대 한 네트워크 사이트를 만든 경우에는 호출 허용 제어를 배포 하는 동안 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c95d6-156">비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c95d6-157">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c95d6-158">새-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="c95d6-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-159">For example:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="c95d6-160">이 예제에서는 "NorthAmerica" 네트워크 지역에 "시카고" 라는 네트워크 사이트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c95d6-161">이 명령을 성공적으로 실행 하려면 NorthAmerica 네트워크 지역이 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="c95d6-162">토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c95d6-163">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c95d6-164">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c95d6-165">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="c95d6-166">**사이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="c95d6-167">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-167">Click **New**.</span></span>

5. <span data-ttu-id="c95d6-168">**새 사이트** 페이지에서 **이름을** 클릭 한 다음 네트워크 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="c95d6-169">**지역을**클릭 한 다음 목록에서 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="c95d6-170">필요에 따라 **대역폭 정책을**클릭 한 다음 목록에서 대역폭 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c95d6-171">대역폭 정책은 사이트에서 통화 허용 제어를 배포 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="c95d6-172">필요에 따라 **위치 정책을**클릭 한 다음 목록에서 위치 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c95d6-173">위치 정책은 사이트에 E9-1-1을 배포 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="c95d6-174">필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="c95d6-175">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-175">Click **Commit**.</span></span>

11. <span data-ttu-id="c95d6-176">토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트의 설정을 사용 하 여 4 ~ 10 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c95d6-177">비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 사이트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c95d6-178">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c95d6-179">집합-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="c95d6-180">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-180">For example:</span></span>

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="c95d6-181">이 예제에서는 "Albuquerque" 라는 사이트가 "NorthAmerica" 네트워크 지역으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="c95d6-182">통화 허용 제어, E9-1-1 또는 미디어 바이패스를 배포 하도록 네트워크 사이트 구성을 수정 하려면 BWPolicyProfileID 또는 LocationPolicy 매개 변수를 사용 하 여 Set-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c95d6-183">BypassID 매개 변수는 미디어를 우회 하는 데 존재 하지만 자동으로 생성 된 우회 Id를 재정의 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-183">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs.</span></span> <span data-ttu-id="c95d6-184">미디어 바이패스를 위해 네트워크 사이트를 구성 하기 위해 추가 매개 변수를 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-184">You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="c95d6-185">토폴로지의 네트워크 사이트 수정을 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c95d6-186">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c95d6-187">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c95d6-188">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="c95d6-189">**사이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="c95d6-190">표에서 수정 하려는 네트워크 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="c95d6-191">**편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="c95d6-192">**사이트 편집** 페이지에서이 네트워크 사이트의 설정 값을 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="c95d6-193">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-193">Click **Commit**.</span></span>

8. <span data-ttu-id="c95d6-194">네트워크 사이트 수정을 완료 하려면 다른 사이트 설정에 대해 4 ~ 7 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="c95d6-195">네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="c95d6-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="c95d6-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="c95d6-196"></span></span>

<span data-ttu-id="c95d6-197">네트워크의 모든 서브넷은 새 세션이 시작 되는 동안 끝점이 위치한 네트워크 사이트를 결정 하는 데 사용 되므로 서브넷 정보는 특정 네트워크 사이트와 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="c95d6-198">세션에서 각 파티의 위치를 알고 있는 경우 고급 엔터프라이즈 음성 기능에서 해당 정보를 적용 하 여 전화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="c95d6-199">배포에 있는 오디오/비디오에 지 서버의 모든 구성 된 공용 IP 주소를 네트워크 구성 설정에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="c95d6-200">이러한 IP 주소는 32의 마스크로 서브넷으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="c95d6-201">연결 된 네트워크 사이트는 적절 하 게 구성 된 네트워크 사이트와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="c95d6-202">예를 들어 중앙 사이트 시카고의 A/V Edge 서비스에 해당 하는 공용 IP 주소는 NetworkSiteID 시카고입니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c95d6-203">비즈니스용 Skype Server Management Shell을 사용 하 여 서브넷을 네트워크 사이트와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c95d6-204">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c95d6-205">**새-CsNetworkSubnet** cmdlet을 실행 하 여 서브넷을 네트워크 사이트와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="c95d6-206">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-206">For example:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="c95d6-207">이 예제에서는 서브넷 172.11.12.13와 네트워크 사이트 "시카고" 간에 연결을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="c95d6-208">토폴로지의 모든 서브넷에 대해 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="c95d6-209">CSV 파일을 가져와 서브넷을 네트워크 사이트와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="c95d6-210">추가 하려는 모든 서브넷을 포함 하는 CSV 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-210">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="c95d6-211">예를 들어 다음 콘텐츠를 사용 하 여 **subnet** 이라는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-211">For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="c95d6-212">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="c95d6-213">다음 cmdlet을 실행 하 여 **서브넷 .csv**를 가져온 다음 Lync Server 관리 저장소에 해당 콘텐츠를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c95d6-214">비즈니스용 Skype Server 제어판을 사용 하 여 서브넷을 네트워크 사이트와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="c95d6-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c95d6-215">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c95d6-216">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="c95d6-217">**서브넷** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="c95d6-218">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-218">Click **New**.</span></span>

5. <span data-ttu-id="c95d6-219">**새 서브넷** 페이지에서 **서브넷 ID**를 클릭 한 다음 네트워크 사이트와 연결 하려는 서브넷이 정의한 IP 주소 범위에 첫 번째 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="c95d6-220">**마스크**를 클릭 한 다음 서브넷에 적용할 비트 마스크를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="c95d6-221">**네트워크 사이트 id**를 클릭 한 다음이 서브넷을 추가할 사이트의 사이트 id를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c95d6-222">아직 네트워크 사이트를 만들지 않은 경우에는이 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="c95d6-223">절차에 대 한 자세한 내용은 [네트워크 사이트 만들기 또는 수정을](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c95d6-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="c95d6-224">또한 **Get-CsNetworkSite** cmdlet을 실행 하 여 배포에 대 한 사이트 id를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="c95d6-225">자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c95d6-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="c95d6-226">필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 서브넷을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="c95d6-227">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-227">Click **Commit**.</span></span>

<span data-ttu-id="c95d6-228">네트워크 사이트에 다른 서브넷을 추가 하려면이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="c95d6-229">네트워크에는 있지만 서브넷에 연결 되지 않았거나 IP 주소가 포함 된 서브넷이 네트워크 사이트와 연결 되어 있지 않은 경우 KHI (키 상태 표시기) 경고가 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="c95d6-230">이 알림은 8 시간 내에 두 번 이상 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="c95d6-231">관련 경고 정보 및 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="c95d6-232">**원본**: CS 대역폭 정책 서비스 (Core)</span><span class="sxs-lookup"><span data-stu-id="c95d6-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="c95d6-233">**이벤트 번호**: 36034</span><span class="sxs-lookup"><span data-stu-id="c95d6-233">**Event number**: 36034</span></span>

 <span data-ttu-id="c95d6-234">**수준**: 2</span><span class="sxs-lookup"><span data-stu-id="c95d6-234">**Level**: 2</span></span>

 <span data-ttu-id="c95d6-235">**설명**: 다음 ip 주소의 서브넷: \<ip 주소\> 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="c95d6-236">**원인**: 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에 없거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="c95d6-237">**해결**방법: IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="c95d6-238">예를 들어 alert의 IP 주소 목록에서 10.121.248.226 및 10.121.249.20를 지정 하는 경우 이러한 IP 주소가 서브넷과 연결 되어 있지 않거나 연결 된 서브넷이 네트워크 사이트에 속해 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-238">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="c95d6-239">10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당 하는 서브넷 이면 다음과 같이이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-239">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="c95d6-240">IP 주소 10.121.248.226이 10.121.248.0/24 서브넷 및 IP 주소 10.121.249.20와 연결 되어 있는지 확인 하 고 10.121.249.0/24 서브넷과 연결 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="c95d6-241">10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95d6-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="c95d6-242">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c95d6-242">See also</span></span>
<span data-ttu-id="c95d6-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="c95d6-243"></span></span>


[<span data-ttu-id="c95d6-244">새-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="c95d6-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="c95d6-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="c95d6-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="c95d6-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="c95d6-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="c95d6-247">CsNetworkRegion 제거</span><span class="sxs-lookup"><span data-stu-id="c95d6-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="c95d6-248">새-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c95d6-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="c95d6-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c95d6-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="c95d6-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c95d6-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="c95d6-251">CsNetworkSubnet 제거</span><span class="sxs-lookup"><span data-stu-id="c95d6-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

