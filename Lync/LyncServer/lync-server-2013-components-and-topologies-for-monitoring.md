---
title: 'Lync Server 2013: 모니터링의 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0c848b3c404bc9bce3b54d6ed52157d1b9da679
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="87ad7-102">Lync Server 2013의 모니터링의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="87ad7-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87ad7-103">_**마지막으로 수정한 주제:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="87ad7-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="87ad7-104">통합 데이터 수집 에이전트는 각 프런트 엔드 서버에서 자동으로 설치 되 고 활성화 되므로 모니터링 서버로 작동 하도록 서버를 구성할 필요가 없습니다. 각 프런트 엔드 서버는 이미 모니터링 서버로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="87ad7-105">그러나 모니터링 데이터에 대 한 백 엔드 데이터 저장소 역할을 하는 데이터베이스를 설치 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="87ad7-106">Microsoft Lync Server 2013는 다음 데이터베이스 중 하나를 모니터링을 위한 백엔드 저장소로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="87ad7-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="87ad7-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="87ad7-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="87ad7-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="87ad7-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="87ad7-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="87ad7-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="87ad7-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="87ad7-111">이러한 데이터베이스의 64 비트 버전을 사용 해야 한다는 점에 유의 하십시오. 32 비트 버전의 SQL Server는 모니터링을 위한 백엔드 저장소로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="87ad7-112">마찬가지로 Lync Server 2013는 SQL Server 2008 또는 SQL Server 2012의 Express 버전을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="87ad7-113">Lync Server 2013의 데이터베이스 요구 사항에 대 한 자세한 내용은 Lync server 2013 지원 가능성 가이드의 [Lync server 2013에서 데이터베이스 소프트웨어 지원](lync-server-2013-database-software-support.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ad7-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="87ad7-114">모니터링을 배포 하 고 구성 하기 전에 SQL Server를 설치 하 고 구성 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ad7-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="87ad7-115">그러나 SQL Server 자체를 배포 하기만 하면 됩니다. 모니터링 데이터베이스를 미리 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="87ad7-116">대신 이러한 데이터베이스는 Lync Server 토폴로지를 게시할 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="87ad7-117">모니터링 데이터는 SQL Server 인스턴스를 다른 유형의 데이터로 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="87ad7-118">일반적으로 LcsCdr (통화 정보 기록 데이터베이스)와 QoEMetrics (경력 과정 데이터베이스)는 동일한 SQL 인스턴스를 공유 합니다. 또한 두 모니터링 데이터베이스가 보관 데이터베이스 (LcsLog)와 동일한 SQL 인스턴스에 있어야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="87ad7-119">SQL Server 인스턴스를 사용 하는 유일한 실질적인 요구 사항은 SQL Server의 한 인스턴스가 다음을 제한 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="87ad7-120">Lync Server 2013 백 엔드 데이터베이스의 인스턴스가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="87ad7-121">일반적으로 모니터링 데이터베이스는 동일한 SQL 인스턴스에서 또는 동일한 컴퓨터 (백 엔드 데이터베이스)에 collocated 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="87ad7-122">기술적으로 가능 하지만 백 엔드 데이터베이스에 필요한 디스크 공간을 사용 하 여 모니터링 데이터베이스의 위험을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="87ad7-123">통화 정보 기록 데이터베이스의 한 가지 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="87ad7-124">경력 수준의 데이터베이스 한 가지 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="87ad7-125">보관 데이터베이스의 한 가지 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-125">One instance of the archiving database.</span></span>

<span data-ttu-id="87ad7-126">즉, 동일한 SQL Server 인스턴스에 두 개의 LcsCdr 데이터베이스 인스턴스가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="87ad7-127">LcsCdr 데이터베이스의 인스턴스가 여러 개 필요한 경우에는 SQL Server의 여러 인스턴스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ad7-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="87ad7-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87ad7-128">See Also</span></span>


[<span data-ttu-id="87ad7-129">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="87ad7-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

