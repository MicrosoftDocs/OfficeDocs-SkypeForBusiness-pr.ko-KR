---
title: 비즈니스용 Skype 서버 2019 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 섹션의 항목에서는 비즈니스용 Skype Server 2019로 마이그레이션하는 과정을 안내 합니다.
ms.openlocfilehash: 8e58eaa3870e8149e874a1ec196a728976f429f3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238088"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="33016-103">비즈니스용 Skype 서버 2019 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="33016-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="33016-104">이 섹션의 항목에서는 비즈니스용 Skype Server 2019로 마이그레이션하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="33016-105">이 문서에서는 Lync Server 2013 또는 비즈니스용 Skype Server 2015을 비즈니스용 Skype 서버 2019로 마이그레이션하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33016-106">모든 콘텐츠를 통해 *레거시* Lync server 2013 또는 비즈니스용 skype server 2015을 비즈니스용 skype server 2019로 마이그레이션하는 것을 참조 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="33016-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33016-107">이 가이드에서는 각 마이그레이션 단계를 수행 하는 데 일반적으로 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="33016-108">모든 가능 레거시 배포 토폴로지 또는 모든 가능 마이그레이션 시나리오를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33016-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="33016-109">따라서 설명 된 모든 단계를 수행 하거나 배포에 따라 추가 단계를 수행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33016-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="33016-110">이 가이드에서는 확인 단계의 예제도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="33016-111">이러한 확인 단계는 마이그레이션을 진행 하면서 각 단계가 성공적으로 완료 되도록 하기 위해 찾아야 할 사항을 파악 하는 데 도움이 되도록 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33016-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="33016-112">이러한 확인 단계를 특정 마이그레이션 프로세스에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33016-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="33016-113">이 가이드에서는 기존 배포를 업그레이드 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="33016-114">기존 토폴로지를 변경 하는 방법은 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33016-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="33016-115">이 가이드에서는 새로운 기능을 구현 하는 방법을 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33016-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="33016-116">세부 절차를 다른 곳에서 문서화 한 경우이 가이드는 문서 또는 문서 섹션으로 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="33016-117">이 문서에서는 다음 목록에 명시 된 약관을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="33016-118">**마이그레이션:** Lync Server 2013 또는 비즈니스용 Skype Server 2015에서 비즈니스용 skype server 2019으로 프로덕션 배포를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="33016-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="33016-119">**공존 방법:** 일부 기능을 비즈니스용 Skype 서버 2019으로 마이그레이션 하 고 다른 기능을 이전 버전에 그대로 유지할 때 마이그레이션하는 동안 존재 하는 임시 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="33016-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="33016-120">**상호 운용성:** 공존 기간 동안 성공적으로 작동 하는 배포 능력.</span><span class="sxs-lookup"><span data-stu-id="33016-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="33016-121">**레거시:** 마이그레이션할 시스템 (Lync Server 2013 또는 비즈니스용 Skype Server 2015)입니다.</span><span class="sxs-lookup"><span data-stu-id="33016-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="33016-122">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="33016-122">In this section</span></span>

- [<span data-ttu-id="33016-123">마이그레이션을 시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="33016-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="33016-124">1 단계: 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="33016-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="33016-125">2 단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="33016-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="33016-126">3 단계: 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="33016-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="33016-127">4 단계: 시험 운용 풀로 테스트 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="33016-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="33016-128">5 단계: 파일럿 풀에 Edge 서버 추가</span><span class="sxs-lookup"><span data-stu-id="33016-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="33016-129">6 단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="33016-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="33016-130">7 단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="33016-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="33016-131">8 단계: 레거시 풀 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="33016-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

