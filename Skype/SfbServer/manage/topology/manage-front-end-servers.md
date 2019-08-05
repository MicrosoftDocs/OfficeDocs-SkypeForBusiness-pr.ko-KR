---
title: 비즈니스용 Skype 서버에서 프런트 엔드 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 비즈니스용 Skype 서버에서 프런트 엔드 서버를 추가, 제거, 패치 또는 업데이트 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187104"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="046a1-103">비즈니스용 Skype 서버에서 프런트 엔드 서버 관리</span><span class="sxs-lookup"><span data-stu-id="046a1-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="046a1-104">이 문서에서는 프런트 엔드 서버를 추가 또는 제거 하는 방법과 프런트 엔드 서버에 업그레이드 또는 패치를 적용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="046a1-105">프런트 엔드 서버 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="046a1-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="046a1-106">풀에 프런트 엔드 서버를 추가 하거나 풀에서 프런트 엔드 서버를 제거 하는 경우에는 풀을 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="046a1-107">토폴로지에 있는 풀에 서버를 추가 하거나 제거 하 고 업데이트 된 토폴로지를 게시 하면 풀의 모든 서버가 동시에 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-107">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="046a1-108">서버가 풀을 다시 시작 하는 동안에는 해당 풀에 연결 된 사용자에 대 한 서비스를 중단 하는 동안 오프 라인 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-108">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="046a1-109">사용자에 대 한 서비스 중단을 방지 하려면 업무 외 시간에 풀에 새 서버를 사용 하 여 토폴로지를 게시 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-109">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="046a1-110">프런트 엔드 서버를 추가 하거나 제거 하는 경우 다음 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="046a1-111">풀에 새 서버를 추가 하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="046a1-112">프런트 엔드 서버를 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="046a1-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="046a1-113">프런트 엔드 서버를 제거 하는 경우 먼저 해당 서버에 대 한 새 연결을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="046a1-114">이렇게 하려면 다음 cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="046a1-115">토폴로지 작성기를 열고 필요한 서버를 추가 또는 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="046a1-116">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="046a1-117">토폴로지에 있는 풀에 서버를 추가 하거나 제거 하 고 업데이트 된 토폴로지를 게시 하면 풀의 모든 서버가 동시에 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-117">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="046a1-118">서버가 풀을 다시 시작 하는 동안에는 해당 풀에 연결 된 사용자에 대 한 서비스를 중단 하는 동안 오프 라인 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-118">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="046a1-119">사용자에 대 한 서비스 중단을 방지 하려면 업무 외 시간에 풀에 새 서버를 사용 하 여 토폴로지를 게시 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-119">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="046a1-120">또한 풀에 서버를 추가 하거나 제거할 때 추가 또는 제거 된 각 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행 해야 합니다. 자세한 내용은 [토폴로지에 있는 서버에 비즈니스용 Skype 서버 설치](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="046a1-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="046a1-121">프런트 엔드 풀의 서버 수를 다음 방법 중 하나로 변경한 경우 다음 cmdlet을 입력 하 여 풀을 다시 설정 합니다. CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="046a1-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="046a1-122">2에 모두</span><span class="sxs-lookup"><span data-stu-id="046a1-122">2 to any</span></span>
    
     - <span data-ttu-id="046a1-123">모두 2</span><span class="sxs-lookup"><span data-stu-id="046a1-123">Any to 2</span></span>
    
     - <span data-ttu-id="046a1-124">3 ~ any</span><span class="sxs-lookup"><span data-stu-id="046a1-124">3 to any</span></span>
    
     - <span data-ttu-id="046a1-125">모두 3</span><span class="sxs-lookup"><span data-stu-id="046a1-125">Any to 3</span></span>
    
5. <span data-ttu-id="046a1-126">다음 cmdlet을 입력 하 여 풀을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="046a1-127">프런트 엔드 서버 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="046a1-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="046a1-128">프런트 엔드 풀에 서버를 패치 하는 경우 한 번에 하나의 서버를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="046a1-129">풀의 프런트 엔드 서버에 업그레이드를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="046a1-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="046a1-130">다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="046a1-131">이 cmdlet에 누락 된 복제본이 표시 되는 경우 패치를 적용 하기 전에 다음 cmdlet을 실행 하 여 풀을 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="046a1-132">패치를 적용할 첫 번째 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="046a1-133">이 cmdlet은 모든 서비스를 풀의 다른 프런트 엔드 서버로 이동 하 고이 서버를 오프 라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="046a1-134">이 서버에 업그레이드 또는 패치를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="046a1-135">업그레이드 된 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="046a1-136">서버가 서비스에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="046a1-137">업그레이드 해야 하는 각 서버에 대해 2-4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="046a1-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
