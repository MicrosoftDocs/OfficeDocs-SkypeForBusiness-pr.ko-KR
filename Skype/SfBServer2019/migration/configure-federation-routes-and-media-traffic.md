---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 페더레이션은 개별 조직의 사용자가 네트워크 경계에서 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간 신뢰 관계입니다. 파일럿 풀로 마이그레이션한 후에는 이전 버전에 지 서버의 페더레이션 경로에서 비즈니스용 Skype 서버 2019에 지 서버의 페더레이션 경로로 전환 해야 합니다.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754038"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="acf4d-104">페더레이션 경로 및 미디어 트래픽 구성</span><span class="sxs-lookup"><span data-stu-id="acf4d-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="acf4d-105">페더레이션은 개별 조직의 사용자가 네트워크 경계에서 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간 신뢰 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="acf4d-106">파일럿 풀로 마이그레이션한 후에는 이전 버전에 지 서버의 페더레이션 경로에서 비즈니스용 Skype 서버 2019에 지 서버에 대 한 페더레이션 경로로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="acf4d-107">다음 절차에 따라 단일 사이트 배포에 대해 이전 버전의에 지 서버 및 디렉터에서 비즈니스용 Skype 서버 2019 Edge 서버로의 페더레이션 경로와 미디어 트래픽 경로를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="acf4d-108">페더레이션 경로 및 미디어 트래픽 경로를 변경 하려면 비즈니스용 Skype 서버 2019 및 이전 버전에 지 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="acf4d-109">이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="acf4d-110">사용자 활동이 최소로 예상되는 시간으로 중단 시간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="acf4d-111">또한 최종 사용자에게 충분한 알림을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="acf4d-112">이 중단에 맞게 계획하고 조직 내에서 적당한 기대치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="acf4d-113">레거시에 지 서버가 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스에 대해 동일한 FQDN을 사용 하도록 구성 되어 있는 경우이 섹션의 절차는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="acf4d-114">레거시에 지 서비스가 동일한 FQDN을 사용 하도록 구성 되어 있는 경우 비즈니스용 Skype 서버 2019에 지 서버에서 페더레이션을 사용 하도록 설정 하기 전에 먼저 모든 사용자를 마이그레이션한 다음 이전 버전에 지 서버를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="acf4d-115">XMPP 페더레이션이 비즈니스용 Skype 서버 2019에 지 서버를 통해 라우팅되는 경우, 모든 사용자가 비즈니스용 Skype 서버 2019로 이동 될 때까지 이전 버전의 사용자는 XMPP 페더레이션 파트너와 통신할 수 없으며 xmpp 정책 및 인증서가 구성 되었으며 XMPP 페더레이션 파트너는 비즈니스용 Skype 서버 2019에 구성 되어 있습니다. , 마지막으로 DNS 항목이 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="acf4d-116">비즈니스용 Skype 서버 2019 사이트에서 레거시 페더레이션 연결을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="acf4d-117">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기의 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="acf4d-118">왼쪽 창에서 **비즈니스용 Skype 서버**바로 아래에 있는 사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="acf4d-119">사이트에서 마우스 오른쪽 단추를 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="acf4d-120">왼쪽 창에서 **페더레이션 경로**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="acf4d-121">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용** 확인란의 선택을 취소 하 여 레거시 환경을 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="acf4d-122">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="acf4d-123">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="acf4d-124">**동작** 메뉴에서 **토폴로지 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="acf4d-125">**다음** 을 클릭 하 여 게시 프로세스를 완료 하 고 게시 프로세스가 완료 되 면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="acf4d-126">레거시 에지 서버를 비페더레이션 에지 서버로 구성하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="acf4d-127">왼쪽 창에서 레거시 설치 노드로 이동한 다음에 **지 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="acf4d-128">에지 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="acf4d-129">왼쪽 창에서 **일반**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="acf4d-130">**이에 지 풀에 페더레이션 사용 (포트 5061)** 확인란의 선택을 취소 하 고 **확인** 을 선택 하 여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="acf4d-131">**동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="acf4d-132">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="acf4d-133">토폴로지 작성기에서 레거시에 지 서버에 대 한 페더레이션이 사용 되지 않도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="acf4d-134">레거시에 지 서버에서 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="acf4d-135">개인 키를 사용 하 여 레거시에 지 서버에서 외부 액세스 프록시 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="acf4d-136">비즈니스용 Skype 서버 2019에 지 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="acf4d-137">액세스 프록시 외부 인증서를에 지 서버의 비즈니스용 Skype 서버 2019 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="acf4d-138">비즈니스용 Skype 서버 2019에 지 서버의 내부 인터페이스 인증서를 신뢰할 수 있는 CA에서 요청 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="acf4d-139">비즈니스용 Skype 서버 2019에 지 서버를 사용 하도록 이전 버전의 페더레이션 경로를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="acf4d-140">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype 서버 2019** 노드로 이동한 다음에 **지 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="acf4d-141">에지 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="acf4d-142">왼쪽 창에서 **일반**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="acf4d-143">**이에 지 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 하 고 **확인** 을 클릭 하 여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="acf4d-144">**동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="acf4d-145">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="acf4d-146">토폴로지 작성기에서 **페더레이션 (포트 5061)** 이 **사용** 으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="acf4d-147">비즈니스용 Skype 서버 2019에 지 서버 페더레이션 다음 홉을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="acf4d-148">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype 서버 2019** 노드로 이동한 다음에 **지 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="acf4d-149">노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="acf4d-150">**일반** 페이지의 **다음 홉 선택**에서 비즈니스용 Skype 서버 2019 풀 드롭다운 목록에서를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="acf4d-151">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="acf4d-152">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="acf4d-153">**동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="acf4d-154">비즈니스용 Skype 서버 2019에 지 서버 아웃 바운드 미디어 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="acf4d-155">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype 서버 2019** 노드로 이동한 다음 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="acf4d-156">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="acf4d-157">**연결** 섹션에서 **에지 풀 연결(미디어 구성 요소)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="acf4d-158">드롭다운 상자에서 비즈니스용 Skype 서버 2019에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="acf4d-159">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="acf4d-160">비즈니스용 Skype 서버 2019에 지 서버 페더레이션을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="acf4d-161">토폴로지 작성기의 왼쪽 창에서 **비즈니스용 Skype 서버 2019** 노드로 이동한 다음에 **지 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="acf4d-162">노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="acf4d-163">페더레이션은 단일에 지 풀에 대해서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="acf4d-164">에지 풀이 여러 개인 경우 페더레이션 에지 풀로 사용할 항목을 하나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="acf4d-165">**일반** 페이지에서 **이에 지 풀에 페더레이션 사용 (포트 5061)** 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="acf4d-166">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="acf4d-167">사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="acf4d-168">사이트에서 마우스 오른쪽 단추를 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="acf4d-169">왼쪽 창에서 **페더레이션 경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="acf4d-170">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 비즈니스용 Skype 서버 2019에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="acf4d-171">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="acf4d-172">다중 사이트 배포의 경우 각 사이트에서 이 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="acf4d-173">에지 서버 구성 변경 사항을 게시하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="acf4d-174">**토폴로지 작성기**에서 최상위 노드인 **비즈니스용 Skype 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="acf4d-175">**동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="acf4d-176">배포의 모든 풀에 대해 Active Directory 복제가 발생할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acf4d-177">다음과 같은 메시지가 표시 될 수 있습니다. **경고: 토폴로지에 두 개 이상의 페더레이션에 지 서버가 포함 되어 있습니다. 이 문제는 제품의 최신 버전으로 마이그레이션하는 동안 발생할 수 있습니다. 이 경우에는 하나의에 지 서버만 페더레이션에 사용 됩니다. 외부 DNS SRV 레코드가 올바른에 지 서버를 가리키는지 확인 합니다. 동시에 활성화 되도록 여러 페더레이션에 지 서버를 배포 하려는 경우 (즉 마이그레이션 시나리오는 아님) 모든 페더레이션 파트너가 비즈니스용 Skype 서버를 사용 하 고 있는지 확인 합니다. 외부 DNS SRV 레코드가 모든 페더레이션 사용에 지 서버를 나열 하는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="acf4d-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="acf4d-178">이 경고는 예상된 경고이므로 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="acf4d-179">비즈니스용 Skype 서버 2019에 지 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="acf4d-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="acf4d-180">모든 비즈니스용 Skype 서버 2019에 지 서버를 온라인으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="acf4d-181">외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정을 업데이트 하 여 외부 액세스에 대 한 SIP 트래픽 (일반적으로 포트 443)과 페더레이션 (일반적으로 포트 5061)을 레거시에 지 서버가 아닌 비즈니스용 Skype 서버 2019에 지 서버에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="acf4d-182">하드웨어 부하 분산 장치를 사용 하지 않는 경우 새로운 비즈니스용 Skype 서버 액세스에 지 서버로 확인 되도록 페더레이션에 대 한 DNS A 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="acf4d-183">이 작업을 최소화 하 여이 작업을 수행 하려면 외부 비즈니스용 skype 서버 액세스에 지 FQDN에 대 한 TLL 값을 줄여 DNS가 새 비즈니스용 Skype 서버 액세스에 지를 가리키도록 업데이트 되 면 페더레이션 및 원격 액세스가 빠르게 업데이트 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="acf4d-184">각에 지 서버 컴퓨터에서 **비즈니스용 Skype 서버 액세스에 지** 를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="acf4d-185">각 레거시에 지 서버 컴퓨터의 **관리 도구**에서 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="acf4d-186">서비스 목록에서 **비즈니스용 Skype 서버 액세스에 지**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="acf4d-187">서비스 이름을 마우스 오른쪽 단추로 클릭한 후 **중지**를 선택하여 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="acf4d-188">시작 유형을 **사용 안 함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="acf4d-189">**확인**을 클릭하여 **속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="acf4d-189">Click **OK** to close the **Properties** window.</span></span> 
    

