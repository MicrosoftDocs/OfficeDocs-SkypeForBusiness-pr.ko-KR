---
title: 'Lync Server 2013: 동시 연결'
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
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="dbbad-102">Lync Server 2013의 동시 연결</span><span class="sxs-lookup"><span data-stu-id="dbbad-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbbad-103">_**마지막으로 수정한 주제:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="dbbad-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="dbbad-104">상대방이 동시 연결을 사용 하도록 설정 하면 위치 기반 라우팅이 호출 당사자의 위치와 호출 대상의 끝점을 분석 하 여 호출을 라우팅해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbad-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="dbbad-105">다음 표에서는 동시 신호음을 사용 하 여 구성 된 사용자와 동시에 발생 하는 대상 사용자가 같은 네트워크 사이트의 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트에 있는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbbad-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbbad-106">에 대 한 수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="dbbad-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="dbbad-107">호출 수신자와 동일한 네트워크 사이트에 위치</span><span class="sxs-lookup"><span data-stu-id="dbbad-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="dbbad-108">호출 수신자가 아닌 다른 네트워크 사이트에 위치</span><span class="sxs-lookup"><span data-stu-id="dbbad-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="dbbad-109">알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="dbbad-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbbad-110">Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="dbbad-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="dbbad-111">동시 신호음 허용</span><span class="sxs-lookup"><span data-stu-id="dbbad-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="dbbad-112">동시 반지 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="dbbad-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="dbbad-113">동시 반지 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="dbbad-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="dbbad-114">다음 표에서는 Lync 사용자 (예: Lync 발신자)에서 동일한 네트워크 사이트, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트의 통화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbbad-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="dbbad-115">호출 수신자의 PSTN 끝점 (즉, 휴대 전화)이 동시 링 대상으로 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbad-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="dbbad-116">이 시나리오에서 위치 기반 라우팅은 호출을 피호출자의 동시 링 대상 (예: 휴대 전화)에 라우팅해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbad-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbbad-117">동시 링 대상</span><span class="sxs-lookup"><span data-stu-id="dbbad-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="dbbad-118">호출 수신자와 동일한 네트워크 사이트에 위치</span><span class="sxs-lookup"><span data-stu-id="dbbad-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="dbbad-119">호출 수신자가 아닌 다른 네트워크 사이트에 위치</span><span class="sxs-lookup"><span data-stu-id="dbbad-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="dbbad-120">알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="dbbad-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbbad-121">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="dbbad-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="dbbad-122">발신자의 사이트 음성 라우팅 정책을 통해 동시 연결 허용</span><span class="sxs-lookup"><span data-stu-id="dbbad-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="dbbad-123">발신자의 사이트 음성 라우팅 정책을 통해 동시 연결 허용</span><span class="sxs-lookup"><span data-stu-id="dbbad-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="dbbad-124">발신자의 음성 정책을 통해 허용 된 동시 연결을 통해 위치 기반 라우팅에 대해 trunks을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbad-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="dbbad-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbbad-125">See Also</span></span>


[<span data-ttu-id="dbbad-126">Lync Server 2013의 위치 기반 라우팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="dbbad-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

