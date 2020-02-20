---
title: 'Lync Server 2013: 미디어 바이패스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95653f645e7eafa508892beeaf1bd20f02e21f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="673f4-102">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="673f4-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="673f4-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="673f4-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="673f4-104">미디어 바이패스는 배포할 중재 서버 수를 최소화할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="673f4-105">일반적으로 중재 서버 풀은 중앙 사이트에 배포되며 분기 사이트에서 게이트웨이를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="673f4-106">미디어 바이패스를 사용하도록 설정하면 분기 사이트에서 클라이언트의 PSTN(공중 전화망) 통화에 대한 미디어가 해당 사이트에서 게이트웨이를 통과해 바로 흐르도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="673f4-107">Lync Server 2013 아웃 바운드 통화 경로 및 Enterprise Voice 정책을 적절 하 게 구성 해야 분기 사이트에 있는 클라이언트의 PSTN 통화가 해당 게이트웨이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="673f4-p102">Wi-Fi 네트워크는 일반적으로 유선 네트워크보다 패킷 손실이 많습니다. 손실된 패킷을 복구하는 것은 일반적으로 게이트웨이에서 처리할 수 있는 사항이 아닙니다. 따라서 무선 서브넷에 대해 바이패스를 사용할지 여부를 결정하기 전에 Wi-Fi 네트워크 품질을 평가하는 것이 좋습니다. 대기 시간 감소와 손실된 패킷 복구 간 득실 관계를 고려해야 합니다. 중재 서버를 바이패스하지 않는 통화에 사용할 수 있는 코덱인 RTAudio는 패킷 손실을 처리하는 데 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="673f4-113">Enterprise Voice 구조를 마련 하 고 나면 미디어 바이패스를 계획 하는 것은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="673f4-114">분기 사이트에 대한 WAN 링크가 없는 중앙화된 토폴로지가 있는 경우 세분화된 제어가 필요하지 않으므로 전역 미디어 바이패스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="673f4-115">하나 이상의 네트워크 지역 및 관련 분기 사이트로 구성된 분산 토폴로지가 있는 경우에는 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="673f4-116">중재 서버 피어가 미디어 바이패스에 필요한 기능을 지원할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="673f4-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="673f4-117">각 네트워크 지역에서 제대로 연결된 사이트</span><span class="sxs-lookup"><span data-stu-id="673f4-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="673f4-118">네트워크에 적합한 미디어 바이패스 및 통합 허용 제어 결합</span><span class="sxs-lookup"><span data-stu-id="673f4-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="673f4-p103">미디어 바이패스를 사용하도록 설정하면 해당 지역 내 대역폭 제약 조건 없이 모든 네트워크 사이트 및 네트워크 지역에 대해 고유한 바이패스 ID가 자동으로 생성됩니다. 지역 내 대역폭 제약 조건이 있는 사이트 및 대역폭 제한 조건이 있는 WAN 링크를 통해 지역에 연결된 사이트에는 각각 고유한 바이패스 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="673f4-121">사용자가 PSTN을 호출 하면 중재 서버가 클라이언트 서브넷의 바이패스 ID와 게이트웨이 서브넷의 우회 ID를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="673f4-122">두 개의 바이패스 ID가 일치할 경우 통화에 미디어 바이패스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="673f4-123">바이패스 Id가 일치 하지 않으면 통화에 사용 되는 미디어는 중재 서버를 통해 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="673f4-124">사용자가 PSTN을 통해 전화를 받으면 사용자의 클라이언트가 클라이언트의 바이패스 ID와 PSTN 게이트웨이의 바이패스 ID를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="673f4-125">두 바이패스 Id가 일치 하는 경우에는 미디어를 게이트웨이에서 클라이언트에 직접 연결 하 여 중재 서버를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="673f4-126">Lync 2010 이상 클라이언트 및 장치만 중재 서버와의 미디어 바이패스 상호 작용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="673f4-p106">미디어 바이패스를 전역적으로 사용하도록 설정하는 것 외에도 각 PSTN 트렁크에서 미디어 바이패스를 개별적으로 사용하도록 설정해야 합니다. 바이패스가 전역적으로 사용하도록 설정되었지만 특정 PSTN 트렁크에 대해 사용하지 않도록 설정된 경우에는 해당 PSTN 트렁크와 관련된 통화에 대해 미디어 바이패스가 호출되지 않습니다. 또한 미디어 바이패스가 <STRONG>사이트 및 지역 정보 사용</STRONG>으로 설정된 경우에는 라우팅할 수 있는 모든 서브넷을 서브넷이 있는 사이트에 연결해야 합니다. 바이패스가 필요하지 않은 사이트에 라우팅 가능한 서브넷이 있는 경우 미디어 바이패스를 사용하도록 설정하기 전에 새 사이트 내에서 이 서브넷을 그룹화해야 합니다. 이렇게 하면 라우팅할 수 없는 서브넷에 다른 바이패스 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="673f4-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="673f4-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="673f4-132">See Also</span></span>


[<span data-ttu-id="673f4-133">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="673f4-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="673f4-134">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="673f4-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="673f4-135">Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="673f4-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

