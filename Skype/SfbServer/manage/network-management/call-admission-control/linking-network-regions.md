---
title: 네트워크 지역 연결
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
description: 'CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다. '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816468"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="b7a74-103">비즈니스용 Skype 서버에서 네트워크 지역 연결</span><span class="sxs-lookup"><span data-stu-id="b7a74-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="b7a74-104">CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="b7a74-105">이 문서의 섹션을 사용하여 새 작업 영역 링크 정보를 보거나 netwrok 지역 링크를 구성하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="b7a74-106">네트워크 지역 링크 정보 보기</span><span class="sxs-lookup"><span data-stu-id="b7a74-106">View network region link information</span></span> 

<span data-ttu-id="b7a74-107">CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="b7a74-108">네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="b7a74-109">비즈니스용 Skype 서버 제어판을 사용하여 두 네트워크 지역 간의 기존 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b7a74-110">비즈니스용 Skype 서버 제어판에서 네트워크 지역 링크를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="b7a74-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b7a74-111">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7a74-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7a74-113">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 링크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7a74-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="b7a74-114">**지역 링크** 페이지에서 보려는 지역 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="b7a74-115">한 번에 하나의 지역 링크에 대한 정보만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="b7a74-116">**편집** 메뉴에서 **세부 정보 표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b7a74-117">cmdlet을 사용하여 네트워크 지역 링크 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="b7a74-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b7a74-118">네트워크 지역 링크는 Windows PowerShell **Get-CsNetworkRegionLink** cmdlet을 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="b7a74-119">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="b7a74-120">네트워크 지역 링크 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="b7a74-120">To view network region link information</span></span>

  - <span data-ttu-id="b7a74-121">모든 네트워크 지역 링크에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="b7a74-122">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="b7a74-123">자세한 내용은 [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b7a74-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="b7a74-124">네트워크 지역 링크 구성</span><span class="sxs-lookup"><span data-stu-id="b7a74-124">Configure network region links</span></span> 

<span data-ttu-id="b7a74-125">CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="b7a74-126">네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="b7a74-127">비즈니스용 Skype 서버 제어판을 사용하여 두 네트워크 지역 간의 링크를 정의하고 이러한 지역 간의 오디오 및 비디오 연결에 대한 대역폭 제한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="b7a74-128">네트워크 지역 링크를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b7a74-128">To create a network region link</span></span>

1.  <span data-ttu-id="b7a74-129">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7a74-130">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7a74-131">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 링크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7a74-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="b7a74-132">**지역 링크** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="b7a74-133">**새 지역 링크** 에서 **이름** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="b7a74-134">이 값은 비즈니스용 Skype 서버 배포 내에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="b7a74-135">네트워크 **지역 \# 1** 드롭다운 목록에서 연결할 두 지역 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="b7a74-136">네트워크 **지역 \# 2** 드롭다운 목록에서 연결할 다른 지역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="b7a74-137">이 지역은 네트워크 지역 1에 대해 선택한 지역과 달라야 \# 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="b7a74-138">(선택 사항) 이러한 지역 간의 음성 또는 화상 통화에 대역폭 제한을 설정하려면 **대역폭 정책** 드롭다운 목록에서 대역폭 정책 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="b7a74-139">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="b7a74-140">네트워크 지역 링크를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="b7a74-140">To modify a network region link</span></span>

1.  <span data-ttu-id="b7a74-141">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7a74-142">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7a74-143">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 링크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7a74-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="b7a74-144">**지역 링크** 페이지에서 수정할 지역 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="b7a74-145">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b7a74-146">**지역 링크 편집** 에서 연결된 지역 또는 이 링크에 대한 대역폭 정책 프로필을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="b7a74-147">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="b7a74-148">네트워크 지역 링크 삭제</span><span class="sxs-lookup"><span data-stu-id="b7a74-148">Delete network region links</span></span>

<span data-ttu-id="b7a74-149">CAC(통화 허용 제어)의 일환으로 두 네트워크 지역 간의 링크를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="b7a74-150">네트워크 내의 지역은 실제 WAN(Wide Area Network) 연결을 통해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="b7a74-151">비즈니스용 Skype 서버 제어판을 사용하여 두 네트워크 지역 간의 기존 링크를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="b7a74-152">네트워크 지역 링크를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="b7a74-152">To delete a network region link</span></span>

1.  <span data-ttu-id="b7a74-153">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7a74-154">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7a74-155">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **지역 링크를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b7a74-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="b7a74-156">**지역 링크** 페이지에서 삭제할 지역 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="b7a74-p107">한 번에 둘 이상의 지역 링크를 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역 링크를 선택합니다. 또는 모든 지역 링크를 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="b7a74-160">**편집** 메뉴에서 **삭제** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="b7a74-161">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a74-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="b7a74-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7a74-162">See Also</span></span>

[<span data-ttu-id="b7a74-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7a74-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="b7a74-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7a74-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="b7a74-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7a74-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="b7a74-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7a74-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
