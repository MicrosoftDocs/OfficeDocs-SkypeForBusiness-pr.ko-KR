---
title: Lync Server 2013; 네트워크 통과 영역 경로 만들기
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 156f2322d5b1b7cc1951f1cbd4df41eb231a8170
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="17bfa-102">Lync Server 2013에서 네트워크 간 지역 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="17bfa-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17bfa-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="17bfa-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="17bfa-p101">*네트워크 지역 간 경로*는 네트워크 지역 쌍 간의 경로를 정의합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 간 경로가 필요합니다. 따라서 배포 내의 모든 네트워크 지역이 다른 모든 지역에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="17bfa-107">지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하는 반면, 지역 간 경로는 연결이 지역 간에 이어지는 링크된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="17bfa-108">네트워크 통과 경로를 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17bfa-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="17bfa-109">새-Csnetworkinterroute</span><span class="sxs-lookup"><span data-stu-id="17bfa-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="17bfa-110">Get-Csnetworkinterroute</span><span class="sxs-lookup"><span data-stu-id="17bfa-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="17bfa-111">설정-Csnetworkinter지역 경로</span><span class="sxs-lookup"><span data-stu-id="17bfa-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="17bfa-112">제거-Csnetworkinterroute</span><span class="sxs-lookup"><span data-stu-id="17bfa-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="17bfa-113">예제 토폴로지에서는 각각의 세 지역 쌍, 즉 North America/EMEA, EMEA/APAC, North America/APAC에 대해 네트워크 지역 간 경로를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="17bfa-114">Lync Server 관리 셸을 사용 하 여 네트워크 간 지역 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="17bfa-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="17bfa-115">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="17bfa-116">**New-CsNetworkInterRegionRoute** cmdlet을 사용하여 필요한 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="17bfa-117">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-117">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="17bfa-118">North America/APAC 네트워크 지역 간 경로의 경우, 지역 간에 직접 네트워크 지역 링크가 없으므로 네트워크 지역 링크가 두 개 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="17bfa-119">Lync Server 제어판을 사용 하 여 네트워크 간 지역 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="17bfa-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="17bfa-120">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="17bfa-121">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17bfa-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="17bfa-122">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="17bfa-123">**지역 경로** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="17bfa-124">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-124">Click **New**.</span></span>

5.  <span data-ttu-id="17bfa-125">**새 지역 경로** 페이지에서 **이름**을 클릭하고 네트워크 지역 간 경로의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="17bfa-126">**네트워크 지역 \# 1**을 클릭 하 고 목록에서 네트워크 지역 2로 라우팅할 네트워크 지역을 클릭 \# 합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="17bfa-127">**네트워크 지역 \# 2**를 클릭 하 고 목록에서 네트워크 지역 1로 라우팅할 네트워크 지역을 클릭 \# 합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="17bfa-128">**네트워크 지역 링크** 필드 옆의 **추가**를 클릭한 다음, 네트워크 지역 간 경로에 사용할 네트워크 지역 링크를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="17bfa-p104">두 네트워크 지역에 대한 경로를 만드는데 해당 지역 사이에 직접 네트워크 지역 링크가 없는 경우, 경로를 완료하려면 필요한 모든 링크를 추가해야 합니다. 예를 들어 North America/APAC 네트워크 지역 간 경로의 경우, 지역 간에 직접 네트워크 지역 링크가 없으므로 네트워크 지역 링크가 두 개 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="17bfa-131">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-131">Click **Commit**.</span></span>

10. <span data-ttu-id="17bfa-132">토롤로지에 대해 네트워크 지역 간 경로 만들기를 완료하려면 다른 네트워크 지역 간 경로에 대한 설정을 사용하여 4-9단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="17bfa-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

