---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754964"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="1f6f6-102">페더레이션 경로 및 미디어 트래픽 구성</span><span class="sxs-lookup"><span data-stu-id="1f6f6-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="1f6f6-103">페더레이션은 개별 조직의 사용자가 네트워크 경계에서 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간 신뢰 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="1f6f6-104">Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 Microsoft Office Communications Server 2007 R2에 지 서버의 페더레이션 경로에서 Lync Server 2013에 지 서버의 페더레이션 경로로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="1f6f6-105">단일 사이트 배포의 경우 다음 절차를 사용 하 여 Office Communications Server 2007 R2에 지 서버 및 디렉터에서 Lync Server 2013 Edge 서버로의 페더레이션 경로 및 미디어 트래픽 경로를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="1f6f6-106">페더레이션 경로 및 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Office Communications Server 2007 R2에 지 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="1f6f6-107">이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="1f6f6-108">사용자 활동이 최소로 예상되는 시간으로 중단 시간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="1f6f6-109">또한 최종 사용자에게 충분한 알림을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="1f6f6-110">이 중단에 맞게 계획하고 조직 내에서 적당한 기대치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="1f6f6-111">레거시 Office Communications Server 2007 R2에 지 서버가 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스에 대해 동일한 FQDN을 사용 하도록 구성 되어 있는 경우이 섹션의 절차를 통해 페더레이션 설정을 Lync Server 2013에 지 서버로 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="1f6f6-112">레거시에 지 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우 먼저 Office Communications Server 2007 R2에서 Lync Server 2013로 모든 사용자를 마이그레이션한 다음 Lync Server 2013 Edge Server에서 페더레이션을 사용 하기 전에 Office Communications Server 2007 R2에 지 서버를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="1f6f6-113">자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1f6f6-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Lync Server 2013로 나머지 사용자 이동</A></span><span class="sxs-lookup"><span data-stu-id="1f6f6-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="1f6f6-115">"서버 및 서버 역할 제거"<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="1f6f6-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="1f6f6-116">XMPP 페더레이션이 Lync Server 2013에 지 서버를 통해 라우팅되는 경우, 모든 사용자가 Lync Server 2013로 이동 되 고 XMPP 정책 및 인증서가 구성 되었으며, Lync Server 2013에 XMPP 페더레이션 파트너가 구성 되어 있고, 마지막으로 DNS 항목이 업데이트 된 경우에는 레거시 Office Communications Server 2007 R2 사용자가 XMPP 페더레이션 파트너와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="1f6f6-117">서버 역할을 추가하거나 제거할 때 토폴로지를 게시하거나, 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원인 사용자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="1f6f6-118">또한 서버 역할에 적당한 사용자 권리 및 사용 권한을 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="1f6f6-119">자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서에서 [Lync Server 2013의 대리인 설치 권한](lync-server-2013-delegate-setup-permissions.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="1f6f6-120">그 밖의 구성 변경은 RTCUniversalServerAdmins 그룹의 구성원이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="1f6f6-121">Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="1f6f6-122">토폴로지 작성기를 사용하여 파일럿 풀 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="1f6f6-123">왼쪽 창에서 사이트 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="1f6f6-124">사이트를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="1f6f6-125">왼쪽 창에서 **페더레이션 경로**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="1f6f6-126">사이트 페더레이션 경로 지정에서 **SIP 페더레이션 사용(Enable SIP federation)** 옆에 있는 확인란의 선택을 취소하여 **BackCompatSite**를 통해 페더레이션 경로를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="1f6f6-127">![속성 편집 대화 상자, 페더레이션 경로](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="1f6f6-128">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="1f6f6-129">**토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="1f6f6-130">**동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="1f6f6-131">레거시 에지 서버를 비페더레이션 에지 서버로 구성하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="1f6f6-132">**토폴로지 작성기**의 **동작** 메뉴에서 **Office Communications Server 2007 R2 토폴로지 병합(Merge Office Communications Server 2007 R2 Topology)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="1f6f6-133">**다음**을 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="1f6f6-134">**에지 설정 지정**에서 현재 페더레이션에 대해 구성된 **에지 서버 내부 FQDN**을 선택한 후 **변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="1f6f6-135">![OCS 2007 R2 토폴로지 병합,에 지 설정 지정](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 토폴로지 병합,에 지 설정 지정")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="1f6f6-136">**다음**을 클릭하고 **외부 에지 지정** 페이지에 연결될 때까지 기본 설정을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="1f6f6-137">![토폴로지 작성기 외부에 지 지정 페이지](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "토폴로지 작성기 외부에 지 지정 페이지")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="1f6f6-p105">**외부 에지 지정**에서 **이 에지 풀은 페더레이션 및 공용 IM 연결에 사용됩니다.** 확인란의 선택을 취소합니다. 그러면 BackCompatSite와의 페더레이션 연결이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-p105">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f6f6-p106">이 단계는 중요한 단계입니다. 레거시 페더레이션 연결을 제거하려면 이 옵션의 선택을 취소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-p106">This step is important. You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="1f6f6-142">**다음**을 클릭하고 마법사의 남은 페이지에서 기본 설정을 그대로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="1f6f6-143">**요약**에서 **다음**을 클릭하여 토폴로지 병합을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="1f6f6-144">**상태** 열에서 값이 **성공**인지 확인 한 다음 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="1f6f6-145">**동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="1f6f6-146">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="1f6f6-147">![병합 후 사이트가 표시 되는 토폴로지 작성기](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "병합 후 사이트가 표시 되는 토폴로지 작성기")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="1f6f6-148">이전 그림에서처럼 **사이트 페더레이션 경로 지정** 아래에 있는 **SIP 페더레이션**이 **사용 안 함**으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="1f6f6-149">Lync Server 2013 에지 서버에서 인증서를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="1f6f6-150">레거시 Office Communications Server 2007 R2에 지 서버에서 개인 키를 사용 하 여 외부 액세스 프록시 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="1f6f6-151">Lync Server 2013에 지 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="1f6f6-152">액세스 프록시 외부 인증서를에 지 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="1f6f6-153">Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 변경 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="1f6f6-154">Lync Server 2010 에지 서버를 사용하도록 Office Communications Server 2013 R2 페더레이션 경로를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="1f6f6-155">Office Communications Server 2007 R2 Standard Edition server 또는 프런트 엔드 서버에서 Office Communications Server 2007 R2 관리 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="1f6f6-p107">왼쪽 창에서 맨 위의 노드를 확장한 후 **포리스트** 노드를 마우스 오른쪽 단추로 클릭합니다. **속성**을 선택한 후 **전역 속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-p107">In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="1f6f6-158">**페더레이션** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="1f6f6-159">확인란을 선택하여 페더레이션 및 공용 IM 연결을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="1f6f6-160">Lync Server 2013 Edge 서버의 FQDN을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="1f6f6-161">![OCS 전역 속성, 페더레이션 탭](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 전역 속성, 페더레이션 탭")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="1f6f6-162">Lync Server 2013 에지 서버 페더레이션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="1f6f6-163">토폴로지 작성기의 왼쪽 창에서 Lync Server 2013 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="1f6f6-164">노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1f6f6-165">페더레이션은 단일에 지 풀에 대해서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="1f6f6-166">에지 풀이 여러 개인 경우 페더레이션 에지 풀로 사용할 항목을 하나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="1f6f6-167">**일반** 페이지에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="1f6f6-168">![속성 편집, 일반,에 지 페더레이션 사용](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "속성 편집, 일반,에 지 페더레이션 사용")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="1f6f6-169">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="1f6f6-170">그런 다음 사이트 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="1f6f6-171">사이트에서 마우스 오른쪽 단추를 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="1f6f6-172">왼쪽 창에서 **페더레이션 경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="1f6f6-173">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync Server 2013에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="1f6f6-174">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="1f6f6-175">![속성 편집, 일반,에 지 풀 연결](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "속성 편집, 일반,에 지 풀 연결")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="1f6f6-176">다중 사이트 배포의 경우 각 사이트에서 이 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="1f6f6-177">Lync Server 2013 에지 서버 아웃바운드 미디어 경로를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="1f6f6-178">**토폴로지 작성기**에서 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 Lync Server 2013 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="1f6f6-179">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1f6f6-180">**연결** 섹션에서 **에지 풀 연결(미디어 구성 요소)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="1f6f6-181">드롭다운 상자에서 Lync Server 2013에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="1f6f6-182">![속성 편집 대화 상자,에 지 풀 연결](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "속성 편집 대화 상자,에 지 풀 연결")</span><span class="sxs-lookup"><span data-stu-id="1f6f6-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="1f6f6-183">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="1f6f6-184">에지 서버 구성 변경 사항을 게시하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="1f6f6-185">**토폴로지 작성기**에서 맨 위에 있는 최상위 노드 **Lync Server**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="1f6f6-186">**동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="1f6f6-187">배포의 모든 풀에 대해 Active Directory 복제가 발생할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1f6f6-188">다음 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-188">You may see the following message:</span></span><BR><span data-ttu-id="1f6f6-189"><STRONG>경고: 토폴로지에 둘 이상의 페더레이션 에지 서버가 포함되어 있습니다. 상위 버전의 제품으로 마이그레이션하는 동안 이 상황이 발생할 수 있습니다. 이 경우 하나의 에지 서버만 페더레이션에 사용됩니다. 외부 DNS SRV 레코드가 올바른 에지 서버를 가리키는지 확인하십시오. 동시에 활성화되도록 여러 페더레이션 에지 서버를 배포하려면(즉, 마이그레이션 시나리오가 아님) 모든 페더레이션 파트너가 Office Communications Server 2007 R2 또는 Lync Server를 사용하고 있는지 확인하고 외부 DNS SRV 레코드에 모든 페더레이션 사용 가능 에지 서버가 나열되는지 확인하십시오.</STRONG></span><span class="sxs-lookup"><span data-stu-id="1f6f6-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="1f6f6-190">이 경고는 예상된 경고이므로 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="1f6f6-191">외부 사용자를 위한 페더레이션 및 원격 액세스를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="1f6f6-192">Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="1f6f6-193">페더레이션 및 원격 액세스 상태를 확인하려면 명령줄에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="1f6f6-194">페더레이션 및 원격 액세스를 사용하려면 명령줄에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="1f6f6-195">이러한 cmdlet에 대 한 자세한 내용은 [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) 및 [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="1f6f6-196">Lync Server 2013에 지 서버를 온라인으로 전환 하 고 페더레이션 및 외부 액세스를 테스트 하기 전에 복제가 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="1f6f6-197">Lync Server 2013 에지 서버를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="1f6f6-198">모든 Lync Server 2013에 지 서버를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="1f6f6-199">외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정을 업데이트 하 여 외부 액세스에 대 한 SIP 트래픽 (일반적으로 포트 443)과 페더레이션 (일반적으로 포트 5061)을 레거시에 지 서버 대신 Lync Server 2013에 지 서버에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1f6f6-p109">하드웨어 부하 분산 기능이 없는 경우 페더레이션에 대한 DNS A를 업데이트하여 새 Lync Server 액세스 에지 서버를 확인해야 합니다. 최소한의 중단만으로 이 작업을 수행하려면 DNS가 업데이트되어 새 Lync Server 액세스 에지 서버를 가리킬 때 페더레이션 및 원격 액세스가 신속히 업데이트되도록 외부 Lync Server 액세스 에지 FQDN에 대한 TTL 값을 낮춥니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-p109">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="1f6f6-202">다음으로 각에 지 서버 컴퓨터에서 **Lync Server 액세스에 지** 를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="1f6f6-203">각 레거시에 지 서버 컴퓨터의 **관리 도구**에서 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="1f6f6-204">서비스 목록에서 **Office Communications Server 액세스 에지**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="1f6f6-205">서비스 이름을 마우스 오른쪽 단추로 클릭한 후 **중지**를 선택하여 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="1f6f6-206">시작 유형을 **사용 안 함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="1f6f6-207">**확인**을 클릭하여 **속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="1f6f6-208">외부 사용자 및 외부 액세스 연결을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="1f6f6-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="1f6f6-209">하나 이상의 페더레이션 도메인에서 사용자, Lync Server 2013의 내부 사용자 및 Office Communications Server 2007 r 2에 대 한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1f6f6-210">IM(인스턴트 메시징), 현재 상태, A/V(오디오/비디오) 및 데스크톱 공유를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="1f6f6-211">조직이 지원 하 고 프로 비전이 완료 된 각 공용 IM 서비스 공급자의 사용자가 Lync Server 2013 및 Office Communications Server 2007 r 2의 사용자와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="1f6f6-212">익명 사용자가 회의에 참가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="1f6f6-213">Lync Server 2013에 있는 사용자와 Office communications Server 2007 r 2에 대 한 사용자의 원격 사용자 액세스를 사용 하 여 Office communications server 2007 R2에 호스트 되는 사용자 2007 (VPN 제외)</span><span class="sxs-lookup"><span data-stu-id="1f6f6-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1f6f6-214">IM, 현재 상태, A/V 및 데스크톱 공유를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="1f6f6-215">Lync server 2013을 사용 하 여 lync server 2013에 2013 호스트 되는 사용자에 게 원격 사용자 액세스 (VPN 제외)로 로그온 하 고, Office Communications Server 2007 r 2에 대 한 사용자와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1f6f6-216">IM, 현재 상태, A/V 및 데스크톱 공유를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6f6-216">Test IM, presence, A/V, and desktop sharing.</span></span>

