---
title: 비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 비즈니스용 Skype 서버에서 네트워크 지역, 네트워크 사이트를 만들거나 수정하고 네트워크 서브넷을 연결합니다. 이러한 모든 기능은 미디어 우회, 통화 Enterprise Voice 라우팅과 같은 고급 서비스 기능에 사용됩니다.
ms.openlocfilehash: adfcf418fd2b1ef607947687afb766fee6b64715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103524"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="6ae62-104">비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="6ae62-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="6ae62-105">비즈니스용 Skype 서버에서 네트워크 지역, 네트워크 사이트를 만들거나 수정하고 네트워크 서브넷을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="6ae62-106">이러한 모든 기능은 미디어 우회, 통화 Enterprise Voice 라우팅과 같은 고급 서비스 기능에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="6ae62-107">고급 Enterprise Voice [기능은](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)통화 입장 [제어,](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)미디어 [우회,](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)위치 기반 라우팅 및 [E9-1-1입니다.](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)</span><span class="sxs-lookup"><span data-stu-id="6ae62-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="6ae62-108">이러한 기능을 사용하려면 네트워크 지역, 네트워크 사이트 및 서브넷을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="6ae62-109">예를 들어 이러한 모든 기능을 사용하려면 토폴로지의 각 서브넷을 특정 네트워크 사이트와 연결해야 합니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="6ae62-110">이러한 용어에 대한 자세한 내용은 비즈니스용 Skype 서버의 고급 Enterprise Voice 네트워크 설정을 [참조하세요.](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="6ae62-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="6ae62-111">통화 허용 제어 및 E9-1-1의 경우 네트워크 사이트에 대한 추가 구성 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="6ae62-112">통화 허용 제어의 경우 WAN 대역폭 제한을 통해 제약되는 각 사이트에 대해 대역폭 정책 프로필을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="6ae62-113">통화 제한을 배포하려면 네트워크 사이트를 구성하기 전에 비즈니스용 [Skype 서버에서](create-bandwidth-policy-profiles.md) 대역폭 정책 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="6ae62-114">E9-1-1의 경우 각 사이트에 대해 위치 정책을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="6ae62-115">E9-1-1을 배포하려면 네트워크 사이트를 구성하기 전에 비즈니스용 [Skype 서버에서](create-location-policies.md) 위치 정책 만들기를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="6ae62-116">네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="6ae62-116">Create or modify a Network Region</span></span>

<span data-ttu-id="6ae62-117">이러한 기능 중 하나에 대한 네트워크 지역을 이미 만든 경우 새 네트워크 지역을 만들 필요가 없습니다. 다른 고급 Enterprise Voice 기능은 동일한 네트워크 지역을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="6ae62-118">그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="6ae62-119">예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ae62-120">비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 지역을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6ae62-121">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae62-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6ae62-122">New-CsNetworkRegion cmdlet을 실행하여 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="6ae62-123">예:</span><span class="sxs-lookup"><span data-stu-id="6ae62-123">For example:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="6ae62-124">이 예제에서는 사이트 ID가 CHICAGO인 중앙 사이트와 연결된 "NorthAmerica"라는 네트워크 지역을 만들었다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="6ae62-125">토폴로지에 대한 네트워크 지역 만들기를 종료하려면 각 네트워크 지역에 대한 설정을 사용하여 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ae62-126">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6ae62-127">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6ae62-128">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="6ae62-129">**지역** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-129">Click **Region**.</span></span>

4. <span data-ttu-id="6ae62-130">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-130">Click **New**.</span></span>

5. <span data-ttu-id="6ae62-131">**새 지역** 페이지에서 **이름** 을 클릭한 다음 네트워크 지역에 대한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="6ae62-132">**중앙 사이트** 를 클릭한 다음 목록에서 중앙 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="6ae62-133">필요한 경우 **설명** 을 클릭한 다음 이 네트워크 사이트를 설명하는 추가 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="6ae62-134">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-134">Click **Commit**.</span></span>

