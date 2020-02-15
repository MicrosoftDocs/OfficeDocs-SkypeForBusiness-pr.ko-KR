---
title: 'Lync Server 2013: 네트워크 서브넷 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47075e96171bbeef5c2709e3eb38a480d08938f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="be0e5-102">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="be0e5-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be0e5-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="be0e5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="be0e5-104">네트워크 서브넷은 해당 서브넷에 속한 호스트의 지리적 위치를 확인할 수 있도록 네트워크 사이트에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="be0e5-105">Lync Server 제어판을 사용 하 여 서브넷을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="be0e5-106">Lync Server 제어판에서는 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="be0e5-107">네트워크 서브넷을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 서브넷 삭제](lync-server-2013-deleting-network-subnets.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be0e5-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="be0e5-108">Microsoft Lync Server 2013의 대부분의 배포에서 CAC (통화 허용 제어)가 구현 되는 경우 일반적으로 서브넷 수가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="be0e5-109">따라서 Lync Server 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="be0e5-110">여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="be0e5-111">두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="be0e5-112">.csv 파일에서 서브넷을 만드는 방법의 예는 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="be0e5-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="be0e5-113">네트워크 서브넷을 만들려면</span><span class="sxs-lookup"><span data-stu-id="be0e5-113">To create a network subnet</span></span>

1.  <span data-ttu-id="be0e5-114">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="be0e5-115">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="be0e5-116">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be0e5-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="be0e5-117">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="be0e5-118">**서브넷** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="be0e5-p104">**새 서브넷**의 **서브넷 ID** 필드에 값을 입력합니다. 이 ID는 IP 주소(예: 174.11.12.0)여야 하며 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="be0e5-121">**마스크** 필드에 1에서 32 사이의 숫자 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be0e5-122">이 값은 작성 중인 서브넷에 적용할 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="be0e5-123">**네트워크 사이트 ID**에서 이 서브넷이 속하는 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="be0e5-124">(선택 사항) 이름만으로는 표현할 수 없는 이 서브넷에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="be0e5-125">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="be0e5-126">네트워크 서브넷을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="be0e5-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="be0e5-127">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="be0e5-128">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="be0e5-129">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be0e5-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="be0e5-130">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="be0e5-131">**서브넷** 페이지에서 수정할 서브넷을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="be0e5-132">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="be0e5-p106">**서브넷 편집** 페이지에서 비트 마스크, 연결된 네트워크 사이트 또는 설명을 수정할 수 있습니다. 비트 마스크를 수정하는 경우에도 서브넷 ID는 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="be0e5-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="be0e5-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="be0e5-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be0e5-136">See Also</span></span>


[<span data-ttu-id="be0e5-137">Lync Server 2013에서 네트워크 서브넷 삭제</span><span class="sxs-lookup"><span data-stu-id="be0e5-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="be0e5-138">Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보</span><span class="sxs-lookup"><span data-stu-id="be0e5-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="be0e5-139">새-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="be0e5-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="be0e5-140">설정-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="be0e5-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="be0e5-141">제거-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="be0e5-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="be0e5-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="be0e5-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

