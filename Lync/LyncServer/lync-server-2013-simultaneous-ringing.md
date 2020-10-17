---
title: 'Lync Server 2013: 동시 신호음 울림'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358a0dd6dab96b67b26c211c9f28dbc6c0842804
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519795"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="f9575-102">Lync Server 2013의 동시 신호음</span><span class="sxs-lookup"><span data-stu-id="f9575-102">Simultaneous ringing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9575-103">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f9575-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f9575-104">호출한 상대방이 동시 신호음을 사용 하도록 설정 되어 있는 경우, Location-Based 라우팅은 발신자의 위치와 호출한 파티의 끝점을 분석 하 여 통화를 라우팅해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9575-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="f9575-105">다음 표에서는 동시 울림을 사용 하 여 구성 된 사용자와, 동시 신호음 대상이 동일한 네트워크 사이트의 사용자 이거나, 다른 네트워크 사이트에 있거나, 알 수 없는 네트워크 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9575-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9575-106">에 대 한 수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="f9575-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="f9575-107">피호출자와 동일한 네트워크 사이트에 위치</span><span class="sxs-lookup"><span data-stu-id="f9575-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="f9575-108">수신자가 아닌 다른 네트워크 사이트에 있음</span><span class="sxs-lookup"><span data-stu-id="f9575-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="f9575-109">알 수 없는 네트워크 사이트에 있거나 Location-Based 라우팅을 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="f9575-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9575-110">Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="f9575-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="f9575-111">동시 벨 울림 허용</span><span class="sxs-lookup"><span data-stu-id="f9575-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="f9575-112">동시 벨 울림 허용 안 됨</span><span class="sxs-lookup"><span data-stu-id="f9575-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="f9575-113">동시 벨 울림 허용 안 됨</span><span class="sxs-lookup"><span data-stu-id="f9575-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="f9575-114">다음 표에서는 동일한 네트워크 사이트, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트에서 Lync 사용자 (예: Lync 발신자) 로부터의 통화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9575-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="f9575-115">수신자는 PSTN 끝점 (즉, 휴대폰)을 동시 링 대상으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9575-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="f9575-116">이 시나리오에서 라우팅을 Location-Based 호출을 수신자의 동시 링 대상 (예: 휴대폰)으로 라우팅해야 하는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9575-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9575-117">동시 링 대상</span><span class="sxs-lookup"><span data-stu-id="f9575-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="f9575-118">피호출자와 동일한 네트워크 사이트에 위치</span><span class="sxs-lookup"><span data-stu-id="f9575-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="f9575-119">수신자가 아닌 다른 네트워크 사이트에 있음</span><span class="sxs-lookup"><span data-stu-id="f9575-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="f9575-120">알 수 없는 네트워크 사이트에 있거나 Location-Based 라우팅을 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="f9575-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9575-121">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="f9575-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f9575-122">발신자의 사이트 음성 라우팅 정책을 통해 허용 되는 동시 벨 울림</span><span class="sxs-lookup"><span data-stu-id="f9575-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f9575-123">발신자의 사이트 음성 라우팅 정책을 통해 허용 되는 동시 벨 울림</span><span class="sxs-lookup"><span data-stu-id="f9575-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f9575-124">발신자의 음성 정책을 통해 허용 되는 동시 링이 Location-Based 라우팅에 대해 사용 하도록 설정 되지 않음 트렁크</span><span class="sxs-lookup"><span data-stu-id="f9575-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f9575-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9575-125">See Also</span></span>


[<span data-ttu-id="f9575-126">Lync Server 2013의 Location-Based 라우팅에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="f9575-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

