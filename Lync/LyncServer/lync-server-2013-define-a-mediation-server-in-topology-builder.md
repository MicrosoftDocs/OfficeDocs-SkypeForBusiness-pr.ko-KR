---
title: 'Lync Server 2013: 토폴로지 작성기에서 중재 서버 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f284b793c79ff3dcf8589a60469ed8525426de1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="eaf61-102">Lync Server 2013의 토폴로지 작성기에서 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="eaf61-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaf61-103">_**마지막으로 수정 된 항목:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="eaf61-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="eaf61-104">토폴로지 작성기를 사용 하 여 독립 실행형 중재 서버 또는 이전에 Enterprise Voice를 배포 하지 않은 사이트의 프런트 엔드 풀이 있는 풀 배치 된을 정의 하려면이 항목의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="eaf61-105">Administrators 그룹의 구성원 계정을 사용하여 토폴로지를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="eaf61-106">프런트 엔드 풀에 대 한 중재 서버 배치 된 정의</span><span class="sxs-lookup"><span data-stu-id="eaf61-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="eaf61-107">토폴로지 작성기를 사용 하 여 엔터프라이즈 음성이 이전에 배포 되지 않은 사이트의 프런트 엔드 풀로 중재 서버 배치 된를 정의 하려면이 항목의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="eaf61-108">프런트 엔드 풀에 중재 서버를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="eaf61-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="eaf61-109">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="eaf61-110">토폴로지 작성기의 콘솔 트리에서 프런트 엔드 풀을 정의할 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="eaf61-111">콘솔 트리에서 원하는 프런트 엔드 풀 유형을 마우스 오른쪽 단추로 클릭 하 고 **새 프런트 엔드 풀 ...** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="eaf61-112">**배치된 서버 역할 선택** 페이지에 도달할 때까지 **새 프런트 엔드 풀 정의** 마법사를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="eaf61-113">**배치 된 서버 역할 선택**에서 **함께 배치할 중재 서버**옵션을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="eaf61-114">선택한 프런트 엔드 풀 유형이 Enterprise Edition 이면 해당 프런트 엔드 풀의 모든 프런트 엔드 서버에 중재 서버 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eaf61-115">중재 서버에서 사용 되는 <STRONG>다음 홉 풀</STRONG> 은 중재 서버가 배치 된 되는 프런트 엔드 풀이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="eaf61-116">중재 서버에서 사용 되는에 <STRONG>지 풀</STRONG> 은 중재 서버가 배치 된 프런트 엔드 풀과 연결 된 동일한에 지 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="eaf61-117">이 프런트 엔드 풀을 사용 하 여 Microsoft Office Communications Server 2007 2 r 2의 통화를 PSTN으로 라우팅하도록 **기본값으로 설정** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="eaf61-118">하나 이상의 피어를 프런트 엔드 풀에 연결 하는 작업이 끝나면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eaf61-119">Enterprise Voice 배포 프로세스의 다음 단계로 진행 하기 전에 중재 서버 풀 (즉, 중재 서버 구성 요소가 배치 된 인 프런트 엔드 풀)이 지정한 Fqdn을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="eaf61-120">그런 다음 필요에 따라 중재 서버의 수신 대기 포트를 수정 하는 다음 단계를 진행 하기 전에 배포 가이드 설명서의 [Lync server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차에 따라 중재 서버를 토폴로지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="eaf61-121">토폴로지 작성기를 사용 하 여 토폴로지를 정의 하거나 수정할 때마다 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="eaf61-122">독립 실행형 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="eaf61-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="eaf61-123">엔터프라이즈 음성이 이전에 배포 되지 않은 사이트에서 토폴로지 작성기를 사용 하 여 독립 실행형 중재 서버 또는 풀을 정의 하려면이 항목의 단계를 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="eaf61-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="eaf61-124">이 사이트의 프런트 엔드 풀에 배치 된 중재 서버를 이미 배포한 경우 [Lync server 2013에서 트렁크 구성을](lync-server-2013-configuring-trunks.md)진행 하기 전에이 섹션을 건너뛰고 [lync Server 2013에서 중재 서버용 파일을 설치할](lync-server-2013-install-the-files-for-mediation-server.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eaf61-125">이 섹션에서는 배포 가이드 설명서의 lync server <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">2013에서 프런트 엔드 풀 또는 Standard Edition Server 정의 및 구성</A> 에 설명 된 대로 하나 이상의 프런트 엔드 풀을 이미 설정 하 <A href="lync-server-2013-publish-the-topology.md">2013</A> 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="eaf61-126">중재 서버를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="eaf61-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="eaf61-127">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="eaf61-128">토폴로지 작성기의 콘솔 트리에서 중재 서버를 정의 하려는 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="eaf61-129">콘솔 트리에서 **중재 풀** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **중재 서버 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="eaf61-130">**새 중재 풀 정의**에 중재 서버 풀 FQDN (정규화 된 도메인 이름)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="eaf61-131">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="eaf61-132">고가용성을 제공 하기 위해 풀에 여러 중재 서버를 배포 하려면 **다중 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="eaf61-133">여러 중재 서버가 있는 중재 서버 풀을 지원 하려면 DNS 부하 분산을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="eaf61-134">자세한 내용은 계획 설명서의 <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013에서 dns 부하 분산</A> 의 중재 서버 풀에서 Dns 부하 분산 사용 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eaf61-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="eaf61-135">고가용성이 필요 하지 않으므로 풀에 중재 서버를 하나만 배포 하려면 **단일 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="eaf61-136">다음 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-136">Skip the following step.</span></span>

