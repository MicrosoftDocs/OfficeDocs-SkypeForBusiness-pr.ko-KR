---
title: 'Lync Server 2013: 위치 기반 라우팅에서 지원하지 않는 기능'
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
ms.openlocfilehash: 967b5b7388ce60eafd46791c226bf1a3edbe0c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="99f03-102">Lync Server 2013의 위치 기반 라우팅에서 지원하지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="99f03-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99f03-103">_**마지막으로 수정한 주제:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="99f03-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="99f03-104">위치 기반 라우팅은 다음 유형의 조작에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f03-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="99f03-105">이러한 기능을 사용 하 여 Lync 끝점이 PSTN 끝점과 상호 작용 하는 경우 위치 기반 라우팅이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f03-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="99f03-106">PSTN 전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="99f03-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="99f03-107">응답 그룹을 통해 들어오고 나가는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="99f03-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="99f03-108">통화 공원를 통한 PSTN 통화 통화 대기 또는 검색</span><span class="sxs-lookup"><span data-stu-id="99f03-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="99f03-109">알림 서비스에 대 한 수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="99f03-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="99f03-110">그룹 통화 픽업을 통해 검색 된 수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="99f03-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="99f03-111">위치 기반 라우팅 규칙을 다음 목록에 있는 조작 유형에 적용 하려면 회의에 위치 기반 라우팅을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f03-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="99f03-112">회의에서 PSTN 다이얼 아웃</span><span class="sxs-lookup"><span data-stu-id="99f03-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="99f03-113">PSTN 끝점을 포함 하는 회의로 피어 투 피어 오디오 대화에서 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="99f03-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="99f03-114">PSTN 끝점과 관련 된 Consultative 전송</span><span class="sxs-lookup"><span data-stu-id="99f03-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="99f03-115">회의에 위치 기반 라우팅을 사용 하려면 [Lync Server 2013에서 회의에 대 한 위치 기반 라우팅을](lync-server-2013-location-based-routing-for-conferencing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f03-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="99f03-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99f03-116">See Also</span></span>


[<span data-ttu-id="99f03-117">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="99f03-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