9. <span data-ttu-id="6ae62-135">토폴로지에 대한 네트워크 지역 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ae62-136">비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 지역을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="6ae62-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6ae62-137">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae62-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6ae62-138">Set-CsNetworkRegion cmdlet을 실행하여 기존 네트워크 지역을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="6ae62-139">예:</span><span class="sxs-lookup"><span data-stu-id="6ae62-139">For example:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="6ae62-140">이 예제에서는 설명을 변경하여 "NorthAmerica"라는 기존 네트워크 지역(이 항목의 앞부분에 있는 절차를 사용하여 만든)을 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="6ae62-141">"NorthAmerica" 지역에 대한 설명이 있는 경우 이 명령은 이 값으로 덮어 덮어 행위를 합니다. 설명이 설정되지 않은 경우 이 명령은 설명을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="6ae62-142">다른 네트워크 지역을 수정하려면 다른 지역에 대한 설정을 사용하여 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ae62-143">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="6ae62-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6ae62-144">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6ae62-145">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="6ae62-146">**지역** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="6ae62-147">테이블에서 수정할 네트워크 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="6ae62-148">**편집** 을 클릭한 다음 **자세한 정보 표시...** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="6ae62-149">지역 **편집 페이지에서** 이 네트워크 지역의 설정 값을 적절하게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="6ae62-150">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-150">Click **Commit**.</span></span>

8. <span data-ttu-id="6ae62-151">네트워크 지역 수정을 완료하려면 다른 지역에 대한 설정을 사용하여 4-7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="6ae62-152">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="6ae62-152">Create or modify a network site</span></span>

<span data-ttu-id="6ae62-153">이러한 기능 중 하나에 대한 네트워크 사이트를 이미 만든 경우 새 네트워크 사이트를 만들 필요가 없습니다. 다른 고급 Enterprise Voice 기능은 동일한 네트워크 사이트를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="6ae62-154">그러나 기능별 설정을 적용하려면 기존 네트워크 사이트 정의를 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="6ae62-155">예를 들어 E9-1-1에 대한 네트워크 사이트를 만든 경우 대역폭 정책 프로필을 적용하려면 통화 제한을 배포하는 동안 네트워크 사이트를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ae62-156">비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6ae62-157">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae62-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6ae62-158">New-CsNetworkSite cmdlet을 실행하여 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="6ae62-159">예:</span><span class="sxs-lookup"><span data-stu-id="6ae62-159">For example:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="6ae62-160">이 예제에서는 "NorthAmerica" 네트워크 지역에 있는 "시카고"라는 네트워크 사이트를 만들었다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ae62-161">이 명령을 실행하려면 북미 네트워크 지역이 이미 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="6ae62-162">토폴로지에 대한 네트워크 사이트 만들기를 종료하려면 다른 사이트에 대한 설정을 사용하여 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ae62-163">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6ae62-164">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6ae62-165">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="6ae62-166">**사이트** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="6ae62-167">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-167">Click **New**.</span></span>

5. <span data-ttu-id="6ae62-168">**네트워크 사이트** 페이지에서 **이름** 을 클릭한 다음 네트워크 사이트 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="6ae62-169">**지역** 을 클릭한 다음 목록에서 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="6ae62-170">필요한 경우 **대역폭 정책** 을 클릭한 다음 목록에서 대역폭 정책을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ae62-171">대역폭 정책은 사이트에 통화 허용 제어를 배포할 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="6ae62-172">필요한 경우 **위치 정책** 을 클릭한 다음 목록에서 위치 정책을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ae62-173">위치 정책은 사이트에 E9-1-1을 배포할 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="6ae62-174">필요한 경우 **설명** 을 클릭한 다음 이 네트워크 사이트를 설명하는 추가 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="6ae62-175">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-175">Click **Commit**.</span></span>

