---
title: 'Lync Server 2013: 위치 기반 라우팅을 위한 기술적 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29187cf1a5cf99ae5312f655c924565f6a38a706
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f4f3a-102">Lync Server 2013의 위치 기반 라우팅을 위한 기술적 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f4f3a-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4f3a-103">_**마지막으로 수정한 주제:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f4f3a-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f4f3a-104">위치 기반 라우팅을 계획할 때는 다음 시나리오에 미치는 영향을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="f4f3a-105">재해 복구</span><span class="sxs-lookup"><span data-stu-id="f4f3a-105">Disaster Recovery</span></span>

<span data-ttu-id="f4f3a-106">기본 풀에서 백업 풀로 장애 조치를 수행 하는 것은 물론, 정상 작업을 주 풀로 복원 하는 동안에는 재해 및 복구 절차 중에 위치 기반 라우팅이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="f4f3a-107">Survivable 분기 기기</span><span class="sxs-lookup"><span data-stu-id="f4f3a-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="f4f3a-108">위치 기반 라우팅 구성은 Survivable Branch 기기와 연결 된 게이트웨이를 배포 하는 위치 계획에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="f4f3a-109">SBA에 연결 된 게이트웨이는 Survivable Branch 기기와 동일한 네트워크 사이트에 있어야 합니다. 그렇지 않으면 위치 기반 라우팅이 구성 된 경우 Survivable Branch 기기에 속한 사용자는 아웃 바운드 호출을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="f4f3a-110">Survivable Branch 기기와 중앙 사이트 간의 WAN 연결이 중단 되 면 위치 기반 라우팅 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4f3a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4f3a-111">See Also</span></span>


[<span data-ttu-id="f4f3a-112">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="f4f3a-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

