---
title: 'Lync Server 2013: 미디어 바이패스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="56db6-102">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="56db6-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56db6-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="56db6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="56db6-104">미디어 바이패스는 배포 된 중재 서버 수를 최소화 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="56db6-105">일반적으로 중재 서버 풀은 중앙 사이트에 배포 되며 지점 사이트에서 게이트웨이를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="56db6-106">미디어 바이패스를 사용 하도록 설정 하면 지점 사이트에서 클라이언트의 PSTN (공개 통신 네트워크) 호출에 대 한 미디어가 해당 사이트의 게이트웨이를 통해 직접 흐를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="56db6-107">Lync Server 2013 아웃 바운드 통화 경로와 엔터프라이즈 음성 정책을 적절 하 게 구성 하 여 지점 사이트의 클라이언트에 대 한 PSTN 호출이 해당 게이트웨이로 라우팅되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="56db6-108">Wi-fi 네트워크에는 일반적으로 유선 네트워크 보다 더 많은 패킷 손실이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-108">Wi-Fi networks typically experience more packet loss than wired networks.</span></span> <span data-ttu-id="56db6-109">이 패킷 손실에 대 한 복구는 일반적으로 게이트웨이에서 수용할 수 있는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-109">Recovery from this packet loss is not typically something that can be accommodated by gateways.</span></span> <span data-ttu-id="56db6-110">따라서 무선 서브넷에 대해 우회를 사용 해야 하는지 여부를 결정 하기 전에 Wi-fi 네트워크의 품질을 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-110">Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet.</span></span> <span data-ttu-id="56db6-111">대기 시간 감소와 패킷 손실에 대 한 복구도 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-111">There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well.</span></span> <span data-ttu-id="56db6-112">중재 서버를 우회 하지 않는 호출에 사용할 수 있는 RTAudio는 패킷 손실 처리에 더 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-112">RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="56db6-113">엔터프라이즈 음성 구조가 준비 된 후 미디어 바이패스 계획은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="56db6-114">지점 사이트에 대 한 WAN 링크 없이 중앙 집중화 된 토폴로지가 있는 경우 세밀 하 게 조정 된 컨트롤이 필요 하지 않으므로 전역 미디어 바이패스를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="56db6-115">하나 이상의 네트워크 지역 및 관련 지점 사이트로 구성 된 분산 토폴로지가 있는 경우 다음을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="56db6-116">중재 서버 피어가 미디어 바이패스에 필요한 기능을 지원할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="56db6-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="56db6-117">각 네트워크 영역에 제대로 연결 된 사이트</span><span class="sxs-lookup"><span data-stu-id="56db6-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="56db6-118">미디어 우회 및 통화 허용 제어의 조합은 네트워크에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="56db6-119">미디어 바이패스를 사용 하도록 설정 하면 네트워크 영역과 해당 지역 내에서 대역폭 제약 조건이 없는 모든 네트워크 사이트에 대해 고유한 우회 ID가 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-119">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region.</span></span> <span data-ttu-id="56db6-120">지역 내에서 대역폭 제약 조건이 있는 사이트 및 대역폭 제약 조건이 있는 WAN 링크를 통해 지역에 연결 된 사이트에는 각각 고유한 우회 Id가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-120">Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="56db6-121">사용자가 PSTN에 전화를 거는 경우 중재 서버는 클라이언트 서브넷의 우회 ID를 게이트웨이 서브넷의 우회 ID와 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="56db6-122">두 우회 Id가 일치 하는 경우 통화에 미디어 바이패스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="56db6-123">우회 Id가 일치 하지 않는 경우, 통화에 대 한 미디어는 중재 서버를 통해 전달 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="56db6-124">사용자가 PSTN에서 전화를 받으면 사용자의 클라이언트는 우회 ID를 PSTN 게이트웨이의 해당 사용과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="56db6-125">두 우회 Id가 일치 하는 경우에는 클라이언트가 게이트웨이에서 클라이언트에 게 직접 전달 하 고 중재 서버를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="56db6-126">Lync 2010 이상 클라이언트 및 장치만 미디어 조정 서버와의 상호 작용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="56db6-127">미디어 우회를 전역적으로 사용 하도록 설정 하는 것 외에, 각 PSTN 트렁크에서 미디어 우회를 개별적으로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-127">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk.</span></span> <span data-ttu-id="56db6-128">Bypass을 전역으로 사용 하도록 설정 했지만 특정 PSTN 트렁크에 대해 사용 하도록 설정 하지 않은 경우에는 해당 PSTN 트렁크와 관련 된 모든 통화에 대해 미디어 바이패스를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-128">If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk.</span></span> <span data-ttu-id="56db6-129">또한, 미디어 바이패스가 <STRONG>사이트 및 지역 정보를 사용</STRONG>하도록 설정 된 경우에는 라우팅할 수 있는 모든 서브넷을 해당 사용자가 위치한 사이트와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-129">In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located.</span></span> <span data-ttu-id="56db6-130">사이트 내에서 bypass이 필요 하지 않은 라우팅 가능한 서브넷이 있는 경우 미디어 바이패스를 사용 하도록 설정 하기 전에 이러한 서브넷을 새 사이트 내에서 그룹화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-130">If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass.</span></span> <span data-ttu-id="56db6-131">이렇게 하면 unroutable 서브넷에 다른 우회 ID가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56db6-131">Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56db6-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56db6-132">See Also</span></span>


[<span data-ttu-id="56db6-133">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="56db6-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="56db6-134">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="56db6-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="56db6-135">Lync Server 2013의 미디어 바이패스에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="56db6-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

