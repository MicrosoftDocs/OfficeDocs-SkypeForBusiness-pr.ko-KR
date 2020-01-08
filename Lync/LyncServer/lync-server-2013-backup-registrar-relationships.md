---
title: Lync Server 2013 백업 등록자 관계
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a642c8d8872b2c0d1372a209c9c05dac704ee20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="d1cbf-102">Lync Server 2013의 백업 등록자 관계</span><span class="sxs-lookup"><span data-stu-id="d1cbf-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1cbf-103">_**마지막으로 수정한 주제:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d1cbf-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d1cbf-104">재해 복구 기능을 제공 하는 것 외에도 쌍을 두 번 연결 하는 풀은 서로에 대 한 백업 등록 기관 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="d1cbf-105">Lync Server 2013에서는 프런트 엔드 풀 간의 등록자에 대 한 백업본이 항상 1:1 and 상호 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="d1cbf-106">즉, P1이 P2에 대 한 백업이 면 P2는 P1에 대 한 백업 이어야 하며 다른 프런트 엔드 풀에 대 한 백업만 가능 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="d1cbf-107">이는 프런트 엔드 풀의 백업 관계가 다를 수 있는 Lync Server 2010의 변경 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="d1cbf-108">두 프런트 엔드 풀 간의 백업 관계는 1:1 및 대칭 이어야 하지만, Lync Server 2010 에서처럼 각 프런트 엔드 풀은 여러 Survivable 분기 기기에 대 한 백업 등록 기관 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="d1cbf-109">Lync Server 2013는 Survivable Branch 기기에 속한 사용자에 게 재해 복구 지원을 확장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="d1cbf-110">Survivable Branch 기기에 대 한 백업 역할을 하는 프런트 엔드 풀이 다운 되 면 Survivable Branch 기기에 로그인 한 사용자는 프런트 엔드 풀에 속한 사용자가 백업 프런트 엔드 풀로 장애 조치 된 후에도 복원 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1cbf-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

