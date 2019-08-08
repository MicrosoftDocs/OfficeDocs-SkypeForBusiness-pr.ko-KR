---
title: 마이그레이션 단계
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019에서 비즈니스용 Skype Server 2019 구성 요소를 포함 하는 네트워크 사이트를 정의 합니다. 사이트는 단일 LAN 또는 고속 광섬유 네트워크로 연결 된 두 대의 네트워크와 같이 고속의 짧은 대기 네트워크로 연결 되는 컴퓨터 집합입니다..
ms.openlocfilehash: 1ad93a512a1aab596e08744f76d74e2e41a9faa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238141"
---
# <a name="migration-phases"></a><span data-ttu-id="a935c-104">마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="a935c-104">Migration phases</span></span>

<span data-ttu-id="a935c-105">비즈니스용 Skype 서버 2019에서 비즈니스용 Skype Server 2019 구성 요소를 포함 하는 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="a935c-106">사이트는 단일 LAN 또는 고속 광섬유 네트워크로 연결 된 두 대의 네트워크와 같이 고속의 짧은 대기 네트워크로 연결 되는 컴퓨터 집합입니다..</span><span class="sxs-lookup"><span data-stu-id="a935c-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="a935c-107">프런트 엔드 풀은 동일 하 게 구성 된 프런트 엔드 서버 집합으로, 공통 사용자 그룹에 대 한 서비스를 제공 하기 위해 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="a935c-108">풀은 사용자에 게 확장성 및 장애 조치 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="a935c-109">풀의 각 서버는 동일한 서버 역할 또는 역할을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="a935c-110">소규모 조직을 위해 디자인 된 스탠더드 버전 서버는 풀을 정의 하 고 단일 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="a935c-111">이렇게 하면 저렴 한 비용으로 비즈니스용 Skype 서버 2019 기능을 사용할 수 있지만, 진정한 고가용성 솔루션은 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="a935c-112">다음 단계에서는 비즈니스용 Skype Server 2019에 대 한 풀 마이그레이션 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="a935c-113">여러 개의 풀을 포함 하는 여러 사이트의 경우 각 풀이이 단계별 방법을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a935c-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="a935c-114">1 단계: 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="a935c-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="a935c-115">2 단계: 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="a935c-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="a935c-116">3 단계: 비즈니스용 Skype 서버 배포 2019 파일럿 풀</span><span class="sxs-lookup"><span data-stu-id="a935c-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="a935c-117">4 단계: 시험 운용 풀로 테스트 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="a935c-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="a935c-118">5 단계: 파일럿 풀에 비즈니스용 Skype 서버 2019 Edge 서버 추가</span><span class="sxs-lookup"><span data-stu-id="a935c-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="a935c-119">6 단계: 파일럿 배포에서 프로덕션으로 이동</span><span class="sxs-lookup"><span data-stu-id="a935c-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="a935c-120">7 단계: 마이그레이션 후 작업 완료</span><span class="sxs-lookup"><span data-stu-id="a935c-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="a935c-121">8 단계: 레거시 풀 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="a935c-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

