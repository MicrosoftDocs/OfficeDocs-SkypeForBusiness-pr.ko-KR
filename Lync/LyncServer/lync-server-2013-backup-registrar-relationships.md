---
title: Lync Server 2013 백업 등록자 관계
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07380cbea030f5c9219cef2654b4761f215988e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="dd5a6-102">Lync Server 2013의 등록자 간 관계 백업</span><span class="sxs-lookup"><span data-stu-id="dd5a6-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd5a6-103">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="dd5a6-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="dd5a6-104">재해 복구 기능을 제공하는 것 외에도 쌍으로 연결된 두 개의 풀이 서로 백업 등록자로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="dd5a6-105">Lync Server 2013에서 프런트 엔드 풀 간의 백업 등록자 관계는 항상 1:1 및 상호 상대입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="dd5a6-106">즉, P1이 P2의 백업이면 P2도 P1의 백업이어야 하며, 둘 중 어느 것도 다른 프런트 엔드 풀의 백업이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="dd5a6-107">이는 프런트 엔드 풀 백업 관계가 다를 수 있는 Lync Server 2010에서 변경 된 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="dd5a6-108">두 프런트 엔드 풀 간의 백업 관계가 1:1 및 대칭 이어야 하지만 각 프런트 엔드 풀은 Lync Server 2010와 마찬가지로 Sba (survivable 분기 기기의 백업 등록자 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="dd5a6-109">Lync Server 2013는 Sba (survivable Branch 기기에 있는 사용자에 게 재해 복구 지원을 확장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="dd5a6-110">Sba (survivable 분기 기기의 백업으로 사용 되는 프런트 엔드 풀이 다운 되 면 Sba (survivable 분기 기기에 로그인 한 사용자는 프런트 엔드 풀에 있는 사용자가 백업 프런트 엔드 풀로 장애 조치 (failover) 된 후에도 복구 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

