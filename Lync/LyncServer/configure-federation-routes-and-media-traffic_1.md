---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af8228a7537f1bbef4e92af852834459281a817
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728178"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="8beb0-102">페더레이션 경로 및 미디어 트래픽 구성</span><span class="sxs-lookup"><span data-stu-id="8beb0-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="8beb0-103">페더레이션은 서로 다른 조직의 사용자가 네트워크 경계를 통해 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간의 신뢰 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="8beb0-104">Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 Microsoft Office Communications Server 2007 R2 Edge 서버의 페더레이션 경로에서 Lync Server 2013 Edge 서버의 페더레이션 경로로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="8beb0-105">단일 사이트 배포의 경우 다음 절차를 사용 하 여 Office Communications Server 2007 R2 Edge 서버와 디렉터에서 Lync Server 2013 Edge 서버로 페더레이션 경로와 미디어 트래픽 경로를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="8beb0-106">페더레이션 경로와 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Office Communications Server 2007 R2 Edge 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="8beb0-107">또한이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="8beb0-108">최소한의 사용자 작업을 예상 하는 동안 가동 중지 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="8beb0-109">또한 최종 사용자에 게 충분 한 알림을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="8beb0-110">이 중단에 대 한 계획을 수립 하 고 조직 내에서 적절 한 기대치를 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="8beb0-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="8beb0-111">레거시 Office 통신 서버 2007 R2 Edge 서버가 액세스 경계 서비스, 웹 회의 Edge 서비스 및 A/V Edge 서비스에 대해 동일한 FQDN을 사용 하도록 구성 된 경우이 섹션의 절차는 페더레이션 설정을 Lync Server 2013 Edge 서버로 전환 하는 것이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="8beb0-112">레거시 Edge 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우 먼저 Office Communications Server 2007 R2에서 Lync Server 2013로 모든 사용자를 마이그레이션한 다음, 페더레이션 사용을 설정 하기 전에 Office Communications Server 2007 R2 Edge 서버의 서비스를 해제 해야 합니다. Lync Server 2013 Edge 서버.</span><span class="sxs-lookup"><span data-stu-id="8beb0-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="8beb0-113">자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8beb0-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8beb0-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Lync Server 2013으로 나머지 사용자 이동</A></span><span class="sxs-lookup"><span data-stu-id="8beb0-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="8beb0-115">"서버 및 서버 역할 제거"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="8beb0-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="8beb0-116">XMPP 페더레이션이 Lync Server 2013 Edge 서버를 통해 라우팅된 경우, 모든 사용자가 Lync Server 2013, XMPP 정책으로 이동 될 때까지 레거시 Office Communications Server 2007 R2 사용자는 XMPP 페더레이션 파트너와 통신할 수 없습니다. 인증서가 구성 되 고 XMPP 페더레이션 파트너가 Lync Server 2013에 구성 되어 있고 마지막으로 DNS 항목이 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="8beb0-117">서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="8beb0-118">또한 서버 역할 추가에 대 한 적절 한 사용자 권한 및 사용 권한을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="8beb0-119">자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서의 [Lync Server 2013에서 설정 위임을](lync-server-2013-delegate-setup-permissions.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8beb0-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="8beb0-120">다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="8beb0-121">Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="8beb0-122">토폴로지 작성기를 사용 하 여 파일럿 풀 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="8beb0-123">왼쪽 창에서 사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="8beb0-124">사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="8beb0-125">왼쪽 창에서 **페더레이션 경로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="8beb0-126">사이트 페더레이션 경로 할당에서 **SIP 페더레이션 사용** 옆에 있는 확인란의 선택을 취소 하 여 **BackCompatSite**를 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="8beb0-127">![속성 편집 대화 상자, 페더레이션 경로](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로")</span><span class="sxs-lookup"><span data-stu-id="8beb0-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="8beb0-128">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="8beb0-129">**토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="8beb0-130">**작업** 메뉴에서 **토폴로지 게시** 를 클릭 하 고 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="8beb0-131">레거시 Edge 서버를 비 페더레이션에 지 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="8beb0-132">**토폴로지 작성기**의 **동작** 메뉴에서 **Office Communications Server 2007 R2 토폴로지 병합**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="8beb0-133">계속하려면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="8beb0-134">**Edge 설정 지정**에서 현재 페더레이션에 대해 구성 된 **EDGE Server 내부 FQDN** 을 선택한 다음 **변경을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="8beb0-135">![OCS 2007 R2 토폴로지 병합, 에지 설정 지정](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 토폴로지 병합, 에지 설정 지정")</span><span class="sxs-lookup"><span data-stu-id="8beb0-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="8beb0-136">**다음** 을 클릭 하 고 **외부에 지 지정** 페이지에 도달할 때까지 기본 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="8beb0-137">![토폴로지 작성기 외부 에지 지정 페이지](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "토폴로지 작성기 외부 에지 지정 페이지")</span><span class="sxs-lookup"><span data-stu-id="8beb0-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="8beb0-138">**외부에 지 지정**에서 **이 Edge 풀은 페더레이션 및 공용 IM 연결에 사용 됨** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="8beb0-139">이렇게 하면 BackCompatSite에 대 한 페더레이션 연결이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8beb0-140">이 단계는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-140">This step is important.</span></span> <span data-ttu-id="8beb0-141">레거시 페더레이션 연결을 제거 하려면이 옵션을 선택 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="8beb0-142">**다음** 을 클릭 하 고 마법사의 나머지 페이지에 대 한 기본 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="8beb0-143">**요약**에서 **다음** 을 클릭 하 여 토폴로지 병합을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="8beb0-144">**상태** 열에서 값이 **성공**인지 확인 한 다음 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="8beb0-145">**작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="8beb0-146">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="8beb0-147">![병합된 후의 사이트가 표시된 토폴로지 작성기](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "병합된 후의 사이트가 표시된 토폴로지 작성기")</span><span class="sxs-lookup"><span data-stu-id="8beb0-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="8beb0-148">앞의 그림과 같이 **사이트 페더레이션 경로 할당** 아래에 있는 **SIP 페더레이션** 이 **사용 안 함으로**설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="8beb0-149">Lync Server 2013 Edge 서버에서 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="8beb0-150">개인 키를 사용 하 여 외부 액세스 프록시 인증서를 레거시 Office Communications Server 2007 R2 Edge 서버에서 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="8beb0-151">Lync Server 2013 Edge 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="8beb0-152">액세스 프록시 외부 인증서를 Edge 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="8beb0-153">Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 변경 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="8beb0-154">Lync Server 2013 Edge 서버를 사용 하도록 Office Communications Server 2007 R2 페더레이션 경로를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="8beb0-155">Office Communications Server 2007 R2 Standard Edition server 또는 프런트 엔드 서버에서 Office Communications Server 2007 R2 관리 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="8beb0-156">왼쪽 창에서 최상위 노드를 확장 한 다음 **포리스트** 노드를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="8beb0-157">**속성**을 선택 하 고 **전역 속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="8beb0-158">**페더레이션** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="8beb0-159">페더레이션 및 공용 IM 연결을 사용 하도록 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="8beb0-160">Lync Server 2013 Edge 서버의 FQDN을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="8beb0-161">![OCS 전역 속성, 페더레이션 탭](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 전역 속성, 페더레이션 탭")</span><span class="sxs-lookup"><span data-stu-id="8beb0-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="8beb0-162">Lync Server 2013 Edge 서버 페더레이션을 켜려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="8beb0-163">토폴로지 작성기의 왼쪽 창에서 Lync Server 2013 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="8beb0-164">노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8beb0-165">페더레이션은 단일 Edge 풀에 대해서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="8beb0-166">Edge 풀이 여러 개 있는 경우 하나를 선택 하 여 페더레이션 가장자리 풀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="8beb0-167">**일반** 페이지에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="8beb0-168">![속성 편집, 일반, 에지 페더레이션 사용](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "속성 편집, 일반, 에지 페더레이션 사용")</span><span class="sxs-lookup"><span data-stu-id="8beb0-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="8beb0-169">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="8beb0-170">다음으로, 사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="8beb0-171">사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="8beb0-172">왼쪽 창에서 **페더레이션 경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="8beb0-173">**사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync server 2013 Edge 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="8beb0-174">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="8beb0-175">![속성 편집, 일반, 에지 풀 연결](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "속성 편집, 일반, 에지 풀 연결")</span><span class="sxs-lookup"><span data-stu-id="8beb0-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="8beb0-176">여러 사이트 배포의 경우 각 사이트에서이 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="8beb0-177">Lync Server 2013 Edge 서버 아웃 바운드 미디어 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="8beb0-178">**토폴로지 작성기**에서 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 Lync Server 2013 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="8beb0-179">풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="8beb0-180">**연결** 섹션에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="8beb0-181">드롭다운 상자에서 Lync Server 2013 Edge 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="8beb0-182">![속성 편집 대화 상자, 에지 풀 연결](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "속성 편집 대화 상자, 에지 풀 연결")</span><span class="sxs-lookup"><span data-stu-id="8beb0-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="8beb0-183">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="8beb0-184">Edge 서버 구성 변경 내용을 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="8beb0-185">**토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="8beb0-186">**작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="8beb0-187">Active Directory 복제가 배포의 모든 풀에 발생 하는 것을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8beb0-188">다음과 같은 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-188">You may see the following message:</span></span><BR><span data-ttu-id="8beb0-189"><STRONG>경고: 토폴로지에 두 개 이상의 페더레이션된 Edge 서버가 있습니다. 이 문제는 최신 버전의 제품으로 마이그레이션하는 동안 발생할 수 있습니다. 이 경우에는 오직 하나의 Edge 서버만 페더레이션에 사용 됩니다. 외부 DNS SRV 레코드가 올바른 Edge 서버를 가리키는지 확인 합니다. 동시에 여러 페더레이션에 지 서버를 배포 하려는 경우 (즉 마이그레이션 시나리오가 아닌 경우) 모든 페더레이션 파트너가 Office Communications Server 2007 R2 또는 Lync Server를 사용 하 고 있는지 확인 합니다. 외부 DNS SRV 레코드에 모든 페더레이션 가능 Edge 서버가 나열 되는지 확인 합니다.</STRONG></span><span class="sxs-lookup"><span data-stu-id="8beb0-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="8beb0-190">이 경고는 예상 되는 것으로 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="8beb0-191">외부 사용자에 대 한 페더레이션 및 원격 액세스를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="8beb0-192">Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="8beb0-193">페더레이션 및 원격 액세스의 상태를 확인 하려면 명령줄에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="8beb0-194">페더레이션 및 원격 액세스를 사용 하도록 설정 하려면 명령줄에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="8beb0-195">이러한 cmdlet에 대 한 자세한 내용은 다음 항목을 참조 하세요. [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) 및 [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="8beb0-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="8beb0-196">복제가 완료 될 때까지 기다렸다가 Lync Server 2013 Edge 서버를 온라인 상태로 전환 하 고 페더레이션 및 외부 액세스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="8beb0-197">Lync Server 2013 Edge 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="8beb0-198">모든 Lync Server 2013 Edge 서버를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="8beb0-199">외부에 지 서버 대신 외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정 (일반적으로 포트 443) 및 페더레이션 (일반적으로 포트 5061)에 대 한 SIP 트래픽을 Lync Server 2013 Edge 서버에 전송 하도록 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8beb0-200">하드웨어 부하 분산이 없는 경우 새 Lync Server 액세스 Edge 서버를 확인 하려면 페더레이션에 대 한 DNS A 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="8beb0-201">최소 중단으로이 작업을 수행 하려면 DNS가 새 Lync Server 액세스 Edge 서버를 가리키도록 업데이트 될 때 페더레이션 및 원격 액세스가 빠르게 업데이트 되도록 외부 Lync Server 액세스에 지 FQDN에 대 한 TTL 값을 줄이십시오.</span><span class="sxs-lookup"><span data-stu-id="8beb0-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="8beb0-202">다음으로 각 Edge 서버 컴퓨터에서 **Lync Server 액세스 가장자리** 를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="8beb0-203">각 레거시 Edge 서버 컴퓨터에서 **관리 도구**를 통해 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="8beb0-204">서비스 목록에서 **Office Communications Server 액세스 Edge**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="8beb0-205">서비스 이름을 마우스 오른쪽 단추로 클릭 하 고 **중지** 를 선택 하 여 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="8beb0-206">시작 유형을 **사용 안 함으로**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="8beb0-207">**확인** 을 클릭 하 여 **속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="8beb0-208">외부 사용자 및 외부 액세스의 연결을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="8beb0-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="8beb0-209">하나 이상의 페더레이션 도메인, Lync Server 2013의 내부 사용자 및 Office Communications Server 2007 R2 사용자의 사용자</span><span class="sxs-lookup"><span data-stu-id="8beb0-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="8beb0-210">인스턴트 메시지 (IM), 현재 상태, 오디오/비디오 (A/V) 및 데스크톱 공유를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="8beb0-211">조직에서 지 원하는 각 공용 IM 서비스 공급자의 사용자 (그리고 프로 비전이 완료 된 경우)는 Lync Server 2013 및 Office Communications Server 2007 R2 사용자와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="8beb0-212">익명 사용자가 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="8beb0-213">원격 사용자 액세스를 사용 하 여 Office communications Server 2007 R2에 호스팅되는 사용자 (인트라넷 외부에서는 Office Communications Server 2007 R2에 로그인 하 고 VPN 제외)는 Lync Server 2013의 사용자와 Office Communications Server 2007 R2에 대 한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="8beb0-214">IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="8beb0-215">Lync server 2013에서 원격 사용자 액세스를 사용 하 여 (인트라넷 외부에서 Lync Server 2013에 로그인 하 고 VPN이 없는 경우 2013) 사용자에 대 한 자세한 2007 정보</span><span class="sxs-lookup"><span data-stu-id="8beb0-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="8beb0-216">IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8beb0-216">Test IM, presence, A/V, and desktop sharing.</span></span>

