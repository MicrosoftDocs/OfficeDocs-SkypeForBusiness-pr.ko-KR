---
title: 'Lync Server 2013: 부하 분산을 위한 DNS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831968516ef155d6ad018f33bfa27226f58292dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537145"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="7d0a3-102">Lync Server 2013에서 부하 분산을 위한 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="7d0a3-102">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d0a3-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7d0a3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7d0a3-104">이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="7d0a3-105">DNS (Domain Name System) 부하 분산은 SIP 트래픽 및 미디어 트래픽 같은 Lync Server 2013에 고유한 네트워크 트래픽의 균형을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="7d0a3-106">DNS 부하 분산은 프런트 엔드 풀, 에지 풀, 디렉터 풀 및 독립 실행형 중재 풀에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="7d0a3-107">DNS 부하 분산을 사용 하도록 구성 된 풀에는 두 개의 Fqdn (정규화 된 도메인 이름)이 정의 되어 있어야 합니다. DNS 부하 분산 (예: pool1.contoso.com)에서 사용 되며 풀에 있는 서버의 실제 Ip로 확인 되는 일반 풀 FQDN 및 풀의 웹 서비스 (예: web1.contoso.net)에 대 한 다른 FQDN이 풀의 가상 IP 주소로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="7d0a3-108">DNS 부하 분산에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d0a3-109">클라이언트에서 서버로의 HTTPS 트래픽에는 하드웨어 부하 분산을 계속 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="7d0a3-110">DNS 부하 분산을 사용하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="7d0a3-111">내부 웹 서비스 풀 FQDN을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7d0a3-112">내부 웹 서비스를 자체 정의 된 FQDN으로 다시 정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="7d0a3-113">풀 FQDN이 풀에 있는 모든 서버의 IP 주소로 확인되도록 DNS A 호스트 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="7d0a3-114">IP 주소 임의화를 사용하도록 설정하거나, Windows Server DNS의 경우 라운드 로빈을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d0a3-115">라운드 로빈은 기본적으로 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="7d0a3-116">내부 웹 서비스 FQDN을 재정의하려면</span><span class="sxs-lookup"><span data-stu-id="7d0a3-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="7d0a3-117">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7d0a3-118">콘솔 트리에서 Enterprise Edition 프런트 엔드 풀 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="7d0a3-119">풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭한 후에 **웹 서비스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="7d0a3-120">**내부 웹 서비스** 아래에서 **FQDN 다시 정의** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="7d0a3-121">풀에 있는 서버의 실제 IP 주소로 확인되는 풀 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="7d0a3-122">**외부 웹 서비스**아래에 풀의 가상 IP 주소로 확인되는 외부 풀 FQDN을 입력하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="7d0a3-123">콘솔 트리에서 **Lync Server 2013**을 클릭 한 다음 **작업** 창에서 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="7d0a3-124">모든 내부 풀 서버에 대해 DNS 호스트(A) 레코드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7d0a3-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="7d0a3-125">**시작**을 클릭하고 **모든 프로그램**과 **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="7d0a3-126">**DNS 관리자**에서 레코드를 관리하는 DNS 서버를 클릭하여 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="7d0a3-127">**정방향 조회 영역**을 클릭하여 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="7d0a3-128">레코드를 추가해야 하는 DNS 도메인을 마우스 오른쪽 단추로 클릭하고 **새 호스트(A 또는 AAAA)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="7d0a3-129">**이름** 상자에 호스트 레코드의 이름을 입력 합니다 (도메인 이름은 자동으로 추가 됨).</span><span class="sxs-lookup"><span data-stu-id="7d0a3-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="7d0a3-130">IP 주소 상자에 개별 프런트 엔드 서버의 IP 주소를 입력하고 **연결된 PTR(포인터) 레코드 만들기** 또는 해당하는 경우 **인증된 사용자는 누구든지 DNS 레코드를 같은 소유자 이름으로 업데이트할 수 있도록 허용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="7d0a3-131">계속해서 DNS 부하 분산에 참가할 모든 구성원 프런트 엔드 서버에 대해 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="7d0a3-132">예를 들어 풀 이름이 pool1.contoso.com이고 프런트 엔드 서버가 세 개 있는 경우에는 다음과 같은 DNS 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7d0a3-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0a3-133">FQDN</span></span></th>
    <th><span data-ttu-id="7d0a3-134">타이핑</span><span class="sxs-lookup"><span data-stu-id="7d0a3-134">Type</span></span></th>
    <th><span data-ttu-id="7d0a3-135">데이터</span><span class="sxs-lookup"><span data-stu-id="7d0a3-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7d0a3-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d0a3-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="7d0a3-137">호스트(A)</span><span class="sxs-lookup"><span data-stu-id="7d0a3-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="7d0a3-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="7d0a3-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d0a3-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d0a3-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="7d0a3-140">호스트(A)</span><span class="sxs-lookup"><span data-stu-id="7d0a3-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="7d0a3-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="7d0a3-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d0a3-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7d0a3-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="7d0a3-143">호스트(A)</span><span class="sxs-lookup"><span data-stu-id="7d0a3-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="7d0a3-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="7d0a3-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="7d0a3-145">DNS 호스트 (A) 레코드를 만드는 방법에 대 한 자세한 내용은 [CONFIGURE Dns Host records For Lync Server 2013](lync-server-2013-configure-dns-host-records.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="7d0a3-146">Windows Server에 대해 라운드 로빈을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7d0a3-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="7d0a3-147">**시작**을 클릭하고 **모든 프로그램**과 **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="7d0a3-148">**DNS**를 확장하고 구성할 DNS 서버를 마우스 오른쪽 단추로 클릭한 후에 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="7d0a3-149">**고급** 탭을 클릭하고 **라운드 로빈 사용** 및 **네트워크 마스크 순서 사용**을 선택한 후에 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="7d0a3-150">![DNS 라운드 로빈 대화 상자](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS 라운드 로빈 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="7d0a3-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d0a3-151">이 기능은 기본적으로 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d0a3-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d0a3-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d0a3-152">See Also</span></span>


[<span data-ttu-id="7d0a3-153">Lync Server 2013의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="7d0a3-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

