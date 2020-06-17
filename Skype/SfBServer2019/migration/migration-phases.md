---
title: 마이그레이션 단계
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
description: 비즈니스용 Skype 서버 2019에서 비즈니스용 Skype 서버 2019 구성 요소를 포함 하는 네트워크의 사이트를 정의 합니다. 사이트는 단일 LAN(Local Area Network)이나 고속 광섬유 네트워크로 연결된 두 개의 네트워크와 같이 고속, 저지연 네트워크로 견고하게 연결된 컴퓨터 집합입니다.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752630"
---
# <a name="migration-phases"></a><span data-ttu-id="6f07a-104">마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="6f07a-104">Migration phases</span></span>

<span data-ttu-id="6f07a-105">비즈니스용 Skype 서버 2019에서 비즈니스용 Skype 서버 2019 구성 요소를 포함 하는 네트워크의 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="6f07a-106">사이트는 단일 LAN(Local Area Network)이나 고속 광섬유 네트워크로 연결된 두 개의 네트워크와 같이 고속, 저지연 네트워크로 견고하게 연결된 컴퓨터 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="6f07a-107">프런트 엔드 풀은 동일하게 구성된 프런트 엔드 서버 집합으로서, 이러한 서버가 함께 작동하여 일반 사용자 그룹에 대한 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="6f07a-108">풀은 사용자에게 확장성 및 장애 조치 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="6f07a-109">풀의 각 서버는 동일한 서버 역할을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="6f07a-110">소규모 조직을 위해 설계 된 Standard Edition 서버는 풀을 정의 하 고 단일 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="6f07a-111">이를 통해 비즈니스용 Skype 서버 2019 기능을 저렴 한 비용으로 사용할 수는 있지만, 진정한 고가용성 솔루션은 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="6f07a-112">다음 단계에서는 비즈니스용 Skype 서버 2019에 대 한 풀 마이그레이션 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="6f07a-113">여러 풀을 포함하는 다중 사이트의 경우 각각의 개별 풀에서 이러한 단계별 접근 방식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f07a-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="6f07a-114">1단계: 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="6f07a-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="6f07a-115">2단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="6f07a-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="6f07a-116">3 단계: 비즈니스용 Skype 서버 2019 파일럿 풀 배포</span><span class="sxs-lookup"><span data-stu-id="6f07a-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="6f07a-117">4 단계: 테스트 사용자를 파일럿 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="6f07a-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="6f07a-118">단계 5: 파일럿 풀에 비즈니스용 Skype 서버 2019에 지 서버 추가</span><span class="sxs-lookup"><span data-stu-id="6f07a-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="6f07a-119">6단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="6f07a-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="6f07a-120">7단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="6f07a-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="6f07a-121">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="6f07a-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

