---
title: 'Lync Server 2013: 회의에 대 한 Location-Based 라우팅'
description: 'Lync Server 2013: 회의를 위한 라우팅을 Location-Based 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 979c835e03bbf87c9a9bf86b030cb9a8f4e138e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554854"
---
# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8550e-103">Lync Server 2013의 회의에 대 한 Location-Based 라우팅</span><span class="sxs-lookup"><span data-stu-id="8550e-103">Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8550e-104">_**마지막으로 수정 된 항목:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="8550e-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="8550e-105">Location-Based 라우팅을 사용 하면 통화에서 파티 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 통화 라우팅을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8550e-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="8550e-106">Lync Server 2013의 누적 업데이트 2를 사용 하 여 PSTN 전화 바이패스를 방지 하기 위해 Lync 모임 (예: 회의)에서 라우팅 규칙을 적용할 수 Location-Based.</span><span class="sxs-lookup"><span data-stu-id="8550e-106">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="8550e-107">이 응용 프로그램은 활성 회의를 모니터링 하 고 참가 하는 사용자의 위치에 따라 Location-Based 라우팅 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8550e-107">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="8550e-108">Location-Based 라우팅 회의 응용 프로그램을 사용 하면 PSTN 끝점이 포함 된 문의 후 전송에 대 한 라우팅 제한 Location-Based 추가로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8550e-108">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8550e-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="8550e-109">In This Section</span></span>

  - [<span data-ttu-id="8550e-110">Lync Server 2013의 회의에 대 한 Location-Based 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="8550e-110">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="8550e-111">Lync Server 2013의 위치 기반 라우팅 및 문의 후 통화 전송</span><span class="sxs-lookup"><span data-stu-id="8550e-111">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="8550e-112">Lync Server 2013에서 회의에 대 한 Location-Based 라우팅을 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8550e-112">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="8550e-113">Lync Server 2013에서 회의에 대 한 Location-Based 라우팅을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8550e-113">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

