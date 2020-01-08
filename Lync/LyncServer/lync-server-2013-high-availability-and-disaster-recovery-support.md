---
title: 'Lync Server 2013: 고가용성 및 재해 복구 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="04682-102">Lync Server 2013의 고가용성 및 재해 복구 지원</span><span class="sxs-lookup"><span data-stu-id="04682-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04682-103">_**마지막으로 수정한 주제:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="04682-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="04682-104">Lync 서버 2013는 풀링을 통해 서버 중복성으로 고가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04682-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="04682-105">특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="04682-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="04682-106">이는 프런트 엔드 서버, Edge 서버, 중재 서버 및 디렉터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04682-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="04682-107">서버 역할에 대 한 자세한 내용은 [Lync server 2013의 서버 역할](lync-server-2013-server-roles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04682-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="04682-108">Lync 서버 2013는 또한 풀 페어링을 사용 하도록 설정 하 여 재해 복구 측정값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="04682-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="04682-109">이 토폴로지를 배포 하는 경우 별도의 데이터 센터에 있는 쌍의 각 풀과 별도의 지역 영역에 프런트 엔드 풀 쌍을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04682-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="04682-110">풀 또는 사이트의 작동이 중단 되 면 해당 풀의 사용자가 쌍의 다른 풀을 사용 하도록 리디렉션 하 여 서비스 중단을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04682-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="04682-111">또한 Lync Server 2013는 백 엔드 서버 고가용성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="04682-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="04682-112">이는 프런트 엔드 풀에 대해 두 백 엔드 서버를 배포 하 고 백 엔드 서버에서 실행 되는 모든 Lync 데이터베이스에 대해 동기 SQL Server 미러링을 설정 하는 선택적 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="04682-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="04682-113">풀 페어링 및 백 엔드 서버 미러링에 대 한 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04682-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="04682-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04682-114">See Also</span></span>


[<span data-ttu-id="04682-115">Lync Server 2013의 서버 역할</span><span class="sxs-lookup"><span data-stu-id="04682-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="04682-116">Lync Server 2013의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="04682-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

