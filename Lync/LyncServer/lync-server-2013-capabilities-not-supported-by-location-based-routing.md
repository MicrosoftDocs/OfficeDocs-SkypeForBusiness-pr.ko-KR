---
title: 'Lync Server 2013: Location-Based 라우팅에서 지원 하지 않는 기능'
description: 'Lync Server 2013: Location-Based 라우팅에서 지원 하지 않는 기능입니다.'
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
ms.openlocfilehash: bf9cd03a8cbdd50e136605c4f172598b2ad3f523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565164"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="efb8a-103">Lync Server 2013의 Location-Based 라우팅에서 지원 하지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="efb8a-103">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efb8a-104">_**마지막으로 수정 된 항목:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="efb8a-104">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="efb8a-105">Location-Based 라우팅은 다음과 같은 유형의 상호 작용에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb8a-105">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="efb8a-106">Location-Based 라우팅은 이러한 기능을 사용 하 여 Lync 끝점이 PSTN 끝점과 상호 작용 하는 경우 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb8a-106">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="efb8a-107">PSTN 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="efb8a-107">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="efb8a-108">응답 그룹을 통한 들어오고 나가는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="efb8a-108">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="efb8a-109">통화 대기를 통한 PSTN 통화 검색</span><span class="sxs-lookup"><span data-stu-id="efb8a-109">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="efb8a-110">알림 서비스에 대 한 수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="efb8a-110">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="efb8a-111">그룹 통화 픽업를 통해 검색 되는 들어오는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="efb8a-111">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="efb8a-112">다음 목록에 있는 상호 작용 유형에 Location-Based 라우팅 규칙을 적용 하려면 회의에 Location-Based 라우팅을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb8a-112">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="efb8a-113">PSTN 다이얼 아웃 전화 회의</span><span class="sxs-lookup"><span data-stu-id="efb8a-113">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="efb8a-114">PSTN 끝점과 관련 된 회의에 대 한 피어 투 피어 오디오 대화에서의 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="efb8a-114">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="efb8a-115">PSTN 끝점과 관련 된 문의 후 전송</span><span class="sxs-lookup"><span data-stu-id="efb8a-115">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="efb8a-116">회의에 대 한 Location-Based 라우팅을 사용 하도록 설정 하려면 [Lync Server 2013에서 회의에 대 한 위치 기반 라우팅을](lync-server-2013-location-based-routing-for-conferencing.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="efb8a-116">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="efb8a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efb8a-117">See Also</span></span>


[<span data-ttu-id="efb8a-118">Lync Server 2013의 Location-Based 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="efb8a-118">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

