---
title: 'Lync Server 2013: 네트워크 사이트 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="43655-102">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="43655-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43655-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="43655-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="43655-104">CAC (Call 허용 제어), E9-1-1, 미디어 바이패스 배포는 네트워크 영역과 항상 연결 되어 있으며,이에 따라 지정 되는 *네트워크 사이트* 의 구성에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="43655-105">네트워크 사이트는 지사 위치, 건물 집합 또는 캠퍼스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43655-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="43655-106">네트워크 사이트는 대역폭이 유사한 서브넷의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43655-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="43655-107">다음 절차를 사용 하 여 네트워크 사이트를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="43655-108">예를 들어 하나의 음성 기능에 대 한 네트워크 사이트를 이미 만든 경우 새 네트워크 사이트를 만들 필요가 없습니다. 다른 음성 기능은 동일한 사이트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="43655-109">그러나 기능별 설정을 적용 하려면 기존 네트워크 사이트 정의를 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="43655-110">예를 들어 E9-1에 대 한 네트워크 사이트를 만든 경우에는 호출 허용 제어를 배포 하는 동안 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43655-111">해당 위치가 있는 경우 각 기능에 대 한 배포 설명서의 고급 음성 기능에 해당 하는 것 처럼 특정 예제 및 네트워크 사이트에 대 한 요구 사항을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="43655-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성</A></span><span class="sxs-lookup"><span data-stu-id="43655-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="43655-113">네트워크 사이트를 사용 하 여 작업 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43655-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="43655-114">새-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="43655-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="43655-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="43655-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="43655-116">집합-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="43655-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="43655-117">CsNetworkSite 사이트 제거</span><span class="sxs-lookup"><span data-stu-id="43655-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="43655-118">네트워크 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="43655-118">Create a Network Site</span></span>

<span data-ttu-id="43655-119">통화 허용 제어, E9-1-1 또는 미디어 바이패스에 사용할 수 있는 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43655-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="43655-120">관리 셸을 사용 하 여 네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="43655-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="43655-121">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="43655-122">새-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43655-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="43655-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="43655-124">이 예제에서는 "NorthAmerica" 네트워크 지역에 "시카고" 라는 네트워크 사이트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43655-125">이 명령을 성공적으로 실행 하려면 NorthAmerica 네트워크 지역이 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="43655-126">토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="43655-127">Lync Server 제어판을 사용 하 여 네트워크 사이트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="43655-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="43655-128">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43655-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43655-129">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43655-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="43655-130">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="43655-131">**사이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="43655-132">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-132">Click **New**.</span></span>

5.  <span data-ttu-id="43655-133">**새 사이트** 페이지에서 **이름을** 클릭 한 다음 네트워크 사이트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="43655-134">**지역을**클릭 한 다음 목록에서 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="43655-135">필요에 따라 **대역폭 정책을**클릭 한 다음 목록에서 대역폭 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43655-136">대역폭 정책은 사이트에서 통화 허용 제어를 배포 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="43655-137">필요에 따라 **위치 정책을**클릭 한 다음 목록에서 위치 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43655-138">위치 정책은 사이트에 E9-1-1을 배포 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="43655-139">필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="43655-140">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-140">Click **Commit**.</span></span>

11. <span data-ttu-id="43655-141">토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트의 설정을 사용 하 여 4 ~ 10 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="43655-142">네트워크 사이트 수정</span><span class="sxs-lookup"><span data-stu-id="43655-142">Modify a Network Site</span></span>

<span data-ttu-id="43655-143">통화 허용 제어, E9-1-1 또는 미디어 바이패스에 사용할 수 있는 네트워크 지역을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="43655-144">네트워크 사이트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="43655-144">To modify a network site</span></span>

1.  <span data-ttu-id="43655-145">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="43655-146">집합-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="43655-147">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="43655-148">이 예제에서는 "Albuquerque" 라는 사이트가 "NorthAmerica" 네트워크 지역으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-148">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region.</span></span> <span data-ttu-id="43655-149">통화 허용 제어, E9-1-1 또는 미디어 바이패스를 배포 하도록 네트워크 사이트 구성을 수정 하려면 BWPolicyProfileID 또는 LocationPolicy 매개 변수를 사용 하 여 Set-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-149">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43655-150">BypassID 매개 변수는 미디어를 우회 하는 데 존재 하지만 자동으로 생성 된 우회 Id를 재정의 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-150">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs.</span></span> <span data-ttu-id="43655-151">미디어 바이패스를 위해 네트워크 사이트를 구성 하기 위해 추가 매개 변수를 지정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43655-151">You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="43655-152">토폴로지의 네트워크 사이트 수정을 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="43655-153">Lync Server 제어판을 사용 하 여 네트워크 사이트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="43655-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="43655-154">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43655-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43655-155">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43655-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="43655-156">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="43655-157">**사이트** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="43655-158">표에서 수정 하려는 네트워크 사이트를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="43655-159">**편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="43655-160">**사이트 편집** 페이지에서이 네트워크 사이트의 설정 값을 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="43655-161">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="43655-162">네트워크 사이트 수정을 완료 하려면 다른 사이트 설정에 대해 4 ~ 7 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="43655-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

