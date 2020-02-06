---
title: 영구 채팅 서버 토폴로지 계획
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
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '요약: 비즈니스용 Skype Server 2015의 영구 채팅 서버 구성 요소와 토폴로지에 대해 자세히 알아보려면이 항목을 읽으십시오.'
ms.openlocfilehash: afcdf7ed85cca6b54652dcf5170316258a6b5551
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815726"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="29402-103">영구 채팅 서버 토폴로지 계획</span><span class="sxs-lookup"><span data-stu-id="29402-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="29402-104">**요약:** 이 항목에서는 비즈니스용 Skype 서버 2015의 영구 채팅 서버 구성 요소와 토폴로지에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="29402-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="29402-105">영구 채팅 서버는 단일 서버 및 다중 서버 구성을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="29402-106">비즈니스용 Skype Server 2015 Enterprise Edition 또는 Standard Edition 서버에 영구 채팅 서버를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="29402-107">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="29402-108">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="29402-109">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="29402-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="29402-110">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="29402-111">영구 채팅 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="29402-111">Persistent Chat Server components</span></span>

<span data-ttu-id="29402-112">영구 채팅 서버는 다음 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29402-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="29402-113">영구 채팅 서버를 실행 하 고 다음 서비스를 제공 하는 하나 이상의 컴퓨터:</span><span class="sxs-lookup"><span data-stu-id="29402-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="29402-114">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="29402-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="29402-115">준수를 사용 하도록 설정 된 규정 준수 서비스</span><span class="sxs-lookup"><span data-stu-id="29402-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="29402-116">하나 이상의 서버 (미러링이 사용 되는 경우 둘 이상)는 채팅방 콘텐츠, 채팅방 및 범주가 저장 되는 영구 채팅 콘텐츠 데이터베이스를 호스팅하기 위해 SQL Server 백 엔드 데이터베이스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="29402-117">백 엔드 데이터베이스에는 범주 및 생성 된 영구 채팅방에 대 한 정보를 포함 하 여 채팅 기록 데이터가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29402-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="29402-118">규정 준수를 사용 하는 경우 하나 이상의 서버 (미러링이 사용 되는 경우)를 실행 하 여 지속적인 채팅 준수 데이터베이스를 호스트 하는 SQL Server 백 엔드 데이터베이스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="29402-119">영구 채팅 서버용 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 비즈니스용 skype [서버 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 및 비즈니스용 [skype Server 2015의 영구 채팅 서버용 하드웨어 및 소프트웨어 요구](hardware-and-software-requirements.md)사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29402-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="29402-120">영구 채팅 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="29402-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="29402-121">단일 서버 또는 다중 서버 풀에서 영구 채팅 서버를 배포 하 고 단일 풀 또는 다중 풀 토폴로지에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="29402-122">영구 채팅 서버는 다음 토폴로지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="29402-123">프런트 엔드 서버의 영구 채팅 서버 collocated 스탠더드 버전 서버</span><span class="sxs-lookup"><span data-stu-id="29402-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="29402-124">별도의 서버에서 영구 채팅 서버를 사용 하는 스탠더드 버전 서버</span><span class="sxs-lookup"><span data-stu-id="29402-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="29402-125">별도의 서버에 단일 영구 채팅 서버가 있는 Enterprise Edition 서버</span><span class="sxs-lookup"><span data-stu-id="29402-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="29402-126">별도의 서버에 둘 이상의 영구 채팅 서버가 있는 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="29402-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="29402-127">표준 버전 서버에 영구 채팅 서버를 배포할 수는 있지만 성능 및 확장성에는 영향이 있으며 높은 가용성은 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="29402-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="29402-128">따라서 개념 증명 및 평가 목적 으로만 표준 버전 서버에 영구적 채팅을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="29402-129">비즈니스용 Skype Server 2015는 한 대의 서버에서 여러 구성 요소를 실행 하 여 하드웨어 비용을 절약 하 고 (소규모 조직의 경우), 다른 서버에서 개별 구성 요소를 실행 하는 유연성을 제공 하는 다양 한 collocation 시나리오를 지원 합니다 ( 확장성 및 성능이 필요한 대규모 조직이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="29402-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="29402-130">구성 요소를 collocate 여부를 결정 하기 전에 확장성 요인을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="29402-131">Collocation 시나리오는 비즈니스용 Skype 서버 2015 Enterprise Edition 및 Standard Edition 서버에 대해 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="29402-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="29402-132">다음 섹션에서는 백 엔드 데이터베이스 서버에 대 한 collocation 시나리오 및 옵션을 포함 하 여 토폴로지에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="29402-133">모든 서버 역할 및 데이터베이스의 collocation에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 토폴로지 기본 사항을](../../plan-your-deployment/topology-basics/topology-basics.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29402-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="29402-134">프런트 엔드 서버의 영구 채팅 서버 collocated 스탠더드 버전 서버</span><span class="sxs-lookup"><span data-stu-id="29402-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="29402-135">스탠더드 버전을 사용 하면 프런트 엔드 서버에서 영구 채팅을 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="29402-136">가장 간단 하 고 기본적인 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="29402-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="29402-137">기존 프런트 엔드 서버에 실제 리소스 (CPU, 메모리, 디스크 공간 등)의 측면에서 충분 한 용량을가지고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="29402-138">또한 로컬 SQL Server Express 백 엔드 서버에서 영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스 (사용 가능한 경우)를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="29402-139">전용 인스턴스가 있는 별도의 SQL Server를 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="29402-140">첫 번째 영구 채팅 서버가 표준 버전의 프런트 엔드 서버와 collocated 경우 영구 채팅 서버 풀에 다른 서버를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="29402-141">필요한 경우 나중에 서버를 더 추가할 수 있도록 첫 번째 서버를 독립 실행형 인스턴스로 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="29402-142">영구 채팅 서버를 별도의 서버에 설치 하는 스탠더드 버전 서버</span><span class="sxs-lookup"><span data-stu-id="29402-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="29402-143">스탠더드 버전에서는 영구 채팅 서버를 독립 실행형 인스턴스로 설치 하 고 필요한 경우 나중에 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="29402-144">로컬 SQL Server Express 백 엔드 서버에서 영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스 (사용 가능한 경우)를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="29402-145">전용 인스턴스가 있는 별도의 SQL Server를 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="29402-146">단일 영구 채팅 서버를 사용 하는 Enterprise Edition 서버</span><span class="sxs-lookup"><span data-stu-id="29402-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="29402-147">Enterprise Edition을 사용 하는 경우 별도의 컴퓨터에 영구 채팅 서버를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="29402-148">즉, Enterprise Edition 프런트 엔드 서버에서 영구 채팅 서버를 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="29402-149">이 배포에는 영구 채팅 서버와 준수 서비스 (사용 가능한 경우)를 실행 하는 별도의 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="29402-150">그러나 Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스에서 영구 채팅 서버용 SQL Server 데이터베이스를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29402-151">HA DR에 SQL AlwaysOn 가용성 그룹을 사용 하려는 경우 영구 채팅 서버 데이터베이스에 대해 지원 되지 않는 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="29402-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="29402-152">백 엔드 데이터베이스에 영구 채팅 데이터베이스를 collocate 경우 모든 데이터베이스에 대해 단일 SQL Server 인스턴스를 사용 하거나 각 데이터베이스에 대해 별도의 SQL Server 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="29402-153">영구 채팅 데이터베이스를 호스트 하는 서버는 다른 데이터베이스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="29402-154">그러나 다른 데이터베이스와 영구 채팅 데이터베이스를 collocating 하는 경우에는 여러 사용자의 메시지를 저장 하는 경우 영구 채팅 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 점에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="29402-155">이 때문에 백 엔드 데이터베이스에서 영구 채팅 데이터베이스를 collocating 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="29402-156">다음 그림은 규정 준수를 사용 하는 단일 영구 채팅 서버에 대 한 토폴로지의 모든 구성 요소를 보여 줍니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="29402-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="29402-157">**단일 서버 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="29402-157">**Single Server Topology**</span></span>

