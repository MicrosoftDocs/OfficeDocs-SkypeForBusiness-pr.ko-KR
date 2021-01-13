---
title: 비즈니스용 Skype 서버에서 프런트 엔드 서버 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 비즈니스용 Skype 서버에서 프런트 엔드 서버를 추가, 제거, 패치 또는 업데이트하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 16af245b3c49b21309edd3ee2843f2585814ce9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826328"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="effd3-103">비즈니스용 Skype 서버에서 프런트 엔드 서버 관리</span><span class="sxs-lookup"><span data-stu-id="effd3-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="effd3-104">이 문서에서는 프런트 엔드 서버를 추가 또는 제거하는 방법과 프런트 엔드 서버에 업그레이드 또는 패치를 적용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="effd3-105">비즈니스용 Skype 서버 2019는 프런트 엔드 서버가 두 대인 Enterprise Edition 프런트 엔드 풀을 지원하지 않습니다. 이 시나리오에서는 토폴로지가 게시될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="effd3-106">프런트 엔드 서버 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="effd3-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="effd3-107">풀에 프런트 엔드 서버를 추가하거나 풀에서 프런트 엔드 서버를 제거할 때 풀을 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="effd3-108">토폴로지의 풀에 서버를 추가하거나 제거한 다음 업데이트된 토폴로지 게시하면 풀의 모든 서버가 동시에 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="effd3-109">서버가 풀을 다시 시작하는 동안에는 풀이 오프라인 상태이면 해당 풀에 연결된 사용자의 서비스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="effd3-110">사용자에게 서비스가 중단되지 않도록 방지하기 위해 업무 시간 이외 시간에 풀에 새 서버와 함께 토폴로지 게시를 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="effd3-111">프런트 엔드 서버를 추가하거나 제거할 때 다음 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="effd3-112">풀에 새 서버를 추가하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="effd3-113">프런트 엔드 서버를 추가하거나 제거하려면</span><span class="sxs-lookup"><span data-stu-id="effd3-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="effd3-114">프런트 엔드 서버를 제거하는 경우 먼저 해당 서버에 대한 새 연결을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-114">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="effd3-115">이렇게 하여 다음 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-115">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="effd3-116">토폴로지 작성기를 열고 필요한 서버를 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="effd3-117">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="effd3-118">토폴로지의 풀에 서버를 추가하거나 제거한 다음 업데이트된 토폴로지 게시하면 풀의 모든 서버가 동시에 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="effd3-119">서버가 풀을 다시 시작하는 동안에는 풀이 오프라인 상태이면 해당 풀에 연결된 사용자의 서비스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="effd3-120">사용자에게 서비스가 중단되지 않도록 방지하기 위해 업무 시간 이외 시간에 풀에 새 서버와 함께 토폴로지 게시를 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="effd3-121">또한 풀에 서버를 추가하거나 제거할 때 추가되거나 제거된 각 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행해야 합니다. 자세한 내용은 토폴로지의 서버에 [비즈니스용 Skype 서버 설치를 참조하세요.](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="effd3-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="effd3-122">다음과 같은 방법으로 프런트 엔드 풀의 서버 수를 변경한 경우 -ResetType FullReset -PoolFqdn과 같은 cmdlet을 입력하여 Reset-CsPoolRegistrarState 풀을 다시 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="effd3-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="effd3-123">2에서 모든</span><span class="sxs-lookup"><span data-stu-id="effd3-123">2 to any</span></span>
    
     - <span data-ttu-id="effd3-124">2개까지</span><span class="sxs-lookup"><span data-stu-id="effd3-124">Any to 2</span></span>
    
     - <span data-ttu-id="effd3-125">3 ~ 모든</span><span class="sxs-lookup"><span data-stu-id="effd3-125">3 to any</span></span>
    
     - <span data-ttu-id="effd3-126">3개까지</span><span class="sxs-lookup"><span data-stu-id="effd3-126">Any to 3</span></span>
    
5. <span data-ttu-id="effd3-127">다음 cmdlet을 입력하여 풀 다시 시작</span><span class="sxs-lookup"><span data-stu-id="effd3-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="effd3-128">프런트 엔드 서버 패치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="effd3-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="effd3-129">프런트 엔드 풀에서 서버를 패치할 때 한 서버에 한 번씩 패치를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="effd3-130">풀의 프런트 엔드 서버에 업그레이드를 적용하려면</span><span class="sxs-lookup"><span data-stu-id="effd3-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="effd3-131">다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="effd3-132">이 cmdlet에 누락된 복제본이 표시될 경우 패치를 적용하기 전에 다음 cmdlet을 실행하여 풀을 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="effd3-133">패치할 첫 번째 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="effd3-134">이 cmdlet은 모든 서비스를 풀의 다른 프런트 엔드 서버로 이동하고 이 서버를 오프라인으로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="effd3-135">이 서버에 업그레이드 또는 패치를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="effd3-136">업그레이드된 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="effd3-137">서버가 서비스로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="effd3-138">업그레이드해야 하는 각 서버에 대해 2-4단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="effd3-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
