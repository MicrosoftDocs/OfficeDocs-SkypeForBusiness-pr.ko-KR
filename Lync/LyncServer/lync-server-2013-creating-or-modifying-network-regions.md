---
title: 'Lync Server 2013: 네트워크 지역 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="2dfda-102">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="2dfda-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2dfda-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2dfda-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2dfda-104">네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2dfda-105">모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="2dfda-106">중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="2dfda-107">Lync Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="2dfda-108">네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="2dfda-109">Lync Server 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="2dfda-110">이 항목을 사용 하 여 네트워크 지역을 만들고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="2dfda-111">기존 네트워크 지역을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 영역 삭제](lync-server-2013-deleting-existing-network-regions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2dfda-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="2dfda-112">네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="2dfda-112">To create a network region</span></span>

1.  <span data-ttu-id="2dfda-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2dfda-114">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2dfda-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2dfda-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2dfda-116">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="2dfda-117">**지역** 페이지에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="2dfda-118">**새 지역** 페이지의 **이름** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="2dfda-119">이 값은 Microsoft Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="2dfda-120">**중앙 사이트** 드롭다운 목록에서이 네트워크 영역에 대 한 중앙 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="2dfda-121">**오디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-121">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="2dfda-122">이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 오디오 통화가 대체 경로를 통해 라우팅되는 지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-122">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="2dfda-123">인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-123">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="2dfda-124">인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-124">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="2dfda-125">**비디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-125">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="2dfda-126">이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 영상 통화를 대체 경로를 통해 라우팅할 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-126">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="2dfda-127">인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-127">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="2dfda-128">인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-128">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="2dfda-129">) 이름 만으로 표현할 수 없는이 영역에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="2dfda-130">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-130">Click **Commit**.</span></span>

<span data-ttu-id="2dfda-131">**연결 된 사이트** 테이블은 네트워크 지역을 만드는 데 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="2dfda-132">사이트를 만들거나 수정할 때 사이트를 영역과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="2dfda-133">자세한 내용은 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-sites.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2dfda-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="2dfda-134">네트워크 지역 수정</span><span class="sxs-lookup"><span data-stu-id="2dfda-134">To modify a network region</span></span>

1.  <span data-ttu-id="2dfda-135">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2dfda-136">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2dfda-137">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2dfda-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2dfda-138">왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="2dfda-139">**지역** 페이지에서 수정 하려는 지역을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="2dfda-140">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2dfda-141">**지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용 하거나 사용 하지 않도록 설정 하는 설정을 수정 하 고 설명 (자세한 내용은이 항목의 "네트워크 영역 만들기" 섹션을 참조 하세요.)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="2dfda-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-142">Click **Commit**.</span></span>

<span data-ttu-id="2dfda-143">이 페이지에서 **연결 된 사이트** 를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-143">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="2dfda-144">연결 된 사이트 목록은 지역 설정을 수정할 때 영향을 받는 사이트를 알 수 있도록 참조용으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dfda-144">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2dfda-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dfda-145">See Also</span></span>


[<span data-ttu-id="2dfda-146">Lync Server 2013에서 기존 네트워크 영역 삭제</span><span class="sxs-lookup"><span data-stu-id="2dfda-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="2dfda-147">Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성</span><span class="sxs-lookup"><span data-stu-id="2dfda-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="2dfda-148">새-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2dfda-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="2dfda-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2dfda-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="2dfda-150">CsNetworkRegion 제거</span><span class="sxs-lookup"><span data-stu-id="2dfda-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="2dfda-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="2dfda-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