11. <span data-ttu-id="6ae62-176">토폴로지에 대한 네트워크 사이트 만들기를 종료하려면 다른 사이트에 대한 설정을 사용하여 4~10단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ae62-177">비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 사이트를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="6ae62-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6ae62-178">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae62-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6ae62-179">Set-CsNetworkSite cmdlet을 실행하여 네트워크 사이트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="6ae62-180">예:</span><span class="sxs-lookup"><span data-stu-id="6ae62-180">For example:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="6ae62-181">이 예제에서는 "앨버커키"라는 사이트가 "NorthAmerica" 네트워크 지역으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="6ae62-182">통화 허용 제어, E9-1-1 또는 미디어 바이패스를 배포하기 위해 네트워크 사이트 구성을 수정하려면 각각 BWPolicyProfileID 또는 LocationPolicy 매개 변수와 함께 Set-CsNetworkSite cmdlet을 실행하여 네트워크 사이트 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ae62-p110">미디어 바이패스에는 BypassID 매개 변수가 있지만 자동으로 생성된 바이패스 ID를 재정의하지 않는 것이 좋습니다. 미디어 바이패스에 대한 네트워크 사이트를 구성하기 위해 추가 매개 변수를 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="6ae62-185">토폴로지에 대한 네트워크 사이트 수정을 종료하려면 다른 사이트에 대한 설정을 사용하여 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ae62-186">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 사이트를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="6ae62-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6ae62-187">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6ae62-188">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="6ae62-189">**사이트** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="6ae62-190">테이블에서 수정할 네트워크 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="6ae62-191">**편집** 을 클릭한 다음 **자세한 정보 표시...** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="6ae62-192">사이트 **편집 페이지에서** 이 네트워크 사이트의 설정 값을 적절하게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="6ae62-193">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-193">Click **Commit**.</span></span>

8. <span data-ttu-id="6ae62-194">네트워크 사이트 수정을 종료하려면 다른 사이트에 대한 설정을 사용하여 4~7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="6ae62-195">네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="6ae62-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="6ae62-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="6ae62-196"><a name="BKMK_AssociateSubnets"> </a></span></span>

<span data-ttu-id="6ae62-197">새 세션이 시작되는 동안 끝점이 있는 네트워크 사이트를 확인하는 데 서브넷 정보가 사용될 수 있기 때문에 네트워크의 모든 서브넷은 특정 네트워크 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="6ae62-198">세션에서 각 파티의 위치를 알 수 있는 경우 고급 Enterprise Voice 해당 정보를 적용하여 통화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="6ae62-199">배포에 있는 오디오/비디오 에지 서버의 구성된 모든 공용 IP 주소를 네트워크 구성 설정에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="6ae62-200">이러한 IP 주소는 마스크가 32인 서브넷으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="6ae62-201">연결된 네트워크 사이트는 구성된 적절한 네트워크 사이트에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="6ae62-202">예를 들어 시카고 중앙 사이트의 A/V 에지 서비스에 해당하는 공용 IP 주소는 NetworkSiteID Chicago가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6ae62-203">비즈니스용 Skype 서버 관리 셸을 사용하여 서브넷을 네트워크 사이트에 연결</span><span class="sxs-lookup"><span data-stu-id="6ae62-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6ae62-204">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae62-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6ae62-205">**New-CsNetworkSubnet** cmdlet을  실행하여 서브넷과 네트워크 사이트를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="6ae62-206">예:</span><span class="sxs-lookup"><span data-stu-id="6ae62-206">For example:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="6ae62-207">이 예제에서는 서브넷 172.11.12.13과 네트워크 사이트 "Chicago" 간에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="6ae62-208">토폴로지의 모든 서브넷에 대해 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="6ae62-209">CSV 파일을 가져와서 서브넷과 네트워크 사이트를 연결하려면</span><span class="sxs-lookup"><span data-stu-id="6ae62-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="6ae62-p113">추가할 모든 서브넷을 포함하는 CSV 파일을 만듭니다. 예를 들어 다음 내용이 포함된 **subnet.csv** 이름의 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="6ae62-212">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ae62-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="6ae62-213">다음 cmdlet을 실행하여subnet.csv를 가져온 다음 해당 콘텐츠를 Lync Server 관리 저장소에 저장합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6ae62-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ae62-214">비즈니스용 Skype 서버 제어판을 사용하여 서브넷을 네트워크 사이트에 연결</span><span class="sxs-lookup"><span data-stu-id="6ae62-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6ae62-215">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6ae62-216">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="6ae62-217">**서브넷** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="6ae62-218">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-218">Click **New**.</span></span>

