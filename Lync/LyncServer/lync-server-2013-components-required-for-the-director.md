---
title: 'Lync Server 2013: 디렉터에 필요한 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a1461e7edb0b90d7cb3bf3a7238e764a900e50b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502415"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="57214-102">Lync Server 2013의 디렉터에 필요한 구성 요소</span><span class="sxs-lookup"><span data-stu-id="57214-102">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57214-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="57214-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="57214-104">디렉터를 만들고 구성 하는 데 필요한 유일한 구성 요소는 디렉터 서버 역할을 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57214-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="57214-105">토폴로지 작성기를 사용 하 여이 작업을 수행 하 고 디렉터 풀 노드에 단일 컴퓨터 풀 또는 다중 컴퓨터 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="57214-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="57214-106">디렉터 또는 디렉터 풀을 정의한 후에는 디렉터가 될 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57214-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="57214-107">디렉터 풀의 경우 풀의 구성원이 되는 각 서버에서 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57214-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="57214-108">기술</span><span class="sxs-lookup"><span data-stu-id="57214-108">Topologies</span></span>

<span data-ttu-id="57214-109">단일 디렉터 서버 또는 디렉터 풀을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57214-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="57214-110">배치 된은 Lync Server 2013의 다른 서버 역할을 사용 하는 것이 아니라 항상 별도의 서버 또는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="57214-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57214-111">디렉터를 배포 하지 않으면 프런트 엔드 서버 또는 프런트 엔드 풀에서 디렉터 역할을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57214-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="57214-112">디렉터 풀은 부하 분산 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57214-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="57214-113">다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57214-113">You can do one of the following:</span></span>

  - <span data-ttu-id="57214-114">웹 서비스에는 하드웨어 부하 분산 장치를 사용하고 다른 트래픽 유형에는 DNS(Domain Name System) 부하 분산을 사용하는 토폴로지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57214-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="57214-115">Lync Server 2013의 확장 된 디렉터 풀-DNS 부하 분산 및 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="57214-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="57214-116">디렉터 풀에 필요한 부하 분산을 위해 하드웨어 부하 분산 장치를 사용 하는 토폴로지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57214-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="57214-117">확장 된 디렉터 풀-Lync Server 2013의 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="57214-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

