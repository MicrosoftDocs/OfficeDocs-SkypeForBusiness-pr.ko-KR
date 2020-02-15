---
title: 'Lync Server 2013: Lync Server 백업 및 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d65d06ac9c72e776eee51b9b3dff6c6db3a59031
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="b81f2-102">Lync Server 2013 백업 및 복원</span><span class="sxs-lookup"><span data-stu-id="b81f2-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b81f2-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b81f2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b81f2-104">이 섹션에서는 Lync Server 2013 데이터를 백업 하 고 오류가 발생 한 경우이를 복원 하기 위한 모범 사례를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="b81f2-105">이러한 모범 사례는 다음과 같은 상황에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="b81f2-106">모든 유형의 전체 Lync Server 풀 (프런트 엔드 서버,에 지 서버, 중재 서버, 영구 채팅 서버 또는 디렉터) 또는 이러한 풀 중 하나의 개별 서버</span><span class="sxs-lookup"><span data-stu-id="b81f2-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="b81f2-107">중앙 관리 서버</span><span class="sxs-lookup"><span data-stu-id="b81f2-107">The Central Management Server</span></span>

  - <span data-ttu-id="b81f2-108">Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="b81f2-108">A Standard Edition server</span></span>

  - <span data-ttu-id="b81f2-109">Enterprise Edition 백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="b81f2-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="b81f2-110">파일 저장소</span><span class="sxs-lookup"><span data-stu-id="b81f2-110">A File Store</span></span>

  - <span data-ttu-id="b81f2-111">보관 데이터베이스, 모니터링 데이터베이스 또는 영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="b81f2-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="b81f2-112">이 섹션에는 전체 사이트를 복원 하거나 대기 사이트를 개발 하는 방법에 대 한 정보가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="b81f2-113">쌍으로 된 프런트 엔드 풀을 사용 하는 재해 복구 솔루션을 개발 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b81f2-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="b81f2-114">이 방법은 재해 복구를 계획 하는 데 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="b81f2-115">쌍으로 된 프런트 엔드 풀을 배포한 경우 이러한 풀 중 하나에 오류가 발생 하 여 복구할 수 없는 경우 쌍을 이룬 풀에서 새 FQDN (정규화 된 도메인 이름)으로 복원 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="b81f2-116">이 복구를 수행 하는 단계에 대 한 자세한 내용은 [Lync Server 2013에서 풀 장애 조치](lync-server-2013-failing-over-a-pool.md)(failover)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b81f2-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="b81f2-117">또한 나중에 프런트 엔드 쌍의 일부인 실패 및 복구할 수 없는 풀을 다시 만들려면 [Lync Server 2013에서 ABC 프런트 엔드 풀 장애 조치 (failover)를 수행](lync-server-2013-performing-an-abc-front-end-pool-failover.md)하는 단계를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="b81f2-118">이 문서에서 설명하는 방법에는 계획 단계 중의 특별한 고려 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b81f2-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="b81f2-119">자세한 내용은 [Lync Server 2013에 대 한 백업 및 복원 계획 수립](lync-server-2013-establishing-a-backup-and-restoration-plan.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b81f2-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b81f2-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b81f2-120">In This Section</span></span>

  - [<span data-ttu-id="b81f2-121">Lync Server 2013 백업 및 복원 준비</span><span class="sxs-lookup"><span data-stu-id="b81f2-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="b81f2-122">Lync Server 2013에서 데이터 및 설정 백업</span><span class="sxs-lookup"><span data-stu-id="b81f2-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="b81f2-123">Lync Server 2013에서 데이터 및 설정 복원</span><span class="sxs-lookup"><span data-stu-id="b81f2-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="b81f2-124">Lync Server 2013의 백업 및 복원 워크시트</span><span class="sxs-lookup"><span data-stu-id="b81f2-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