![영구 채팅 서버-단일 서버 토폴로지](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="29402-159">여러 영구 채팅 서버가 있는 Enterprise Edition 서버</span><span class="sxs-lookup"><span data-stu-id="29402-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="29402-160">Enterprise Edition을 사용 하면 용량 및 안정성을 강화 하기 위해 다중 서버 토폴로지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="29402-161">다중 서버 토폴로지는 여러 서버에서 영구 채팅 서버를 호스트 하는 것을 제외 하 고 단일 서버 토폴로지와 동일 하며 더 높은 배율을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="29402-162">다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 4 대의 활성 컴퓨터가 포함 될 수 있습니다 (고가용성 및 재해 복구 구성은 최대 8 개까지 허용 되지만, 나머지 4 개는 활성 상태로 유지 될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="29402-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="29402-163">각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대에서 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="29402-164">영구 채팅 서버를 실행 하는 여러 컴퓨터는 비즈니스용 Skype 서버 및 규정 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 상주해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="29402-165">다음 그림은 영구 채팅 서버, 선택적 준수 서비스, 별도 규정 준수 데이터베이스를 실행 하는 여러 컴퓨터가 있는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29402-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="29402-166">**다중 서버 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="29402-166">**Multiple Server Topology**</span></span>

![영구 채팅 서버-다중 서버 토폴로지](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="29402-168">다중 서버 토폴로지는 서버 기능 풀링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="29402-169">서버 풀에서 영구 채팅 서비스는 데이터를 통신 하 고 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="29402-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="29402-170">예를 들어 원래 하나의 영구 채팅 서비스에 게시 된 채팅 기록을 시스템의 모든 영구 채팅 서비스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="29402-171">하나의 영구 채팅 서비스를 통해 업로드 되는 파일은 영구 채팅 서비스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="29402-172">사용자는 서로 다른 영구 채팅 서버 프런트 엔드 서버에 연결 되어 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29402-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="29402-173">TCP 8011의 기본 포트는 서버를 서버 풀에 연결 하 고 영구 채팅 서비스에서 자신과 관리 목적으로 통신 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29402-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="29402-174">예를 들어 4 서버 영구 채팅 서버 배포에서 8만 사용자가 동시에 영구 채팅에 로그인 할 수 있는 경우 부하는 서버 당 2만 사용자에 게 균등 하 게 분배 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29402-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="29402-175">한 서버를 사용할 수 없게 되 면 해당 서버에 연결 된 사용자가 영구 채팅 서버에 대 한 액세스 권한을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29402-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="29402-176">연결이 끊긴 사용자는 사용할 수 없는 서버가 복원 될 때까지 자동으로 나머지 서버로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29402-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

