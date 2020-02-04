---
title: 'Lync Server 2013: ABC 프론트 엔드 풀 장애 조치 수행'
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
ms.openlocfilehash: 155d8224b80e614ac8609c007a16072e9d3a5c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="64b4b-102">Lync Server 2013에서 ABC 프론트 엔드 풀 장애 조치 수행</span><span class="sxs-lookup"><span data-stu-id="64b4b-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64b4b-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64b4b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64b4b-104">이 섹션의 두 가지 항목에서는 Lync server 2013에서 ABC 풀 장애 조치를 수행 하는 절차에 대해 설명 하 고, 여기에는 연결 된 Lync Server 프런트 엔드 풀 A 및 B가 있으며 풀 A가 복구할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64b4b-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="64b4b-105">이 절차를 사용 하 여 새 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 프런트 엔드 풀 C를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64b4b-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="64b4b-106">풀 C는 실패 한 풀 A의 정보를 통해 생성 됩니다. 이 절차에는 또한 풀 B 및 C에 연결 된 쌍이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64b4b-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="64b4b-107">Lync Server 2013에서 ABC 풀 장애 조치 (failover)에 대 한 백업 선행 조건</span><span class="sxs-lookup"><span data-stu-id="64b4b-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="64b4b-108">Lync Server 2013의 프런트 엔드 풀 ABC 장애 조치(failover) 절차</span><span class="sxs-lookup"><span data-stu-id="64b4b-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

