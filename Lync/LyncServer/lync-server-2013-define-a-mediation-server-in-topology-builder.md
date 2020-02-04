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
ms.openlocfilehash: bdff7da86bd7298511ea0ef384b2736a47882a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="da9ae-102">Lync Server 2013의 토폴로지 작성기에서 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="da9ae-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da9ae-103">_**마지막으로 수정한 주제:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="da9ae-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="da9ae-104">이 항목의 단계를 따라 토폴로지 작성기를 사용 하 여 독립 실행형 중재 서버 또는 이전에 엔터프라이즈 음성을 배포 하지 않은 사이트의 프런트 엔드 풀을 사용 하는 풀 collocated을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="da9ae-105">관리자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="da9ae-106">프런트 엔드 풀에 대 한 중재 서버 collocated 정의</span><span class="sxs-lookup"><span data-stu-id="da9ae-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="da9ae-107">이 항목의 단계를 따라 토폴로지 작성기를 사용 하 여 엔터프라이즈 음성이 이전에 배포 되지 않은 사이트의 프런트 엔드 풀에 대 한 중재 서버 collocated 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="da9ae-108">프런트 엔드 풀에 중재 서버를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="da9ae-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="da9ae-109">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="da9ae-110">토폴로지 작성기의 콘솔 트리에서 프런트 엔드 풀을 정의 하려는 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="da9ae-111">콘솔 트리에서 원하는 프런트 엔드 풀의 종류를 마우스 오른쪽 단추로 클릭 한 다음 **새 프런트 엔드 풀 ...** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="da9ae-112">**Collocated 서버 역할 선택** 페이지에 도달할 때까지 **새 프런트 엔드 풀 정의** 마법사를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="da9ae-113">**Collocated 서버 역할 선택**에서 **Collocate 중재 서버**옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="da9ae-114">선택한 프런트 엔드 풀 유형이 Enterprise Edition 이면 해당 프런트 엔드 풀의 모든 프런트 엔드 서버에 중재 서버 구성 요소가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="da9ae-115">조정 서버에서 사용 하는 <STRONG>다음 홉 풀</STRONG> 은 중재 서버가 Collocated 된 프런트 엔드 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="da9ae-116">조정 서버에서 사용 되는 <STRONG>edge 풀</STRONG> 은 중재 서버가 Collocated 인 프런트 엔드 풀과 연결 된 edge 풀과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="da9ae-117">이 프런트 엔드 풀을 사용 하 여 Microsoft Office Communications Server 2007 R2의 통화를 PSTN으로 라우팅하기 위해 **기본값으로 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="da9ae-118">하나 이상의 피어를 프런트 엔드 풀에 연결 하는 작업이 완료 되 면 **마침을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da9ae-119">엔터프라이즈 음성 배포 프로세스의 다음 단계로 진행 하기 전에 조정 서버 풀 (즉, 중재 서버 구성 요소가 collocated 인 프런트 엔드 풀)이 지정한 Fqdn을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="da9ae-120">다음으로, 필요한 경우 중재 서버의 수신 대기 포트를 수정 하는 다음 단계로 진행 하기 전에 배포 가이드 설명서의 [Lync server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차에 따라 토폴로지에 조정 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="da9ae-121">토폴로지를 정의 하거나 수정할 때마다 토폴로지 작성기를 사용 하 여 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="da9ae-122">독립 실행형 중재 서버 정의</span><span class="sxs-lookup"><span data-stu-id="da9ae-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="da9ae-123">이 항목의 단계를 따라 토폴로지 작성기를 사용 하 여 엔터프라이즈 음성이 이전에 배포 되지 않은 사이트에서 독립 실행형 중재 서버 또는 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="da9ae-124">이 사이트의 프런트 엔드 풀에 collocated 중재 서버를 이미 배포한 경우 lync server [2013에서 Trunks 구성을](lync-server-2013-configuring-trunks.md)진행 하기 전에이 섹션을 건너뛰고 [lync Server 2013에서 중재 서버용 파일을 설치할](lync-server-2013-install-the-files-for-mediation-server.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="da9ae-125">이 섹션에서는 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성</A> 에 설명 된 대로 하나 이상의 프런트 엔드 풀을 이미 설정 했다고 가정 하 고 배포 가이드 설명서의 <A href="lync-server-2013-publish-the-topology.md">lync server 2013에 토폴로지를 게시</A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="da9ae-126">중재 서버를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="da9ae-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="da9ae-127">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="da9ae-128">토폴로지 작성기의 콘솔 트리에서 중재 서버를 정의 하려는 사이트의 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="da9ae-129">콘솔 트리에서 **중재 풀** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **중재 서버 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="da9ae-130">**새 중재 풀 정의**에 중재 서버 풀 정규화 된 도메인 이름 (FQDN)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="da9ae-131">다음으로 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="da9ae-132">풀에 여러 중재 서버를 배포 하 여 고가용성을 제공 하려는 경우 **여러 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="da9ae-133">여러 중재 서버가 있는 중재 서버 풀을 지원 하려면 DNS 부하 분산을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="da9ae-134">자세한 내용은 계획 설명서의 <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013에서 dns 부하 분산</A> 의 중재 서버 풀에 Dns 부하 분산 사용 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da9ae-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="da9ae-135">고가용성이 필요 하지 않으므로 풀에 하나의 중재 서버만 배포 하려면 **단일 컴퓨터 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="da9ae-136">다음 단계를 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="da9ae-136">Skip the following step.</span></span>

6.  <span data-ttu-id="da9ae-137">이전 단계에서 **컴퓨터 풀을 여러 개** 선택한 경우 **이 풀의 컴퓨터 정의** 항목에서 **컴퓨터 fqdn**을 클릭 하 고 풀의 각 서버에 대 한 fqdn을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="da9ae-138">풀에 추가 하려는 다른 모든 중재 서버에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="da9ae-139">풀의 모든 컴퓨터를 정의한 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="da9ae-140">**다음 홉 선택** 페이지에서 **다음 홉 풀**을 클릭 하 고이 중재 서버 풀을 사용 하는 프런트 엔드 풀의 FQDN을 클릭 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="da9ae-141">**Edge 서버 선택** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="da9ae-142">Enterprise Voice에 대해 사용 하도록 설정 된 외부 사용자에 게 PSTN 연결을 제공 하려는 경우 **이 중재 서버에서 사용 하는 Edge 풀 선택**아래에서이 중재 서버 풀을 사용 하는 edge 서버 풀의 FQDN을 클릭 하 여 해당 외부 사용자에 게 PSTN 연결을 제공 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="da9ae-143">외부 사용자에 게 Enterprise Voice를 사용할 수 있도록 설정 하지 않으려는 경우 또는 내부 네트워크 외부에 있을 때 사용자에 게 PSTN 연결을 제공 하지 않으려는 경우 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="da9ae-144">다음으로 배포 설명서의 [Lync server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 의 절차에 따라 중재 서버를 토폴로지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="da9ae-145">데이터를 사용 하 여 Lync Server를 실행 하는 서버에 대 한 파일을 설치할 수 있도록 토폴로지 작성기를 사용 하 여 토폴로지를 빌드하거나 수정할 때마다 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="da9ae-146">필요에 따라 다음 단계를 계속 진행 하 여 중재 서버의 수신 대기 포트를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="da9ae-147">중재 서버 수신 대기 포트 정의</span><span class="sxs-lookup"><span data-stu-id="da9ae-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="da9ae-148">토폴로지 작성기를 사용 하 여 수신 대기 포트를 정의 하려면이 항목의 단계를 따르세요. 중재 서버 또는 풀은 게이트웨이 피어에서 들어오는 연결을 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="da9ae-149">중재 서버 수신 대기 포트를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="da9ae-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="da9ae-150">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="da9ae-151">토폴로지 작성기의 콘솔 트리에서 **중재 풀** 노드를 확장 하 고 이전에 만든 중재 서버를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="da9ae-152">기본적으로 중재 서버의 SIP 수신 대기 포트는 Lync Server의 TLS 트래픽용 5070, 피어에서의 TLS 트래픽 (게이트웨이, PBXes 또는 SBCs)에 대해 5067입니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="da9ae-153">TCP 포트는 기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-153">TCP port is disabled by default.</span></span> <span data-ttu-id="da9ae-154">TLS를 지원 하지 않는 게이트웨이가 있는 경우 TCP 포트를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="da9ae-155">중재 서버가 PSTN 게이트웨이에서 들어오는 연결을 허용 하는 원하는 TLS 또는 TCP 수신 대기 포트 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da9ae-156"><STRONG>Tcp 포트 사용</STRONG> 이 선택 되어 있지 않은 경우 tcp 포트 범위를 입력 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="da9ae-157">이 설정은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="da9ae-158">다음으로 [Lync server 2013의 토폴로지 작성기에서 게이트웨이를 정의](lync-server-2013-define-a-gateway-in-topology-builder.md) 하 고 [lync server 2013의 조정 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md)절차에 따라 풀의 각 중재 서버에 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="da9ae-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

