---
title: 네트워크 서브넷 관리
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
description: 호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다. 이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817467"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="ce2bd-104">비즈니스용 Skype 서버에서 네트워크 서브넷 관리</span><span class="sxs-lookup"><span data-stu-id="ce2bd-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="ce2bd-105">비즈니스용 Skype Server 제어판 또는 비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 서브넷을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="ce2bd-106">호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ce2bd-107">이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="ce2bd-108">이 문서의 섹션을 사용 하 여 네트워크 서브넷 정보를 보거나 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="ce2bd-109">네트워크 서브넷 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ce2bd-109">View network subnet information</span></span> 

<span data-ttu-id="ce2bd-110">다음 절차를 사용 하 여 네트워크 서브넷을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="ce2bd-111">비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="ce2bd-112">네트워크 서브넷을 보려면</span><span class="sxs-lookup"><span data-stu-id="ce2bd-112">To view a network subnet</span></span>

1.  <span data-ttu-id="ce2bd-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce2bd-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ce2bd-115">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ce2bd-116">**서브넷** 페이지에서 보려는 서브넷을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ce2bd-117">한 번에 하나의 서브넷만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="ce2bd-118">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ce2bd-119">Windows PowerShell cmdlet을 사용 하 여 네트워크 서브넷 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ce2bd-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ce2bd-120">네트워크 서브넷 정보는 Windows PowerShell 및 Get-CsNetworkSubnet cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="ce2bd-121">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="ce2bd-122">네트워크 서브넷 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="ce2bd-122">To view network subnet information</span></span>

  - <span data-ttu-id="ce2bd-123">모든 네트워크 서브넷에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="ce2bd-124">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="ce2bd-125">자세한 내용은 [Get CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="ce2bd-126">네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="ce2bd-126">Create or modify network subnets</span></span> 

<span data-ttu-id="ce2bd-127">네트워크 서브넷이이 서브넷에 속한 호스트의 지리적 위치를 확인 하기 위해 네트워크 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="ce2bd-128">비즈니스용 Skype 서버 제어판을 사용 하 여 서브넷을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="ce2bd-129">비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="ce2bd-130">호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ce2bd-131">이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ce2bd-132">여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ce2bd-133">이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ce2bd-134">.Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="ce2bd-135">네트워크 서브넷을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ce2bd-135">To create a network subnet</span></span>

1.  <span data-ttu-id="ce2bd-136">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce2bd-137">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ce2bd-138">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ce2bd-139">**서브넷** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="ce2bd-140">**새 서브넷**에서 **서브넷 ID** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="ce2bd-141">이는 IP 주소 (예: 174.11.12.0) 여야 하며 서브넷에 정의 된 IP 주소 범위에서 첫 번째 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="ce2bd-142">**마스크** 필드에 1부터 32 까지의 숫자 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ce2bd-143">이 값은 만들려는 서브넷에 적용 되는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="ce2bd-144">**네트워크 사이트 ID**에서이 서브넷이 속한 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="ce2bd-145">) 이름 만으로 표현할 수 없는이 서브넷에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="ce2bd-146">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="ce2bd-147">네트워크 서브넷을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="ce2bd-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="ce2bd-148">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce2bd-149">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ce2bd-150">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ce2bd-151">**서브넷** 페이지에서 수정 하려는 서브넷을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="ce2bd-152">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ce2bd-153">**서브넷 편집** 페이지에서 비트 마스크, 관련 네트워크 사이트 또는 설명을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="ce2bd-154">비트 마스크를 수정 하는 경우 서브넷 ID가 서브넷에 정의 된 IP 주소 범위에서 첫 번째 주소 여야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="ce2bd-155">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="ce2bd-156">네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="ce2bd-156">Delete network subnets</span></span>

<span data-ttu-id="ce2bd-157">다음 절차를 사용 하 여 서브넷을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="ce2bd-158">비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="ce2bd-159">호출 허용 제어 (CAC)가 구현 된 비즈니스용 Skype 서버를 대부분 배포 하는 경우에는 일반적으로 서브넷 수가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ce2bd-160">이 때문에 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ce2bd-161">여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ce2bd-162">이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ce2bd-163">.Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="ce2bd-164">네트워크 서브넷을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="ce2bd-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="ce2bd-165">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ce2bd-166">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ce2bd-167">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 한 다음 **서브넷**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ce2bd-168">**서브넷** 페이지에서 삭제 하려는 서브넷을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ce2bd-169">한 번에 둘 이상의 서브넷을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="ce2bd-170">이 작업을 수행 하려면 ctrl 키를 누른 채 여러 서브넷을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="ce2bd-171">또는 모든 서브넷을 선택 하려면 **편집** 메뉴에서 **모두 선택을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ce2bd-172">**편집** 메뉴에서 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ce2bd-173">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2bd-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="ce2bd-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce2bd-174">See Also</span></span>

[<span data-ttu-id="ce2bd-175">새-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ce2bd-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="ce2bd-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ce2bd-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="ce2bd-177">CsNetworkSubnet 제거</span><span class="sxs-lookup"><span data-stu-id="ce2bd-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="ce2bd-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ce2bd-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
