---
title: 'Lync Server 2013: 트렁크 간 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="91291-102">Lync Server 2013의 트렁크 간 라우팅</span><span class="sxs-lookup"><span data-stu-id="91291-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91291-103">_**마지막으로 수정한 주제:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="91291-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="91291-104">Lync Server 2013는 intertrunk 라우팅 지원을 통해 기본적인 세션 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91291-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="91291-105">이 새로운 접근 권한 값을 통해 Lync Server에서 다운스트림 전화 통신 시스템에 대 한 통화 제어 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91291-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="91291-106">Intertrunk 라우팅은 IP-PBX (사설 브랜치 교환) 휴대폰의 호출을 PSTN으로 라우팅할 수 있고 들어오는 PSTN 통화를 PBX 전화기로 라우팅할 수 있도록 IP PBX를 PSTN (공개 전환 통신 네트워크) 게이트웨이와 상호 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91291-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="91291-107">마찬가지로, Lync Server는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 여러 IP PBX 시스템에서 PBX 전화기 간에 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91291-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="91291-108">다음 그림에서는 PSTN 게이트웨이와 IP PBX 간의 interconnectivity을 제공 하는 Lync Server 2013을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91291-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="91291-109">![Lync Server 연결 PSTN 게이트웨이/IP-PBX 다이어그램](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 연결 PSTN 게이트웨이/IP-PBX 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="91291-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="91291-110">다음 그림은 두 개의 IP PBX 시스템을 연결 하는 Lync Server 2013을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91291-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="91291-111">![Lync Server 상호 연결 IP-PAX 시스템 다이어그램](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 상호 연결 IP-PAX 시스템 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="91291-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

