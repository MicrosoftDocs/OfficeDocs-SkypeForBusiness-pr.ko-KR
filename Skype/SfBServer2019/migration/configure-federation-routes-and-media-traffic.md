---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 페더레이션은 서로 다른 조직의 사용자가 네트워크 경계를 통해 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간의 신뢰 관계입니다. 파일럿 풀로 마이그레이션한 후에는 이전 버전의 Edge 서버의 페더레이션 경로에서 비즈니스용 Skype 서버 2019 Edge 서버의 페더레이션 경로로 전환 해야 합니다.
ms.openlocfilehash: 6b76932c8b988dbed61cba1470f32a51f6585536
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196969"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="b0903-104">페더레이션 경로 및 미디어 트래픽 구성</span><span class="sxs-lookup"><span data-stu-id="b0903-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="b0903-105">페더레이션은 서로 다른 조직의 사용자가 네트워크 경계를 통해 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간의 신뢰 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="b0903-106">파일럿 풀로 마이그레이션한 후에는 이전 버전의 Edge 서버의 페더레이션 경로에서 비즈니스용 Skype 서버 2019 Edge 서버의 페더레이션 경로로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="b0903-107">단일 사이트 배포의 경우 다음 절차를 사용 하 여 이전 버전의 Edge 서버의 페더레이션 경로와 미디어 트래픽 경로를 전환 하 고, 사용자의 비즈니스용 Skype Server 2019 Edge 서버로 이사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0903-108">페더레이션 경로 및 미디어 트래픽 경로를 변경 하려면 비즈니스용 Skype Server 2019 및 이전 버전에 지 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="b0903-109">또한이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="b0903-110">최소한의 사용자 작업을 예상 하는 동안 가동 중지 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="b0903-111">또한 최종 사용자에 게 충분 한 알림을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="b0903-112">이 중단에 대 한 계획을 수립 하 고 조직 내에서 적절 한 기대치를 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0903-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b0903-113">레거시 Edge 서버에서 액세스 경계 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스에 대해 동일한 FQDN을 사용 하도록 구성 된 경우이 섹션의 절차는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="b0903-114">레거시 Edge 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우에는 먼저 모든 사용자를 마이그레이션한 다음 비즈니스용 Skype Server 2019 Edge 서버에서 페더레이션을 사용 하기 전에 이전 버전 Edge 서버의 역할을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b0903-115">XMPP 페더레이션이 비즈니스용 Skype Server 2019 Edge 서버를 통해 라우팅되는 경우 모든 사용자가 비즈니스용 Skype Server 2019, XMPP 정책으로 이동할 때까지 이전 버전의 사용자는 XMPP 페더레이션 파트너와 통신할 수 없습니다. 인증서가 구성 되 고 XMPP 페더레이션 파트너가 비즈니스용 Skype 서버 2019에 구성 되어 있으며, 마지막으로 DNS 항목이 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="b0903-116">비즈니스용 Skype Server 2019 사이트에서 레거시 페더레이션 연결을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="b0903-117">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기의 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="b0903-118">왼쪽 창에서 **비즈니스용 Skype 서버**바로 아래에 있는 사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="b0903-119">사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="b0903-120">왼쪽 창에서 **페더레이션 경로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="b0903-121">**사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용** 확인란의 선택을 취소 하 여 레거시 환경을 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="b0903-122">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="b0903-123">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="b0903-124">**작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="b0903-125">**다음** 을 클릭 하 여 게시 프로세스를 완료 한 다음 게시 프로세스가 완료 되 면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="b0903-126">레거시 Edge 서버를 비 페더레이션에 지 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="b0903-127">왼쪽 창에서 레거시 설치 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b0903-128">Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b0903-129">왼쪽 창에서 **일반** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="b0903-130">**이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 취소 하 고 **확인** 을 선택 하 여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="b0903-131">**작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b0903-132">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="b0903-133">토폴로지 작성기에서 레거시 Edge 서버의 페더레이션을 사용할 수 없도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="b0903-134">레거시 Edge 서버에서 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="b0903-135">개인 키를 사용 하 여 외부 액세스 프록시 인증서를 레거시 Edge 서버에서 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="b0903-136">비즈니스용 Skype 서버 2019 Edge 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="b0903-137">액세스 프록시 외부 인증서를 Edge 서버의 비즈니스용 Skype 서버 2019 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="b0903-138">비즈니스용 Skype Server 2019 Edge 서버의 내부 인터페이스 인증서는 신뢰할 수 있는 CA에서 요청 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="b0903-139">비즈니스용 Skype Server 2019 Edge 서버를 사용 하도록 이전 버전의 페더레이션 경로를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="b0903-140">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype Server 2019** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b0903-141">Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b0903-142">왼쪽 창에서 **일반** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="b0903-143">**이 Edge 풀에 페더레이션 사용 확인란 (포트 5061)** 을 선택한 다음 **확인** 을 클릭 하 여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="b0903-144">**작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b0903-145">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="b0903-146">토폴로지 작성기에서 **페더레이션 (포트 5061)** 이 **사용** 으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="b0903-147">비즈니스용 Skype 서버 2019 Edge 서버 페더레이션에서 다음 홉을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="b0903-148">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype Server 2019** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b0903-149">노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="b0903-150">**일반** 페이지의 **다음 홉 선택**아래에 있는 비즈니스용 Skype 서버 2019 풀 드롭다운 목록에서을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="b0903-151">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="b0903-152">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="b0903-153">**작업** 메뉴에서 **토폴로지 게시** 를 클릭 하 고 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="b0903-154">비즈니스용 Skype 서버 2019 Edge 서버 아웃 바운드 미디어 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="b0903-155">토폴로지 작성기에서 왼쪽 창에 있는 **비즈니스용 Skype Server 2019** 노드로 이동한 다음, **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래에 있는 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="b0903-156">풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b0903-157">**연결** 섹션에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="b0903-158">드롭다운 상자에서 비즈니스용 Skype 서버 2019 Edge 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="b0903-159">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="b0903-160">비즈니스용 Skype 서버 2019 Edge 서버 페더레이션을 켜려면</span><span class="sxs-lookup"><span data-stu-id="b0903-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="b0903-161">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype Server 2019** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="b0903-162">노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b0903-163">페더레이션은 단일 Edge 풀에 대해서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="b0903-164">Edge 풀이 여러 개 있는 경우 하나를 선택 하 여 페더레이션 가장자리 풀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="b0903-165">**일반** 페이지에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="b0903-166">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="b0903-167">사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="b0903-168">사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="b0903-169">왼쪽 창에서 **페더레이션 경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="b0903-170">**사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 비즈니스용 Skype 서버 2019 Edge 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="b0903-171">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="b0903-172">여러 사이트 배포의 경우 각 사이트에서이 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="b0903-173">Edge 서버 구성 변경 내용을 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="b0903-174">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="b0903-175">**작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="b0903-176">Active Directory 복제가 배포의 모든 풀에 발생 하는 것을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0903-177">다음과 같은 메시지가 표시 될 수 있습니다. **경고: 토폴로지에 두 개 이상의 페더레이션된 Edge 서버가 있습니다. 이 문제는 최신 버전의 제품으로 마이그레이션하는 동안 발생할 수 있습니다. 이 경우에는 오직 하나의 Edge 서버만 페더레이션에 사용 됩니다. 외부 DNS SRV 레코드가 올바른 Edge 서버를 가리키는지 확인 합니다. 동시에 여러 페더레이션에 지 서버 (마이그레이션 시나리오는 아님)를 배포 하려는 경우 모든 페더레이션 파트너가 비즈니스용 Skype 서버를 사용 하 고 있는지 확인 합니다. 외부 DNS SRV 레코드에 모든 페더레이션 가능 Edge 서버가 나열 되는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0903-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="b0903-178">이 경고는 예상 되는 것으로 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="b0903-179">비즈니스용 Skype 서버 2019 Edge 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="b0903-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="b0903-180">모든 비즈니스용 Skype 서버 2019 Edge 서버를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="b0903-181">외부 통신 라우팅 규칙 또는 하드웨어 부하 분산 장치 설정을 업데이트 하 여 외부 액세스 (일반적으로 포트 443) 및 페더레이션 (일반적으로 포트 5061)에 대 한 SIP 트래픽을 레거시 Edge 서버 대신 비즈니스용 Skype 서버 2019 Edge 서버에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0903-182">하드웨어 부하 분산이 없는 경우 새 비즈니스용 Skype 서버 액세스에 지 서버를 확인 하려면 페더레이션에 대 한 DNS A 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="b0903-183">이 작업을 최소화 하기 위해 DNS가 비즈니스용 skype 서버 액세스에 새 Edge를 가리키도록 업데이트 되 면 페더레이션 및 원격 액세스가 빠르게 업데이트 되도록 외부 비즈니스용 Skype 서버 액세스에 지 FQDN에 대 한 TLL 값을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="b0903-184">각 Edge 서버 컴퓨터에서 **비즈니스용 Skype Server Access Edge** 를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="b0903-185">각 레거시 Edge 서버 컴퓨터에서 **관리 도구**를 통해 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="b0903-186">서비스 목록에서 **비즈니스용 Skype 서버 액세스 Edge**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="b0903-187">서비스 이름을 마우스 오른쪽 단추로 클릭 하 고 **중지** 를 선택 하 여 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="b0903-188">시작 유형을 **사용 안 함으로**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="b0903-189">**확인** 을 클릭 하 여 **속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0903-189">Click **OK** to close the **Properties** window.</span></span> 
    

