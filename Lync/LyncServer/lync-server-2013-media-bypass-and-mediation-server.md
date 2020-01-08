---
title: 'Lync Server 2013: 미디어 바이패스 및 중재 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="05b4b-102">Lync Server 2013의 미디어 바이패스 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="05b4b-102">Media bypass and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b4b-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="05b4b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="05b4b-104">미디어 바이패스는 관리자가 조정 서버를 통과 하지 않고 사용자 끝점과 PSTN (공용 전환 통신 네트워크) 게이트웨이 간에 직접 흐르도록 호출 라우팅을 구성할 수 있는 Lync Server 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="05b4b-104">Media bypass is a Lync Server capability that enables an administrator to configure call routing to flow directly between the user endpoint and the public switched telephone network (PSTN) gateway without traversing the Mediation Server.</span></span> <span data-ttu-id="05b4b-105">미디어 바이패스는 대기 시간, 불필요 한 번역, 패킷 손실 가능성 및 잠재적 실패 지점 수를 줄여 통화 품질을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b4b-105">Media bypass improves call quality by reducing latency, unnecessary translation, possibility of packet loss, and the number of potential points of failure.</span></span> <span data-ttu-id="05b4b-106">제한 된 대역폭이 있는 하나 이상의 WAN 링크로 중앙 사이트에 중재 서버를 사용 하지 않는 원격 사이트를 연결 하는 경우 미디어 우회는 원격 사이트의 클라이언트에서 미디어를 통해 로컬 게이트웨이로 바로 이동 하도록 하 여 대역폭 요구 사항을 줄입니다. 중앙 사이트의 중재 서버에 대 한 WAN 링크를 통해 먼저 이동 해야 합니다. 이러한 미디어 처리 감소는 또한 여러 게이트웨이를 제어 하는 중재 서버의 기능을 보완 합니다.</span><span class="sxs-lookup"><span data-stu-id="05b4b-106">Where a remote site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by enabling media from a client at a remote site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.This reduction in media processing also complements the Mediation Server’s ability to control multiple gateways.</span></span>

<span data-ttu-id="05b4b-107">미디어 바이패스 및 호출 허용 제어 (CAC)는 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="05b4b-107">Media bypass and call admission control (CAC) are mutually exclusive.</span></span> <span data-ttu-id="05b4b-108">통화에 미디어 바이패스를 사용 하는 경우 해당 통화에 대해 CAC가 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05b4b-108">If media bypass is employed for a call, CAC is not performed for that call.</span></span> <span data-ttu-id="05b4b-109">통화에는 제한 된 대역폭을 사용 하는 링크가 없다는 가정입니다.</span><span class="sxs-lookup"><span data-stu-id="05b4b-109">The assumption is that there are no links with constrained bandwidth involved in the call.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="05b4b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05b4b-110">See Also</span></span>


[<span data-ttu-id="05b4b-111">Lync Server 2013의 통화 허용 제어 서비스 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="05b4b-111">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)  


[<span data-ttu-id="05b4b-112">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="05b4b-112">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

