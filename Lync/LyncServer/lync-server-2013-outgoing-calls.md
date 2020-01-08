---
title: 'Lync Server 2013: 발신 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2ccd095cfe27f173ff0fe7ac0dac92ca51a7c1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="8069e-102">Lync Server 2013의 발신 전화</span><span class="sxs-lookup"><span data-stu-id="8069e-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8069e-103">_**마지막으로 수정한 주제:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="8069e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8069e-104">위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자의 아웃 바운드 통화 라우팅은 사용자 끝점의 네트워크 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="8069e-105">다음 표에서는 위치 기반 라우팅이 호출자 끝점의 위치에 따라 아웃 바운드 호출의 라우팅에 영향을 주는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="8069e-106">발신자가 PSTN으로 발신 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="8069e-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8069e-107">위치 기반 라우팅에 사용 되는 네트워크 사이트에 위치한 사용자 끝점</span><span class="sxs-lookup"><span data-stu-id="8069e-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="8069e-108">알 수 없는 네트워크 사이트에 있거나 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 사용자 끝점</span><span class="sxs-lookup"><span data-stu-id="8069e-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8069e-109">아웃 바운드 통화 승인</span><span class="sxs-lookup"><span data-stu-id="8069e-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="8069e-110">통화는 사용자의 음성 정책에 따라 승인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="8069e-111">통화는 사용자의 음성 정책에 따라 승인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8069e-112">아웃 바운드 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="8069e-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="8069e-113">네트워크 사이트의 음성 라우팅 정책에 따라 통화가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8069e-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8069e-114">통화는 사용자의 음성 정책에 따라 라우팅 되며 위치 기반 라우팅에 대 한 trunks 사용 하지 않는 경우에만 가능 합니다 (사용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="8069e-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="8069e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8069e-115">See Also</span></span>


[<span data-ttu-id="8069e-116">Lync Server 2013의 위치 기반 라우팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="8069e-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

