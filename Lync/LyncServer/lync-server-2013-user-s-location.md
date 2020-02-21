---
title: 'Lync Server 2013: 사용자 위치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2e0454b5f8fc891aa878623575ee3850050ba28
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="5be57-102">Lync Server 2013의 사용자 위치</span><span class="sxs-lookup"><span data-stu-id="5be57-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5be57-103">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5be57-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5be57-104">위치 기반 라우팅은 E9-1-1, CAC 및 미디어 바이패스에 정의 된 것과 동일한 네트워크 지역, 사이트 및 서브넷을 사용 하 여 PSTN 전화 바이패스를 방지 하기 위해 통화 라우팅 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="5be57-105">사용자의 위치는 사용자의 Lync 끝점에 연결 된 IP 서브넷에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="5be57-106">각 IP 서브넷은 관리자가 정의한 네트워크 지역으로 집계 되는 네트워크 사이트에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="5be57-107">위치 기반 라우팅은 사용자의 네트워크 사이트에 따라 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="5be57-108">위치 기반 라우팅 규칙은 네트워크 사이트별로 적용 되므로 지정 된 규칙 집합이 동일한 네트워크 사이트 내에 있는 위치 기반 라우팅에 사용 되는 모든 끝점에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="5be57-109">관리자는 위치 기반 라우팅을 필요한 네트워크 사이트에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="5be57-110">네트워크 사이트 단위로 음성 라우팅 정책을 정의 하 여 PSTN 전화 번호를 호출 하기 위해 네트워크 사이트에 있는 모든 사용자가 사용 해야 하는 특정 PSTN 게이트웨이를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="5be57-111">이러한 음성 라우팅 정책은 위치 기반 라우팅을 사용 하도록 설정 된 네트워크 사이트에 사용자가 있는 경우 사용자의 음성 정책에 의해 정의 된 라우팅 보다 우선 적용 되며, 사용 하도록 설정 되는 다른 PSTN 게이트웨이를 통해 호출을 라우팅할 수 없게 됩니다. 위치 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="5be57-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="5be57-112">Lync 사용자가 PSTN 전화를 걸 때 사용자의 음성 정책은 사용자에 게 전화를 걸 수 있는 권한을 부여할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="5be57-113">사용자의 음성 정책에 따라 사용자가 전화를 걸 수 있는 경우 위치 기반 라우팅은 통화를 송신 하는 PSTN 게이트웨이를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="5be57-114">위치 기반 라우팅은 사용자의 위치에 따라이 결정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="5be57-115">사용자 위치는 다음과 같은 방식으로 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="5be57-116">사용자가 위치 기반 라우팅을 위해 사용 하도록 설정 된 알려진 네트워크 사이트에 있고 같은 네트워크 사이트 (예: office)에 있는 PSTN 게이트웨이에서 종료 되었습니다 (직접 내부 다이얼) 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="5be57-117">아웃 바운드 통화 라우팅은 사용자가 있는 네트워크 사이트의 음성 라우팅 정책을 통해 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="5be57-118">사용자에 게 들어오는 PSTN 통화는 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 끝점으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="5be57-119">사용자가 PSTN 게이트웨이가 있는 네트워크 사이트와는 다른 알려진 네트워크 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="5be57-120">(즉, 사용자가 다른 회사 사무실로 이동 하는 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="5be57-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="5be57-121">아웃 바운드 통화 라우팅은 사용자가 있는 네트워크 사이트의 음성 라우팅 정책을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="5be57-122">사용자에 대 한 수신 PSTN 통화는 PSTN을 바이패스 하지 못하도록 PSTN 게이트웨이와 다른 사이트에 있는 끝점으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="5be57-123">사용자가 Lync Server 배포에 알려지지 않은 네트워크 사이트에 있는 경우 아웃 바운드 통화 라우팅은 위치 기반 라우팅 제한에 바인딩되지 않은 PSTN 게이트웨이에 사용자에 게 할당 되는 음성 정책을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="5be57-124">들어오는 PSTN 통화는 PSTN 무료 바이패스를 방지 하기 위해 알 수 없는 네트워크 사이트에 있는 끝점으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5be57-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5be57-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5be57-125">See Also</span></span>


[<span data-ttu-id="5be57-126">Lync Server 2013의 위치 기반 라우팅에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="5be57-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

