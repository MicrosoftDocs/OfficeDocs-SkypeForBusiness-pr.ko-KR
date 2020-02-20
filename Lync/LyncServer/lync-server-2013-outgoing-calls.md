---
title: 'Lync Server 2013: 발신 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5626e5e60a72967c84a79b6ec9aca818d8d62800
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="5ec41-102">Lync Server 2013의 발신 전화</span><span class="sxs-lookup"><span data-stu-id="5ec41-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ec41-103">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5ec41-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5ec41-104">위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자의 아웃 바운드 호출 라우팅은 사용자 끝점의 네트워크 위치에 따라 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec41-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="5ec41-105">다음 표에서는 발신자의 끝점 위치에 따라 위치 기반 라우팅이 아웃 바운드 호출의 라우팅에 미치는 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ec41-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="5ec41-106">발신자가 PSTN에 대 한 아웃 바운드 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec41-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5ec41-107">위치 기반 라우팅을 사용 하도록 설정 된 네트워크 사이트에 있는 사용자 끝점</span><span class="sxs-lookup"><span data-stu-id="5ec41-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="5ec41-108">알 수 없는 네트워크 사이트에 있는 사용자 끝점 또는 위치 기반 라우팅을 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="5ec41-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ec41-109">아웃 바운드 호출 권한 부여</span><span class="sxs-lookup"><span data-stu-id="5ec41-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="5ec41-110">사용자의 음성 정책에 따라 통화가 승인 됨</span><span class="sxs-lookup"><span data-stu-id="5ec41-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="5ec41-111">사용자의 음성 정책에 따라 통화가 승인 됨</span><span class="sxs-lookup"><span data-stu-id="5ec41-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ec41-112">아웃 바운드 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="5ec41-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="5ec41-113">통화가 네트워크 사이트의 음성 라우팅 정책에 따라 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec41-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="5ec41-114">통화는 사용자의 음성 정책에 따라 경로를 설정 하 고 위치 기반 라우팅에는 트렁크을 사용 하지 않도록 설정할 수 있습니다 (사용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="5ec41-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="5ec41-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ec41-115">See Also</span></span>


[<span data-ttu-id="5ec41-116">Lync Server 2013의 위치 기반 라우팅에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="5ec41-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

