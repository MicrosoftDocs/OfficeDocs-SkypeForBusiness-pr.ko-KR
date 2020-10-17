---
title: 'Lync Server 2013: 모니터링을 위한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf9724089eeed36d48cbce8e1872078e3940beae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502525"
---
# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="93cff-102">Lync Server 2013의 모니터링에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="93cff-102">Components and topologies for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93cff-103">_**마지막으로 수정 된 항목:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="93cff-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="93cff-104">통합 데이터 수집 에이전트는 각 프런트 엔드 서버에서 자동으로 설치 및 활성화 되므로 모니터링 서버로 작동 하도록 서버를 구성할 필요가 없습니다. 각 프런트 엔드 서버는 이미 모니터링 서버로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="93cff-105">그러나 모니터링 데이터에 대 한 백 엔드 데이터 저장소로 작동 하도록 데이터베이스를 설치 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="93cff-106">Microsoft Lync Server 2013에서는 모니터링할 백 엔드 저장소로 다음 데이터베이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="93cff-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="93cff-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="93cff-108">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="93cff-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="93cff-109">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="93cff-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="93cff-110">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="93cff-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="93cff-111">이러한 데이터베이스의 64 비트 버전을 사용 해야 합니다. 32 비트 버전의 SQL Server는 모니터링을 위한 백엔드 저장소로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="93cff-112">마찬가지로 Lync Server 2013에서는 Express Edition for SQL Server 2008 또는 SQL Server 2012을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="93cff-113">Lync Server 2013에 대 한 데이터베이스 요구 사항에 대 한 자세한 내용은 lync server 2013 지원 가능성 가이드의 [Lync server 2013에서 데이터베이스 소프트웨어 지원](lync-server-2013-database-software-support.md) 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93cff-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="93cff-114">모니터링을 배포 및 구성 하기 전에 SQL Server를 설치 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="93cff-115">그러나 SQL Server 자체를 배포 하기만 하면 됩니다. 모니터링 데이터베이스를 미리 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="93cff-116">대신 사용자가 Lync Server 토폴로지를 게시할 때 해당 데이터베이스가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="93cff-117">모니터링 데이터는 SQL Server 인스턴스를 다른 유형의 데이터와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="93cff-118">일반적으로 통화 정보 기록 데이터베이스 (LcsCdr) 및 QoEMetrics (Experience Quality database)는 동일한 SQL 인스턴스를 공유 합니다. 또한 두 모니터링 데이터베이스가 보관 데이터베이스 (LcsLog)와 동일한 SQL 인스턴스에 있는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="93cff-119">SQL Server 인스턴스를 사용 하는 유일한 실질적인 요구 사항은 SQL Server의 인스턴스 하나가 다음에 제한 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="93cff-120">Lync Server 2013 백 엔드 데이터베이스의 인스턴스 1 개</span><span class="sxs-lookup"><span data-stu-id="93cff-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="93cff-121">일반적으로는 모니터링 데이터베이스를 동일한 SQL 인스턴스 또는 같은 컴퓨터에 백엔드 데이터베이스와 동일 하 게 배치 된 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="93cff-122">기술적으로는 가능 하지만 백 엔드 데이터베이스에 필요한 디스크 공간을 사용 하 여 모니터링 데이터베이스의 위험을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="93cff-123">통화 정보 기록 데이터베이스의 인스턴스 하나</span><span class="sxs-lookup"><span data-stu-id="93cff-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="93cff-124">품질을 경험 하는 데이터베이스의 한 가지 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="93cff-125">보관 데이터베이스의 인스턴스 하나</span><span class="sxs-lookup"><span data-stu-id="93cff-125">One instance of the archiving database.</span></span>

<span data-ttu-id="93cff-126">즉, 동일한 SQL Server 인스턴스에 두 개의 LcsCdr 데이터베이스 인스턴스가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="93cff-127">LcsCdr 데이터베이스의 인스턴스가 여러 개 필요한 경우에는 여러 SQL Server 인스턴스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cff-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="93cff-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93cff-128">See Also</span></span>


[<span data-ttu-id="93cff-129">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="93cff-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

