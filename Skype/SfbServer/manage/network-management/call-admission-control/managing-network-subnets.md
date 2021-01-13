---
title: 네트워크 서브넷 관리
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
description: CAC(통화 제어)가 구현된 비즈니스용 Skype 서버의 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다. 따라서 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성하는 것이 가장 좋습니다.
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816398"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="5ddf3-104">비즈니스용 Skype 서버에서 네트워크 서브넷 관리</span><span class="sxs-lookup"><span data-stu-id="5ddf3-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="5ddf3-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 네트워크 서브넷을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="5ddf3-106">CAC(통화 제어)가 구현된 비즈니스용 Skype 서버의 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5ddf3-107">따라서 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="5ddf3-108">이 문서의 섹션을 사용하여 네트워크 서브넷 정보를 보거나 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="5ddf3-109">네트워크 서브넷 정보 보기</span><span class="sxs-lookup"><span data-stu-id="5ddf3-109">View network subnet information</span></span> 

<span data-ttu-id="5ddf3-110">다음 절차에 따라 네트워크 서브넷을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="5ddf3-111">비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="5ddf3-112">네트워크 서브넷을 보려면</span><span class="sxs-lookup"><span data-stu-id="5ddf3-112">To view a network subnet</span></span>

1.  <span data-ttu-id="5ddf3-113">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddf3-114">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddf3-115">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **서브넷을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ddf3-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5ddf3-116">**서브넷** 페이지에서 보려는 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5ddf3-117">서브넷을 한 번에 하나만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="5ddf3-118">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5ddf3-119">cmdlet을 사용하여 네트워크 서브넷 Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="5ddf3-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5ddf3-120">네트워크 서브넷 정보는 네트워크 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkSubnet 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5ddf3-121">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="5ddf3-122">네트워크 서브넷 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="5ddf3-122">To view network subnet information</span></span>

  - <span data-ttu-id="5ddf3-123">모든 네트워크 서브넷에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="5ddf3-124">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="5ddf3-125">자세한 내용은 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet의 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="5ddf3-126">네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5ddf3-126">Create or modify network subnets</span></span> 

<span data-ttu-id="5ddf3-127">네트워크 서브넷은 해당 서브넷에 속한 호스트의 지리적 위치를 확인할 수 있도록 네트워크 사이트에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="5ddf3-128">비즈니스용 Skype 서버 제어판을 사용하여 서브넷을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="5ddf3-129">비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="5ddf3-130">CAC(통화 제어)가 구현된 비즈니스용 Skype 서버의 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5ddf3-131">따라서 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5ddf3-132">이 경우 **New-CsNetworkSubnet을** 다른 cmdlet **Import-CSV와 Windows PowerShell 호출할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ddf3-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5ddf3-133">두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5ddf3-134">.csv 파일에서 서브넷을 만드는 방법의 예는 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="5ddf3-135">네트워크 서브넷을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5ddf3-135">To create a network subnet</span></span>

1.  <span data-ttu-id="5ddf3-136">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddf3-137">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddf3-138">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **서브넷을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ddf3-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5ddf3-139">**서브넷** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="5ddf3-p107">**새 서브넷** 의 **서브넷 ID** 필드에 값을 입력합니다. 이 ID는 IP 주소(예: 174.11.12.0)여야 하며 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="5ddf3-142">**마스크** 필드에 1에서 32 사이의 숫자 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="5ddf3-143">이 값은 작성 중인 서브넷에 적용할 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="5ddf3-144">**네트워크 사이트 ID** 에서 이 서브넷이 속하는 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="5ddf3-145">(선택 사항) 이름만으로는 표현할 수 없는 이 서브넷에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="5ddf3-146">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="5ddf3-147">네트워크 서브넷을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="5ddf3-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="5ddf3-148">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddf3-149">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddf3-150">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **서브넷을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ddf3-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5ddf3-151">**서브넷** 페이지에서 수정할 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="5ddf3-152">**편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5ddf3-p108">**서브넷 편집** 페이지에서 비트 마스크, 연결된 네트워크 사이트 또는 설명을 수정할 수 있습니다. 비트 마스크를 수정하는 경우에도 서브넷 ID는 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="5ddf3-155">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="5ddf3-156">네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="5ddf3-156">Delete network subnets</span></span>

<span data-ttu-id="5ddf3-157">다음 절차를 사용하여 서브넷을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="5ddf3-158">비즈니스용 Skype 서버 제어판에서 네트워크 서브넷을 만들거나 수정하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="5ddf3-159">CAC(통화 제어)가 구현된 비즈니스용 Skype 서버의 대부분의 배포에는 일반적으로 많은 수의 서브넷이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="5ddf3-160">따라서 비즈니스용 Skype 서버 관리 셸에서 서브넷을 구성하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5ddf3-161">이 경우 **New-CsNetworkSubnet을** 다른 cmdlet **Import-CSV와 Windows PowerShell 호출할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5ddf3-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="5ddf3-162">두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="5ddf3-163">.csv 파일에서 서브넷을 만드는 방법의 예제는 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="5ddf3-164">네트워크 서브넷을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="5ddf3-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="5ddf3-165">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddf3-166">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddf3-167">왼쪽 탐색 모음에서 네트워크 구성을 클릭한 다음 **서브넷을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ddf3-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="5ddf3-168">**서브넷** 페이지에서 삭제할 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="5ddf3-p111">한 번에 둘 이상의 서브넷을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 서브넷을 선택합니다. 또는 모든 서브넷을 선택하려면 **편집** 메뉴에서 **모두 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="5ddf3-172">**편집** 메뉴에서 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="5ddf3-173">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="5ddf3-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ddf3-174">See Also</span></span>

[<span data-ttu-id="5ddf3-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5ddf3-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="5ddf3-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5ddf3-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="5ddf3-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5ddf3-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="5ddf3-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5ddf3-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
