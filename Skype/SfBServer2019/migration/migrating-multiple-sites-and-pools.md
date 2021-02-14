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
description: 비즈니스용 Skype 서버 2019는 다중 사이트 및 다중 풀 배포를 지원합니다. 여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스에서는 다음과 같은 사항을 고려해야 합니다.
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752660"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="f48c1-104">여러 사이트 및 풀 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f48c1-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="f48c1-105">비즈니스용 Skype 서버 2019는 다중 사이트 및 다중 풀 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="f48c1-106">여러 풀을 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스에서는 다음과 같은 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="f48c1-107">비즈니스용 Skype 서버 2019 파일럿 풀을 배포한 후 비즈니스용 Skype 서버 2019 풀로 이동할 파일럿 사용자의 하위 집합과 사용자의 기능 유효성을 검사하기 위한 방법을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="f48c1-108">예를 들어 사용자를 파일럿 풀로 이동한 후 사용자의 전화 회의 정책이 비즈니스용 Skype 서버 2019로 이동된지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="f48c1-109">파일럿 풀에 에지 서버를 배포한 후 외부 사용자가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="f48c1-110">영구 채팅, SQL 미러링 및 XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않지만 이전에 레거시 환경에 배포된 경우 공존 환경에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="f48c1-111">이러한 기능을 계속 사용하려는 경우 특정 사용자가 레거시 풀에 남아 있는 공존 환경을 계속 사용하려는 경우</span><span class="sxs-lookup"><span data-stu-id="f48c1-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="f48c1-112">페더링 경로의 에지 서버를 파일럿 비즈니스용 Skype 서버 2019 에지 서버로 전환한 후 페더링된 사용자가 비즈니스용 Skype 서버 2019 풀과 통신할 수 있는지 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="f48c1-113">모든 사용자 및 비사용자 연락처 개체를 이동한 후 레거시 풀이 비어있는지 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="f48c1-114">레거시 풀이 비어 있는지 확인한 후 풀을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="f48c1-115">레거시 풀 및 서버를 비활성화하는 방법에 대한 자세한 내용은 [8단계:](phase-8-decommission-legacy-pools.md)레거시 풀 해제를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f48c1-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

