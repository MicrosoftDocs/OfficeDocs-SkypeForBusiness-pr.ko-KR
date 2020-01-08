---
title: 'Lync Server 2013: Enterprise Voice 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66bba2fe6f53198fcc1e1fc423423e02d46ac8b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="faba3-102">Lync Server 2013 의 Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="faba3-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faba3-103">_**마지막으로 수정한 주제:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="faba3-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="faba3-104">음성 복원 기능은 WAN (광역 네트워크) 장애 또는 다른 이유를 통해 Lync Server 2013을 호스트 하는 중앙 사이트를 사용할 수 없게 되는 경우 사용자가 전화를 걸고 받을 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="faba3-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="faba3-105">중앙 사이트에 장애가 발생 하는 경우 엔터프라이즈 음성 서비스는 원활한 장애 조치를 통해 백업 사이트에 대 한 중단 없이 계속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faba3-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="faba3-106">WAN 장애가 발생 하는 경우 지사 사이트 호출이 로컬 PSTN 게이트웨이로 리디렉션 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faba3-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="faba3-107">이 섹션에서는 중앙 사이트 또는 WAN 장애가 발생 하는 경우 음성 복원 계획에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="faba3-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="faba3-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="faba3-108">In This Section</span></span>

  - [<span data-ttu-id="faba3-109">Lync Server 2013의 중앙 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="faba3-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="faba3-110">Lync Server 2013의 분기 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="faba3-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

