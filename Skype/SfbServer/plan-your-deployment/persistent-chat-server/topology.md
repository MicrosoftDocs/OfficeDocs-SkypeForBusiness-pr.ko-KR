---
title: 영구 채팅 서버 토폴로지 계획
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
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 2015의 영구 채팅 서버 구성 요소 및 토폴로지에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825508"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="47e16-103">영구 채팅 서버 토폴로지 계획</span><span class="sxs-lookup"><span data-stu-id="47e16-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="47e16-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2015의 영구 채팅 서버 구성 요소 및 토폴로지에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="47e16-105">영구 채팅 서버는 단일 서버 및 다중 서버 구성을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="47e16-106">영구 채팅 서버는 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition Server에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="47e16-107">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="47e16-108">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="47e16-109">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="47e16-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="47e16-110">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="47e16-111">영구 채팅 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="47e16-111">Persistent Chat Server components</span></span>

<span data-ttu-id="47e16-112">영구 채팅 서버는 다음 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="47e16-113">영구 채팅 서버를 실행하고 다음 서비스를 제공하는 하나 이상의 컴퓨터:</span><span class="sxs-lookup"><span data-stu-id="47e16-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="47e16-114">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="47e16-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="47e16-115">준수가 사용하도록 설정된 경우 켜진 준수 서비스</span><span class="sxs-lookup"><span data-stu-id="47e16-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="47e16-116">채팅방 콘텐츠, 채팅방 및 범주가 저장되는 영구 채팅 콘텐츠 데이터베이스를 호스팅하기 위해 SQL Server 백 엔드 데이터베이스를 실행하는 하나 이상의 서버(미러링이 사용되는 경우 두 개 이상)</span><span class="sxs-lookup"><span data-stu-id="47e16-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47e16-117">백 엔드 데이터베이스는 만들어진 범주 및 영구 채팅방에 대한 정보를 포함하여 채팅 기록 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="47e16-118">준수를 사용하도록 설정하면 준수 목적으로 준수 이벤트 및 채팅 콘텐츠가 저장되는 영구 채팅 준수 데이터베이스를 호스팅하기 위해 SQL Server 백 엔드 데이터베이스를 실행하는 하나 이상의 서버(미러링이 사용되는 경우 두 개 이상)가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="47e16-119">영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 서버 요구 사항 및 영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항을 비즈니스용 [Skype 서버 2015에서](hardware-and-software-requirements.md)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47e16-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="47e16-120">영구 채팅 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="47e16-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="47e16-121">단일 서버 또는 다중 서버 풀 및 단일 풀 또는 다중 풀 토폴로지에서 영구 채팅 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="47e16-122">영구 채팅 서버는 다음과 같은 토폴로지가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="47e16-123">프런트 엔드 서버에 영구 채팅 서버가 함께 함께 있는 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="47e16-124">영구 채팅 서버가 별도의 서버에 있는 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="47e16-125">별도의 서버에 단일 영구 채팅 서버가 있는 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="47e16-126">별도의 서버에 영구 채팅 서버가 두 개 이상 있는 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="47e16-127">Standard Edition Server에 영구 채팅 서버를 배포할 수 있습니다. 그러나 성능 및 확장은 영향을 받을 수 있으며 고가용성은 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="47e16-128">따라서 개념 증명 및 평가를 위해 Standard Edition Server에 영구 채팅을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="47e16-129">비즈니스용 Skype 서버 2015는 여러 구성 요소를 한 서버에서 실행하여 하드웨어 비용을 절약하거나(소규모 조직인 경우) 서로 다른 서버에서 개별 구성 요소를 실행하여 하드웨어 비용을 절약할 수 있는 유연성을 제공합니다(확장성과 성능이 필요한 대규모 조직인 경우).</span><span class="sxs-lookup"><span data-stu-id="47e16-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="47e16-130">구성 요소를 함께할지 여부를 결정하기 전에 확장성 요인을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="47e16-131">비즈니스용 Skype 서버 2015 Enterprise Edition 및 Standard Edition 서버의 경우 함께 사용 시나리오가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="47e16-132">다음 섹션에서는 백 엔드 데이터베이스 서버에 대한 설명 시나리오 및 옵션을 포함하여 토폴로지에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="47e16-133">모든 서버 역할 및 데이터베이스를 함께 설치하는 데 대한 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/topology-basics/topology-basics.md)토폴로지 기본 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47e16-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="47e16-134">프런트 엔드 서버에 영구 채팅 서버가 함께 함께 있는 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="47e16-135">Standard Edition에서는 프런트 엔드 서버에 영구 채팅을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="47e16-136">가장 간단하고 기본적인 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="47e16-137">CPU, 메모리, 디스크 공간 등 실제 리소스 측면에서 기존 프런트 엔드 서버에 충분한 용량이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="47e16-138">또한 영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스(사용하도록 설정된 경우)를 로컬 SQL Server 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="47e16-139">전용 인스턴스에 별도의 응용 SQL Server 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="47e16-140">첫 번째 영구 채팅 서버가 Standard Edition 프런트 엔드 서버와 함께 함께 있는 경우 영구 채팅 서버 풀에 서버를 더 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="47e16-141">필요한 경우 나중에 서버를 더 추가할 수 있도록 첫 번째 서버를 독립 실행형 인스턴스로 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="47e16-142">영구 채팅 서버가 별도의 서버에 설치된 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="47e16-143">Standard Edition에서는 영구 채팅 서버를 독립 실행형 인스턴스로 설치하고 필요한 경우 나중에 서버를 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="47e16-144">영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스(사용하도록 설정된 경우)를 로컬 SQL Server 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="47e16-145">전용 인스턴스에 별도의 응용 SQL Server 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="47e16-146">단일 영구 채팅 서버가 있는 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="47e16-147">Enterprise Edition에서는 영구 채팅 서버를 별도의 컴퓨터에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="47e16-148">즉, Enterprise Edition 프런트 엔드 서버에 영구 채팅 서버를 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="47e16-149">이 배포를 사용하려면 영구 채팅 서버와 준수 서비스를 실행하는 별도의 서버가 필요합니다(사용하도록 설정된 경우).</span><span class="sxs-lookup"><span data-stu-id="47e16-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="47e16-150">그러나 Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스에 영구 채팅 SQL Server 데이터베이스를 함께 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47e16-151">HA DR에 대해 SQL AlwaysOn 가용성 그룹을 사용하려면 영구 채팅 서버 데이터베이스에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="47e16-152">영구 채팅 데이터베이스를 백 엔드 데이터베이스와 함께 사용하는 경우 모든 데이터베이스에 대해 단일 SQL Server 인스턴스를 사용하거나 각 데이터베이스에 대해 별도의 SQL Server 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="47e16-153">영구 채팅 데이터베이스를 호스팅하는 서버는 다른 데이터베이스를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="47e16-154">그러나 영구 채팅 데이터베이스를 다른 데이터베이스와 함께 사용할 경우 여러 사용자의 메시지를 저장하는 경우 영구 채팅 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="47e16-155">따라서 영구 채팅 데이터베이스를 백 엔드 데이터베이스와 함께 두지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="47e16-156">다음 그림에서는 준수가 사용하도록 설정된 단일 영구 채팅 서버(선택 사항)에 대한 토폴로지의 모든 구성 요소를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="47e16-157">**단일 서버 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="47e16-157">**Single Server Topology**</span></span>