6.  <span data-ttu-id="eaf61-137">이전 단계에서 **다중 컴퓨터 풀**을 선택한 경우 **이 풀의 컴퓨터 정의** 항목에서 **컴퓨터 FQDN**을 클릭하고 풀의 각 서버에 대한 FQDN을 입력한 다음 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="eaf61-138">풀에 추가 하려는 모든 중재 서버에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="eaf61-139">풀의 모든 컴퓨터를 정의했으면 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="eaf61-140">**다음 홉 선택** 페이지에서 **다음 홉 풀**을 클릭 하 고이 중재 서버 풀을 사용할 프런트 엔드 풀의 FQDN을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="eaf61-141">**에지 서버 선택** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="eaf61-142">Enterprise Voice에 대해 사용 하도록 설정 된 외부 사용자에 게 PSTN 연결을 제공 하려면이 **중재 서버에서 사용 하는에 지 풀 선택**에서이 중재 서버 풀을 사용 하는에 지 서버 풀의 FQDN을 클릭 하 여 해당 외부 사용자에 게 PSTN 연결을 제공 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="eaf61-143">Enterprise Voice에 대 한 외부 사용자를 사용 하도록 설정 하지 않거나 내부 네트워크 외부에 있는 사용자에 게 PSTN 연결을 제공 하지 않으려는 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="eaf61-144">다음에는 배포 설명서의 [Lync server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차에 따라 중재 서버를 토폴로지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="eaf61-145">데이터를 사용 하 여 Lync Server를 실행 하는 서버에 대 한 파일을 설치할 수 있도록 토폴로지 작성기를 사용 하 여 토폴로지를 작성 하거나 수정할 때마다 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="eaf61-146">필요한 경우 다음 단계를 진행하여 중재 서버의 수신 대기 포트를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="eaf61-147">중재 서버 수신 대기 포트 정의</span><span class="sxs-lookup"><span data-stu-id="eaf61-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="eaf61-148">토폴로지 작성기를 사용 하 여 중재 서버 또는 풀이 게이트웨이 피어에서 들어오는 연결을 수락 하는 수신 대기 포트를 정의 하려면이 항목의 단계를 수행 하십시오.</span><span class="sxs-lookup"><span data-stu-id="eaf61-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="eaf61-149">중재 서버 수신 대기 포트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="eaf61-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="eaf61-150">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="eaf61-151">토폴로지 작성기의 콘솔 트리에서 **중재 풀** 노드를 확장 하 고 이전에 만든 중재 서버를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="eaf61-152">기본적으로 중재 서버의 SIP 수신 대기 포트는 Lync Server의 TLS 트래픽에 대 한 5070이 고 피어 (게이트웨이, PBXes 또는 sbc)의 TLS 트래픽을 위한 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="eaf61-153">TCP 포트는 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-153">TCP port is disabled by default.</span></span> <span data-ttu-id="eaf61-154">게이트웨이가 TLS를 지원하지 않는 경우 TCP 포트를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="eaf61-155">적절 한 TLS 또는 TCP 수신 대기 포트 범위 지정 중재 서버가 PSTN 게이트웨이에서 들어오는 연결을 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eaf61-156"><STRONG>TCP 포트 사용</STRONG>을 선택하지 않은 경우 TCP 포트 범위를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="eaf61-157">이 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="eaf61-158">그런 다음 lync server [2013의 토폴로지 작성기에서 게이트웨이를 정의](lync-server-2013-define-a-gateway-in-topology-builder.md) 하 고 [lync Server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md)의 절차에 따라 풀의 각 중재 서버에 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaf61-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

