---
title: 'Lync Server 2013: 위치 기반 라우팅 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3873e8710d6ab70212de7780ef5f34d1436df1d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f2ba3-102">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="f2ba3-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2ba3-103">_**마지막으로 수정한 주제:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="f2ba3-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="f2ba3-104">이 항목의 정보는 Lync Server 2013의 누적 업데이트 (2013:2 월)와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="f2ba3-105">위치 기반 라우팅을 사용 하면 통화 중 파티의 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 호출 라우팅을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="f2ba3-106">위치 기반 라우팅은 Lync Server 2013 엔터프라이즈 음성 인프라의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="f2ba3-107">위치 기반 라우팅은 Lync Server 2013 CU1에서 통화가 라우팅되는 방법을 제어 하는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="f2ba3-108">Lync 발신자의 지리적 위치를 기반으로 통화를 PBX 또는 PSTN 끝점에 라우팅할 수 있는지 여부에 대 한 통화 권한 부여 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f2ba3-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f2ba3-109">In This Section</span></span>

  - [<span data-ttu-id="f2ba3-110">Lync Server 2013의 위치 기반 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="f2ba3-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-111">Lync Server 2013의 위치 기반 라우팅에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="f2ba3-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-112">Lync Server 2013의 위치 기반 라우팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="f2ba3-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-113">Lync Server 2013의 위치 기반 라우팅을 위한 기술적 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f2ba3-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-114">Lync Server 2013의 위치 기반 라우팅을 위한 클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="f2ba3-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-115">Lync Server 2013의 위치 기반 라우팅에서 지원하지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="f2ba3-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-116">Lync Server 2013의 위치 기반 라우팅 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f2ba3-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="f2ba3-117">Lync Server 2013에서 회의를 위한 위치 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="f2ba3-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2ba3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ba3-118">See Also</span></span>


[<span data-ttu-id="f2ba3-119">Lync Server 2013에서 엔터프라이즈 음성에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="f2ba3-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

