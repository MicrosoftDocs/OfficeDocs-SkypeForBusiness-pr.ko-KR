---
title: 네트워크 지역 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다. '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817527"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="c090e-103">비즈니스용 Skype 서버에서 네트워크 지역 연결</span><span class="sxs-lookup"><span data-stu-id="c090e-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="c090e-104">두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="c090e-105">이 문서의 섹션을 사용 하 여 newtwork 지역 링크 정보를 보거나 netwrok 지역 링크를 구성 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="c090e-106">네트워크 지역 링크 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c090e-106">View network region link information</span></span> 

<span data-ttu-id="c090e-107">호출 허용 제어 (CAC)의 일부로 두 네트워크 지역 간 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="c090e-108">네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="c090e-109">비즈니스용 Skype Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c090e-110">비즈니스용 Skype Server 제어판에서 네트워크 지역 링크 보기</span><span class="sxs-lookup"><span data-stu-id="c090e-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="c090e-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c090e-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c090e-113">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="c090e-114">**지역 링크** 페이지에서 보려는 지역 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="c090e-115">한 번에 하나의 지역 링크에 대 한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="c090e-116">**편집** 메뉴에서 **세부 정보 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c090e-117">Windows PowerShell cmdlet을 사용 하 여 네트워크 지역 링크 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c090e-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c090e-118">Windows PowerShell 및 **Get-Csnetworkregion 링크** cmdlet을 사용 하 여 네트워크 지역 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="c090e-119">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="c090e-120">네트워크 지역 링크 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="c090e-120">To view network region link information</span></span>

  - <span data-ttu-id="c090e-121">모든 네트워크 지역 링크에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="c090e-122">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="c090e-123">자세한 내용은 [Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c090e-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="c090e-124">네트워크 지역 링크 구성</span><span class="sxs-lookup"><span data-stu-id="c090e-124">Configure network region links</span></span> 

<span data-ttu-id="c090e-125">두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="c090e-126">네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="c090e-127">비즈니스용 Skype Server 제어판을 사용 하 여 두 네트워크 지역 간의 링크를 정의 하 고 이러한 지역 간의 오디오 및 비디오 연결에 대 한 대역폭 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="c090e-128">네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c090e-128">To create a network region link</span></span>

1.  <span data-ttu-id="c090e-129">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c090e-130">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c090e-131">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="c090e-132">**지역 링크** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="c090e-133">**새 영역 링크**의 **이름** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="c090e-134">이 값은 비즈니스용 Skype 서버 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="c090e-135">**네트워크 지역 \#1** 드롭다운 목록에서 연결할 두 지역 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="c090e-136">**네트워크 지역 \#2** 드롭다운 목록에서 연결할 다른 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="c090e-137">이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="c090e-138">) 이러한 지역 간의 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 **대역폭 정책** 드롭다운 목록에서 대역폭 정책 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="c090e-139">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="c090e-140">네트워크 지역 링크를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c090e-140">To modify a network region link</span></span>

1.  <span data-ttu-id="c090e-141">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c090e-142">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c090e-143">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="c090e-144">**지역 링크** 페이지에서 수정 하려는 지역 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="c090e-145">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c090e-146">**지역 편집 링크**에서 연결 된 영역이 나이 링크에 대 한 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="c090e-147">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="c090e-148">네트워크 지역 링크 삭제</span><span class="sxs-lookup"><span data-stu-id="c090e-148">Delete network region links</span></span>

<span data-ttu-id="c090e-149">두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="c090e-150">네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="c090e-151">비즈니스용 Skype Server 제어판을 사용 하 여 두 네트워크 지역 간의 기존 링크를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="c090e-152">네트워크 지역 링크를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="c090e-152">To delete a network region link</span></span>

1.  <span data-ttu-id="c090e-153">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c090e-154">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c090e-155">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **지역 링크**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="c090e-156">**지역 링크** 페이지에서 삭제 하려는 지역 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="c090e-157">한 번에 둘 이상의 지역 링크를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="c090e-158">이 작업을 수행 하려면 ctrl 키를 누른 채로 여러 지역 링크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="c090e-159">또는 모든 지역 링크를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="c090e-160">**편집** 메뉴에서 **삭제**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="c090e-161">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c090e-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="c090e-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c090e-162">See Also</span></span>

[<span data-ttu-id="c090e-163">새-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="c090e-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="c090e-164">Set-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="c090e-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="c090e-165">-Csnetwork국가 링크 제거</span><span class="sxs-lookup"><span data-stu-id="c090e-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="c090e-166">Get-Csnetwork국가 링크</span><span class="sxs-lookup"><span data-stu-id="c090e-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
