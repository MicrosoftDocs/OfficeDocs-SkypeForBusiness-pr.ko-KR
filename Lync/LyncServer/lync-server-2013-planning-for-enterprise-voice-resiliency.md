---
title: 'Lync Server 2013: Enterprise Voice 복구 계획'
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
ms.openlocfilehash: 16ca49b8548b60fce6adb723f5a4546ad1ff7388
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="abdf0-102">Lync Server 2013의 Enterprise Voice 복구 계획</span><span class="sxs-lookup"><span data-stu-id="abdf0-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abdf0-103">_**마지막으로 수정 된 항목:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="abdf0-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="abdf0-104">음성 복원 이란 Lync Server 2013를 호스트 하는 중앙 사이트가 WAN (광역 네트워크) 오류 또는 다른 원인에 따라 사용할 수 없는 경우 전화를 걸고 수신 하는 사용자 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="abdf0-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="abdf0-105">중앙 사이트가 실패할 경우에는 Enterprise Voice 서비스에서 백업 사이트에 대해 원활한 장애 조치를 수행하여 중단 없이 작업을 계속 수행하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdf0-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="abdf0-106">WAN 실패의 경우 분기 사이트 통화가 로컬 PSTN 게이트웨이로 리디렉션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abdf0-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="abdf0-107">이 섹션에서는 중앙 사이트 또는 WAN 실패 시 음성 복구 기능 계획에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="abdf0-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abdf0-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="abdf0-108">In This Section</span></span>

  - [<span data-ttu-id="abdf0-109">Lync Server 2013의 중앙 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="abdf0-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="abdf0-110">Lync Server 2013의 분기 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="abdf0-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

