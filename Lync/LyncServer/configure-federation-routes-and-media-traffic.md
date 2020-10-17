---
title: 페더레이션 경로 및 미디어 트래픽 구성
description: 페더레이션 경로 및 미디어 트래픽을 구성 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de26f472bddc504ff79e427b5243587f27020c3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542984"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="77a95-103">페더레이션 경로 및 미디어 트래픽 구성</span><span class="sxs-lookup"><span data-stu-id="77a95-103">Configure federation routes and media traffic</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77a95-104">_**마지막으로 수정 된 항목:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="77a95-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="77a95-105">페더레이션은 개별 조직의 사용자가 네트워크 경계에서 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간 신뢰 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="77a95-106">Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 lync server 2010에 지 서버의 페더레이션 경로에서 Lync Server 2013에 지 서버의 페더레이션 경로로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-106">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="77a95-107">단일 사이트 배포의 경우 다음 절차에 따라 Lync Server 2010에 지 서버 및 디렉터에서 Lync server 2013 Edge 서버로의 페더레이션 경로 및 미디어 트래픽 경로를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-107">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77a95-108">페더레이션 경로 및 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Lync Server 2010에 지 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="77a95-109">이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="77a95-110">사용자 활동이 최소로 예상되는 시간으로 중단 시간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="77a95-111">또한 최종 사용자에게 충분한 알림을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="77a95-112">이 중단에 맞게 계획하고 조직 내에서 적당한 기대치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77a95-113">레거시 Lync Server 2010에 지 서버가 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스에 대해 동일한 FQDN을 사용 하도록 구성 되어 있는 경우이 섹션의 절차는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-113">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="77a95-114">레거시에 지 서비스가 동일한 FQDN을 사용 하도록 구성 되어 있는 경우 lync server 2013에 지 서버에서 페더레이션을 사용 하도록 설정 하기 전에 먼저 Lync server 2010에서 lync server 2013로 모든 사용자를 마이그레이션한 다음 Lync Server 2010에 지 서버를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77a95-115">XMPP 페더레이션이 Lync Server 2013에 지 서버를 통해 라우팅되는 경우, 모든 사용자가 Lync Server 2013로 이동 되 고 XMPP 정책 및 인증서가 구성 되었으며, Lync Server 2013에 XMPP 페더레이션 파트너가 구성 되어 있고, 마지막으로 DNS 항목이 업데이트 된 경우에만 레거시 Lync Server 2010 사용자가 XMPP 페더레이션 파트너와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-115">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="77a95-116">Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-116">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="77a95-117">Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기의 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-117">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="77a95-118">왼쪽 창에서 **Lync Server** 아래에 있는 사이트 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-118">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="77a95-119">사이트를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-119">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="77a95-120">왼쪽 창에서 **페더레이션 경로**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-120">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="77a95-121">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용** 확인란의 선택을 취소 하 여 레거시 Lync Server 2010 환경을 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="77a95-122">![속성 편집 대화 상자, 페더레이션 경로 페이지](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로 페이지")</span><span class="sxs-lookup"><span data-stu-id="77a95-122">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="77a95-123">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-123">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="77a95-124">**토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-124">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="77a95-125">**동작** 메뉴에서 **토폴로지 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-125">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="77a95-126">**다음**을 클릭하여 게시 프로세스를 완료하고 게시 프로세스가 완료되었으면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-126">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="77a95-127">레거시 에지 서버를 비페더레이션 에지 서버로 구성하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-127">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="77a95-128">왼쪽 창에서 **Lync Server 2010** 노드로 이동하고 **에지 풀** 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-128">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="77a95-129">에지 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-129">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="77a95-130">왼쪽 창에서 **일반**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-130">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="77a95-131">**이 에지 풀에 페더레이션 사용(포트 5061)** 확인란 항목의 선택을 취소하고 **확인**을 선택하여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-131">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="77a95-132">![속성 편집, 일반, 페더레이션 사용 지우기](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "속성 편집, 일반, 페더레이션 사용 지우기")</span><span class="sxs-lookup"><span data-stu-id="77a95-132">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="77a95-133">**동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-133">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="77a95-134">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-134">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="77a95-135">레거시 에지 서버에 대한 페더레이션이 사용하지 않도록 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-135">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="77a95-136">![토폴로지 작성기,에 지 풀, 페더레이션 사용 안 함](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "토폴로지 작성기,에 지 풀, 페더레이션 사용 안 함")</span><span class="sxs-lookup"><span data-stu-id="77a95-136">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="77a95-137">Lync Server 2010 에지 서버에서 인증서를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-137">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="77a95-138">레거시 Lync Server 2010에 지 서버에서 개인 키를 사용 하 여 외부 액세스 프록시 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-138">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="77a95-139">Lync Server 2013에 지 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-139">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="77a95-140">액세스 프록시 외부 인증서를에 지 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-140">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="77a95-141">Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 신뢰할 수 있는 CA에서 요청 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-141">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="77a95-142">Lync Server 2013 에지 서버를 사용하도록 Lync Server 2010 페더레이션 경로를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-142">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="77a95-143">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동하고 **에지 풀** 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-143">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="77a95-144">에지 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-144">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="77a95-145">왼쪽 창에서 **일반**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-145">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="77a95-146">**이 에지 풀에 페더레이션 사용(포트 5061)** 에 대한 확인란 항목을 선택한 후 **확인**을 클릭하여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-146">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="77a95-147">![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")</span><span class="sxs-lookup"><span data-stu-id="77a95-147">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="77a95-148">**동작** 창에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-148">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="77a95-149">**게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-149">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="77a95-150">**페더레이션(포트 5061)** 이 **사용**으로 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-150">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="77a95-151">![토폴로지 작성기,에 지 풀, 페더레이션 사용](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "토폴로지 작성기,에 지 풀, 페더레이션 사용")</span><span class="sxs-lookup"><span data-stu-id="77a95-151">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="77a95-152">Lync Server 2013 에지 서버 페더레이션 다음 홉을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-152">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="77a95-153">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동하고 **에지 풀** 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-153">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="77a95-154">노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-154">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="77a95-155">**일반** 페이지의 **다음 홉 선택**에 있는 드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-155">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="77a95-156">![속성 편집 대화 상자의 다음 홉 페이지](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "속성 편집 대화 상자의 다음 홉 페이지")</span><span class="sxs-lookup"><span data-stu-id="77a95-156">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="77a95-157">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-157">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="77a95-158">**토폴로지 작성기**에서 최상위 노드 **Lync Server** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-158">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="77a95-159">**동작** 메뉴에서 **토폴로지 게시**를 클릭한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-159">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="77a95-160">Lync Server 2013 에지 서버 아웃바운드 미디어 경로를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-160">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="77a95-161">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래의 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-161">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="77a95-162">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-162">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="77a95-163">**연결** 섹션에서 **에지 풀 연결(미디어 구성 요소)** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-163">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="77a95-164">![속성 편집, 일반,에 지 풀 연결](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "속성 편집, 일반,에 지 풀 연결")</span><span class="sxs-lookup"><span data-stu-id="77a95-164">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="77a95-165">드롭다운 상자에서 Lync Server 2013에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-165">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="77a95-166">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-166">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="77a95-167">Lync Server 2013 에지 서버 페더레이션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-167">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="77a95-168">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동하고 **에지 풀** 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-168">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="77a95-169">노드를 확장하고 나열된 에지 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-169">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77a95-170">페더레이션은 단일에 지 풀에 대해서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-170">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="77a95-171">에지 풀이 여러 개인 경우 페더레이션 에지 풀로 사용할 항목을 하나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-171">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="77a95-172">**일반** 페이지에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 설정이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-172">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="77a95-173">![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")</span><span class="sxs-lookup"><span data-stu-id="77a95-173">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="77a95-174">**확인**을 클릭하여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-174">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="77a95-175">그런 다음 사이트 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-175">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="77a95-176">사이트에서 마우스 오른쪽 단추를 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-176">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="77a95-177">왼쪽 창에서 **페더레이션 경로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-177">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="77a95-178">**사이트 페더레이션 경로**지정에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync Server 2013에 지 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-178">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="77a95-179">![속성 편집, 페더레이션 경로 페이지](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "속성 편집, 페더레이션 경로 페이지")</span><span class="sxs-lookup"><span data-stu-id="77a95-179">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="77a95-180">**확인**을 클릭하여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-180">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="77a95-181">다중 사이트 배포의 경우 각 사이트에서 이 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-181">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="77a95-182">에지 서버 구성 변경 사항을 게시하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-182">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="77a95-183">**토폴로지 작성기**에서 최상위 노드 **Lync Server** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-183">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="77a95-184">**동작** 메뉴에서 **토폴로지 게시**를 선택한 후 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-184">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="77a95-185">배포의 모든 풀에 대해 Active Directory 복제가 발생할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-185">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77a95-186">다음 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-186">You may see the following message:</span></span><BR><span data-ttu-id="77a95-187"><STRONG>경고: 토폴로지에 둘 이상의 페더레이션 에지 서버가 포함되어 있습니다. 상위 버전의 제품으로 마이그레이션하는 동안 이 상황이 발생할 수 있습니다. 이 경우 하나의 에지 서버만 페더레이션에 사용됩니다. 외부 DNS SRV 레코드가 올바른 에지 서버를 가리키는지 확인하십시오. 동시에 활성화되도록 여러 페더레이션 에지 서버를 배포하려면(즉, 마이그레이션 시나리오가 아님) 모든 페더레이션 파트너가 Lync Server를 사용하고 있는지 확인하고 외부 DNS SRV 레코드에 모든 페더레이션 사용 가능 에지 서버가 나열되는지 확인하십시오.</STRONG></span><span class="sxs-lookup"><span data-stu-id="77a95-187"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="77a95-188">이 경고는 예상된 경고이므로 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-188">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="77a95-189">Lync Server 2013 에지 서버를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="77a95-189">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="77a95-190">모든 Lync Server 2013에 지 서버를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-190">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="77a95-191">외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정을 업데이트 하 여 외부 액세스에 대 한 SIP 트래픽 (일반적으로 포트 443)과 페더레이션 (일반적으로 포트 5061)을 레거시에 지 서버 대신 Lync Server 2013에 지 서버에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-191">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77a95-p105">하드웨어 부하 분산 장치가 없으면 새 Lync Server 액세스 에지 서버로 확인되도록 페더레이션에 대한 DNS A 레코드를 업데이트해야 합니다. 최소한의 중단으로 이를 수행하려면 새 Lync Server 액세스 에지를 가리키도록 DNS를 업데이트할 때 페더레이션 및 원격 액세스를 빠르게 업데이트할 수 있도록 외부 Lync Server 액세스 에지 FQDN에 대한 TLL 값을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="77a95-194">다음으로 각에 지 서버 컴퓨터에서 **Lync Server 액세스에 지** 를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-194">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="77a95-195">각 레거시에 지 서버 컴퓨터의 **관리 도구**에서 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-195">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="77a95-196">서비스 목록에서 **Lync Server 액세스 에지**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-196">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="77a95-197">서비스 이름을 마우스 오른쪽 단추로 클릭한 후 **중지**를 선택하여 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-197">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="77a95-198">시작 유형을 **사용 안 함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-198">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="77a95-199">**확인**을 클릭하여 **속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77a95-199">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