5. <span data-ttu-id="6ae62-219">**새 서브넷** 페이지에서 **서브넷 ID** 를 클릭한 다음 네트워크 사이트와 연결할 서브넷에서 정의한 IP 주소 범위에 첫 번째 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="6ae62-220">**마스크** 를 클릭한 다음 서브넷에 적용할 비트 마스크를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="6ae62-221">**네트워크 사이트 ID** 를 클릭한 다음 이 서브넷을 추가하고 있는 사이트의 사이트 ID를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ae62-222">네트워크 사이트를 아직 만들지 않은 경우에는 이 목록이 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="6ae62-223">절차를 보려면 [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ae62-223">For details about the procedure, see [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site).</span></span> <span data-ttu-id="6ae62-224">**Get-CsNetworkSite** cmdlet을 실행하여 배포에 사용할 사이트 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="6ae62-225">자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ae62-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="6ae62-226">경우에 따라 **설명** 을 클릭하고 이 서브넷을 설명하는 추가 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="6ae62-227">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-227">Click **Commit**.</span></span>

<span data-ttu-id="6ae62-228">다른 서브넷을 네트워크 사이트에 추가하려면 이러한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="6ae62-229">네트워크에 있지만 서브넷과 연결되지 않은 IP 주소 목록 또는 IP 주소가 포함되어 있지만 네트워크 사이트에 연결되지 않은 서브넷 목록을 지정하는 KHI(Key Health Indicator) 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="6ae62-230">이 알림은 8시간 간격으로 한 번만 발생합니다(해당되는 경우).</span><span class="sxs-lookup"><span data-stu-id="6ae62-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="6ae62-231">관련 알림 정보 및 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="6ae62-232">**원본**: CS 대역폭 정책 서비스(핵심)</span><span class="sxs-lookup"><span data-stu-id="6ae62-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="6ae62-233">**이벤트 번호**: 36034</span><span class="sxs-lookup"><span data-stu-id="6ae62-233">**Event number**: 36034</span></span>

 <span data-ttu-id="6ae62-234">**수준**: 2</span><span class="sxs-lookup"><span data-stu-id="6ae62-234">**Level**: 2</span></span>

 <span data-ttu-id="6ae62-235">**설명:** 다음 IP 주소에 대한 서브넷이 구성되지 않았습니다. 또는 서브넷이 네트워크 사이트에 \<List of IP Addresses\> 연결되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="6ae62-236">**원인**: 해당 IP 주소에 대한 서브넷이 네트워크 구성 설정에서 누락되었거나 서브넷이 네트워크 사이트에 연결되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="6ae62-237">**해결 방법**: IP 주소 목록에 해당하는 서브넷을 네트워크 구성 설정에 추가하고 모든 서브넷을 네트워크 사이트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="6ae62-p116">예를 들어 알림에 표시된 IP 주소 목록이 10.121.248.226 및 10.121.249.20을 나타내는 경우 이러한 IP 주소가 서브넷에 연결되지 않았거나, 이러한 IP 주소가 연결된 서브넷이 네트워크 사이트 속해 있지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당하는 서브넷인 경우 다음과 같이 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="6ae62-240">IP 주소 10.121.248.226이 10.121.248.0/24 서브넷과 연결되고, IP 주소 10.121.249.20이 10.121.249.0/24 서브넷과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="6ae62-241">10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae62-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ae62-242">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ae62-242">See also</span></span>
<span data-ttu-id="6ae62-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="6ae62-243"><a name="BKMK_AssociateSubnets"> </a></span></span>


[<span data-ttu-id="6ae62-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6ae62-244">New-CsNetworkRegion</span></span>](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="6ae62-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6ae62-245">Get-CsNetworkRegion</span></span>](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="6ae62-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6ae62-246">Set-CsNetworkRegion</span></span>](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="6ae62-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="6ae62-247">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="6ae62-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6ae62-248">New-CsNetworkSubnet</span></span>](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="6ae62-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6ae62-249">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="6ae62-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6ae62-250">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="6ae62-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="6ae62-251">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)