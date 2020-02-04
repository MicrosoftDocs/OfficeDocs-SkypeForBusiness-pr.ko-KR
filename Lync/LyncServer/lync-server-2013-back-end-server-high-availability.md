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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="e097f-102">백 엔드 서버의 Lync Server 2013에서 높은 가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e097f-103">_**마지막으로 수정한 주제:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="e097f-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="e097f-104">백 엔드 서버의 가용성을 높이기 위해 동기 SQL 미러링 또는 SQL 클러스터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="e097f-105">이러한 솔루션 중 하나를 선택 하는 것이 좋지만 조직의 비즈니스 연속성을 유지 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="e097f-106">Lync Server 2013에서 백 엔드 서버 가용성을 높일 수 있는 비동기 SQL 미러링이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="e097f-107">이 문서의 나머지 부분에서 SQL 미러링은 명시적으로 명시 되지 않는 한 동기 SQL 미러링을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="e097f-108">토폴로지 작성기를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="e097f-109">SQL 장애 조치(failover) 클러스터링의 경우 설정을 위해 SQL Server를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="e097f-110">재해 복구를 위해 다른 프런트 엔드 풀과 쌍을 이루는 풀에서 SQL 미러링 또는 SQL 클러스터링을 사용 하는 경우 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="e097f-111">Sql 미러를 사용 하 여 풀을 연결 하는 경우에만 SQL 클러스터링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="e097f-112">SQL 미러링을 배포 하는 경우 중앙 관리 저장소를 포함 하 여 해당 풀에 있는 모든 Lync Server 데이터베이스가 미러링 되며 응답 그룹 응용 프로그램 데이터베이스 및 통화 공원 응용 프로그램 데이터베이스 풀에서 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="e097f-113">SQL 미러링에서는 서버에 공유 저장소를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="e097f-114">각 서버는 로컬 저장소에 데이터베이스 복사본을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="e097f-115">미러링 모니터 서버와 함께 SQL 미러링을 배포 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="e097f-116">미러링 모니터 서버를 사용 하 여 백 엔드 서버의 장애 조치를 자동으로 수행할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="e097f-117">그렇지 않으면 관리자가 장애 조치를 수동으로 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="e097f-118">미러링 모니터 서버가 배포 된 경우에도 관리자는 필요한 경우 백 엔드 서버 장애 조치를 수동으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="e097f-119">미러링 모니터 서버를 사용 하는 경우 백 엔드 서버의 여러 쌍에 단일 미러링 모니터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-119">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="e097f-120">백 엔드 서버와 witnesses의 짝이 엄격한 1:1 대응 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-120">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="e097f-121">여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용 하는 배포는 각 백 엔드 서버 쌍에 대해 별도의 감시가 있는 토폴로지로 탄력적으로 복구 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-121">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="e097f-122">SQL 클러스터링 지원에 대 한 자세한 내용은 [Lync Server 2013의 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e097f-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="e097f-123">SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 Sql Server 클러스터링 구성을](lync-server-2013-configure-sql-server-clustering.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e097f-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="e097f-124">SQL 미러링으로 자동 백 엔드 서버 장애 조치 복구 시간</span><span class="sxs-lookup"><span data-stu-id="e097f-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="e097f-125">SQL 미러링의 자동 백 엔드 장애 조치의 경우, RTO (복구 시간 목표)에 대 한 엔지니어링 대상이 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="e097f-126">동기 SQL 미러링 때문에, 서버 간에 데이터를 이동 하는 동안 프런트 엔드 서버와 백 엔드 서버가 동시에 종료 되는 경우를 제외 하 고는 백 엔드 서버 오류 시 데이터 손실이 예상 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="e097f-127">RPO (복구 시점 목표)에 대 한 엔지니어링 대상은 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="e097f-128">SQL 미러링과 함께 백 엔드 서버 오류 발생 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="e097f-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="e097f-129">오류 발생 시 사용자 환경은 오류의 성격 및 토폴로지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="e097f-130">SQL 미러링을 사용 하 고 미러링 모니터 서버가 구성 되어 있는 경우 주 서버가 실패 하면 백 엔드 서버 장애 조치는 자동으로 신속 하 게 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="e097f-131">활성 사용자는 진행 중인 세션을 크게 중단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="e097f-132">미러링 모니터가 구성 되어 있지 않은 경우 관리자가 장애 조치를 수동으로 호출 하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="e097f-133">이 기간 동안에는 활성 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-133">During that time, active users may be affected.</span></span> <span data-ttu-id="e097f-134">약 30 분 동안에는 세션을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="e097f-135">기본 상태가 복원 되지 않거나 관리자가 백업으로 장애 조치 되지 않으면 사용자가 복원 모드로 전환 되어 Lync Server (예: 대화 상대 추가)에 영구적으로 변경 해야 하는 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="e097f-136">주 서버와 미러 백 엔드 서버가 둘 다 실패 하거나 이러한 서버와 미러링 모니터 서버가 실패 한 경우 백 엔드 서버를 사용할 수 없게 됩니다 (아직 작동 중인 주에 포함).</span><span class="sxs-lookup"><span data-stu-id="e097f-136">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="e097f-137">이 경우 활성 사용자는 잠시 후에 복원 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e097f-137">In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

