---
title: 'Lync Server 2013: 미디어 바이패스 및 통화 허용 제어'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49de294605372b4b407f0ee16a3fd5661822074f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3b4cb-102">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="3b4cb-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b4cb-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3b4cb-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3b4cb-p101">미디어 바이패스 및 CAC(통화 허용 제어)는 함께 작동하여 통화 미디어에 대한 대역폭 제어를 관리합니다. 미디어 바이패스는 정상적으로 연결된 링크를 통한 미디어 흐름을 원활하게 하고, CAC는 대역폭 제약 조건이 있는 링크에 대한 트래픽을 관리합니다. 미디어 바이패스 및 CAC는 함께 사용할 수 없으므로 한 기능을 계획할 때는 다른 기능을 고려해야 합니다. 다음과 같은 조합이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="3b4cb-p102">CAC와 미디어 바이패스를 둘 다 사용하도록 설정. 미디어 바이패스는 **사이트 및 지역 정보 사용**으로 설정해야 합니다. 이 사이트 및 지역 정보는 CAC에 사용되는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="3b4cb-p103">CAC를 사용하도록 설정하는 경우에는 **항상 바이패스**를 선택할 수 없으며 그 반대의 경우도 마찬가지입니다. 이 두 구성은 함께 사용할 수 없기 때문입니다. 즉, 지정된 PSTN 통화에는 두 구성 중 하나만 적용됩니다. 먼저 미디어 바이패스가 통화에 적용되는 지를 확인한 다음, 적용되는 경우에는 CAC가 사용되지 않습니다. 통화를 바이패스할 수 있는 경우에는 기본적으로 CAC가 필요하지 않은 연결을 사용하기 때문입니다. 통화에 바이패스를 적용할 수 없는 경우(클라이언트 및 게이트웨이의 바이패스 ID가 일치하지 않는 경우) CAC가 통화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="3b4cb-117">CAC는 사용하도록 설정하지 않고 미디어 바이패스를 **항상 바이패스**로 설정</span><span class="sxs-lookup"><span data-stu-id="3b4cb-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="3b4cb-118">이 구성에서는 클라이언트와 트렁크 서브넷이 모두 단일 바이패스 ID에 매핑됩니다. ID는 이 항목 하나뿐이며, 시스템에서 자동으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="3b4cb-119">CAC는 사용하도록 설정하지 않고 미디어 바이패스를 **사이트 및 지역 정보 사용**으로 설정</span><span class="sxs-lookup"><span data-stu-id="3b4cb-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="3b4cb-p104">**사이트 및 지역 정보 사용**을 사용하도록 설정하면 CAC가 사용하도록 설정되어 있는지 여부에 관계없이 바이패스 결정도 기본적으로 같은 방식으로 작동합니다. 즉, 지정된 PSTN 통화에 대해 클라이언트 서브넷이 특정 사이트로 매핑되고 해당 서브넷의 바이패스 ID가 추출됩니다. 마찬가지로, 게이트웨이 서브넷이 특정 사이트로 매핑되고 해당 서브넷의 바이패스 ID가 추출됩니다. 두 바이패스 ID가 동일한 경우에만 통화에 대해 바이패스가 수행되며, ID가 동일하지 않은 경우에는 미디어 바이패스가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="3b4cb-p105">CAC를 전역적으로 사용하지 않도록 설정하더라도, 사이트 및 지역 구성을 사용하여 바이패스 결정을 제어하려면 각 사이트 및 링크에 대해 대역폭 정책을 정의해야 합니다. 대역폭 제약 조건의 실제 값과 해당 형식은 관계가 없습니다. 최종적인 목표는 시스템에서 서로 다른 바이패스 ID를 자동으로 계산하여 정상적으로 연결되지 않은 각 로캘에 연결하도록 하는 것입니다. 정의를 통해 대역폭 제약 조건을 정의하는 경우에는 링크가 정상적으로 연결되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="3b4cb-129">CAC는 사용하도록 설정하고 미디어 바이패스는 사용하도록 설정하지 않음.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="3b4cb-130">모든 게이트웨이 및 IP-PBX가 정상적으로 연결되어 있지 않거나 미디어 바이패스를 위한 기타 요구 사항을 충족하지 않는 경우에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="3b4cb-131">미디어 바이패스 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-media-bypass.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b4cb-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3b4cb-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b4cb-132">See Also</span></span>


[<span data-ttu-id="3b4cb-133">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="3b4cb-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="3b4cb-134">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="3b4cb-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="3b4cb-135">Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b4cb-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

