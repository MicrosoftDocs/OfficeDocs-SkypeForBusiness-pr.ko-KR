---
title: Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624891658fb925fbc2522e98f8b216e535d2bf0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="2817e-102">Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2817e-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2817e-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2817e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2817e-104">이 섹션의 항목에서는 Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="2817e-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2817e-p101">이 문서에서는 각 마이그레이션 단계를 수행하는 데 일반적으로 필요한 단계에 대해 설명합니다. 모든 가능한 레거시 배포 토폴로지 또는 모든 가능한 마이그레이션 시나리오는 여기에서 다루지 않습니다. 따라서 배포에 따라 설명된 모든 단계를 수행할 필요가 없거나 추가 단계를 수행해야 할 수도 있습니다. 이 문서에서는 또한 확인 단계에 대한 예를 제공합니다. 이러한 확인 단계는 마이그레이션을 진행하면서 각 단계가 성공적으로 완료되었는지 완료되었는지 확인하기 위해 검토할 사항에 대한 이해를 돕기 위해 제공됩니다. 이러한 확인 단계를 사용자의 마이그레이션 프로세스에 맞게 조정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2817e-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="2817e-p102">이 설명서에서는 기존 배포 업그레이드와 관련된 정보를 제공하며 기존 토폴로지를 변경하는 방법이나 새 기능 구현은 다루지 않습니다. 단, 자세한 절차가 다른 문서에 설명되어 있는 경우 해당 문서 또는 문서 섹션으로 사용자를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="2817e-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="2817e-115">이 문서에서는 다음 목록에 지정된 용어를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2817e-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="2817e-116">*마이그레이션하기*</span><span class="sxs-lookup"><span data-stu-id="2817e-116">*migration*</span></span>  
    <span data-ttu-id="2817e-117">프로덕션 배포를 이전 버전의 Office Communications Server 2007 R2에서 Lync Server 2013로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="2817e-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="2817e-118">*업그레이드*</span><span class="sxs-lookup"><span data-stu-id="2817e-118">*upgrade*</span></span>  
    <span data-ttu-id="2817e-119">서버 또는 클라이언트 컴퓨터에 새 버전의 소프트웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2817e-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="2817e-120">*동시*</span><span class="sxs-lookup"><span data-stu-id="2817e-120">*coexistence*</span></span>  
    <span data-ttu-id="2817e-121">마이그레이션 중에 발생 하는 일시적인 환경으로, 일부 기능이 Lync Server 2013로 마이그레이션 되었지만 기타 기능은 이전 버전의 Office Communications Server 2007 r 2에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2817e-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="2817e-122">*가능*</span><span class="sxs-lookup"><span data-stu-id="2817e-122">*interoperability*</span></span>  
    <span data-ttu-id="2817e-123">동시 사용 기간 중 배포를 성공적으로 운영할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2817e-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2817e-124">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2817e-124">In This Section</span></span>

  - [<span data-ttu-id="2817e-125">마이그레이션을 시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="2817e-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="2817e-126">Migration phases</span><span class="sxs-lookup"><span data-stu-id="2817e-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="2817e-127">1 단계: Office Communications Server 2007 r 2에서 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="2817e-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="2817e-128">2 단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="2817e-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="2817e-129">3 단계: Lync Server 2013 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="2817e-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="2817e-130">4 단계: 토폴로지 병합</span><span class="sxs-lookup"><span data-stu-id="2817e-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="2817e-131">단계 5: 파일럿 풀 구성</span><span class="sxs-lookup"><span data-stu-id="2817e-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="2817e-132">단계 6: 사용자를 파일럿 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="2817e-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="2817e-133">단계 7: 파일럿 풀에 Lync Server 2013에 지 서버 추가</span><span class="sxs-lookup"><span data-stu-id="2817e-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="2817e-134">8 단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="2817e-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="2817e-135">단계 9: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="2817e-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="2817e-136">단계 10: 레거시 사이트 해제</span><span class="sxs-lookup"><span data-stu-id="2817e-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

