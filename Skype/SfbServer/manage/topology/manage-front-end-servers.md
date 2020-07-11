---
title: 비즈니스용 Skype 서버에서 프런트 엔드 서버 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 비즈니스용 Skype 서버에서 프런트 엔드 서버를 추가, 제거, 패치 또는 업데이트 하는 방법을 알아봅니다.'
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098416"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="420e1-103">비즈니스용 Skype 서버에서 프런트 엔드 서버 관리</span><span class="sxs-lookup"><span data-stu-id="420e1-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="420e1-104">이 문서에서는 프런트 엔드 서버를 추가 또는 제거 하는 방법과 프런트 엔드 서버에 업그레이드 또는 패치를 적용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="420e1-105">비즈니스용 Skype 서버 2019에서는 프런트 엔드 서버가 두 대 인 Enterprise Edition 프런트 엔드 풀을 지원 하지 않으며,이 시나리오에서 토폴로지를 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="420e1-106">프런트 엔드 서버 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="420e1-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="420e1-107">프런트 엔드 서버를 풀에 추가 하거나 풀에서 프런트 엔드 서버를 제거 하는 경우에는 풀을 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="420e1-108">토폴로지의 풀에 서버를 추가 하거나 제거한 다음 업데이트 된 토폴로지를 게시 하면 풀에 있는 모든 서버가 동시에 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="420e1-109">서버를 다시 시작 하는 동안에는 해당 풀에 연결 된 사용자에 대 한 서비스를 중단 하는 서버가 오프 라인 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="420e1-110">사용자에 대 한 서비스가 중단 되지 않도록 하려면 업무 외 시간에 새 서버를 사용 하 여 토폴로지를 해당 풀에 게시 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="420e1-111">프런트 엔드 서버를 추가 또는 제거할 때 다음 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="420e1-112">풀에 새 서버를 추가 하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="420e1-113">프런트 엔드 서버를 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="420e1-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="420e1-114">프런트 엔드 서버를 제거 하는 경우 먼저 해당 서버에 대 한 새 연결을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-114">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="420e1-115">이렇게 하려면 다음 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-115">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="420e1-116">토폴로지 작성기를 열고 필요한 서버를 추가 또는 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="420e1-117">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="420e1-118">토폴로지의 풀에 서버를 추가 하거나 제거한 다음 업데이트 된 토폴로지를 게시 하면 풀에 있는 모든 서버가 동시에 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="420e1-119">서버를 다시 시작 하는 동안에는 해당 풀에 연결 된 사용자에 대 한 서비스를 중단 하는 서버가 오프 라인 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="420e1-120">사용자에 대 한 서비스가 중단 되지 않도록 하려면 업무 외 시간에 새 서버를 사용 하 여 토폴로지를 해당 풀에 게시 하도록 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="420e1-121">또한 풀에 서버를 추가 하거나 제거 하는 경우 추가 하거나 제거한 각 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행 해야 합니다. 자세한 내용은 [토폴로지의 서버에 비즈니스용 Skype 서버 설치](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="420e1-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="420e1-122">프런트 엔드 풀의 서버 수를 다음과 같은 방식으로 변경한 경우 다음 cmdlet을 입력 하 여 풀을 다시 설정 합니다. Reset-cspoolregistrarstate-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="420e1-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="420e1-123">2 ~ any</span><span class="sxs-lookup"><span data-stu-id="420e1-123">2 to any</span></span>
    
     - <span data-ttu-id="420e1-124">모두 2</span><span class="sxs-lookup"><span data-stu-id="420e1-124">Any to 2</span></span>
    
     - <span data-ttu-id="420e1-125">3 ~ any</span><span class="sxs-lookup"><span data-stu-id="420e1-125">3 to any</span></span>
    
     - <span data-ttu-id="420e1-126">모두 3</span><span class="sxs-lookup"><span data-stu-id="420e1-126">Any to 3</span></span>
    
5. <span data-ttu-id="420e1-127">다음 cmdlet을 입력 하 여 풀을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="420e1-128">프런트 엔드 서버 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="420e1-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="420e1-129">프런트 엔드 풀에 서버를 패치 하는 경우 한 번에 하나의 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="420e1-130">풀의 프런트 엔드 서버에 업그레이드를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="420e1-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="420e1-131">다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="420e1-132">이 cmdlet이 누락 된 복제본을 표시 하는 경우 패치를 적용 하기 전에 다음 cmdlet을 실행 하 여 풀을 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="420e1-133">패치를 적용할 첫 번째 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="420e1-134">이 cmdlet은 모든 서비스를 풀의 다른 프런트 엔드 서버로 이동 하 고이 서버를 오프 라인으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="420e1-135">이 서버에 업그레이드 또는 패치를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="420e1-136">업그레이드 된 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="420e1-137">서버가 서비스에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="420e1-138">업그레이드 해야 하는 각 서버에 대해 2-4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="420e1-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
