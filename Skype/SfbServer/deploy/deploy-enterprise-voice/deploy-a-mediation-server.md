---
title: 비즈니스용 Skype 서버에서 토폴로지 작성기에서 중재 서버 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버에서 토폴로지 작성기에서 중재 서버를 정의하고 배포하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836918"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="efb9e-103">비즈니스용 Skype 서버에서 토폴로지 작성기에서 중재 서버 배포</span><span class="sxs-lookup"><span data-stu-id="efb9e-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="efb9e-104">**요약:** 비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버를 정의하고 배포하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="efb9e-105">프런트 엔드 풀에서는 Enterprise Voice, 전화 접속 회의 및 고급 Enterprise Voice 응용 프로그램(응답 그룹 응용 프로그램, 통화 파킹 응용 프로그램, CAC(통화 가능 제어) 등)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="efb9e-106">중재 서버의 기능은 프런트 엔드 서버에 기본 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="efb9e-107">별도의 독립 실행형 중재 서버는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="efb9e-108">단, ITSP(인터넷 전화 통신 서비스 공급자)에 대한 SBC(세션 경계 컨트롤러)에 연결하도록 SIP 트렁크를 구성하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="efb9e-109">Enterprise Voice 인프라를 SIP 트렁크 공급자에 연결하려면 별도의 중재 서버를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="efb9e-110">비즈니스용 Skype 서버(프런트 엔드 풀에 함께 함께 있는 중재 서버 또는 독립 실행형 중재 서버)와 게이트웨이 간의 연결은 트렁크라는 논리적 연결로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="efb9e-111">이 섹션의 항목은 트렁크를 정의하는 방법과 SIP 트렁크에 연결하기 위해 독립 실행형 중재 서버를 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="efb9e-112">토폴로지 작성기에서 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="efb9e-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="efb9e-113">중재 서버를 프런트 엔드 풀에 함께 있는 역할로 추가하거나 별도의 독립 실행형 중재 서버 풀을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="efb9e-114">중재 서버를 프런트 엔드 풀에 추가</span><span class="sxs-lookup"><span data-stu-id="efb9e-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="efb9e-115">토폴로지 작성기 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype 서버 2015Topology Builder를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="efb9e-116">토폴로지 작성기의 콘솔 트리에서 프런트 엔드 풀을 정의할 사이트의 이름을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="efb9e-117">콘솔 트리에서 원하는 프런트 엔드 풀 유형을 마우스 오른쪽 단추로 클릭한 다음 새 프런트 엔드 **풀을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="efb9e-118">**배치된 서버 역할 선택** 페이지에 도달할 때까지 **새 프런트 엔드 풀 정의** 마법사를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="efb9e-119">함께 **있는 서버 역할** 선택에서 중재 서버 **Collocate 옵션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="efb9e-120">선택한 프런트 엔드 풀의 유형이 Enterprise Edition인 경우 중재 서버 구성 요소가 해당 프런트 엔드 풀의 모든 프런트 엔드 서버에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="efb9e-121">중재 **서버에서** 사용하는 다음 홉 풀은 중재 서버가 함께 있는 프런트 엔드 풀이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="efb9e-122">중재 **서버에서** 사용하는 에지 풀은 중재 서버가 함께 함께 사용되는 프런트 엔드 풀과 연결된 에지 풀과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="efb9e-123">이 **프런트** 엔드 풀을 사용하여 통화를 PSTN으로 라우팅하려면 기본값으로 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="efb9e-124">하나 **이상의** 피어를 프런트 엔드 풀에 연결한 후 완료를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="efb9e-125">Enterprise Voice 배포 프로세스의 다음 단계를 진행하기 전에 중재 서버 풀(즉, 중재 서버 구성 요소가 배치된 프런트 엔드 풀)이 지정한 FQDNS를 사용하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="efb9e-126">비즈니스용 **Skype 서버 2015** 노드를 마우스 오른쪽 단추로 클릭한 다음 **토폴로지 게시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="efb9e-127">독립 실행형 중재 서버를 추가하는 경우</span><span class="sxs-lookup"><span data-stu-id="efb9e-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="efb9e-128">토폴로지 작성기 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype 서버 2015Topology Builder를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="efb9e-129">토폴로지 작성기의 콘솔 트리에서 중재 서버를 정의할 사이트의 이름을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="efb9e-130">콘솔 트리에서 중재 풀  노드를 마우스 오른쪽 단추로 클릭한 다음 **중재 서버 풀을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="efb9e-131">새 **중재 풀 정의에서** 중재 서버 풀 FQDN(정식 도메인 이름)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="efb9e-132">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="efb9e-133">풀에 여러 중재 서버를 배포하여 고가용성을 제공하려면 여러 컴퓨터 **풀을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="efb9e-134">중재 [서버가](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 여러 개 있는 중재 서버 풀을 지원하려면 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="efb9e-135">고가용성을 요구하지 않는 풀에 중재 서버를 하나만 배포하려면 단일 컴퓨터 **풀을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="efb9e-136">다음 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="efb9e-137">이전 단계에서 **다중 컴퓨터 풀** 을 선택한 경우 **이 풀의 컴퓨터 정의** 항목에서 **컴퓨터 FQDN** 을 클릭하고 풀의 각 서버에 대한 FQDN을 입력한 다음 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="efb9e-138">풀에 추가할 다른 모든 중재 서버에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="efb9e-139">풀의 모든 컴퓨터를 정의했으면 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="efb9e-140">다음 **홉** 선택 페이지에서 다음 홉 풀을 클릭하고 **이** 중재 서버 풀을 사용할 프런트 엔드 풀의 FQDN을 클릭한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="efb9e-141">**에지 서버 선택** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="efb9e-142">Enterprise Voice 사용하도록 설정된 외부 사용자에게 PSTN 연결을 제공하려면 이 중재 서버에서 사용하는 에지 풀 선택에서 이 중재 서버 풀을 사용하여 해당 외부 사용자에게 PSTN 연결을 제공하는 에지 서버 풀의 FQDN을 클릭한 후 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="efb9e-143">외부 사용자가 내부 네트워크 외부에 있는 Enterprise Voice PSTN 연결을 제공하지 않을 경우 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="efb9e-144">비즈니스용 **Skype 서버 2015** 노드를 마우스 오른쪽 단추로 클릭한 다음 **토폴로지 게시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="efb9e-145">중재 서버 수신 포트 정의</span><span class="sxs-lookup"><span data-stu-id="efb9e-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="efb9e-146">토폴로지 작성기에서 이 항목의 단계에 따라 중재 서버 또는 풀이 게이트웨이 피어로부터 들어오는 연결을 수락하는 수신 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="efb9e-147">중재 서버 수신 포트를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="efb9e-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="efb9e-148">토폴로지 작성기 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype 서버 2015Topology Builder를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="efb9e-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="efb9e-149">토폴로지 작성기의 콘솔 트리에서  중재 풀 노드를 확장하고 이전에 만든 중재 서버를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="efb9e-150">기본적으로 중재 서버의 SIP 수신 포트는 비즈니스용 Skype 서버의 TLS 트래픽에 대해 5070, 피어(예: 게이트웨이, PBX 또는 SBC)의 TLS 트래픽의 경우 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="efb9e-151">TCP 포트는 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-151">TCP port is disabled by default.</span></span> <span data-ttu-id="efb9e-152">게이트웨이가 TLS를 지원하지 않는 경우 TCP 포트를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="efb9e-153">중재 서버가 PSTN 게이트웨이에서 들어오는 연결을 수락할 원하는 TLS 또는 TCP 수신 포트 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="efb9e-154">**TCP 포트 사용** 을 선택하지 않은 경우 TCP 포트 범위를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="efb9e-155">이 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="efb9e-155">This setting is optional.</span></span>
  

