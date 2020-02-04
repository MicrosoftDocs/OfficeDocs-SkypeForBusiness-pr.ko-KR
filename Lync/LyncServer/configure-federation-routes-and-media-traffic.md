---
title: 페더레이션 경로 및 미디어 트래픽 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="2af1e-102">페더레이션 경로 및 미디어 트래픽 구성</span><span class="sxs-lookup"><span data-stu-id="2af1e-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2af1e-103">_**마지막으로 수정한 주제:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="2af1e-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="2af1e-104">페더레이션은 서로 다른 조직의 사용자가 네트워크 경계를 통해 통신할 수 있도록 하는 두 개 이상의 SIP 도메인 간의 신뢰 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="2af1e-105">Lync Server 2013 파일럿 풀로 마이그레이션한 후에는 Lync Server 2010 Edge 서버의 페더레이션 경로에서 Lync Server 2013 Edge 서버의 페더레이션 경로로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="2af1e-106">단일 사이트 배포의 경우 다음 절차를 사용 하 여 Lync Server 2010 Edge 서버 및 디렉터에서 Lync server 2013 Edge 서버로의 페더레이션 경로와 미디어 트래픽 경로를 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2af1e-107">페더레이션 경로와 미디어 트래픽 경로를 변경 하려면 Lync Server 2013 및 Lync Server 2010 Edge 서버에 대 한 유지 관리 중단 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="2af1e-108">또한이 전체 전환 프로세스는 중단 기간 동안 페더레이션 액세스를 사용할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="2af1e-109">최소한의 사용자 작업을 예상 하는 동안 가동 중지 시간을 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="2af1e-110">또한 최종 사용자에 게 충분 한 알림을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="2af1e-111">이 중단에 대 한 계획을 수립 하 고 조직 내에서 적절 한 기대치를 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="2af1e-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2af1e-112">레거시 Lync Server 2010 Edge 서버가 액세스 경계 서비스, 웹 회의에 지 서비스, 그리고 A/V Edge 서비스에 대해 동일한 FQDN을 사용 하도록 구성 된 경우이 섹션의 절차는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="2af1e-113">레거시 Edge 서비스가 동일한 FQDN을 사용 하도록 구성 된 경우에는 먼저 Lync server 2010에서 Lync server 2013로 모든 사용자를 마이그레이션한 다음 lync server 2013 edge 서버에서 페더레이션을 사용 하기 전에 Lync 서버 2010 Edge 서버의 서비스를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2af1e-114">XMPP 페더레이션이 Lync Server 2013 Edge 서버를 통해 라우팅된 경우, 모든 사용자가 Lync Server 2013로 이동할 때까지 레거시 Lync Server 2010 사용자가 XMPP 페더레이션 파트너와 통신할 수 없습니다. XMPP 정책 및 인증서가 구성 된 XMPP 페더레이션 파트너는 Lync Server 2013에서 구성 되었고 마지막으로 DNS 항목이 업데이트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="2af1e-115">Lync Server 2013 사이트에서 레거시 페더레이션 연결을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="2af1e-116">Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기의 기존 토폴로지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="2af1e-117">왼쪽 창에서 **Lync Server**바로 아래에 있는 사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="2af1e-118">사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="2af1e-119">왼쪽 창에서 **페더레이션 경로**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="2af1e-120">**사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용** 확인란의 선택을 취소 하 여 레거시 Lync Server 2010 환경을 통해 페더레이션 경로를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="2af1e-121">![속성 편집 대화 상자, 페더레이션 경로 페이지](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "속성 편집 대화 상자, 페더레이션 경로 페이지")</span><span class="sxs-lookup"><span data-stu-id="2af1e-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="2af1e-122">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="2af1e-123">**토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="2af1e-124">**작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="2af1e-125">**다음** 을 클릭 하 여 게시 프로세스를 완료 하 고 게시 프로세스가 완료 되 면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="2af1e-126">레거시 Edge 서버를 비 페더레이션에 지 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="2af1e-127">왼쪽 창에서 **Lync Server 2010** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="2af1e-128">Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2af1e-129">왼쪽 창에서 **일반** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="2af1e-130">**이 Edge 풀에 페더레이션 사용 (포트 5061)** 확인란 항목을 선택 취소 하 고 **확인** 을 선택 하 여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="2af1e-131">![속성 편집, 일반, 페더레이션 사용 선택 취소](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "속성 편집, 일반, 페더레이션 사용 선택 취소")</span><span class="sxs-lookup"><span data-stu-id="2af1e-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="2af1e-132">**작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2af1e-133">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="2af1e-134">레거시 Edge 서버에 대 한 페더레이션이 비활성화 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="2af1e-135">![토폴로지 작성기, 에지 풀, 페더레이션 사용 안 함](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "토폴로지 작성기, 에지 풀, 페더레이션 사용 안 함")</span><span class="sxs-lookup"><span data-stu-id="2af1e-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="2af1e-136">Lync Server 2010 Edge 서버에서 인증서를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="2af1e-137">개인 키가 있는 외부 액세스 프록시 인증서를 레거시 Lync Server 2010 Edge 서버에서 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="2af1e-138">Lync Server 2013 Edge 서버에서 이전 단계에서 액세스 프록시 외부 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="2af1e-139">액세스 프록시 외부 인증서를 Edge 서버의 Lync Server 2013 외부 인터페이스에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="2af1e-140">Lync Server 2013 Edge 서버의 내부 인터페이스 인증서는 신뢰할 수 있는 CA에서 요청 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="2af1e-141">Lync server 2013 Edge 서버를 사용 하도록 Lync Server 2010 페더레이션 경로를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="2af1e-142">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="2af1e-143">Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2af1e-144">왼쪽 창에서 **일반** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="2af1e-145">**이 Edge 풀의 페더레이션 사용 (포트 5061)** 에 대 한 확인란 항목을 선택한 다음 **확인** 을 클릭 하 여 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="2af1e-146">![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")</span><span class="sxs-lookup"><span data-stu-id="2af1e-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="2af1e-147">**작업** 메뉴에서 **토폴로지 게시**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2af1e-148">**게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="2af1e-149">**페더레이션 (포트 5061)** 이 **사용**으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="2af1e-150">![토폴로지 작성기, 에지 풀, 페더레이션 사용](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "토폴로지 작성기, 에지 풀, 페더레이션 사용")</span><span class="sxs-lookup"><span data-stu-id="2af1e-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="2af1e-151">Lync Server 2013 Edge 서버 페더레이션 다음 홉을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="2af1e-152">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="2af1e-153">노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2af1e-154">**일반** 페이지의 **다음 홉 선택**아래에 있는 드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="2af1e-155">![속성 편집 대화 상자, 다음 홉 페이지](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "속성 편집 대화 상자, 다음 홉 페이지")</span><span class="sxs-lookup"><span data-stu-id="2af1e-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="2af1e-156">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="2af1e-157">**토폴로지 작성기**에서 최상위 노드 **Lync 서버** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="2af1e-158">**작업** 메뉴에서 **토폴로지 게시** 를 클릭 하 고 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="2af1e-159">Lync Server 2013 Edge 서버 아웃 바운드 미디어 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="2af1e-160">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Standard Edition 프런트 엔드 서버** 또는 **Enterprise Edition 프런트 엔드 풀**아래에 있는 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="2af1e-161">풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2af1e-162">**연결** 섹션에서 **Edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="2af1e-163">![속성 편집, 일반, 에지 풀 연결](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "속성 편집, 일반, 에지 풀 연결")</span><span class="sxs-lookup"><span data-stu-id="2af1e-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="2af1e-164">드롭다운 상자에서 Lync Server 2013 Edge 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="2af1e-165">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="2af1e-166">Lync Server 2013 Edge 서버 페더레이션을 켜려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="2af1e-167">토폴로지 작성기의 왼쪽 창에서 **Lync Server 2013** 노드로 이동한 다음 **Edge 풀** 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="2af1e-168">노드를 확장 하 고 나열 된 Edge 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2af1e-169">페더레이션은 단일 Edge 풀에 대해서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="2af1e-170">Edge 풀이 여러 개 있는 경우 하나를 선택 하 여 페더레이션 가장자리 풀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="2af1e-171">**일반** 페이지에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 설정이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="2af1e-172">![속성 편집 대화 상자, 일반 페이지](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "속성 편집 대화 상자, 일반 페이지")</span><span class="sxs-lookup"><span data-stu-id="2af1e-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="2af1e-173">**확인** 을 클릭 하 여 속성 편집 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="2af1e-174">다음으로, 사이트 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="2af1e-175">사이트를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="2af1e-176">왼쪽 창에서 **페더레이션 경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="2af1e-177">**사이트 페더레이션 경로 할당**에서 **SIP 페더레이션 사용**을 선택한 다음 목록에서 나열 된 Lync server 2013 Edge 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="2af1e-178">![속성 편집, 페더레이션 경로 페이지](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "속성 편집, 페더레이션 경로 페이지")</span><span class="sxs-lookup"><span data-stu-id="2af1e-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="2af1e-179">**확인** 을 클릭 하 여 **속성 편집** 페이지를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="2af1e-180">여러 사이트 배포의 경우 각 사이트에서이 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="2af1e-181">Edge 서버 구성 변경 내용을 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="2af1e-182">**토폴로지 작성기**에서 최상위 노드 **Lync 서버** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="2af1e-183">**작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="2af1e-184">Active Directory 복제가 배포의 모든 풀에 발생 하는 것을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2af1e-185">다음과 같은 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-185">You may see the following message:</span></span><BR><span data-ttu-id="2af1e-186"><STRONG>경고: 토폴로지에 두 개 이상의 페더레이션된 Edge 서버가 있습니다. 이 문제는 최신 버전의 제품으로 마이그레이션하는 동안 발생할 수 있습니다. 이 경우에는 오직 하나의 Edge 서버만 페더레이션에 사용 됩니다. 외부 DNS SRV 레코드가 올바른 Edge 서버를 가리키는지 확인 합니다. 동시에 여러 페더레이션에 지 서버를 배포 하려는 경우 (즉, 마이그레이션 시나리오가 아닌 경우), 모든 페더레이션 파트너가 Lync Server를 사용 하 고 있는지 확인 합니다. 외부 DNS SRV 레코드에 모든 페더레이션 가능 Edge 서버가 나열 되는지 확인 합니다.</STRONG></span><span class="sxs-lookup"><span data-stu-id="2af1e-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="2af1e-187">이 경고는 예상 되는 것으로 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="2af1e-188">Lync Server 2013 Edge 서버를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="2af1e-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="2af1e-189">모든 Lync Server 2013 Edge 서버를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="2af1e-190">외부에 지 서버 대신 외부 방화벽 라우팅 규칙이 나 하드웨어 부하 분산 장치 설정 (일반적으로 포트 443) 및 페더레이션 (일반적으로 포트 5061)에 대 한 SIP 트래픽을 Lync Server 2013 Edge 서버에 전송 하도록 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2af1e-191">하드웨어 부하 분산이 없는 경우 새 Lync Server 액세스 Edge 서버로 확인 되도록 페더레이션에 대 한 DNS A 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="2af1e-192">최소 중단으로이 작업을 수행 하려면 DNS가 새 Lync Server Access Edge를 가리키도록 업데이트 될 때 페더레이션 및 원격 액세스가 빠르게 업데이트 되도록 외부 Lync Server 액세스 Edge FQDN에 대 한 TLL 값을 줄이십시오.</span><span class="sxs-lookup"><span data-stu-id="2af1e-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="2af1e-193">다음으로 각 Edge 서버 컴퓨터에서 **Lync Server 액세스 가장자리** 를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="2af1e-194">각 레거시 Edge 서버 컴퓨터에서 **관리 도구**를 통해 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="2af1e-195">서비스 목록에서 **Lync Server 액세스 가장자리**를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="2af1e-196">서비스 이름을 마우스 오른쪽 단추로 클릭 하 고 **중지** 를 선택 하 여 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="2af1e-197">시작 유형을 **사용 안 함으로**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="2af1e-198">**확인** 을 클릭 하 여 **속성** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="2af1e-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

