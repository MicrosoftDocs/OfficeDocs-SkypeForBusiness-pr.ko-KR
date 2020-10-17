---
title: 'Lync Server 2013: Intertrunk 라우팅'
description: 'Lync Server 2013: 인터 트렁크 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553144"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="d99b7-103">Lync Server 2013의 인터 트렁크 라우팅</span><span class="sxs-lookup"><span data-stu-id="d99b7-103">Intertrunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d99b7-104">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d99b7-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d99b7-105">Lync Server 2013는 ip-pbx를 pstn (공중 전화망) 게이트웨이에 상호 연결 하 여 PBX 전화 로부터의 통화를 PSTN으로 경로 설정할 수 있으며 들어오는 PSTN 통화를 PBX (private branch exchange) 전화로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-105">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="d99b7-106">마찬가지로 Lync Server 2013는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 서로 다른 IP PBX 시스템에서 PBX 전화 간에 통화를 주고 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-106">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="d99b7-107">이 인터 트렁크 라우팅 기능은 Lync Server 관리 셸 cmdlet, **get-cstrunkconfiguration**, new 매개 변수 PstnUsages을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-107">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="d99b7-108">이 매개 변수는 사용할 PSTN 사용 레코드 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-108">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="d99b7-109">트렁크는이 PSTN 사용을 사용 하 여 경로를 결정 하 고 모든 수신 전화를 적절 하 게 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-109">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="d99b7-110">다음 다이어그램에서는 PSTN 게이트웨이와 ip-pbx 간의 ip-pbx을 제공 하는 Lync Server 2013를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-110">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="d99b7-111">**게이트웨이와 IP PBX 간의 인터 트렁크 라우팅**</span><span class="sxs-lookup"><span data-stu-id="d99b7-111">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="d99b7-112">![Lync Server 연결 PSTN 게이트웨이/i p-PBX 다이어그램](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 연결 PSTN 게이트웨이/i p-PBX 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="d99b7-112">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="d99b7-113">다음 다이어그램에서는 Lync Server 2013 상호 연결 두 개의 IP PBX 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d99b7-113">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="d99b7-114">**두 IP Pbx 사이의 트렁크 라우팅**</span><span class="sxs-lookup"><span data-stu-id="d99b7-114">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="d99b7-115">![Lync Server 상호 연결 IP-PAX systems 다이어그램](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 상호 연결 IP-PAX systems 다이어그램")</span><span class="sxs-lookup"><span data-stu-id="d99b7-115">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

