---
title: 고가용성 및 재해 복구 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 비즈니스용 Skype 서버는 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830618"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="788a2-103">고가용성 및 재해 복구 배포</span><span class="sxs-lookup"><span data-stu-id="788a2-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="788a2-104">비즈니스용 Skype 서버는 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="788a2-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="788a2-105">고가용성이란 하나 이상의 서버가 다운된 경우에도 비즈니스용 Skype 서버 서비스를 사용할 수 있도록 하는 것입니다. 재해 복구란 자연적 또는 사람이 유발한 재해가 발생할 경우 서비스를 계속 유지하며 재해 이전의 데이터를 최대한 보존하는 것을 지어보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="788a2-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="788a2-106">이 섹션에서는 이러한 기능을 배포하는 방법과 다른 서버 역할 중 일부에 대해 고가용성 및 재해 복구를 위해 취할 수 있는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="788a2-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="788a2-107">SQL 미러링은 비즈니스용 Skype 서버에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="788a2-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="788a2-108">AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="788a2-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="788a2-109">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="788a2-109">Related sections</span></span>

[<span data-ttu-id="788a2-110">비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="788a2-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="788a2-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="788a2-111">See also</span></span>

[<span data-ttu-id="788a2-112">비즈니스용 Skype 서버에서 백 엔드 서버에 AlwaysOn 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="788a2-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="788a2-113">비즈니스용 Skype 서버에서 재해 복구를 위해 페어링된 프런트 엔드 풀 배포</span><span class="sxs-lookup"><span data-stu-id="788a2-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="788a2-114">비즈니스용 Skype SQL 백 엔드 서버 고가용성을 위한 미러링 배포</span><span class="sxs-lookup"><span data-stu-id="788a2-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
