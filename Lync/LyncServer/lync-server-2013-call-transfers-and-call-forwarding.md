---
title: 'Lync Server 2013: 통화 전송 및 착신 전환'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b16ad2faac58a5999b803c75d02e01da0da2dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="205e7-102">Lync Server 2013의 통화 전송 및 착신 전환</span><span class="sxs-lookup"><span data-stu-id="205e7-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="205e7-103">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="205e7-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="205e7-104">PSTN 끝점이 포함 된 경우 위치 기반 라우팅은 calle의 끝점과 통화가 전송 되거나 전달 되는 끝점 (즉, 전송/전달 대상)의 위치를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="205e7-105">위치 기반 라우팅은 두 끝점의 위치에 따라 통화를 전송 하거나 전달 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="205e7-106">다음 표에서는 PSTN 끝점을 사용한 통화에서 Lync 사용자의 시나리오를 보여 주고, Lync 사용자가 통화를 다른 Lync 사용자에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="205e7-107">Transferee의 끝점에 대 한 네트워크 사이트 위치에 따라 위치 기반 라우팅은 통화 전송 또는 전달 라우팅에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="205e7-108">착신 전환 또는 전달 시작</span><span class="sxs-lookup"><span data-stu-id="205e7-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="205e7-109">착신 전환/전달을 시작한 사용자</span><span class="sxs-lookup"><span data-stu-id="205e7-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="205e7-110">사용자가 시작 하는 통화 전송 또는 전달을 비롯 한 대상 끝점이 동일한 네트워크 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="205e7-111">사용자가 시작 하는 통화 전송 또는 전달을 통해 대상 끝점이 서로 다른 네트워크 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="205e7-112">대상 끝점이 알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅을 위해 네트워크 사이트를 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="205e7-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="205e7-113">Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="205e7-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="205e7-114">착신 전환 또는 전송이 허용 됨</span><span class="sxs-lookup"><span data-stu-id="205e7-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="205e7-115">착신 전환 또는 전송이 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="205e7-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="205e7-116">착신 전환 또는 전송이 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="205e7-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="205e7-117">예를 들어 PSTN 끝점을 사용한 통화의 Lync 사용자가 동일한 네트워크 사이트에 있는 다른 Lync 사용자에 게 호출을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="205e7-118">이 경우에는 통화 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="205e7-119">다음 표에서는 다른 Lync 사용자와 통화 했을 때 Lync 사용자의 시나리오를 보여 주고 사용자 중 한 명에 게 통화를 PSTN 끝점으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="205e7-120">통화가 전송 되는 사용자의 위치에 따라이 표에서는 위치 기반 라우팅이 통화에 미치는 영향에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="205e7-121">PSTN 끝점에 대 한 통화 전송 또는 전달</span><span class="sxs-lookup"><span data-stu-id="205e7-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="205e7-122">착신 전환/전달 끝점 대상</span><span class="sxs-lookup"><span data-stu-id="205e7-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="205e7-123">같은 네트워크 사이트의 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="205e7-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="205e7-124">서로 다른 네트워크 사이트의 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="205e7-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="205e7-125">위치 기반 라우팅을 위해 알 수 없는 네트워크 사이트 또는 네트워크 사이트의 하나 또는 두 Lync 사용자가 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="205e7-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="205e7-126">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="205e7-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="205e7-127">전송 된 사용자의 사이트 음성 라우팅 정책에 의해 착신 전환 또는 전송 허용</span><span class="sxs-lookup"><span data-stu-id="205e7-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="205e7-128">전송 된 사용자의 사이트 음성 라우팅 정책에 의해 착신 전환 또는 전송 허용</span><span class="sxs-lookup"><span data-stu-id="205e7-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="205e7-129">위치 기반 라우팅을 사용 하도록 설정 되지 않은 트렁크을 통해서만 전송 된 사용자의 음성 정책에 의해 착신 전환 또는 전송 허용</span><span class="sxs-lookup"><span data-stu-id="205e7-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="205e7-130">예를 들어 동일한 네트워크 사이트에 있는 다른 Lync 사용자와의 통화에서 Lync 사용자는 통화를 PSTN 끝점으로 전송 하며 통화 전송은 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="205e7-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="205e7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="205e7-131">See Also</span></span>


[<span data-ttu-id="205e7-132">Lync Server 2013의 위치 기반 라우팅에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="205e7-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

