---
title: 'Lync Server 2013: 발신 전화'
description: 'Lync Server 2013: 발신 전화'
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
ms.openlocfilehash: e14f19dec35a6da47a2ddd62657d5d087a854f16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546854"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="01d83-103">Lync Server 2013의 발신 전화</span><span class="sxs-lookup"><span data-stu-id="01d83-103">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01d83-104">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="01d83-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="01d83-105">Location-Based 라우팅에서 사용 하도록 설정 된 사용자의 아웃 바운드 호출 라우팅은 사용자 끝점의 네트워크 위치에 따라 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="01d83-105">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="01d83-106">다음 표에서는 Location-Based 라우팅이 발신자의 끝점 위치에 따라 아웃 바운드 호출의 라우팅에 미치는 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01d83-106">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="01d83-107">발신자가 PSTN에 대 한 아웃 바운드 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="01d83-107">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="01d83-108">Location-Based 라우팅을 위해 사용 하도록 설정 된 네트워크 사이트에 있는 사용자 끝점</span><span class="sxs-lookup"><span data-stu-id="01d83-108">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="01d83-109">사용자 끝점이 알 수 없는 네트워크 사이트에 있거나 Location-Based 라우팅을 위해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01d83-109">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01d83-110">아웃 바운드 호출 권한 부여</span><span class="sxs-lookup"><span data-stu-id="01d83-110">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="01d83-111">사용자의 음성 정책에 따라 통화가 승인 됨</span><span class="sxs-lookup"><span data-stu-id="01d83-111">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="01d83-112">사용자의 음성 정책에 따라 통화가 승인 됨</span><span class="sxs-lookup"><span data-stu-id="01d83-112">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01d83-113">아웃 바운드 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="01d83-113">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="01d83-114">통화가 네트워크 사이트의 음성 라우팅 정책에 따라 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="01d83-114">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="01d83-115">전화가 사용자의 음성 정책에 따라 Location-Based 라우팅에 사용 하도록 설정 되지 않은 트렁크를 통해서만 라우팅됩니다 (가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="01d83-115">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="01d83-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01d83-116">See Also</span></span>


[<span data-ttu-id="01d83-117">Lync Server 2013의 Location-Based 라우팅에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="01d83-117">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

