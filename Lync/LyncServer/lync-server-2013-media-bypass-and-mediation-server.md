---
title: 'Lync Server 2013: 미디어 바이패스 및 중재 서버'
description: 'Lync Server 2013: 미디어 바이패스 및 중재 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb005d3d52fa9e5a38fdf56a65dfcbd73616d87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556434"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="8abd5-103">Lync Server 2013의 미디어 바이패스 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="8abd5-103">Media bypass and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8abd5-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8abd5-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8abd5-105">미디어 바이패스는 관리자가 중재 서버를 통과 하지 않고 사용자 끝점과 PSTN (공중 전화망) 게이트웨이 간에 직접 흐르도록 전화 라우팅을 구성할 수 있도록 하는 Lync Server 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8abd5-105">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="8abd5-106">미디어 바이패스는 대기 시간, 불필요 한 변환, 패킷 손실 가능성 및 잠재적 실패 지점 수를 줄여 통화 품질을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8abd5-106">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="8abd5-107">중재 서버가 없는 원격 사이트가 제한 된 대역폭을 사용 하는 하나 이상의 WAN 링크에 의해 중앙 사이트에 연결 되어 있는 경우 미디어 바이패스는 먼저 WAN 링크에서 중앙 사이트의 중재 서버로 흐르지 않고 원격 사이트의 클라이언트에서 미디어를 사용 하 여 해당 로컬 게이트웨이로 직접 흐르도록 대역폭 요구 사항을 낮춥니다. 이 미디어 처리 절감은 또한 중재 서버의 여러 게이트웨이를 제어 하는 기능을 보완 합니다.</span><span class="sxs-lookup"><span data-stu-id="8abd5-107">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="8abd5-p102">미디어 바이패스와 CAC(통화 허용 제어)는 함께 사용할 수 없습니다. 통화에 미디어 바이패스가 사용되는 경우 해당 통화에 대해 CAC가 수행되지 않습니다. 통화에 관련된 제한된 대역폭에 대한 링크가 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8abd5-p102">Media bypass and call admission control (CAC) are mutually exclusive. If media bypass is employed for a call, CAC is not performed for that call. The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8abd5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8abd5-111">See Also</span></span>


[<span data-ttu-id="8abd5-112">Lync Server 2013의 통화 허용 제어 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="8abd5-112">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="8abd5-113">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="8abd5-113">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

