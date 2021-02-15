---
title: 영구 채팅 서버의 고가용성 및 재해 복구 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: '요약: 이 항목을 통해 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 고가용성 및 재해 복구를 계획하는 방법을 배워 읽습니다.'
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832358"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="01f86-103">영구 채팅 서버의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="01f86-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="01f86-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 고가용성 및 재해 복구를 계획하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="01f86-105">영구 채팅 서버의 고가용성 및 재해 복구에는 일반적으로 전체 작업에 필요한 리소스 이외에 추가 리소스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="01f86-106">AlwaysOn SQL 영구 채팅 서버 데이터베이스에서는 AlwaysOn 가용성 그룹을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="01f86-107">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="01f86-108">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="01f86-109">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="01f86-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="01f86-110">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="01f86-111">리소스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="01f86-111">Resource requirements</span></span>

<span data-ttu-id="01f86-112">고가용성 및 재해 복구를 위해 영구 채팅 서버를 구성하기 전에 다음과 같은 추가 리소스를 확보해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="01f86-113">영구 채팅 서버 서비스의 홈 프런트 엔드가 있는 동일한 실제 데이터 센터에 있는 전용 데이터베이스 인스턴스 1개</span><span class="sxs-lookup"><span data-stu-id="01f86-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="01f86-114">이 데이터베이스는 기본 영구 채팅 SQL Server 대한 기본 미러로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="01f86-115">원하는 경우 미러 데이터베이스에 대한 SQL Server 장애 조치(failover)를 원하는 경우 미러링 기능으로 사용할 추가 데이터베이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="01f86-116">다른 실제 데이터 센터에 있는 전용 데이터베이스 인스턴스 하나.</span><span class="sxs-lookup"><span data-stu-id="01f86-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="01f86-117">이 데이터베이스는 기본 데이터 SQL Server 데이터베이스의 로그 전달 보조 데이터베이스로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="01f86-118">보조 데이터베이스에 대한 SQL Server 미러로 사용할 전용 데이터베이스 인스턴스 1개</span><span class="sxs-lookup"><span data-stu-id="01f86-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="01f86-119">선택적으로 서버에 대한 추가 SQL Server 미러링된 미러링 서버로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="01f86-120">이 두 가지 모두 보조 데이터베이스와 동일한 실제 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="01f86-121">영구 채팅 서버 준수를 사용하도록 설정한 경우 추가 3개의 전용 데이터베이스 인스턴스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="01f86-122">이러한 배포는 이전에 영구 채팅 데이터베이스에 대해 설명한 배포와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="01f86-123">준수 데이터베이스가 영구 채팅 데이터베이스와 동일한 SQL Server 인스턴스를 공유할 수 있는 반면 고가용성 및 재해 복구를 위한 독립 실행형 인스턴스를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="01f86-124">로그 전달 트랜잭션 로그에 대해 파일 공유를 SQL Server 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="01f86-125">영구 채팅 SQL 실행되는 두 데이터 센터의 모든 서버는 이 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="01f86-126">이 공유는 FileStore 역할의 일부로 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="01f86-127">기본 서버 파일 공유에서 복사되는 SQL Server 로그의 대상 폴더로 사용할 보조 데이터베이스 서버의 파일 공유입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="01f86-128">재해 복구 및 고가용성 솔루션</span><span class="sxs-lookup"><span data-stu-id="01f86-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="01f86-129">비즈니스용 Skype 서버는 데이터베이스 미러링을 포함하여 백 엔드 서버에 대해 여러 가지 고가용성 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="01f86-130">자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)고가용성 및 재해 복구 계획을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01f86-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="01f86-131">이 항목에 설명된 영구 채팅 서버용 재해 복구 솔루션은 확장된 영구 채팅 서버 풀을 토대화합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="01f86-132">확장된 VLAN(가상 지역 네트워크)에 대한 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="01f86-133">영구 채팅 서버 풀을 확장하면 토폴로지에서 하나의 풀을 논리적으로 구성하지만 실제로는 두 개의 서로 다른 데이터 센터에 풀에 서버를 두게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="01f86-134">데이터베이스에 SQL Server 미러링을 구성하고 데이터베이스와 미러를 동일한 데이터 센터에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="01f86-135">보조 데이터 센터에는 백업 데이터베이스를 구성해야 합니다(재해 복구 중 고가용성을 제공하기 위한 선택적인 미러 포함).</span><span class="sxs-lookup"><span data-stu-id="01f86-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="01f86-136">이러한 백업 데이터베이스는 재해 복구 중 장애 조치(Failover)를 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="01f86-137">영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)영구 채팅 서버에 대해 고가용성 및 재해 복구 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01f86-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="01f86-138">다음 그림에서는 서로 다른 두 가지 확장된 풀 토폴로지에서 영구 채팅 서버 풀을 구성하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="01f86-139">데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="01f86-140">데이터 센터가 낮은 대역폭/긴 대기 시간을 사용하여 지리적으로 분산된 경우의 확장 영구 채팅 서버 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="01f86-141">그림 1은 데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 위치하는 확장된 영구 채팅 서버 풀 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="01f86-142">논리적 토폴로지 및 물리적 토폴로지의 경우 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="01f86-143">논리적 토폴로지는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="01f86-144">1에서 8까지의 서버를 포함하는 사이트 1 및 2의 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="01f86-145">사이트 1에 물리적으로 있는 프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러된 데이터베이스 및 미러링된 데이터베이스(다이어그램에 나와 있지 않은 경우)를 선택적으로 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="01f86-146">사이트 2에 물리적으로 있는 두 번째 프런트 엔드 서버 풀 및 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="01f86-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="01f86-147">실제 토폴로지는 다음과 같이 사이트 1과 2로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="01f86-148">사이트 1에서 4까지의 서버 2개, 활성 2개, 유휴 서버 2개가 포함된 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="01f86-149">사이트 2에서 활성 서버 2개, 활성 서버 2개, 유휴 서버 2개가 포함된 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="01f86-150">사이트 1의 프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러된 데이터베이스 및 미러링된 데이터베이스(다이어그램에 나와 있지 않은 경우)의 미러 데이터베이스(선택 사항)입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="01f86-151">사이트 2에서 프런트 엔드 서버 풀 및 SQL 전달 대상인 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="01f86-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="01f86-152">**데이터 센터가 높은 대역폭/짧은 대기 시간을 사용하여 지리적으로 위치한 경우 확장된 영구 채팅 서버 풀**</span><span class="sxs-lookup"><span data-stu-id="01f86-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![높은 대역폭/짧은 대기 시간을 사용하는 영구 채팅 확장 풀](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="01f86-154">그림 2에서는 데이터 센터가 낮은 대역폭/높은 대기 시간으로 지리적으로 위치하는 확장된 영구 채팅 서버 풀 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="01f86-155">논리적 토폴로지는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="01f86-156">1에서 8까지의 서버를 포함하는 사이트 1 및 2의 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="01f86-157">사이트 1에 물리적으로 있는 프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러된 데이터베이스 및 미러링된 데이터베이스(다이어그램에 나와 있지 않은 경우)를 선택적으로 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="01f86-158">사이트 2에 물리적으로 있는 두 번째 프런트 엔드 서버 풀 및 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="01f86-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="01f86-159">실제 토폴로지는 다음과 같이 사이트 1과 2로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="01f86-160">사이트 1에서 1에서 4까지의 서버가 모두 활성 상태인 영구 채팅 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="01f86-161">사이트 2에서 5~8 서버가 모두 유휴인 영구 채팅 풀</span><span class="sxs-lookup"><span data-stu-id="01f86-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="01f86-162">사이트 1의 프런트 엔드 서버 풀, 영구 채팅 데이터베이스, 미러된 데이터베이스 및 미러링된 데이터베이스(다이어그램에 나와 있지 않은 경우)의 미러 데이터베이스(선택 사항)입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="01f86-163">사이트 2에서 프런트 엔드 서버 풀 및 SQL 전달 대상인 백업 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="01f86-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="01f86-164">**데이터 센터가 낮은 대역폭/높은 대기 시간으로 지리적으로 위치한 경우 확장된 영구 채팅 서버 풀**</span><span class="sxs-lookup"><span data-stu-id="01f86-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![낮은 대역폭/높은 대기 시간을 사용하는 영구 채팅 확장 풀](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

