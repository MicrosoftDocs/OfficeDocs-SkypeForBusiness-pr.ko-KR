---
title: 'Lync Server 2013: Enterprise Voice 복구 계획'
description: 'Lync Server 2013: Enterprise Voice 복구를 계획 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2adcf09b87264666924a16543a1b21e8e3cae39f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567264"
---
# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="aab7f-103">Lync Server 2013의 Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="aab7f-103">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aab7f-104">_**마지막으로 수정 된 항목:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="aab7f-104">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="aab7f-105">음성 복원 이란 Lync Server 2013를 호스트 하는 중앙 사이트가 WAN (광역 네트워크) 오류 또는 다른 원인에 따라 사용할 수 없는 경우 전화를 걸고 수신 하는 사용자 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aab7f-105">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="aab7f-106">중앙 사이트가 실패할 경우에는 Enterprise Voice 서비스에서 백업 사이트에 대해 원활한 장애 조치를 수행하여 중단 없이 작업을 계속 수행하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab7f-106">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="aab7f-107">WAN 실패의 경우 분기 사이트 통화가 로컬 PSTN 게이트웨이로 리디렉션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab7f-107">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="aab7f-108">이 섹션에서는 중앙 사이트 또는 WAN 실패 시 음성 복구 기능 계획에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aab7f-108">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aab7f-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="aab7f-109">In This Section</span></span>

  - [<span data-ttu-id="aab7f-110">Lync Server 2013의 중앙 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="aab7f-110">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="aab7f-111">Lync Server 2013의 분기 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="aab7f-111">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

