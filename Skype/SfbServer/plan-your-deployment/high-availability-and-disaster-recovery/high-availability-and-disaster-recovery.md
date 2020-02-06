---
title: 비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 비즈니스용 Skype 서버는 서버 풀링을 사용 하 여 높은 가용성을 제공 하 고, 풀 페어링을 사용한 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 한 백 엔드 서버의 높은 가용성 모드 중 몇 가지입니다.
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815926"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="8100a-103">비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="8100a-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="8100a-104">비즈니스용 Skype 서버는 서버 풀링을 사용 하 여 높은 가용성을 제공 하 고, 풀 페어링을 사용한 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 한 백 엔드 서버의 높은 가용성 모드 중 몇 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="8100a-105">고가용성은 하나 이상의 서버가 작동 하지 않는 경우에도 비즈니스용 Skype 서버 서비스를 사용할 수 있는지 확인 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="8100a-106">재해 복구는 서비스를 자연 스런 실수 또는 사람이 실수로 발생 한 경우를 유지 하 고 재해가 발생할 때까지 최대한 많은 데이터를 유지 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="8100a-107">이전 버전의 Lync Server에서와 마찬가지로 비즈니스용 Skype 서버에서 대부분의 서버 역할에 대 한 기본 고가용성 기능은 풀링을 통해 서버 중복성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="8100a-108">특정 서버 역할을 실행 하는 서버에 오류가 발생 하는 경우 동일한 역할을 실행 하는 풀의 다른 서버에서 해당 서버의 로드를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="8100a-109">이는 프런트 엔드 서버, Edge 서버, 중재 서버 및 디렉터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="8100a-110">비즈니스용 Skype 서버는 또한 프런트 엔드 풀에 대 한 재난 복구 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="8100a-111">각기 다른 지리적 영역에 두 개의 풀을 설정 하 여 서로에 대 한 백업 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="8100a-112">그런 다음 전체 풀 또는 사이트를 사용 하는 경우 백업 풀은 두 사이트의 사용자에 게 서비스를 계속 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="8100a-113">또한 비즈니스용 Skype 서버는 백 엔드 서버에 대 한 높은 수준의 가용성 (SQL 미러링, AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 클러스터링의 4 가지 모드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8100a-114">SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8100a-115">AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="8100a-116">AlwaysOn 가용성 그룹은 영구 채팅 서버에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="8100a-117">이 섹션에서는 이러한 기능에 대해 설명 하 고, 다른 일부 서버 역할에 대 한 가용성 및 재해 복구를 위해 수행할 수 있는 단계에 대해서도 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8100a-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8100a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8100a-118">See also</span></span>

[<span data-ttu-id="8100a-119">프런트 엔드 풀 고가용성 및 관리</span><span class="sxs-lookup"><span data-stu-id="8100a-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="8100a-120">비즈니스용 Skype 서버의 프론트 엔드 풀 재해 복구</span><span class="sxs-lookup"><span data-stu-id="8100a-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="8100a-121">비즈니스용 Skype 서버에서 풀이 실패 하는 경우의 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="8100a-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="8100a-122">비즈니스용 Skype 서버의 백 엔드 서버 고가용성</span><span class="sxs-lookup"><span data-stu-id="8100a-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="8100a-123">비즈니스용 Skype 서버에서 파일 공유 고가용성</span><span class="sxs-lookup"><span data-stu-id="8100a-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
