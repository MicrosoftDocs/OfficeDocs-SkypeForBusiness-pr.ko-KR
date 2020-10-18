---
title: 'Lync Server 2013: 새로운 재해 복구 및 고가용성 기능'
description: 'Lync Server 2013: 새로운 재해 복구 및 고가용성 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92816f61b66d9eed76c16286aaa6c7392dca7708
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578864"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="229d5-103">Lync Server 2013의 새로운 재해 복구 및 고가용성 기능</span><span class="sxs-lookup"><span data-stu-id="229d5-103">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="229d5-104">_**마지막으로 수정 된 항목:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="229d5-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="229d5-105">Lync Server 2010에서와 마찬가지로 Lync Server 2013에 대 한 기본 고가용성 (HA) 체계는 풀링을 통한 서버 중복성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-105">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="229d5-106">특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="229d5-107">이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="229d5-108">Lync Server 2013에서는 두 데이터 센터에 있는 프런트 엔드 풀을 연결할 수 있도록 하 여 새로운 재해 복구 조치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-108">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="229d5-109">쌍으로 연결된 풀 중 하나가 다운되면 관리자가 사용자를 해당 풀에서 다른 풀로 장애 조치(failover)하여 서비스를 계속해서 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-109">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="229d5-110">이 기능에는 저장소 네트워크 또는 공유 디스크와 같이 고비용의 네트워크 또는 하드웨어 솔루션이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-110">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="229d5-111">Lync Server 2013도 백 엔드 서버 고가용성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-111">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="229d5-112">프런트 엔드 풀에 대해 두 개의 백 엔드 서버를 배포 하 고 백 엔드 서버에서 실행 되는 모든 Lync 데이터베이스에 대해 동기 SQL 미러링을 설정 하는 선택적 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="229d5-113">미러에 대해 미러링 모니터를 배포할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="229d5-113">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="229d5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="229d5-114">See Also</span></span>


[<span data-ttu-id="229d5-115">Lync Server 2013의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="229d5-115">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

