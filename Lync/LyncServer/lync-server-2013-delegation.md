---
title: 'Lync Server 2013: 위임'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9d9f5473f94f093d92cce1b4664f54d6f32430d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="5eb4c-102">Lync Server 2013의 위임</span><span class="sxs-lookup"><span data-stu-id="5eb4c-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eb4c-103">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5eb4c-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5eb4c-104">Lync의 위임 기능은 다음과 같은 방식으로 위치 기반 라우팅을 통해 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4c-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="5eb4c-105">위치 기반 라우팅을 사용 하도록 설정 된 대리인이 관리자를 대신 하 여 호출을 하면 대리인의 음성 정책을 사용 하 여 통화 권한을 부여 하 고 대리인의 사이트 음성 라우팅 정책이 통화를 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4c-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="5eb4c-106">관리자에 게 들어오는 PSTN 통화에 대 한 통화 전송 및 착신 전환 항목에 설명 된 것과 동일한 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4c-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="5eb4c-107">대리인이 PSTN 끝점을 동시 링 대상으로 설정 하는 경우 관리자에 대 한 수신 호출에 대해 들어오는 트렁크에 연결 된 사이트의 음성 라우팅 정책이 통화를 대리인의 PSTN 끝점으로 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4c-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="5eb4c-108">위임의 경우 관리자와 연결 된 대리인을 일반적으로 동일한 네트워크 사이트에 배치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5eb4c-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5eb4c-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eb4c-109">See Also</span></span>


[<span data-ttu-id="5eb4c-110">Lync Server 2013의 위치 기반 라우팅에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="5eb4c-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

