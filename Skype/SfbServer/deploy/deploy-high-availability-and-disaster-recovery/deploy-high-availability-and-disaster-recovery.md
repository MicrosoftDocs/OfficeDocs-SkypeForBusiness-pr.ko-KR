---
title: 고가용성 및 재해 복구 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 비즈니스용 Skype 서버는 서버 풀링을 사용 하 여 높은 가용성을 제공 하 고, 풀 페어링을 사용한 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 한 백 엔드 서버의 높은 가용성 모드 중 몇 가지입니다.
ms.openlocfilehash: 7997f71fb1f45801436caa50c4d6b258cc1b843b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197730"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="87c4b-103">고가용성 및 재해 복구 배포</span><span class="sxs-lookup"><span data-stu-id="87c4b-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="87c4b-104">비즈니스용 Skype 서버는 서버 풀링을 사용 하 여 높은 가용성을 제공 하 고, 풀 페어링을 사용한 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 한 백 엔드 서버의 높은 가용성 모드 중 몇 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="87c4b-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="87c4b-105">고가용성은 하나 이상의 서버가 작동 하지 않는 경우에도 비즈니스용 Skype 서버 서비스를 사용할 수 있는지 확인 하는 것을 의미 합니다. 재해 복구는 서비스를 자연 스런 실수 또는 사람이 실수로 발생 한 경우를 유지 하 고 재해가 발생할 때까지 최대한 많은 데이터를 유지 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="87c4b-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="87c4b-106">이 섹션에서는 이러한 기능을 배포 하는 방법에 대해 설명 하 고, 다른 일부 서버 역할에 대 한 가용성 및 재해 복구를 위해 수행할 수 있는 단계에 대해서도 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="87c4b-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="87c4b-107">SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87c4b-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="87c4b-108">AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87c4b-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="87c4b-109">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="87c4b-109">Related sections</span></span>

[<span data-ttu-id="87c4b-110">비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="87c4b-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="87c4b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87c4b-111">See also</span></span>

[<span data-ttu-id="87c4b-112">비즈니스용 Skype 서버에서 백 엔드 서버에 AlwaysOn 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="87c4b-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="87c4b-113">비즈니스용 Skype 서버에서 재해 복구용으로 쌍을 이루는 프런트 엔드 풀 배포</span><span class="sxs-lookup"><span data-stu-id="87c4b-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="87c4b-114">비즈니스용 Skype 서버 2015에서 백 엔드 서버에 대 한 SQL 미러링 배포 높은 가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87c4b-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
