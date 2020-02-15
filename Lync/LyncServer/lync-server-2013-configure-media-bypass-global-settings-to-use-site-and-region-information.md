---
title: 사이트 및 지역 정보를 사용 하도록 미디어 바이패스 전역 설정 구성
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
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="8237c-102">사이트 및 지역 정보를 사용 하도록 Lync Server 2013에서 미디어 바이패스 전역 설정 구성</span><span class="sxs-lookup"><span data-stu-id="8237c-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8237c-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8237c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8237c-104">이 항목에서는 중재 서버 미디어 바이패스를 설정하려는 특정 사이트 또는 서비스에 대해 중재 서버에서 피어(ITSP(인터넷 전화 통신 서비스 공급자)의 공중 전화망(PSTN) 게이트웨이, IP-PBX 또는 SBC(Session Border Controller))로의 트렁크 연결에 대한 미디어 바이패스를 이미 구성한 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="8237c-105">또한이 항목에서는 lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013에서 네트워크 사이트 만들기 또는 수정</A>의 단계에 따라 수행한 네트워크 지역, 네트워크 사이트 및 서브넷 구성과 일치 하는 방식으로 토폴로지 작성기에서 모든 중앙 사이트 및 분기 사이트를 정의 하 고 lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013에서 network site를 만들거나 수정한</A>후 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">서브넷을 네트워크 2013 사이트에 연결</A>하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="8237c-106">구성이 일치하지 않으면 미디어 바이패스에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="8237c-p102">피어와 연결된 개별 트렁크 연결에 대한 미디어 바이패스를 설정하는 것 외에 전역 설정도 구성해야 합니다. 이 항목의 단계를 사용하여 미디어 바이패스에 대한 전역 설정을 구성하는 경우 다음 상황 중 하나 또는 둘 다가 구성에 영향을 주는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="8237c-109">트렁크 연결에서 미디어 바이패스를 구성한 피어와 Lync Server 끝점 간의 연결이 양호 *하지* 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="8237c-110">대역폭 관리에 대한 CAC(통화 허용 제어)가 설정된 경우</span><span class="sxs-lookup"><span data-stu-id="8237c-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8237c-111">통화 허용 제어 및 미디어 바이패스에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-media-bypass-and-mediation-server.md">미디어 바이패스 및 중재 서버 2013</A> 의 "PSTN 연결에 대 한 통화 허용 제어" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8237c-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="8237c-p103">네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 바이패스 고급 Enterprise Voice 기능 간에 공유됩니다(둘 다 설정된 경우). 따라서 통화 허용 제어를 이미 구성한 경우 다음 절차에 따라 특별히 미디어 바이패스에 대해 사이트 및 지역 정보를 편집할 필요가 없습니다. 통화 허용 제어에 대한 네트워크 지역 및 사이트를 아직 구성하지 않은 상태에서 미디어 바이패스 설정을 변경하려는 경우에 이 절차의 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="8237c-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="8237c-115">또는 미디어 바이패스에 대한 결정을 내릴 때 사이트 및 지역 정보를 사용하되, 통화 허용 제어를 설정하지 않으려는 경우에 이러한 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="8237c-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="8237c-116">이러한 경우에는 [Lync Server 2013의 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md)에 설명 된 것 처럼 대역폭 제한 링크는 여전히 네트워크 사이트 간 정책을 통해 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="8237c-117">통화 허용 제어가 설정되지 않았으므로 이 경우 실제 대역폭 제한은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="8237c-118">대신, 이러한 링크는 서브넷을 분할하여 대역폭 제한이 없는 링크를 지정하는 데 사용되므로 미디어 바이패스를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="8237c-119">이는 통화 허용 제어와 미디어 바이패스가 둘 다 설정된 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="8237c-120">또한 바이패스가 제대로 작동 하려면 토폴로지 작성기에 정의 된 사이트와 네트워크 지역 및 네트워크 사이트를 구성할 때 정의 된 대로 일관성을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="8237c-121">예를 들어 PSTN 게이트웨이만 배포 된 것으로 토폴로지 작성기에 정의한 분기 사이트가 있는 경우에는 분기 사이트 사용자가 pstn을 통해 라우팅되는 PSTN 통화를 사용할 수 있도록 하는 엔터프라이즈 음성 정책을 사용 하 여 해당 분기 사이트를 구성 해야 합니다. 분기 사이트의 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="8237c-122">미디어 바이패스에 대한 사이트 및 지역 정보를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="8237c-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="8237c-123">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8237c-124">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8237c-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8237c-125">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8237c-126">테이블에서 **전역** 구성을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="8237c-127">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="8237c-128">**사이트 및 지역 구성 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="8237c-129">필요한 경우 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8237c-p107">이 확인란은 대역폭 제한이 없는 하나 이상의 큰 사이트(예: 대규모 중앙 사이트)를 같은 지역과 연결했지만 대역폭이 제한된 일부 분기 사이트도 이 지역과 연결한 경우에만 선택합니다. 매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면 모든 사이트와 연결된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결된 서브넷만 지정하면 되므로 구성이 간소화됩니다. 통화 허용 제어가 설정된 경우에는 이 확인란을 선택하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="8237c-133">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-133">Click **Commit**.</span></span>

<span data-ttu-id="8237c-134">다음으로, [Lync Server 2013의 미디어 바이패스에 대 한 네트워크 사이트와 서브넷을 연결](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)하는 방법에 설명 된 대로 네트워크 사이트에 서브넷을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="8237c-135">네트워크 사이트에 서브넷을 연결 하는 실제 절차는 [Lync Server 2013의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)에 설명 되어 있습니다. 모든 서브넷을 네트워크 사이트에 연결 하 고 나면 미디어 바이패스 배포가 완료 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8237c-136">네트워크 지역 및 네트워크 사이트를 아직 만들지 않은 경우 미디어 바이패스 배포를 진행하려면 먼저 네트워크 지역과 네트워크 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8237c-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="8237c-137">자세한 내용은 Lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013에서 네트워크 지역 만들기 또는 수정</A> 및 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8237c-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8237c-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8237c-138">See Also</span></span>


[<span data-ttu-id="8237c-139">Lync Server 2013에서 미디어 바이패스를 위해 네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="8237c-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

