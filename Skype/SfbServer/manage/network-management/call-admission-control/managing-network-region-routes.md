---
title: 네트워크 지역 경로 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 네트워크 지역 경로는 네트워크 지역 쌍 간의 경로를 정의합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 경로가 필요합니다.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816438"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="fbfc8-104">비즈니스용 Skype 서버에서 네트워크 지역 경로 지정 관리</span><span class="sxs-lookup"><span data-stu-id="fbfc8-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="fbfc8-105">*네트워크 지역 경로* 는 네트워크 지역 쌍 간의 경로를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="fbfc8-106">통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 경로가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="fbfc8-107">이러한 경로가 있으면 배포 내의 모든 네트워크 지역이 다른 모든 지역에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="fbfc8-108">이 아트의 절차에 따라 네트워크 지역 경로를 보거나, 만들거나, 수정하거나, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="fbfc8-109">네트워크 지역 경로 정보 보기</span><span class="sxs-lookup"><span data-stu-id="fbfc8-109">View network region route information</span></span> 

<span data-ttu-id="fbfc8-110">CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="fbfc8-111">지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="fbfc8-112">다음 절차에 따라 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸에서 기존 네트워크 지역 경로를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="fbfc8-113">비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="fbfc8-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fbfc8-114">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbfc8-115">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fbfc8-116">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 경로를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbfc8-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fbfc8-117">**지역 경로** 페이지에서 보려는 지역 경로를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="fbfc8-118">한 번에 하나의 지역 경로만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="fbfc8-119">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fbfc8-120">cmdlet을 사용하여 네트워크 지역 경로 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="fbfc8-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fbfc8-121">네트워크 지역 경로 정보는 네트워크 지역 경로 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkInterRegionRoute 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="fbfc8-122">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="fbfc8-123">네트워크 지역 경로 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="fbfc8-123">To view network region route information</span></span>

  - <span data-ttu-id="fbfc8-124">모든 네트워크 지역 경로에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="fbfc8-125">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="fbfc8-126">자세한 내용은 [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="fbfc8-127">네트워크 지역 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="fbfc8-127">Create or modify network region routes</span></span>

<span data-ttu-id="fbfc8-128">CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="fbfc8-129">지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="fbfc8-130">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="fbfc8-131">비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로를 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="fbfc8-132">이 항목의 정보에 따라 네트워크 지역을 만들거나 수정하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="fbfc8-133">네트워크 지역 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="fbfc8-133">To create a network region route</span></span>

1.  <span data-ttu-id="fbfc8-134">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbfc8-135">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fbfc8-136">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 경로를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbfc8-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fbfc8-137">**지역 경로** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="fbfc8-138">**새 지역 경로** 에서 **이름** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="fbfc8-139">이 값은 비즈니스용 Skype 서버 배포 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="fbfc8-140">네트워크 **지역 \# 1** 드롭다운 목록에서 이 경로로 연결할 두 지역 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="fbfc8-141">네트워크 **지역 \# 2** 드롭다운 목록에서 이 경로의 다른 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="fbfc8-142">이 지역은 네트워크 지역 1에 대해 선택한 지역과 달라야 \# 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="fbfc8-p107">**네트워크 지역 링크** 목록 상자를 사용하여 경로에 지역 링크를 추가합니다. **추가** 단추를 클릭하여 **지역 링크** 페이지를 표시합니다. 이 경로에 추가할 지역 링크를 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="fbfc8-146">계속해서 링크를 더 추가하려면 **추가** 단추를 클릭하고 링크를 제거하려면 링크를 선택하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="fbfc8-147">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="fbfc8-148">네트워크 지역 경로를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="fbfc8-148">To modify a network region route</span></span>

1.  <span data-ttu-id="fbfc8-149">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbfc8-150">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fbfc8-151">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 경로를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbfc8-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fbfc8-152">**지역 경로** 페이지에서 수정할 지역 경로를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="fbfc8-153">**편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fbfc8-154">**지역 경로 편집** 에서 이 경로에 참가하는 지역 및 해당 경로와 연결된 지역 링크를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="fbfc8-155">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="fbfc8-156">기존 네트워크 지역 경로 삭제</span><span class="sxs-lookup"><span data-stu-id="fbfc8-156">Delete existing network region routes</span></span>

<span data-ttu-id="fbfc8-157">CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="fbfc8-158">지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="fbfc8-159">비즈니스용 Skype 서버 제어판을 사용하여 네트워크 지역 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="fbfc8-160">비즈니스용 Skype 서버 제어판에서 네트워크 지역 경로를 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="fbfc8-161">이 항목을 사용하여 기존 네트워크 지역 경로를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="fbfc8-162">네트워크 지역 경로를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="fbfc8-162">To delete a network region route</span></span>

1.  <span data-ttu-id="fbfc8-163">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbfc8-164">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fbfc8-165">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 경로를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fbfc8-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fbfc8-166">지역 **경로 페이지에서** 삭제할 지역 경로를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="fbfc8-167">한에 두 개 이상의 지역 경로를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="fbfc8-168">이렇게하려면 Ctrl 키를 누를 때 Ctrl 키를 누를 때 여러 지역 경로를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="fbfc8-169">또는 모든 지역 경로를 선택하려면 **편집** 메뉴에서 모두 **선택을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="fbfc8-170">**편집** 메뉴에서 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="fbfc8-171">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfc8-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="fbfc8-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbfc8-172">See Also</span></span>

[<span data-ttu-id="fbfc8-173">비즈니스용 Skype 서버에서 네트워크 지역 관리</span><span class="sxs-lookup"><span data-stu-id="fbfc8-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="fbfc8-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fbfc8-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="fbfc8-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fbfc8-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="fbfc8-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fbfc8-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="fbfc8-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fbfc8-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
