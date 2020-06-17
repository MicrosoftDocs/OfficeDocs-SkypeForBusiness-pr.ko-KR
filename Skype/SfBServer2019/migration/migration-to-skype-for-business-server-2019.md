---
title: 비즈니스용 Skype 서버 2019로 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 섹션의 항목에서는 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스를 안내 합니다.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752620"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="3cbfe-103">비즈니스용 Skype 서버 2019로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3cbfe-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="3cbfe-104">이 섹션의 항목에서는 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="3cbfe-105">이 문서에서는 Lync Server 2013 또는 비즈니스용 Skype 서버 2015를 비즈니스용 Skype 서버 2019로 마이그레이션하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cbfe-106">모든 콘텐츠를 사용 하 여 *레거시* Lync server 2013 또는 비즈니스용 skype 서버 2015 2019로 마이그레이션하려는 Skype (비즈니스에 대 한)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3cbfe-107">이 가이드에서는 마이그레이션의 각 단계를 수행 하는 데 일반적으로 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="3cbfe-108">모든 가능한 레거시 배포 토폴로지 또는 모든 가능한 마이그레이션 시나리오에 대해서는 여기에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="3cbfe-109">따라서 배포에 따라 설명된 모든 단계를 수행할 필요가 없거나 추가 단계를 수행해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="3cbfe-110">이 가이드에서는 확인 단계의 예제도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="3cbfe-111">이러한 확인 단계는 마이그레이션을 진행하면서 각 단계가 성공적으로 완료되었는지 보장하기 위해 조사해야 하는 항목을 확인할 수 있도록 돕기 위해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="3cbfe-112">이러한 확인 단계를 사용자의 마이그레이션 프로세스에 맞게 조정하십시오.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="3cbfe-113">이 설명서에서는 기존 배포를 업그레이드하는 것과 관련된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="3cbfe-114">기존 토폴로지를 변경하는 방법에 대해서는 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="3cbfe-115">또한 새 기능 구현에 대해서도 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="3cbfe-116">자세한 절차를 다른 곳에서 문서화 하면이 가이드에서 문서 또는 기사 섹션으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="3cbfe-117">이 문서에서는 다음 목록에 지정 된 용어를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="3cbfe-118">**마이그레이션:** 프로덕션 배포를 Lync Server 2013 또는 비즈니스용 Skype 서버 2015에서 비즈니스용 Skype 서버 2019로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="3cbfe-119">**동시 사용:** 마이그레이션 중에 발생 하는 일시적인 환경으로, 일부 기능이 비즈니스용 Skype 서버 2019로 마이그레이션 되었지만 다른 기능은 이전 버전에 유지 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="3cbfe-120">**상호 운용성:** 동시 사용 기간 중 배포를 성공적으로 운영할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="3cbfe-121">**레거시:** 마이그레이션하려는 시스템 (Lync Server 2013 또는 비즈니스용 Skype 서버 2015)입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbfe-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="3cbfe-122">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3cbfe-122">In this section</span></span>

- [<span data-ttu-id="3cbfe-123">마이그레이션을 시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="3cbfe-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="3cbfe-124">1단계: 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="3cbfe-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="3cbfe-125">2단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="3cbfe-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="3cbfe-126">3단계: 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="3cbfe-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="3cbfe-127">4 단계: 테스트 사용자를 파일럿 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="3cbfe-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="3cbfe-128">5단계: 파일럿 풀에 Edge 서버 추가</span><span class="sxs-lookup"><span data-stu-id="3cbfe-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="3cbfe-129">6단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="3cbfe-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="3cbfe-130">7단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="3cbfe-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="3cbfe-131">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="3cbfe-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

