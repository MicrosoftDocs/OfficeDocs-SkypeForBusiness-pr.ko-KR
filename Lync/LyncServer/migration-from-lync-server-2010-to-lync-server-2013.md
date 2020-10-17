---
title: Lync Server 2010에서 Lync Server 2013로 마이그레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89bc70635ac941398a71515e77dd1a792973fc35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527305"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="dd80d-102">Lync Server 2010에서 Lync Server 2013로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dd80d-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd80d-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="dd80d-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="dd80d-104">이 섹션의 항목에서는 Lync Server 2010에서 Lync Server 2013로 마이그레이션하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd80d-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dd80d-p101">이 문서에서는 각 마이그레이션 단계를 수행하는 데 일반적으로 필요한 단계에 대해 설명합니다. 모든 가능한 레거시 배포 토폴로지 또는 모든 가능한 마이그레이션 시나리오는 여기에서 다루지 않습니다. 따라서 배포에 따라 설명된 모든 단계를 수행할 필요가 없거나 추가 단계를 수행해야 할 수도 있습니다. 이 문서에서는 또한 확인 단계에 대한 예를 제공합니다. 이러한 확인 단계는 마이그레이션을 진행하면서 각 단계가 성공적으로 완료되었는지 완료되었는지 확인하기 위해 검토할 사항에 대한 이해를 돕기 위해 제공됩니다. 이러한 확인 단계를 사용자의 마이그레이션 프로세스에 맞게 조정하십시오.</span><span class="sxs-lookup"><span data-stu-id="dd80d-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="dd80d-p102">이 설명서에서는 기존 배포 업그레이드와 관련된 정보를 제공하며 기존 토폴로지를 변경하는 방법이나 새 기능 구현은 다루지 않습니다. 단, 자세한 절차가 다른 문서에 설명되어 있는 경우 해당 문서 또는 문서 섹션으로 사용자를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="dd80d-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="dd80d-115">이 문서에서는 다음 목록에 지정된 용어를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dd80d-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="dd80d-116">*마이그레이션하기*</span><span class="sxs-lookup"><span data-stu-id="dd80d-116">*migration*</span></span>  
    <span data-ttu-id="dd80d-117">프로덕션 배포를 이전 버전의 Lync Server 2010에서 Lync Server 2013로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="dd80d-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="dd80d-118">*업그레이드*</span><span class="sxs-lookup"><span data-stu-id="dd80d-118">*upgrade*</span></span>  
    <span data-ttu-id="dd80d-119">서버 또는 클라이언트 컴퓨터에 새 버전의 소프트웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dd80d-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="dd80d-120">*동시*</span><span class="sxs-lookup"><span data-stu-id="dd80d-120">*coexistence*</span></span>  
    <span data-ttu-id="dd80d-121">마이그레이션 중에 발생 하는 일시적인 환경으로, 일부 기능이 Lync Server 2013로 마이그레이션 되었지만 다른 기능은 이전 버전의 Lync Server 2010에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd80d-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="dd80d-122">*가능*</span><span class="sxs-lookup"><span data-stu-id="dd80d-122">*interoperability*</span></span>  
    <span data-ttu-id="dd80d-123">동시 사용 기간 중 배포를 성공적으로 운영할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="dd80d-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd80d-124">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="dd80d-124">In This Section</span></span>

  - [<span data-ttu-id="dd80d-125">마이그레이션을 시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="dd80d-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="dd80d-126">1 단계: Lync Server 2010에서 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="dd80d-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="dd80d-127">2단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="dd80d-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="dd80d-128">3 단계: Lync Server 2013 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="dd80d-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="dd80d-129">4 단계: 테스트 사용자를 파일럿 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="dd80d-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="dd80d-130">단계 5: Lync Server 2013에 지 서버를 파일럿 풀에 추가</span><span class="sxs-lookup"><span data-stu-id="dd80d-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="dd80d-131">6단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="dd80d-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="dd80d-132">7단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="dd80d-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="dd80d-133">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="dd80d-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

