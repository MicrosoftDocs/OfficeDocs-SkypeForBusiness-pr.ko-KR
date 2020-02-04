---
title: 'Lync Server 2013: 수신 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="60839-102">Lync Server 2013의 수신 전화</span><span class="sxs-lookup"><span data-stu-id="60839-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60839-103">_**마지막으로 수정한 주제:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="60839-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="60839-104">위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자에 게 들어오는 통화 라우팅은 사용자 끝점의 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="60839-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="60839-105">수신 전화 라우팅은 다음과 같은 방식으로 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="60839-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="60839-106">사용자가 위치 기반 라우팅 사용 네트워크 사이트에 있는 끝점에 대 한 수신 호출을가지고 있고, 종점이 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 경우에는 통화가 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="60839-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="60839-107">사용자가 위치 기반 라우팅 사용 네트워크 사이트에 있는 끝점에 대 한 수신 호출을가지고 있고 해당 끝점이 PSTN 게이트웨이와 다른 네트워크 사이트에 있는 경우에는 통화가 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60839-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="60839-108">사용자에 게 수신 통화가 시작 되는 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 끝점이 없는 경우 수신 전화는 사용자의 음성 메일로 직접 라우팅되며 부재 중 전화 알림이 상대방이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60839-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="60839-109">위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자의 착신 전환 설정은 계속 적용 되지만, 착신 전환 된 통화에는 사용자의 위치 기반 라우팅 제한 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60839-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="60839-110">다음 표에서는 위치 기반 라우팅이 호출 수신자의 끝점 위치에 따라 인바운드 호출의 라우팅에 영향을 주는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60839-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="60839-111">PSTN 게이트웨이의 네트워크 사이트는 위치 기반 라우팅에 사용할 수 있으며, 위치 기반 라우팅은 동일한 네트워크 사이트 내의 끝점에 대 한 PSTN 호출 라우팅만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="60839-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="60839-112">호출 수신자가 PSTN에서 인바운드 호출을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="60839-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="60839-113">PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 피호출자의 끝점</span><span class="sxs-lookup"><span data-stu-id="60839-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="60839-114">PSTN 게이트웨이와 동일한 네트워크 사이트에 호출 수신자의 끝점이 위치 하지 않음</span><span class="sxs-lookup"><span data-stu-id="60839-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="60839-115">알 수 없는 네트워크 사이트에 있는 피호출자의 끝점 또는 위치 기반 라우팅에 대해 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="60839-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60839-116">인바운드 PSTN 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="60839-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="60839-117">수신 통화가 호출 수신자의 끝점으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="60839-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="60839-118">수신 통화가 피호출자의 끝점으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60839-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="60839-119">수신 통화가 피호출자의 끝점으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60839-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="60839-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60839-120">See Also</span></span>


[<span data-ttu-id="60839-121">Lync Server 2013의 위치 기반 라우팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="60839-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

