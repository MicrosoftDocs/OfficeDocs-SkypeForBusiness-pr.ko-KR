---
title: 'Lync Server 2013: 미디어 바이패스 계획'
description: 'Lync Server 2013: 미디어 바이패스를 계획 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549444"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e9e63-103">Lync Server 2013의 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="e9e63-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9e63-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e9e63-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e9e63-105">미디어 바이패스는 신호가 중재 서버를 트래버스하는 통화에 대해 가능할 때마다 미디어 경로에서 중재 서버를 제거하는 것을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="e9e63-106">미디어 바이패스는 대기 시간, 불필요한 변환, 패킷 손실 가능성 및 잠재적 오류 지점 수를 줄여 음성 품질을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="e9e63-107">바이패스된 통화에 대한 미디어 처리가 없으므로 중재 서버에 대한 부하가 줄어 들어 확장성이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="e9e63-108">이러한 부하가 줄어들면 중재 서버가 여러 게이트웨이를 제어 하는 기능이 보완 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="e9e63-109">중재 서버가 없는 분기 사이트가 제한 된 대역폭을 사용 하는 하나 이상의 WAN 링크를 통해 중앙 사이트에 연결 되어 있는 경우 미디어 바이패스는 먼저 WAN 링크에서 중앙 사이트의 중재 서버로 흐를 필요 없이 분기 사이트에 있는 클라이언트의 미디어가 로컬 게이트웨이로 직접 흐르도록 하 여 대역폭 요구 사항을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="e9e63-110">미디어 바이패스를 통해 중재 서버를 fea-mediation-server-role-plural 하 여 엔터프라이즈 음성 인프라에 필요한 중재 서버 수를 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="e9e63-111">다음 그림에서는 미디어 바이패스가 있는 경우와 없는 경우의 토폴로지의 기본 미디어 및 신호 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="e9e63-112">**미디어 바이패스가 있는 경우와 없는 경우의 미디어 및 신호 경로**</span><span class="sxs-lookup"><span data-stu-id="e9e63-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="e9e63-113">![음성 CAC 미디어 바이패스 연결 적용](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "음성 CAC 미디어 바이패스 연결 적용")</span><span class="sxs-lookup"><span data-stu-id="e9e63-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="e9e63-114">일반적으로 가능한 모든 곳에 미디어 바이패스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9e63-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9e63-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e9e63-115">In This Section</span></span>

  - [<span data-ttu-id="e9e63-116">Lync Server 2013의 미디어 바이패스 개요</span><span class="sxs-lookup"><span data-stu-id="e9e63-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="e9e63-117">Lync Server 2013의 미디어 바이패스 모드</span><span class="sxs-lookup"><span data-stu-id="e9e63-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="e9e63-118">Lync Server 2013의 미디어 바이패스 및 통화 허용 제어 서비스</span><span class="sxs-lookup"><span data-stu-id="e9e63-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="e9e63-119">Lync Server 2013의 미디어 바이패스에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9e63-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e9e63-120">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="e9e63-120">Related Sections</span></span>

[<span data-ttu-id="e9e63-121">Lync Server 2013에서 고급 Enterprise Voice 기능 배포</span><span class="sxs-lookup"><span data-stu-id="e9e63-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9e63-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9e63-122">See Also</span></span>


[<span data-ttu-id="e9e63-123">Lync Server 2013의 미디어 바이패스로 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="e9e63-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="e9e63-124">Lync Server 2013의 글로벌 미디어 바이패스 옵션</span><span class="sxs-lookup"><span data-stu-id="e9e63-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

