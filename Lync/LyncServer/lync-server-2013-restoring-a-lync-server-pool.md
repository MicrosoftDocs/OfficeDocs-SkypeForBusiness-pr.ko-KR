---
title: 'Lync Server 2013: Lync Server 풀 복원'
description: 'Lync Server 2013: Lync Server 풀을 복원 하는 중입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543814"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="7a388-103">Lync Server 2013에서 Lync Server 풀 복원</span><span class="sxs-lookup"><span data-stu-id="7a388-103">Restoring a Lync Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a388-104">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7a388-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7a388-105">Lync Server 배포에는 다음과 같은 유형의 풀이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a388-105">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="7a388-106">Front End Server(프런트 엔드 서버)</span><span class="sxs-lookup"><span data-stu-id="7a388-106">Front End Server</span></span>

  - <span data-ttu-id="7a388-107">중재 서버</span><span class="sxs-lookup"><span data-stu-id="7a388-107">Mediation Server</span></span>

  - <span data-ttu-id="7a388-108">영구적 채팅 서버</span><span class="sxs-lookup"><span data-stu-id="7a388-108">Persistent Chat Server</span></span>

  - <span data-ttu-id="7a388-109">에지 서버</span><span class="sxs-lookup"><span data-stu-id="7a388-109">Edge Server</span></span>

<span data-ttu-id="7a388-110">전체 풀에 중단이 발생 하는 경우 풀의 각 구성원 서버에 대해 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a388-110">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="7a388-111">프런트 엔드 풀의 경우 먼저 백 엔드 서버를 복원한 다음 각 프런트 엔드 서버를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a388-111">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="7a388-112">자세한 내용은 lync server [2013에서 Enterprise Edition 백 엔드 서버 복원](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) 및 [lync Server 2013의 enterprise Edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a388-112">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="7a388-113">다른 모든 유형의 경우 각 구성원 서버를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="7a388-113">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="7a388-114">자세한 내용은 [Lync server 2013에서 Enterprise Edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a388-114">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

