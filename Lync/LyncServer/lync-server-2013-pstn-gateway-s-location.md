---
title: 'Lync Server 2013: PSTN 게이트웨이 위치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="5a183-102">Lync Server 2013의 PSTN 게이트웨이 위치</span><span class="sxs-lookup"><span data-stu-id="5a183-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a183-103">_**마지막으로 수정한 주제:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5a183-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5a183-104">PSTN 게이트웨이와 Pbx를 통해 라우팅되는 통화는 해당 시스템의 위치에 따라 위치 기반 라우팅 제한이 필요할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="5a183-105">위치 기반 라우팅은 각 트렁크 기준으로 세분성에서 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="5a183-106">위치 기반 라우팅은 트렁크에서 사용 하도록 설정 된 경우 다음 규칙 집합을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="5a183-107">위치 기반 라우팅이 트렁크 기준에 따라 사용 되는 경우, 해당 트렁크에 정의 된 규칙은 해당 트렁크를 통해 라우팅되는 통화에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="5a183-108">Pstn 게이트웨이가 있는 네트워크 사이트와 다른 네트워크 사이트에서 발생 하는 호출이 발생 하는 경우 PSTN tolls 우회를 방지 하기 위해 위치 기반 라우팅은 지정 된 트렁크에 대 한 네트워크 사이트의 연결을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="5a183-109">이는 전화를 지정 된 트렁크로 라우팅할 수 있는 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="5a183-110">Trunks는 다음과 같은 두 가지 방법으로 위치 기반 라우팅에 대해 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="5a183-111">트렁크는 PSTN에 대 한 통화를 egresses 하는 PSTN 게이트웨이에 대해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="5a183-112">이 유형의 트렁크가 라우팅된 걸려오는 전화는 트렁크와 같은 네트워크 사이트 내에 있는 끝점 으로만 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="5a183-113">트렁크는 고정 장소 (예: PBX 전화기)의 PSTN 및 서비스 사용자에 게는 전송 되지 않는 중재 서버 피어에 대해 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="5a183-114">이 특정 구성의 경우,이 유형의 트렁크로 라우팅된 모든 수신 전화는 트렁크와 동일한 네트워크 사이트에서 전송 되는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="5a183-115">PBX 사용자의 통화는 트렁크와 같은 네트워크 사이트에 있는 Lync 사용자와 동일한 위치 기반 라우팅 적용을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="5a183-116">별도의 네트워크 사이트에 있는 두 개의 PBX 시스템이 Lync Server를 통해 연결 된 경우 위치 기반 라우팅은 한 네트워크 사이트의 한 PBX 끝점에서 다른 네트워크 사이트의 다른 PBX 끝점으로 라우팅을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="5a183-117">이 시나리오는 위치 기반 라우팅에 의해 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="5a183-118">이 시나리오 외에도 Lync 사용자와 비슷한 방식으로이 구성을 사용 하 여 중재 서버 피어에 연결 된 끝점은 PSTN (i)으로 호출을 라우팅 하지 않는 다른 중재 서버 피어로 전화를 걸거나 받을 수 있습니다. e. 중재 서버 피어가 연결 된 네트워크 사이트에 관계 없이 다른 PBX에 연결 된 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="5a183-119">PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 통화 전달에 따라 해당 중재 서버 피어에 로컬으로 정의 된 PSTN 게이트웨이만 사용할 수 있는 위치를 기반으로 하는 라우팅이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a183-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5a183-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a183-120">See Also</span></span>


[<span data-ttu-id="5a183-121">Lync Server 2013의 위치 기반 라우팅에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="5a183-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

