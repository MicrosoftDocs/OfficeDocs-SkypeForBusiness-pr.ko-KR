---
title: 여러 사이트 및 풀 마이그레이션
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
description: 비즈니스용 Skype 서버 2019에서는 다중 사이트 및 다중 풀 배포를 지원 합니다. 여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스를 수행 하려면 다음 사항을 고려해 야 합니다.
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752660"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="6c13a-104">여러 사이트 및 풀 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="6c13a-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="6c13a-105">비즈니스용 Skype 서버 2019에서는 다중 사이트 및 다중 풀 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="6c13a-106">여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스를 수행 하려면 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="6c13a-107">비즈니스용 Skype 서버 2019 파일럿 풀을 배포한 후에는 비즈니스용 Skype 서버 2019 풀로 이동할 파일럿 사용자의 하위 집합을 정의 해야 하며, 사용자 기능의 유효성을 검사 하는 방법론을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="6c13a-108">예를 들어 파일럿 풀로 사용자를 이동한 후에는 사용자의 회의 정책이 비즈니스용 Skype 서버 2019으로 이동 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="6c13a-109">파일럿 풀에에 지 서버를 배포한 후에는 외부 사용자가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="6c13a-110">영구 채팅, SQL 미러링 및 XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않으며, 비즈니스용 Skype 서버 2019 기능으로는 사용할 수 없지만 이전에 레거시 환경에서 배포한 경우에는 공존 환경에서 계속 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="6c13a-111">이러한 기능을 계속 사용 하려면 특정 사용자가 레거시 풀을 유지 하는 동시 사용 환경을 계속 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="6c13a-112">페더레이션 경로의에 지 서버를 파일럿 비즈니스용 Skype 서버 2019에 지 서버로 전환 했으면 페더레이션 사용자가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="6c13a-113">모든 사용자와 사용자가 아닌 대화 상대 개체를 이동한 후에는 레거시 풀이 비어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="6c13a-114">레거시 풀이 비어 있는지 확인 한 후에는 해당 풀을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c13a-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="6c13a-115">레거시 풀 및 서버를 비활성화 하는 방법에 대 한 자세한 내용은 [Phase 8: 레거시 풀](phase-8-decommission-legacy-pools.md)해제를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6c13a-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

