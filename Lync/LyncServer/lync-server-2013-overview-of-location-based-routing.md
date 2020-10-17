---
title: 'Lync Server 2013: Location-Based 라우팅 개요'
description: 'Lync Server 2013: Location-Based 라우팅에 대 한 개요입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562814"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="db3fa-103">Lync Server 2013의 Location-Based 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="db3fa-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db3fa-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="db3fa-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="db3fa-105">Location-Based 라우팅은 유료 바이패스를 방지 하기 위해 국내 및 국제 PSTN 통화의 라우팅을 수정 하는 새로운 규칙 집합을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="db3fa-106">Location-Based 라우팅은 이러한 규칙을 특정 지역, 특정 게이트웨이 또는 특정 사용자 에게만 범위를 지정 하는 데 사용할 수 있는 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="db3fa-107">다음 시나리오에서는 라우팅을 적용할 수 Location-Based 주요 제한 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="db3fa-108">Egress calls-Location-Based 라우팅은 발신자와 다른 지역에 있는 PSTN 게이트웨이에서 발신 전화가 호출 되지 않도록 하기 위해 PSTN 유료 바이패스를 방지 하는 것과 같은 지역에 있는 PSTN 게이트웨이에서 나가는 호출을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="db3fa-109">Ingress calls-Location-Based 라우팅은 들어오는 호출이 호출 된 Lync 사용자와 동일한 지역에 있지 않은 경우 들어오는 PSTN 호출이 ring Lync 끝점에 전달 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="db3fa-110">알 수 없는 지역-Location-Based 라우팅에서 인터넷에서 연결 하거나 알 수 없는 지역에 있는 원격 사용자와의 수신 및 발신 PSTN 통화를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="db3fa-111">국제 지역-Location-Based 라우팅은 사용자의 위치에 대 한 로컬 게이트웨이를 찾을 수 없는 경우 국제 PSTN 게이트웨이를 통해 발신 전화의 라우팅을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db3fa-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="db3fa-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db3fa-112">See Also</span></span>


[<span data-ttu-id="db3fa-113">Lync Server 2013의 Location-Based 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="db3fa-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

