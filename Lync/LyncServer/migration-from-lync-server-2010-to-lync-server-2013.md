---
title: Lync Server 2010에서 Lync Server 2013으로 마이그레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="708a7-102">Lync Server 2010에서 Lync Server 2013으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="708a7-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="708a7-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="708a7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="708a7-104">이 섹션의 항목에서는 Lync Server 2010에서 Lync Server 2013로 마이그레이션하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="708a7-105">이 문서에서는 각 마이그레이션 단계를 수행 하는 데 일반적으로 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="708a7-106">모든 가능 레거시 배포 토폴로지 또는 모든 가능 마이그레이션 시나리오를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="708a7-107">따라서 설명 된 모든 단계를 수행 하거나 배포에 따라 추가 단계를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="708a7-108">이 문서에서는 확인 단계의 예제도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="708a7-109">이러한 확인 단계는 마이그레이션을 진행 하면서 각 단계가 성공적으로 완료 되도록 하기 위해 찾아야 할 사항을 파악 하는 데 도움이 되도록 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="708a7-110">이러한 확인 단계를 특정 마이그레이션 프로세스에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="708a7-111">이 가이드에서는 기존 배포를 업그레이드 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="708a7-112">기존 토폴로지를 변경 하는 방법은 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="708a7-113">이 가이드에서는 새로운 기능을 구현 하는 방법을 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="708a7-114">세부 절차를 다른 곳에서 문서화 하면이 가이드에서 해당 문서 또는 문서 섹션으로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="708a7-115">이 문서는 다음 목록에 명시 된 약관을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="708a7-116">*마이그레이션하기*</span><span class="sxs-lookup"><span data-stu-id="708a7-116">*migration*</span></span>  
    <span data-ttu-id="708a7-117">이전 버전의 Lync Server 2010에서 Lync Server 2013로 프로덕션 배포를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="708a7-118">*업그레이드*</span><span class="sxs-lookup"><span data-stu-id="708a7-118">*upgrade*</span></span>  
    <span data-ttu-id="708a7-119">서버나 클라이언트 컴퓨터에 최신 버전의 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="708a7-120">*공존 성*</span><span class="sxs-lookup"><span data-stu-id="708a7-120">*coexistence*</span></span>  
    <span data-ttu-id="708a7-121">일부 기능이 Lync Server 2013 및 기타 기능으로 마이그레이션될 때 마이그레이션 중에 존재 하는 임시 환경은 이전 버전의 Lync Server 2010에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="708a7-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="708a7-122">*운용할*</span><span class="sxs-lookup"><span data-stu-id="708a7-122">*interoperability*</span></span>  
    <span data-ttu-id="708a7-123">공존 기간 동안 성공적으로 작동 하는 배포 능력.</span><span class="sxs-lookup"><span data-stu-id="708a7-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="708a7-124">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="708a7-124">In This Section</span></span>

  - [<span data-ttu-id="708a7-125">마이그레이션을 시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="708a7-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="708a7-126">1 단계: Lync Server 2010에서 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="708a7-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="708a7-127">2단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="708a7-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="708a7-128">3 단계: Lync Server 2013 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="708a7-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="708a7-129">4 단계: 시험 운용 풀로 테스트 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="708a7-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="708a7-130">5 단계: 파일럿 풀에 Lync Server 2013 Edge 서버 추가</span><span class="sxs-lookup"><span data-stu-id="708a7-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="708a7-131">6단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="708a7-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="708a7-132">7단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="708a7-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="708a7-133">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="708a7-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

