---
title: 미디어 구성 사이트 및 지역 정보 사용을 위한 전역 설정 무시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac820c444f894aabf060c06d6f034f7d92b696c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="ad6a4-102">미디어 구성 Lync Server 2013에서 사이트 및 지역 정보를 사용 하 여 전역 설정을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad6a4-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ad6a4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ad6a4-104">이 항목에서는 인터넷 전화 통신 서비스의 중재 서버에서 피어 (PSTN (공개 통신 네트워크) 게이트웨이, IP PBX 또는 세션 경계 컨트롤러 (SBC)로의 트렁크 연결에 대 한 미디어 바이패스를 이미 구성 했다고 가정 합니다. 미디어를 사용 하 여 중재 서버를 우회 하려는 특정 사이트 또는 서비스에 대 한 공급자 (ITSP)</span><span class="sxs-lookup"><span data-stu-id="ad6a4-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="ad6a4-105">또한이 항목에서는 lync <A href="lync-server-2013-create-or-modify-a-network-region.md">server 2013에서 네트워크 영역 만들기 또는 수정</A>, lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013에서 네트워크 사이트</A>만들기 또는 수정, lync server <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">2013에서 서브넷을 네트워크 사이트에 연결</A>하는 단계에 따라 수행 된 네트워크 지역, 네트워크 사이트 및 서브넷 구성과 일치 하는 방식으로 모든 중앙 사이트 및 분기 사이트를 토폴로지 작성기에 정의 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="ad6a4-106">일치 하지 않으면 미디어 바이패스에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="ad6a4-107">피어에 연결 된 개별 트렁크 연결에 대해 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 전역 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="ad6a4-108">이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우 다음 상황 중 하나 또는 모두에 따라 구성에 영향을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="ad6a4-109">사용자가 트렁크 연결에서 미디어 바이패스를 구성한 피어와 Lync 서버 끝점 간에는 적절 하 게 연결할 수 *없습니다* .</span><span class="sxs-lookup"><span data-stu-id="ad6a4-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="ad6a4-110">대역폭 관리에 대 한 호출 허용 제어 (CAC)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ad6a4-111">통화 허용 제어 및 미디어 바이패스에 대 한 고려 사항에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013에서 미디어 바이패스 및 조정 서버의</A> "PSTN 연결에 대 한 통화 허용 제어" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="ad6a4-112">네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 건너뛰기 고급 Enterprise Voice 기능을 모두 사용 하도록 설정 되어 있는 경우 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-112">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled.</span></span> <span data-ttu-id="ad6a4-113">따라서 통화 허용 제어를 이미 구성한 경우에는 다음 절차를 사용 하 여 미디어 바이패스에 대 한 사이트 및 지역 정보를 편집할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-113">Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass.</span></span> <span data-ttu-id="ad6a4-114">통화 허용 제어에 대해 아직 네트워크 지역과 사이트를 구성 하지 않은 경우 미디어 우회 설정을 변경 하려면이 절차의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-114">Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="ad6a4-115">또는 우회 결정에 사이트 및 지역 정보를 사용 하려는 경우에는 다음 단계를 수행 하지만,이 경우에는 통화 허용 제어를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="ad6a4-116">이러한 경우에는 [Lync Server 2013의 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md)에 설명 된 대로 네트워크 사이트 간 정책을 통해 대역폭 제한 링크를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="ad6a4-117">이 경우에는 통화 허용 제어를 사용할 수 없기 때문에 실제 대역폭 제약 조건이 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="ad6a4-118">대신 이러한 링크를 사용 하 여 대역폭 한도가 없는 서브넷을 지정 하 고 미디어 바이패스를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="ad6a4-119">이는 또한 통화 허용 제어와 미디어 바이패스를 모두 사용 하는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="ad6a4-120">또한 bypass이 제대로 작동 하려면 토폴로지 작성기에 정의 된 사이트 간에 일관성을 유지 해야 하며, 네트워크 지역과 네트워크 사이트를 구성할 때 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="ad6a4-121">예를 들어, PSTN 게이트웨이만 배포 된 상태로 토폴로지 작성기에 정의한 지점 사이트를 사용 하는 경우에는 지점 사이트 사용자가 pstn을 통해 라우팅되는 PSTN 통화를 할 수 있는 엔터프라이즈 음성 정책으로 해당 지점 사이트를 구성 해야 합니다. 지사 사이트의 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="ad6a4-122">미디어 바이패스에 대 한 사이트 및 지역 정보를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="ad6a4-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="ad6a4-123">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ad6a4-124">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ad6a4-125">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="ad6a4-126">표에서 **전역** 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="ad6a4-127">**전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="ad6a4-128">**사이트 및 지역 구성 사용을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="ad6a4-129">필요한 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ad6a4-130">대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만이 확인란을 선택 하 고, 대역폭이 있는 동일한 지역에 연결 된 일부 지점 사이트도 사항이.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-130">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="ad6a4-131">매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결 된 서브넷만 지정 하는 구성이 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-131">When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="ad6a4-132">통화 허용 제어를 사용 하는 경우이 확인란을 선택 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-132">We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="ad6a4-133">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-133">Click **Commit**.</span></span>

<span data-ttu-id="ad6a4-134">다음으로, [Lync Server 2013에서 미디어를 사용 하 여 서브넷을 연결](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)하는 것과 같이 네트워크 사이트에 서브넷을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="ad6a4-135">네트워크 사이트와 서브넷을 연결 하는 실제 절차는 [Lync Server 2013의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)에 설명 되어 있습니다. 모든 서브넷을 네트워크 사이트에 연결한 후에는 미디어 바이패스 배포가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ad6a4-136">아직 네트워크 지역과 네트워크 사이트를 만들지 않은 경우에는 먼저 해당 지역을 만들어야 미디어 건너뛰기 배포를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="ad6a4-137">자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013에서 네트워크 영역 만들기 또는 수정을</A> 참조 하 고 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013에서 네트워크 사이트를 만들거나 수정</A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6a4-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad6a4-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad6a4-138">See Also</span></span>


[<span data-ttu-id="ad6a4-139">네트워크 사이트와 서브넷을 연결 하 여 Lync Server 2013에서 미디어 무시</span><span class="sxs-lookup"><span data-stu-id="ad6a4-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

