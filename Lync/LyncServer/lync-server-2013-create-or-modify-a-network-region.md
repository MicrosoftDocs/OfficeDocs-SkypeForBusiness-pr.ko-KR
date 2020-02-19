---
title: 'Lync Server 2013: 네트워크 지역 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3579286f0cf4b77c84baa013aead13b3b671549c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="39c40-102">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="39c40-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c40-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="39c40-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="39c40-104">*네트워크 지역*은 통화 허용 제어, E9-1-1 및 미디어 바이패스 구성에 사용되는 네트워크 허브 또는 백본입니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="39c40-105">다음 절차에 따라 네트워크 지역을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="39c40-106">예를 들어 단일 음성 기능에 대해 네트워크 지역을 이미 만든 경우에는 새 네트워크 지역을 만들 필요가 없으며, 다른 고급 Enterprise Voice 기능도 같은 네트워크 지역을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="39c40-107">그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="39c40-108">예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="39c40-109">자세한 내용은 [Configure network regions FOR CAC In Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39c40-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39c40-110">네트워크 지역 정의에 대한 기능별 요구 사항은 해당 기능의 배포 항목에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="39c40-111">네트워크 지역 사용에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39c40-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="39c40-112">새-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="39c40-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="39c40-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="39c40-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="39c40-114">설정-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="39c40-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="39c40-115">CsNetworkRegion 제거</span><span class="sxs-lookup"><span data-stu-id="39c40-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="39c40-116">네트워크 지역 만들기</span><span class="sxs-lookup"><span data-stu-id="39c40-116">Create a Network Region</span></span>

<span data-ttu-id="39c40-117">통화 허용 제어, E9-1-1 또는 미디어 바이패스에서 사용할 수 있는 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="39c40-118">Lync Server 관리 셸을 사용 하 여 네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="39c40-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="39c40-119">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="39c40-120">New-CsNetworkRegion cmdlet을 실행하여 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="39c40-121">예:</span><span class="sxs-lookup"><span data-stu-id="39c40-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="39c40-122">이 예에서는 사이트 ID가 CHICAGO인 중앙 사이트와 연결된 “NorthAmerica”라는 네트워크 지역이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="39c40-123">토폴로지에 대한 네트워크 지역 만들기를 종료하려면 각 네트워크 지역에 대한 설정을 사용하여 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="39c40-124">Lync Server 제어판을 사용 하 여 네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="39c40-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="39c40-125">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39c40-126">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39c40-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="39c40-127">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="39c40-128">**지역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-128">Click **Region**.</span></span>

4.  <span data-ttu-id="39c40-129">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-129">Click **New**.</span></span>

5.  <span data-ttu-id="39c40-130">**새 지역** 페이지에서 **이름**을 클릭한 다음 네트워크 지역에 대한 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="39c40-131">**중앙 사이트**를 클릭한 다음 목록에서 중앙 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="39c40-132">필요한 경우 **설명**을 클릭한 다음 이 네트워크 사이트를 설명하는 추가 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="39c40-133">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="39c40-134">토폴로지에 대한 네트워크 지역 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-8단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="39c40-135">네트워크 지역 수정</span><span class="sxs-lookup"><span data-stu-id="39c40-135">Modify a Network Region</span></span>

<span data-ttu-id="39c40-136">기존 네트워크 지역에 대한 설정을 수정하여 새 기능에 필요한 변경 내용이나 기본 지역 정보에 대한 변경 내용을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="39c40-137">Lync Server 관리 셸을 사용 하 여 네트워크 지역을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="39c40-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="39c40-138">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="39c40-139">Set-CsNetworkRegion cmdlet을 실행하여 기존 네트워크 지역을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="39c40-140">예:</span><span class="sxs-lookup"><span data-stu-id="39c40-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="39c40-p103">이 예에서는 설명을 변경함으로써 이 항목의 앞 부분에 나온 절차를 사용하여 만든 “NorthAmerica”라는 기존의 네트워크 지역을 수정했습니다. 이 명령은 “NorthAmerica” 지역에 설명이 있는 경우 이 값으로 해당 설명을 덮어쓰고, 설정된 설명이 없는 경우 설명을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="39c40-143">다른 네트워크 지역을 수정하려면 다른 지역에 대한 설정을 사용하여 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="39c40-144">Lync Server 제어판을 사용 하 여 네트워크 지역을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="39c40-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="39c40-145">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39c40-146">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39c40-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="39c40-147">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="39c40-148">**지역** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="39c40-149">테이블에서 수정할 네트워크 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="39c40-150">**편집**을 클릭한 다음 **자세한 정보 표시...** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="39c40-151">**지역 편집** 페이지에서 이 네트워크 지역의 설정에 대한 값을 적절하게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="39c40-152">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="39c40-153">네트워크 지역 수정을 완료하려면 다른 지역에 대한 설정을 사용하여 4-7단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="39c40-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

