---
title: 'Lync Server 2013: 새 응답 그룹 응용 프로그램 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="47f1e-102">Lync Server 2013의 새 응답 그룹 응용 프로그램 기능</span><span class="sxs-lookup"><span data-stu-id="47f1e-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47f1e-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="47f1e-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="47f1e-104">응답 그룹 응용 프로그램을 사용 하면 고객 서비스, 내부 지원 센터 또는 부서에 대 한 일반 전화 지원과 같은 특별 한 목적을 위해 지정 된 사용자에 게 수신 전화를 라우팅하고 대기 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="47f1e-105">Lync Server 2013의 새로운 응답 그룹 응용 프로그램 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="47f1e-106">**관리자 역할**</span><span class="sxs-lookup"><span data-stu-id="47f1e-106">**Manager role**</span></span>
    
    <span data-ttu-id="47f1e-107">Lync Server 2013에는 새 응답 그룹 관리자 역할이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="47f1e-108">이제 응답 그룹에 대 한 두 가지 관리 역할인 응답 그룹 관리자 및 응답 그룹 관리자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="47f1e-109">응답 그룹 관리자는 응답 그룹에 대 한 요소를 계속 구성할 수 있지만, 관리자는 자신이 소유한 응답 그룹에 대해서만 특정 요소만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="47f1e-110">관리 모델의 이러한 향상으로 인해 응답 그룹 확장성, 특히 대규모 배포 시나리오에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="47f1e-111">**고가용성**</span><span class="sxs-lookup"><span data-stu-id="47f1e-111">**High availability**</span></span>
    
    <span data-ttu-id="47f1e-112">SQL Server 미러링 형태의 응답 그룹 응용 프로그램에 대 한 고가용성 지원은 Lync Server 2013의 높은 사용 가능성에 대 한 전체 구성 및 배포의 일부로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="47f1e-113">고가용성을 위해 구성 하 고 기본 백 엔드 서버에 대 한 연결이 끊어지면 응답 그룹 기능은 미러 백 엔드 서버를 활용 해도 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="47f1e-114">응답 그룹 응용 프로그램에 대 한 SQL Server 미러링 지원은 전체 Lync Server 2013 고가용성 구성의 범위 밖에 개별적으로 설정 하거나 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="47f1e-115">**재해 복구**</span><span class="sxs-lookup"><span data-stu-id="47f1e-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="47f1e-116">응답 그룹 응용 프로그램에 대 한 재해 복구 지원은 전체 Lync Server 2013 재해 복구 구성의 일부인 페어링 된 프런트 엔드 풀의 구성 및 배포의 일부로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="47f1e-117">또한 응답 그룹 가져오기 및 cmdlet은 백업 풀에 대 한 장애 조치 및 복구 프로세스를 기본 풀이나 새 풀로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="47f1e-118">기본 풀에서 작동 중지가 발생 하는 경우, 응답 그룹을 백업 풀로 장애 조치 (가) 할 수 있으며, 중단을 할 때 주 풀 또는 새 풀로 장애 복구를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f1e-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47f1e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47f1e-119">See Also</span></span>


[<span data-ttu-id="47f1e-120">Lync Server 2013의 응답 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="47f1e-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

