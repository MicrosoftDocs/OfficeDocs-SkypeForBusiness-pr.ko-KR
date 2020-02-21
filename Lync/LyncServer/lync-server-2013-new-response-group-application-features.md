---
title: 'Lync Server 2013: 새 응답 그룹 응용 프로그램 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37263eeb099ea468713526c20a2c6b14bed0694d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="7933a-102">Lync Server 2013의 새 응답 그룹 응용 프로그램 기능</span><span class="sxs-lookup"><span data-stu-id="7933a-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7933a-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7933a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="7933a-104">응답 그룹 응용 프로그램을 사용하면 수신 전화를 특수한 목적(예: 특정 부서의 고객 서비스, 내부 지원 센터 또는 일반 전화 지원)으로 지정된 사람에게 라우팅하고 큐에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="7933a-105">Lync Server 2013에서는 다음과 같은 응답 그룹 응용 프로그램 기능을 새롭게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="7933a-106">**관리자 역할**</span><span class="sxs-lookup"><span data-stu-id="7933a-106">**Manager role**</span></span>
    
    <span data-ttu-id="7933a-107">Lync Server 2013에는 새로운 응답 그룹 관리자 역할이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="7933a-108">이제 응답 그룹에는 응답 그룹 관리자 및 응답 그룹 관리자의 두 가지 관리 역할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="7933a-109">응답 그룹 관리자는 응답 그룹의 모든 요소를 구성할 수 있지만, 관리자는 자신이 소유한 응답 그룹에 대해서만 특정 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="7933a-110">관리 모델에서의 이러한 향상된 기능은 특히 대규모 배포 시나리오에서 응답 그룹의 확장성을 향상시켜줍니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="7933a-111">**고가용성**</span><span class="sxs-lookup"><span data-stu-id="7933a-111">**High availability**</span></span>
    
    <span data-ttu-id="7933a-112">SQL Server 미러링 형태의 응답 그룹 응용 프로그램에 대 한 고가용성 지원은 Lync Server 2013에 대 한 고가용성의 전체 구성 및 배포의 일부분으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="7933a-113">고가용성을 구성한 상태에서는 기본 백 엔드 서버에 대한 연결이 손실되어도 미러링된 백 엔드 서버를 활용하여 응답 그룹 기능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="7933a-114">응답 그룹 응용 프로그램에 대 한 SQL Server 미러링 지원은 전체 Lync Server 2013 고가용성 구성 외부에서 개별적으로 사용 하거나 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="7933a-115">**재해 복구**</span><span class="sxs-lookup"><span data-stu-id="7933a-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="7933a-116">응답 그룹 응용 프로그램에 대 한 재해 복구 지원은 전체 Lync Server 2013 재해 복구 구성의 일부인 쌍으로 된 프런트 엔드 풀을 구성 하 고 배포 하는 과정에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="7933a-117">또한 응답 그룹 가져오기 및 내보내기 cmdlet은 백업 풀에 대한 장애 조치(failover) 프로세스와 기본 풀 또는 새로운 풀에 대한 복구(failback) 프로세스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="7933a-118">기본 풀에서 중단이 발생하면 응답 그룹을 백업 풀로 장애 조치(failover)하고 중단이 끝났을 때 기본 풀 또는 새 풀로 복구(failback)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7933a-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7933a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7933a-119">See Also</span></span>


[<span data-ttu-id="7933a-120">Lync Server 2013의 응답 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="7933a-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

