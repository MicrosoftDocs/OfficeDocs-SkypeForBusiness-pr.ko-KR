---
title: 'Lync Server 2013: 백 엔드 서버 고가용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5b2fe64b4f32a43ff1462ab27daef04694c99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515755"
---
# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="1d39d-102">Lync Server 2013의 백 엔드 서버 고가용성</span><span class="sxs-lookup"><span data-stu-id="1d39d-102">Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d39d-103">_**마지막으로 수정 된 항목:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="1d39d-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="1d39d-104">백 엔드 서버에 대 한 고가용성을 보장 하기 위해 동기 SQL 미러링 또는 SQL 클러스터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="1d39d-105">이러한 솔루션을 선택 하는 것이 좋지만 조직의 비즈니스 연속성을 유지 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="1d39d-106">Lync Server 2013의 백 엔드 서버 고가용성에 대해서는 비동기 SQL 미러링이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="1d39d-107">다른 언급이 없는 한 이 문서에서 사용된 SQL 미러링은 동기 SQL 미러링을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="1d39d-108">토폴로지 작성기를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="1d39d-109">SQL 장애 조치 (failover) 클러스터링의 경우 설치 프로그램에 SQL Server를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="1d39d-110">재해 복구를 위해 다른 프런트 엔드 풀과 쌍을 이루는 풀에서 SQL 미러링 또는 SQL 클러스터링을 사용 하는 경우에는 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="1d39d-111">Sql 미러링을 사용 하 여 풀을 한 풀과 쌍을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="1d39d-112">SQL 미러링을 배포할 때 해당 응용 프로그램이 풀에서 실행 되는 경우 중앙 관리 저장소를 비롯 하 여이 풀에 있는 모든 Lync Server 데이터베이스가 미러링된 다음 응답 그룹 응용 프로그램 데이터베이스 및 통화 대기 응용 프로그램 데이터베이스를 포함 하 여 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="1d39d-p104">SQL 미러링을 사용하면 서버에 공유 저장소를 사용하지 않아도 됩니다. 각 서버는 로컬 저장소에 데이터베이스 복사본을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="1d39d-p105">미러링 모니터를 포함하거나 포함하지 않은 상태로 SQL 미러링을 배포하도록 선택할 수 있습니다. 하지만 벡 엔드 서버의 장애 조치(failover)를 자동화할 수 있도록 미러링 모니터를 사용하는 것이 좋습니다. 그렇지 않으면 관리자가 수동으로 장애 조치를 호출해야 합니다. 참고로, 미러링 모니터가 구축된 경우라도 필요하면 관리자가 수동으로 백 엔드 서버의 장애 조치를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="1d39d-p106">미러링 모니터를 사용하는 경우 여러 쌍의 백 엔드 서버에 대해 단일 미러링 모니터를 사용할 수 있습니다. 미러링 모니터와 백 엔드 서버 쌍 간을 엄격하게 1:1로 일치시킬 필요는 없습니다. 여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용하는 구축의 경우 각 백 엔드 서버 쌍에 별도의 미러링 모니터를 사용하는 토폴로지보다 복원력은 다소 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="1d39d-122">SQL 클러스터링 지원에 대 한 자세한 내용은 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d39d-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="1d39d-123">SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [CONFIGURE SQL Server 클러스터링 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d39d-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="1d39d-124">SQL 미러링을 사용 하는 자동 백 엔드 서버 장애 조치의 복구 시간</span><span class="sxs-lookup"><span data-stu-id="1d39d-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="1d39d-125">SQL 미러링과 함께 자동 백 엔드 장애 조치 (failover)의 경우 RTO (복구 시간 목표)에 대 한 엔지니어링 대상이 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="1d39d-126">동기 SQL 미러링 때문에, 서버 간에 데이터를 이동 하는 동안 프런트 엔드 서버와 백 엔드 서버가 동시에 작동 하지 않는 경우를 제외 하 고는 백 엔드 서버 오류 발생 시 데이터 손실이 예상 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="1d39d-127">RPO (복구 지점 목표)에 대 한 엔지니어링 대상은 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="1d39d-128">SQL 미러링과 함께 백 엔드 서버 오류 발생 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="1d39d-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="1d39d-129">오류가 발생한 동안 사용자 환경에 미치는 영향은 오류의 특성과 토폴로지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="1d39d-130">SQL 미러링을 사용 하 고 미러링 모니터 서버가 구성 되어 있고 주 서버가 실패 하면 백 엔드 서버 장애 조치 (failover)가 자동으로 빠르게 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="1d39d-131">활성 사용자는 진행 중인 세션에서 중단이 발생했는지조차 알아채지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="1d39d-132">미러링 모니터 서버가 구성 되어 있지 않으면 관리자가 장애 조치 (failover)를 수동으로 호출 하는 데 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="1d39d-133">이 시간 동안에는 활성 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-133">During that time, active users may be affected.</span></span> <span data-ttu-id="1d39d-134">이러한 사용자는 약 30 분 동안 표준으로 세션을 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="1d39d-135">기본 설정이 복원 되지 않거나 관리자가 백업에 장애 조치 (failover)를 수행 하지 않은 경우 사용자는 복구 모드로 전환 되므로 Lync Server에 대 한 영구 변경 (예: 대화 상대 추가)이 필요한 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="1d39d-p111">기본 서버와 미러 백 엔드 서버에 모두 오류가 발생하는 경우 또는 이러한 서버 중 하나와 미러링 모니터에 오류가 발생하는 경우 기본 서버가 실행 중이더라도 백 엔드 서버를 사용할 수 없습니다. 이러한 경우 활성 사용자는 일정 시간이 지난 후 복원 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d39d-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

