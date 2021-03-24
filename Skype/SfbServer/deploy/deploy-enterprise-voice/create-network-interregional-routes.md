---
title: 비즈니스용 Skype 서버에서 네트워크 간 경로 만들기
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 비즈니스용 Skype 서버의 통화 Enterprise Voice 제어에 사용되는 네트워크 Enterprise Voice 경로를 만들거나 수정합니다.
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093126"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="51884-103">비즈니스용 Skype 서버에서 네트워크 간 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="51884-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="51884-104">비즈니스용 Skype 서버의 통화 Enterprise Voice 제어에 사용되는 네트워크 Enterprise Voice 경로를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="51884-105">네트워크 지역 간 경로는 네트워크 지역 쌍 간의 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="51884-106">통화 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 간 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="51884-107">이러한 경로가 있으면 배포 내의 모든 네트워크 지역이 다른 모든 지역에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51884-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="51884-108">지역 링크는 지역 간의 연결에 대한 대역폭 제한을 설정하는 반면 지역 간 경로는 연결이 한 지역에서 다른 지역으로 트래버스할 연결된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="51884-109">토폴로지 예제에서 네트워크 지역 간 경로는 북미/EMEA, EMEA/APAC 및 북미/APAC의 세 지역 쌍 각각에 대해 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="51884-110">비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 간 경로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51884-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="51884-111">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="51884-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51884-112">**New-CsNetworkInterRegionRoute** cmdlet을 사용하여 필요한 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="51884-113">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="51884-114">북미/APAC 네트워크 지역 간 경로에는 두 개의 네트워크 지역 링크가 필요하기 때문에 지역 간 직접 네트워크 지역 링크가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51884-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51884-115">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 간 경로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51884-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51884-116">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="51884-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="51884-117">왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="51884-118">**지역 경로** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="51884-119">**새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-119">Click **New**.</span></span>
    
5. <span data-ttu-id="51884-120">새 **지역 경로 페이지에서**  이름을 클릭한 다음 네트워크 지역 간 경로의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="51884-121">**네트워크 지역 #1** 을 클릭하고 목록에서 네트워크 지역 #2로 라우팅할 네트워크 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="51884-122">**네트워크 지역 #2** 를 클릭하고 목록에서 네트워크 지역 #1로 라우팅할 네트워크 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="51884-123">네트워크 **지역**  링크 필드 옆에 있는 추가를 클릭한 다음 네트워크 지역 간 경로에 사용할 네트워크 지역 링크를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51884-124">두 네트워크 지역에 대한 경로를 만드는데 해당 지역 사이에 직접 네트워크 지역 링크가 없는 경우, 경로를 완료하려면 필요한 모든 링크를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="51884-125">예를 들어 북미/APAC 네트워크 지역 간 경로에는 두 개의 네트워크 지역 링크가 필요하기 때문에 지역 간 직접 네트워크 지역 링크가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51884-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="51884-126">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="51884-127">토폴로지의 네트워크Regional 경로 만들기를 완료하려면 다른 네트워크 간 경로에 대한 설정을 사용하여 4-9단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="51884-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="51884-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51884-128">See also</span></span>

[<span data-ttu-id="51884-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="51884-129">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="51884-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="51884-130">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="51884-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="51884-131">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="51884-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="51884-132">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)