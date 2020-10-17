---
title: 'Lync Server 2013: 네트워크 지역 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60e8a5309344a7d504cf958e29dc50a67d50ed29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516735"
---
# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="25bde-102">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="25bde-102">Creating or modifying network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25bde-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="25bde-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="25bde-104">네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="25bde-105">모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="25bde-106">중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="25bde-107">Lync Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="25bde-108">네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="25bde-109">Lync Server 제어판에서는 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="25bde-110">이 항목을 사용 하 여 네트워크 지역을 만들고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="25bde-111">기존 네트워크 지역 삭제에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 지역 삭제](lync-server-2013-deleting-existing-network-regions.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25bde-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="25bde-112">네트워크 지역을 만들려면</span><span class="sxs-lookup"><span data-stu-id="25bde-112">To create a network region</span></span>

1.  <span data-ttu-id="25bde-113">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="25bde-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25bde-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25bde-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25bde-116">왼쪽 탐색 표시줄에서 **네트워크 구성**을 클릭한 다음 **지역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="25bde-117">**지역** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="25bde-118">**새 지역** 페이지의 **이름** 필드에 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="25bde-119">이 값은 Microsoft Lync Server 2013 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="25bde-120">**중앙 사이트** 드롭다운 목록에서 이 네트워크 지역에 대한 중앙 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="25bde-p104">**오디오 대체 경로 사용** 확인란은 기본적으로 선택됩니다. 이 필드는 기본 경로에 적절한 대역폭이 없는 경우 대체 경로를 통해 음성 통화를 라우팅할지 여부를 결정하며, 인터넷으로 오프로드를 해제해야 하는 경우에만 이 확인란을 선택 취소합니다. 통화가 인터넷 통화인 경우 대역폭 설정에 관계없이 이 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="25bde-p105">**비디오 대체 경로 사용** 확인란은 기본적으로 선택됩니다. 이 필드는 기본 경로에 적절한 대역폭이 없는 경우 대체 경로를 통해 화상 통화를 라우팅할지 여부를 결정하며, 인터넷으로 오프로드를 해제해야 하는 경우에만 이 확인란을 선택 취소합니다. 통화가 인터넷 통화인 경우 대역폭 설정에 관계없이 이 확인란을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="25bde-129">(선택 사항) **설명** 필드에 값을 입력하여 이름 하나로만 표시될 수 없는 이 지역에 대해 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="25bde-130">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-130">Click **Commit**.</span></span>

<span data-ttu-id="25bde-131">네트워크 지역을 만드는 데 **연결된 사이트** 표는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="25bde-132">사이트를 만들거나 수정할 때 사이트와 지역이 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="25bde-133">자세한 내용은 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-sites.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25bde-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="25bde-134">네트워크 지역을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="25bde-134">To modify a network region</span></span>

1.  <span data-ttu-id="25bde-135">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="25bde-136">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25bde-137">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="25bde-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25bde-138">왼쪽 탐색 표시줄에서 **네트워크 구성**을 클릭한 다음 **지역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="25bde-139">**지역** 페이지에서 수정할 지역을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="25bde-140">**편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="25bde-141">**지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용하거나 사용하지 않도록 지정하는 설정을 수정하고 설명을 변경할 수 있습니다(자세한 내용은 이 항목의 이전 섹션인 "네트워크 지역을 만들려면" 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="25bde-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="25bde-142">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-142">Click **Commit**.</span></span>

<span data-ttu-id="25bde-p108">이 페이지에서 **연결된 사이트**는 수정할 수 없습니다. 연결된 사이트 목록은 참조용으로 제공되므로 지역 설정을 수정할 때는 영향을 받는 사이트를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25bde-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="25bde-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25bde-145">See Also</span></span>


[<span data-ttu-id="25bde-146">Lync Server 2013에서 기존 네트워크 지역 삭제</span><span class="sxs-lookup"><span data-stu-id="25bde-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="25bde-147">Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성</span><span class="sxs-lookup"><span data-stu-id="25bde-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="25bde-148">새-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="25bde-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="25bde-149">설정-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="25bde-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="25bde-150">CsNetworkRegion 제거</span><span class="sxs-lookup"><span data-stu-id="25bde-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="25bde-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="25bde-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

