---
title: 비즈니스용 Skype 서버에서 네트워크 상호 지역 경로 만들기
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 해외 경로를 만들거나 수정 합니다.
ms.openlocfilehash: aec289143e2b6dd54e2b52cfc231239fe5d73b7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190467"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="b8678-103">비즈니스용 Skype 서버에서 네트워크 상호 지역 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="b8678-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="b8678-104">비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 해외 경로를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="b8678-105">네트워크 상호 지역 경로는 네트워크 지역 쌍 간의 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="b8678-106">통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 상호 지역 경로가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="b8678-107">이렇게 하면 배포 내의 모든 네트워크 영역이 다른 모든 지역에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="b8678-108">지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하는 반면, 지역 경로에는 연결이 한 영역에서 다른 지역으로 이동할 연결 경로가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="b8678-109">예제 토폴로지에서는 네트워크 간 국가별 경로가 세 가지 지역 쌍 (북미/EMEA, EMEA/APAC, 북미/APAC) 각각에 대해 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b8678-110">비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 간 지역 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b8678-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b8678-111">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b8678-112">**새-Csnetworkinter지역 경로** cmdlet을 실행 하 여 필요한 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="b8678-113">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="b8678-114">북미/APAC 네트워크 상호 지역 경로에는 두 개의 네트워크 지역 연결이 없기 때문에 연결을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b8678-115">비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 간 지역별 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b8678-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b8678-116">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b8678-117">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b8678-118">**지역 경로** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="b8678-119">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-119">Click **New**.</span></span>
    
5. <span data-ttu-id="b8678-120">**새 영역 경로** 페이지에서 **이름을** 클릭 한 다음 네트워크 간 경로 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="b8678-121">**네트워크 지역 #1**를 클릭 한 다음 목록에서 네트워크 지역으로 라우팅하도록 할 네트워크 영역을 클릭 #2 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="b8678-122">**네트워크 지역 #2**를 클릭 한 다음 목록에서 네트워크 지역으로 라우팅하도록 할 네트워크 영역을 클릭 #1 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="b8678-123">**네트워크 지역 링크** 필드 옆에 있는 **추가** 를 클릭 한 다음 네트워크 간 경로에 사용 될 네트워크 지역 링크를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8678-124">두 개의 네트워크 지역에 대해 직접 네트워크 지역 링크가 없는 경우 경로를 만들려면 경로를 완료 하는 데 필요한 모든 링크를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="b8678-125">예를 들어 북미/APAC 네트워크 상호 지역 경로에는 두 개의 네트워크 지역 연결이 없기 때문에 연결을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="b8678-126">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="b8678-127">토폴로지에 대 한 네트워크 간 지역별 경로 만들기를 완료 하려면 다른 네트워크 상호 지역 경로에 대 한 설정을 사용 하 여 4 ~ 9 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8678-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b8678-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8678-128">See also</span></span>

[<span data-ttu-id="b8678-129">새-Csnetworkinter국가 경로</span><span class="sxs-lookup"><span data-stu-id="b8678-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="b8678-130">Get-Csnetworkinter국가 경로</span><span class="sxs-lookup"><span data-stu-id="b8678-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="b8678-131">Set-Csnetworkinter국가 경로</span><span class="sxs-lookup"><span data-stu-id="b8678-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="b8678-132">제거-Csnetworkinter국가 경로</span><span class="sxs-lookup"><span data-stu-id="b8678-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
