---
title: 비즈니스용 Skype Server 2015의 영구 채팅 서버에 대 한 고가용성 및 재해 복구 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: '요약: 비즈니스용 Skype Server 2015에서 영구 채팅 서버의 가용성 및 재해 복구를 계획 하는 방법을 알아보려면이 항목을 읽으십시오.'
ms.openlocfilehash: 08b025b09acc4b4db5f26ae67761412a96c0339c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815746"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="645b7-103">비즈니스용 Skype Server 2015의 영구 채팅 서버에 대 한 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="645b7-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="645b7-104">**요약:** 이 항목에서는 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 가용성 및 재해 복구를 계획 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="645b7-105">영구 채팅 서버용 고가용성 및 재해 복구에는 일반적으로 전체 작업에 필요한 작업 외에 추가 리소스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="645b7-106">영구 채팅 서버 데이터베이스에서는 SQL AlwaysOn 가용성 그룹을 사용 하는 것이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="645b7-107">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="645b7-108">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="645b7-109">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="645b7-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="645b7-110">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="645b7-111">리소스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="645b7-111">Resource requirements</span></span>

<span data-ttu-id="645b7-112">고가용성 및 재해 복구를 위해 영구 채팅 서버를 구성 하기 전에 다음 리소스를 추가로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="645b7-113">영구 채팅 서버 서비스의 홈 프론트 엔드가 있는 동일한 물리적 데이터 센터에 있는 하나의 전용 데이터베이스 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="645b7-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="645b7-114">이 데이터베이스는 기본 영구 채팅 데이터베이스에 대 한 SQL Server 미러 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="645b7-115">선택적으로 미러 데이터베이스로 자동화 된 장애 조치를 수행 하려는 경우 미러링 미러링 모니터로 사용할 추가 SQL Server를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="645b7-116">다른 물리적 데이터 센터에 있는 하나의 전용 데이터베이스 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="645b7-117">이 데이터베이스는 기본 데이터 센터의 데이터베이스에 대 한 SQL Server 로그 전달 보조 데이터베이스 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="645b7-118">보조 데이터베이스의 SQL Server 미러 역할을 하는 하나의 전용 데이터베이스 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="645b7-119">선택적으로, 미러링 감시로 서버에 대 한 추가 SQL Server를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="645b7-120">두 가지 모두 보조 데이터베이스와 동일한 물리적 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="645b7-121">영구 채팅 서버 준수를 사용 하는 경우 추가 3 개의 전용 데이터베이스 인스턴스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="645b7-122">해당 배포는 이전에 영구 채팅 데이터베이스에 대해 설명 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="645b7-123">규정 준수 데이터베이스는 영구 채팅 데이터베이스와 동일한 SQL Server 인스턴스를 공유할 수 있지만 고가용성 및 장애 복구용의 독립 실행형 인스턴스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="645b7-124">SQL Server 로그 전달 트랜잭션 로그에 대해 파일 공유를 만들고 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="645b7-125">영구 채팅 데이터베이스를 실행 하는 두 데이터 센터의 모든 SQL Server에는이 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="645b7-126">이 공유는 최대 저장소 역할의 일부로 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="645b7-127">주 서버 파일 공유에서 복사한 SQL Server 트랜잭션 로그의 대상 폴더 역할을 하는 보조 데이터베이스 서버의 파일 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="645b7-128">재해 복구 및 고가용성 솔루션</span><span class="sxs-lookup"><span data-stu-id="645b7-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="645b7-129">비즈니스용 Skype 서버는 데이터베이스 미러링을 포함 하 여 백 엔드 서버에 대 한 여러 가지 고가용성 모드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="645b7-130">자세한 내용은 비즈니스용 [Skype 서버 2015의 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="645b7-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="645b7-131">이 항목에서 설명 하는 영구 채팅 서버의 재해 복구 솔루션은 늘어난 영구 채팅 서버 풀을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="645b7-132">스트레치 된 VLAN (가상 로컬 영역 네트워크)에 대 한 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="645b7-133">영구 채팅 서버 풀을 스트레치 하 여 토폴로지에 논리적으로 하나의 풀을 구성 하지만, 서버를 두 개의 다른 데이터 센터에 물리적으로 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="645b7-134">동일한 방식으로 데이터베이스에 대 한 SQL Server 미러링을 구성 하 고 동일한 데이터 센터에 데이터베이스와 미러를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="645b7-135">재해 복구 중 고가용성을 제공 하는 선택적 미러를 사용 하 여 보조 데이터 센터에서 백업 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="645b7-136">재해 복구 중 장애 조치 (failover)에 사용 되는 백업 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="645b7-137">영구 채팅 서버에 대 한 고가용성 및 재해 복구를 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버에 대해 고가용성 및 재해 복구 구성을](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="645b7-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="645b7-138">다음 그림은 두 개의 다른 스트레치 된 풀 토폴로지에서 영구 채팅 서버 풀을 구성할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="645b7-139">데이터 센터가 고대역폭/대기 시간이 짧은 지리적 위치에 있는 경우 영구 채팅 서버 풀을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="645b7-140">데이터 센터가 낮은 대역폭/대기 시간이 있는 지리적 위치에 있는 경우 영구 채팅 서버 풀을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="645b7-141">그림 1은 데이터 센터가 높은 대역폭/짧은 대기 시간으로 지리적으로 위치한 확장 된 영구 채팅 서버 풀 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="645b7-142">논리적 및 물리적 토폴로지에 대해 다음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="645b7-143">논리적 토폴로지는 다음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="645b7-144">1 ~ 8 서버를 포함 하는 사이트 1 및 2의 영구 채팅 풀.</span><span class="sxs-lookup"><span data-stu-id="645b7-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="645b7-145">프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러링된 데이터베이스, 선택적으로 사이트 1에 있는 미러링 모니터 데이터베이스 (다이어그램에 표시 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="645b7-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="645b7-146">두 번째 프런트 엔드 서버 풀 및 물리적으로 사이트 2에 상주 하는 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="645b7-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="645b7-147">실제 토폴로지는 사이트 1 및 2로 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="645b7-148">서버 1 ~ 4, 활성 2 개, 사이트 1의 유휴 2 개를 포함 하는 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="645b7-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="645b7-149">5 ~ 8 서버를 포함 하는 영구 채팅 풀, 2 개의 활성 2 사이트에서 유휴 2 개.</span><span class="sxs-lookup"><span data-stu-id="645b7-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="645b7-150">프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러된 데이터베이스, 선택적으로 사이트 1에 미러링 모니터 데이터베이스 (다이어그램에 표시 되지 않음)를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="645b7-151">프런트 엔드 서버 풀 및 사이트 2의 SQL 로그 전달 대상에 해당 하는 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="645b7-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="645b7-152">**데이터 센터가 고대역폭/대기 시간이 짧은 지리적 위치에 있는 경우 증가 하는 영구 채팅 서버 풀을 스트레치 함**</span><span class="sxs-lookup"><span data-stu-id="645b7-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![고대역폭/대기 시간이 짧은 영구 채팅 스트레치 풀](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="645b7-154">그림 2는 데이터 센터가 낮은 대역폭/고속 대기 시간으로 지리적으로 위치한 확장 된 영구 채팅 서버 풀 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="645b7-155">논리적 토폴로지는 다음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="645b7-156">1 ~ 8 서버를 포함 하는 사이트 1 및 2의 영구 채팅 풀.</span><span class="sxs-lookup"><span data-stu-id="645b7-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="645b7-157">프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러링된 데이터베이스, 선택적으로 사이트 1에 있는 미러링 모니터 데이터베이스 (다이어그램에 표시 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="645b7-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="645b7-158">두 번째 프런트 엔드 서버 풀 및 물리적으로 사이트 2에 상주 하는 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="645b7-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="645b7-159">실제 토폴로지는 사이트 1 및 2로 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="645b7-160">사이트 1에 있는 서버 1 ~ 4, 모두 활성 상태인 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="645b7-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="645b7-161">사이트 2에 있는 서버 5 ~ 8, 모든 유휴 상태)를 포함 하는 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="645b7-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="645b7-162">프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러된 데이터베이스, 선택적으로 사이트 1에 미러링 모니터 데이터베이스 (다이어그램에 표시 되지 않음)를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="645b7-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="645b7-163">프런트 엔드 서버 풀 및 사이트 2의 SQL 로그 전달 대상에 해당 하는 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="645b7-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="645b7-164">**데이터 센터가 낮은 대역폭/대기 시간이 있는 지리적 위치에 있는 경우 증가 하는 영구 채팅 서버 풀을 스트레치 함**</span><span class="sxs-lookup"><span data-stu-id="645b7-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![대역폭이 낮고 대기 시간이 긴 영구 채팅 스트레치 풀](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

