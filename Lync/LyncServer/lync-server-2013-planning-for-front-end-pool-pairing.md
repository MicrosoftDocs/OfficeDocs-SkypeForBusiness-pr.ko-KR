---
title: 'Lync Server 2013: 프런트 엔드 풀 페어링 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225733c1b91677a622accb3a786f66c9657ae3e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="5b4db-102">Lync Server 2013의 프런트 엔드 풀 페어링 계획</span><span class="sxs-lookup"><span data-stu-id="5b4db-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b4db-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5b4db-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5b4db-104">Lync Server 2013의 모범 재해 복구 기능에 대해 지리적으로 분산 된 두 사이트에 프런트 엔드 풀 쌍을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="5b4db-105">각 사이트에는 다른 사이트의 해당 프런트 엔드 풀과 쌍을 이루는 프런트 엔드 풀이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="5b4db-106">두 사이트가 모두 활성 상태이 고 Lync Server Backup Service에서 풀을 동기화 된 상태로 유지 하기 위한 실시간 데이터 복제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="5b4db-107">백업 서비스는 재해 복구 솔루션을 지원 하기 위해 설계 된 Lync Server 2013의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="5b4db-108">풀을 다른 프런트 엔드 풀과 연결 하면 프런트 엔드 풀에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="5b4db-109">한 사이트의 풀에 오류가 발생 하면 해당 풀의 사용자를 다른 사이트의 풀로 장애 조치 (failover) 하 여 두 풀의 모든 사용자에 게 서비스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="5b4db-110">용량 계획을 위해 각 풀은 재해가 발생 한 경우 두 풀에 있는 모든 사용자의 작업 부하를 처리 하도록 설계 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b4db-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b4db-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5b4db-111">In This Section</span></span>

  - [<span data-ttu-id="5b4db-112">Lync Server 2013에 대 한 지원 되는 풀 페어링 옵션 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="5b4db-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="5b4db-113">Lync Server 2013의 등록자 간 관계 백업</span><span class="sxs-lookup"><span data-stu-id="5b4db-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="5b4db-114">Lync Server 2013의 풀 장애 조치 (failover) 및 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="5b4db-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="5b4db-115">Lync Server 2013의 중앙 관리 저장소 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="5b4db-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="5b4db-116">Lync Server 2013의 프런트 엔드 풀 연결 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="5b4db-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

