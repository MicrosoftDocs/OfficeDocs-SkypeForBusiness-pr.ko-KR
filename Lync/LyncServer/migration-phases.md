---
title: 마이그레이션 단계
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa7226a442d8e41d4ab0e6e3511a35e020decb65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="6c910-102">마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="6c910-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c910-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="6c910-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="6c910-104">Lync Server 2013에서 Lync Server 2013 구성 요소를 포함 하는 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="6c910-105">사이트는 단일 LAN 또는 고속 광섬유 네트워크로 연결 된 두 대의 네트워크와 같이 고속의 짧은 대기 네트워크로 연결 되는 컴퓨터 집합입니다..</span><span class="sxs-lookup"><span data-stu-id="6c910-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="6c910-106">*프런트 엔드 풀* 은 동일 하 게 구성 된 프런트 엔드 서버 집합으로, 공통 사용자 그룹에 대 한 서비스를 제공 하기 위해 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="6c910-107">풀은 사용자에 게 확장성 및 장애 조치 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="6c910-108">풀의 각 서버는 동일한 서버 역할 또는 역할을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="6c910-109">소규모 조직을 위해 디자인 된 스탠더드 버전 서버는 풀을 정의 하 고 단일 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="6c910-110">이렇게 하면 저렴 한 비용으로 Lync Server 2013 기능을 사용할 수 있지만, 진정한 고가용성 솔루션은 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="6c910-111">다음 단계는 Lync Server 2010에서 Lync Server 2013로의 풀 마이그레이션 프로세스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="6c910-112">여러 개의 풀을 포함 하는 여러 사이트의 경우 각 풀이이 단계별 방법을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c910-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="6c910-113">1 단계: Lync Server 2010에서 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="6c910-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="6c910-114">2단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="6c910-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="6c910-115">3 단계: Lync Server 2013 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="6c910-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="6c910-116">4 단계: 시험 운용 풀로 테스트 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="6c910-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="6c910-117">5 단계: 파일럿 풀에 Lync Server 2013 Edge 서버 추가</span><span class="sxs-lookup"><span data-stu-id="6c910-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="6c910-118">6단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="6c910-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="6c910-119">7단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="6c910-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="6c910-120">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="6c910-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

