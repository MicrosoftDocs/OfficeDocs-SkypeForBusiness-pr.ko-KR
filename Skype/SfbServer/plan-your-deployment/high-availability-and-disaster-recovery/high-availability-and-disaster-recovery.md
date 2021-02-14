---
title: 비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버는 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802818"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="92f40-103">비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="92f40-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="92f40-104">비즈니스용 Skype 서버는 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="92f40-105">고가용성이란 하나 이상의 서버가 다운된 경우에도 비즈니스용 Skype 서버 서비스를 사용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="92f40-106">재해 복구란 자연적 또는 사람이 유발한 재해가 발생할 경우 서비스를 계속 유지하며 재해 이전의 데이터를 최대한 보존하는 것을 지어보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="92f40-107">이전 버전의 Lync Server와 동일하게 비즈니스용 Skype 서버의 대부분의 서버 역할에 대한 주요 고가용성 기능은 풀링을 통한 서버 중복입니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="92f40-108">특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="92f40-109">이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="92f40-110">비즈니스용 Skype 서버는 프런트 엔드 풀에 대한 재해 복구 옵션도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="92f40-111">서로 다른 지역에 백업으로 사용할 두 개의 풀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="92f40-112">그런 다음 전체 풀 또는 사이트가 다운된 경우 백업 풀은 두 사이트의 사용자에게 서비스를 계속 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="92f40-113">비즈니스용 Skype 서버는 백 엔드 서버에 대해 SQL 미러링, AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(Failover) 클러스터 인스턴스) 및 장애 조치(failover) 클러스터링의 SQL 모드도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="92f40-114">SQL 미러링은 비즈니스용 Skype 서버에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="92f40-115">AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="92f40-116">AlwaysOn 가용성 그룹은 영구 채팅 서버에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="92f40-117">이 섹션에서는 이러한 기능에 대해 설명하고 다른 서버 역할 중 일부에 대해 고가용성 및 재해 복구에 대해 취할 수 있는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92f40-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="92f40-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92f40-118">See also</span></span>

[<span data-ttu-id="92f40-119">프런트 엔드 풀 고가용성 및 관리</span><span class="sxs-lookup"><span data-stu-id="92f40-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="92f40-120">비즈니스용 Skype 서버의 프런트 엔드 풀 재해 복구</span><span class="sxs-lookup"><span data-stu-id="92f40-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="92f40-121">비즈니스용 Skype 서버에서 풀 오류 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="92f40-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="92f40-122">비즈니스용 Skype 서버의 백 엔드 서버 고가용성</span><span class="sxs-lookup"><span data-stu-id="92f40-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="92f40-123">비즈니스용 Skype 서버에서 파일 공유 고가용성</span><span class="sxs-lookup"><span data-stu-id="92f40-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
