---
title: 'Lync Server 2013: Location-Based 라우팅에 대 한 기술적 고려 사항'
description: 'Lync Server 2013: Location-Based 라우팅에 대 한 기술적 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568054"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="3cdc2-103">Lync Server 2013의 Location-Based 라우팅에 대 한 기술적 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3cdc2-103">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cdc2-104">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="3cdc2-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="3cdc2-105">Location-Based 라우팅을 계획할 때는 다음 시나리오에 미치는 영향을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cdc2-105">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="3cdc2-106">재해 복구</span><span class="sxs-lookup"><span data-stu-id="3cdc2-106">Disaster Recovery</span></span>

<span data-ttu-id="3cdc2-107">기본 풀에서 백업 풀로 장애 조치 (failover) 하는 동안과 (와) 정상 작업 Location-Based을 기본 풀로 복원 하는 동안 재해 복구 절차 중에 항상 라우팅이 계속 해 서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cdc2-107">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="3cdc2-108">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="3cdc2-108">Survivable Branch Appliance</span></span>

<span data-ttu-id="3cdc2-109">Location-Based 라우팅을 구성 하면 Sba (survivable 분기 기기와 연결 된 게이트웨이를 배포 하는 계획에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cdc2-109">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="3cdc2-110">SBA와 연결 된 게이트웨이는 Sba (survivable 분기 기기와 동일한 네트워크 사이트에 있어야 합니다. 그렇지 않으면 Location-Based 라우팅이 구성 된 경우 Sba (survivable 분기 기기에 있는 사용자가 아웃 바운드 호출을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3cdc2-110">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="3cdc2-111">Sba (survivable 분기 어플라이언스와 중앙 사이트 간의 WAN 연결이 다운 되 면 Location-Based 라우팅 제한이 적용 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cdc2-111">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3cdc2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cdc2-112">See Also</span></span>


[<span data-ttu-id="3cdc2-113">Lync Server 2013의 Location-Based 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="3cdc2-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

