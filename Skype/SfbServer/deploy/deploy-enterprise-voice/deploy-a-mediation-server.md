---
title: 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: '요약: 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버를 정의 하 고 배포 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: c651ff3e254165161642c4e729d0d4e3f2983023
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767691"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="ceb7a-103">비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버 배포</span><span class="sxs-lookup"><span data-stu-id="ceb7a-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="ceb7a-104">**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버를 정의 하 고 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="ceb7a-105">엔터프라이즈 음성 작업 부하, 전화 접속 회의 및 고급 엔터프라이즈 음성 애플리케이션 (응답 그룹 응용 프로그램, 통화 공원 응용 프로그램, call 허용 컨트롤 (CAC) 등)은 프런트 엔드 풀에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="ceb7a-106">중재 서버의 기능은 프런트 엔드 서버에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="ceb7a-107">별도의 독립 실행형 중재 서버는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="ceb7a-108">유일한 예외는 인터넷 전화 통신 서비스 공급자에 대 한 세션 경계 컨트롤러에 연결 하도록 SIP 트렁크를 구성 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="ceb7a-109">사용자의 엔터프라이즈 음성 인프라를 SIP 트렁크 공급자에 연결 하려면 별도의 중재 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="ceb7a-110">비즈니스용 Skype 서버 (프런트 엔드 풀 또는 독립 실행형 중재 서버의 중재 서버 collocated)와 게이트웨이 간의 연결은 트렁크 라는 논리적 연결로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="ceb7a-111">이 섹션의 항목에서는 SIP 트렁크에 연결 하는 경우 트렁크를 정의 하는 방법과 독립 실행형 중재 서버를 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="ceb7a-112">토폴로지 작성기에서 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="ceb7a-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="ceb7a-113">Collocated 역할을 프런트 엔드 풀에 추가 하거나 별도의 독립 실행형 중재 서버 풀을 정의 하 여 중재 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="ceb7a-114">프런트 엔드 풀에 중재 서버를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ceb7a-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="ceb7a-115">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="ceb7a-116">토폴로지 작성기의 콘솔 트리에서 프런트 엔드 풀을 정의 하려는 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="ceb7a-117">콘솔 트리에서 원하는 프런트 엔드 풀의 종류를 마우스 오른쪽 단추로 클릭 한 다음 **새 프런트 엔드 풀 ...** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="ceb7a-118">**Collocated 서버 역할 선택** 페이지에 도달할 때까지 **새 프런트 엔드 풀 정의** 마법사를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="ceb7a-119">**Collocated 서버 역할 선택**에서 **Collocate 중재 서버**옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ceb7a-120">선택한 프런트 엔드 풀 유형이 Enterprise Edition 이면 해당 프런트 엔드 풀의 모든 프런트 엔드 서버에 중재 서버 구성 요소가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="ceb7a-121">조정 서버에서 사용 하는 **다음 홉 풀** 은 중재 서버가 Collocated 된 프런트 엔드 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="ceb7a-122">조정 서버에서 사용 되는 **edge 풀** 은 중재 서버가 Collocated 인 프런트 엔드 풀과 연결 된 edge 풀과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="ceb7a-123">이 프론트 엔드 풀을 사용 하 여 PSTN으로 통화를 라우팅하기 위해 **기본값으로 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="ceb7a-124">하나 이상의 피어를 프런트 엔드 풀에 연결 하는 작업이 완료 되 면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ceb7a-125">엔터프라이즈 음성 배포 프로세스의 다음 단계로 진행 하기 전에 조정 서버 풀 (즉, 중재 서버 구성 요소가 collocated 인 프런트 엔드 풀)이 지정한 Fqdn을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="ceb7a-126">**Skype For Business Server 2015** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="ceb7a-127">독립 실행형 중재 서버를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ceb7a-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="ceb7a-128">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="ceb7a-129">토폴로지 작성기의 콘솔 트리에서 중재 서버를 정의 하려는 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="ceb7a-130">콘솔 트리에서 **중재 풀** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **중재 서버 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="ceb7a-131">**새 중재 풀 정의**에 중재 서버 풀 정규화 된 도메인 이름 (FQDN)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="ceb7a-132">다음으로 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="ceb7a-133">풀에 여러 중재 서버를 배포 하 여 고가용성을 제공 하려는 경우 **여러 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ceb7a-134">여러 중재 서버가 있는 중재 서버 풀을 지원 하기 위해 [배포](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="ceb7a-135">고가용성이 필요 하지 않으므로 풀에 하나의 중재 서버만 배포 하려면 **단일 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="ceb7a-136">다음 단계를 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="ceb7a-137">이전 단계에서 **컴퓨터 풀을 여러 개** 선택한 경우 **이 풀의 컴퓨터 정의** 항목에서 **컴퓨터 fqdn**을 클릭 하 고 풀의 각 서버에 대 한 fqdn을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="ceb7a-138">풀에 추가 하려는 다른 모든 중재 서버에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="ceb7a-139">풀의 모든 컴퓨터를 정의한 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="ceb7a-140">**다음 홉 선택** 페이지에서 **다음 홉 풀**을 클릭 하 고이 중재 서버 풀을 사용 하는 프런트 엔드 풀의 FQDN을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="ceb7a-141">**Edge 서버 선택** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="ceb7a-142">Enterprise Voice에 대해 사용 하도록 설정 된 외부 사용자에 게 PSTN 연결을 제공 하려는 경우 **이 중재 서버에서 사용 하는 Edge 풀 선택**아래에서이 중재 서버 풀을 사용 하는 edge 서버 풀의 FQDN을 클릭 하 여 해당 외부 사용자에 게 PSTN 연결을 제공 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="ceb7a-143">외부 사용자에 게 Enterprise Voice를 사용할 수 있도록 설정 하지 않으려는 경우 또는 내부 네트워크 외부에 있을 때 사용자에 게 PSTN 연결을 제공 하지 않으려는 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="ceb7a-144">**Skype For Business Server 2015** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="ceb7a-145">중재 서버 수신 대기 포트 정의</span><span class="sxs-lookup"><span data-stu-id="ceb7a-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="ceb7a-146">토폴로지 작성기를 사용 하 여 수신 대기 포트를 정의 하려면이 항목의 단계를 따르세요. 중재 서버 또는 풀은 게이트웨이 피어에서 들어오는 연결을 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="ceb7a-147">중재 서버 수신 대기 포트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="ceb7a-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="ceb7a-148">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype server 2015topology Builder**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="ceb7a-149">토폴로지 작성기의 콘솔 트리에서 **중재 풀** 노드를 확장 하 고 이전에 만든 중재 서버를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="ceb7a-150">기본적으로 중재 서버의 SIP 수신 대기 포트는 비즈니스용 Skype 서버의 TLS 트래픽에 대 한 5070이 고 피어 (예: 게이트웨이, PBXes 또는 SBCs)의 TLS 트래픽을 위한 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="ceb7a-151">TCP 포트는 기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-151">TCP port is disabled by default.</span></span> <span data-ttu-id="ceb7a-152">TLS를 지원 하지 않는 게이트웨이가 있는 경우 TCP 포트를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="ceb7a-153">중재 서버가 PSTN 게이트웨이에서 들어오는 연결을 허용 하는 원하는 TLS 또는 TCP 수신 대기 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ceb7a-154">**Tcp 포트 사용** 이 선택 되어 있지 않은 경우 tcp 포트 범위를 입력 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="ceb7a-155">이 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ceb7a-155">This setting is optional.</span></span>
  