![영구 채팅 서버 - 단일 서버 토폴로지](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="47e16-159">여러 영구 채팅 서버가 있는 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="47e16-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="47e16-160">Enterprise Edition을 사용하면 용량과 안정성을 향상하기 위해 다중 서버 토폴로지가 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="47e16-161">다중 서버 토폴로지는 단일 서버 토폴로지와 동일합니다. 단, 여러 서버가 영구 채팅 서버를 호스팅하고 더 높은 수준으로 확장할 수 있는 경우를 제외하고는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="47e16-162">다중 서버 토폴로지에는 영구 채팅 서버를 실행하는 최대 4대의 활성 컴퓨터가 포함되어 있을 수 있습니다. 고가용성 및 재해 복구 구성에서는 최대 8대의 활성 컴퓨터를 사용할 수 있지만 4대만 활성 상태일 수 있으며 나머지 4대는 대기 상태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="47e16-163">각 서버는 20,000명까지 동시 사용자를 지원할 수 있으며, 총 80,000명의 동시 사용자가 4대의 서버가 있는 영구 채팅 서버 풀에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="47e16-164">영구 채팅 서버를 실행하는 여러 컴퓨터는 비즈니스용 Skype 서버 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="47e16-165">다음 그림에서는 영구 채팅 서버, 선택적 준수 서비스 및 별도의 준수 데이터베이스를 실행하는 여러 컴퓨터가 있는 다중 서버 토폴로지의 모든 구성 요소를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="47e16-166">**다중 서버 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="47e16-166">**Multiple Server Topology**</span></span>

![영구 채팅 서버 - 다중 서버 토폴로지](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="47e16-168">다중 서버 토폴로지에서는 서버 기능 풀링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="47e16-169">서버 풀에서 영구 채팅 서비스는 데이터를 통신하고 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="47e16-170">예를 들어 원래 하나의 영구 채팅 서비스에 게시된 채팅 기록은 시스템의 모든 영구 채팅 서비스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="47e16-171">하나의 영구 채팅 서비스를 통해 업로드된 파일에는 영구 채팅 서비스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="47e16-172">사용자는 서로 다른 영구 채팅 서버 프런트 엔드 서버에 연결할 수 있으며 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="47e16-173">TCP 8011의 기본 포트는 서버를 서버 풀에 연결하며 영구 채팅 서비스에서 자체 또는 관리 목적으로 통신하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="47e16-174">예를 들어 80,000명을 동시에 영구 채팅에 로그인할 수 있는 4 서버 영구 채팅 서버 배포에서는 서버당 사용자 20,000명에게 부하가 고리적으로 분산됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="47e16-175">한 서버를 사용할 수 없게 되는 경우 해당 서버에 연결된 사용자는 영구 채팅 서버에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="47e16-176">연결이 끊긴 사용자는 해당 서버가 복원될 때까지 나머지 서버로 자동으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e16-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

