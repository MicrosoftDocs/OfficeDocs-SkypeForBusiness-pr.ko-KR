---
title: 여러 사이트 및 풀 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019는 다중 사이트 및 다중 풀 배포를 지원 합니다. 여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스에는 다음 고려 사항이 필요 합니다.
ms.openlocfilehash: 05a94cb47568b9dfc3834f65f960353ad2933b03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196955"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="4804a-104">여러 사이트 및 풀 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4804a-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="4804a-105">비즈니스용 Skype 서버 2019는 다중 사이트 및 다중 풀 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="4804a-106">여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스에는 다음 고려 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="4804a-107">비즈니스용 Skype Server 2019 파일럿 풀을 배포한 후에는 비즈니스용 Skype Server 2019 풀로 이동할 파일럿 사용자의 하위 집합을 정의 하 고 사용자의 기능을 확인 하기 위한 방법론으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="4804a-108">예를 들어 파일럿 풀로 사용자를 이동한 후에는 사용자의 컨퍼런스 정책이 비즈니스용 Skype 서버 2019로 이동 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="4804a-109">파일럿 풀에 Edge 서버를 배포한 후에는 외부 사용자가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="4804a-110">영구 채팅, SQL 미러링 및 XMPP 기능은 비즈니스용 Skype 서버 2019에서 사용 되지 않으며, 더 이상 비즈니스용 Skype Server 2019 기능으로 사용할 수 없지만, 이전에 배포 된 경우에는 공존 환경에서 계속 가능 합니다. 레거시 환경.</span><span class="sxs-lookup"><span data-stu-id="4804a-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="4804a-111">이러한 기능을 계속 사용 하려면 특정 사용자가 레거시 풀에 유지 되는 공존 환경에서 계속 진행할 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="4804a-112">페더레이션된 경로의 Edge 서버를 파일럿 비즈니스용 Skype 서버 2019 Edge 서버로 전환 하 고 나면 페더레이션 사용자가 비즈니스용 Skype Server 2019 풀과 통신할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="4804a-113">모든 사용자 및 사용자가 아닌 연락처 개체를 이동한 후에는 레거시 풀이 비어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="4804a-114">레거시 풀이 비어 있는지 확인 한 후에 풀을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4804a-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="4804a-115">레거시 풀 및 서버를 비활성화 하는 방법에 대 한 자세한 내용은 [8 단계: 레거시 풀 서비스](phase-8-decommission-legacy-pools.md)해제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4804a-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

