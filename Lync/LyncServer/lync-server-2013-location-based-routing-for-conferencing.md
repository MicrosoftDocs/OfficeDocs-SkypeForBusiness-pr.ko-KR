---
title: 'Lync Server 2013: 위치 기반 회의 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ee4c8f996315ede0fd0f7ccd789a73cad25c4f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ebf06-102">Lync Server 2013에서 회의를 위한 위치 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="ebf06-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebf06-103">_**마지막으로 수정한 주제:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="ebf06-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="ebf06-104">위치 기반 라우팅을 사용 하면 통화 중 파티의 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 호출 라우팅을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf06-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="ebf06-105">Lync Server 2013의 누적 업데이트 2를 사용 하는 경우 PSTN 유료 바이패스를 방지 하기 위해 위치 기반 라우팅 규칙을 Lync 모임 (예: 회의)에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf06-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="ebf06-106">이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 사용자의 위치를 기준으로 위치 기반 라우팅 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebf06-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="ebf06-107">또한 위치 기반 라우팅 회의 응용 프로그램을 통해 위치 기반 라우팅 제한을 적용 하 여 PSTN 끝점 관련 consultative 전송을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebf06-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ebf06-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ebf06-108">In This Section</span></span>

  - [<span data-ttu-id="ebf06-109">Lync Server 2013에서 회의를 위한 위치 기반 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="ebf06-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="ebf06-110">Lync Server 2013의 위치 기반 라우팅 및 consultative 통화 전송</span><span class="sxs-lookup"><span data-stu-id="ebf06-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="ebf06-111">Lync Server 2013에서 회의를 위한 위치 기반 라우팅에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebf06-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="ebf06-112">Lync Server 2013에서 회의를 위한 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="ebf06-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

