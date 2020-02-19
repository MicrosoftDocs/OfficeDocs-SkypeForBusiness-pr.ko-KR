---
title: 'Lync Server 2013: 위치 기반 라우팅에서 지원 하지 않는 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff96f72ff7d71c005f97142ed9844b7c9509e022
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="250e5-102">Lync Server 2013의 위치 기반 라우팅에서 지원 하지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="250e5-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="250e5-103">_**마지막으로 수정 된 항목:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="250e5-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="250e5-104">위치 기반 라우팅은 다음 유형의 상호 작용에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="250e5-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="250e5-105">Lync 끝점이 이러한 기능을 사용 하 여 PSTN 끝점과 상호 작용 하는 경우에는 위치 기반 라우팅이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="250e5-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="250e5-106">PSTN 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="250e5-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="250e5-107">응답 그룹을 통한 들어오고 나가는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="250e5-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="250e5-108">통화 대기를 통한 PSTN 통화 검색</span><span class="sxs-lookup"><span data-stu-id="250e5-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="250e5-109">알림 서비스에 대 한 수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="250e5-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="250e5-110">그룹 통화 픽업를 통해 검색 되는 들어오는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="250e5-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="250e5-111">위치 기반 라우팅 규칙을 다음 목록의 상호 작용 유형에 적용 하려면 회의에 위치 기반 라우팅을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="250e5-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="250e5-112">PSTN 다이얼 아웃 전화 회의</span><span class="sxs-lookup"><span data-stu-id="250e5-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="250e5-113">PSTN 끝점과 관련 된 회의에 대 한 피어 투 피어 오디오 대화에서의 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="250e5-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="250e5-114">PSTN 끝점과 관련 된 문의 후 전송</span><span class="sxs-lookup"><span data-stu-id="250e5-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="250e5-115">회의에 대해 위치 기반 라우팅을 사용 하도록 설정 하려면 [Lync Server 2013에서 회의에 대 한 위치 기반 라우팅을](lync-server-2013-location-based-routing-for-conferencing.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="250e5-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="250e5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="250e5-116">See Also</span></span>


[<span data-ttu-id="250e5-117">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="250e5-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

