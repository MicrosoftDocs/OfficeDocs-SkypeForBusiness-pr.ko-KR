---
title: 'Lync Server 2013: ABC 프런트 엔드 풀 장애 조치 (failover) 수행'
description: 'Lync Server 2013: ABC 프런트 엔드 풀 장애 조치 (failover)를 수행 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c1aa7a18bc1f1126bcb942a0b3a21283637dcb6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557224"
---
# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="ad0fa-103">Lync Server 2013에서 ABC 프런트 엔드 풀 장애 조치 (failover) 수행</span><span class="sxs-lookup"><span data-stu-id="ad0fa-103">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad0fa-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ad0fa-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ad0fa-105">이 섹션의 두 항목에서는 Lync Server 2013에서 ABC 풀 장애 조치 (failover)를 수행 하는 절차에 대해 설명 하 고, Lync Server 프런트 엔드 풀 A 및 B가 있고, 풀 A를 복구할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0fa-105">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="ad0fa-106">이 절차를 사용 하 여 새 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 프런트 엔드 풀 C를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad0fa-106">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ad0fa-107">Pool C는 failed pool A의 정보를 통해 생성 됩니다. 이 절차에는 또한 풀 B와 C에 함께 페어링이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad0fa-107">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="ad0fa-108">Lync Server 2013의 ABC 풀 장애 조치 (failover)를 위한 백업 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ad0fa-108">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="ad0fa-109">Lync Server 2013의 프런트 엔드 풀 ABC 장애 조치 (failover) 절차</span><span class="sxs-lookup"><span data-stu-id="ad0fa-109">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

