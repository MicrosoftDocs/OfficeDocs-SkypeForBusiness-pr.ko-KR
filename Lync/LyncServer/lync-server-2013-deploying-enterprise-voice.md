---
title: 'Lync Server 2013: Enterprise Voice 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a19016a095e38a0df70a561976c6b03d59fdfd1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="5c989-102">Lync Server 2013에서 Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="5c989-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c989-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5c989-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5c989-104">Lync Server 2013, Enterprise Voice는 Lync Server 2013 인프라의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="5c989-105">Enterprise Voice를 배포 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="5c989-106">계획 설명서의 [Lync Server 2013에서 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md) 을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="5c989-107">이 작업을 통해 배포할 기능 및 구성 요소에 대 한 계획을 완성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="5c989-108">계획 도구를 실행 하 여 배포 결정 사항을 반영 하는 토폴로지를 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="5c989-109">배포 설명서의 [Lync Server 2013에서 토폴로지 정의 및 구성](lync-server-2013-defining-and-configuring-the-topology.md) 에 설명 된 대로 토폴로지 작성기에서 토폴로지 디자인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5c989-110">토폴로지 작성기 설치는 내부 풀에 대 한 배포 프로세스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="5c989-111">자세한 내용은 배포 설명서의 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 관리 도구</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c989-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="5c989-112">또한 배포 하도록 선택한 참조 토폴로지에 해당 하는 중앙 사이트 및 분기 사이트에 Lync Server, Enterprise Edition이 이미 배포 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="5c989-113">하나 이상의 내부 풀에 대해 파일을 정의, 게시 및 설치한 후에 Enterprise Voice 구성 요소를 배포할 수 있으며, 토폴로지 작성기를 사용 하 여 내부 풀을 정의 하 고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="5c989-114">Enterprise Voice 서버 역할을 배포할 수 있는 위치 (및 서로 다른 Lync Server 2013 서버 역할에 대 한 해당 관계)의 예를 포함 하는 참조 토폴로지를 보려면 계획 설명서에서 [Lync server 2013의 참조 토폴로지](lync-server-2013-reference-topologies.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c989-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="5c989-115">네트워크 지역, 네트워크 사이트 및 서브넷을 비롯 한 샘플 통화 허용 제어 배포를 보여 주고 설명 하는 참조 토폴로지를 보려면 계획 설명서에서 [예제: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c989-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5c989-116">중앙 사이트에서 Enterprise Voice를 배포 하려면이 섹션의 항목을 계속 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="5c989-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="5c989-117">분기 사이트에서 Enterprise Voice를 배포 하려면 배포 설명서에서 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013에서 분기 사이트를 배포</A> 하는 방법을 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="5c989-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="5c989-118">이 섹션에는 각 프런트 엔드 서버 또는 Standard Edition Server에서 권장 되는 중재 서버를 배치 된 하는 배포 및 독립 실행형 중재 서버 풀을 사용 하는 배포에 대 한 절차가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="5c989-119">배포 마법사에서 각 프런트 엔드 서버 또는 Standard Edition Server에서 중재 서버를 찾은 토폴로지를 정의한 후 게시 하는 경우 다음 콘텐츠를 건너뛸 수 있습니다. 중재 서버: 프런트 엔드 서버 풀 또는 Standard Edition Server에 대 한 파일을 설치할 때 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="5c989-120">Lync Server 2013에서 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="5c989-121">토폴로지 작성기를 사용 하 여 독립 실행형 풀에 중재 서버를 정의 하 고 게시 한 경우 다음 콘텐츠를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="5c989-122">[Lync Server 2013에 대 한 Enterprise Voice 필수 구성 요소](lync-server-2013-enterprise-voice-prerequisites.md)에 설명 된 대로 토폴로지가 소프트웨어 및 환경 필수 구성 요소를 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c989-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c989-123">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5c989-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="5c989-124">Lync Server 2013에 대 한 Enterprise Voice 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5c989-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="5c989-125">Lync Server 2013에서 중재 서버 배포 및 피어 정의</span><span class="sxs-lookup"><span data-stu-id="5c989-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="5c989-126">Lync Server 2013에서 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="5c989-127">Lync Server 2013에서 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="5c989-128">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="5c989-129">Lync Server 2013에서 음성 라우팅 구성 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="5c989-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="5c989-130">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="5c989-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="5c989-131">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="5c989-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="5c989-132">Lync Server 2013 음성 메일을 제공 하도록 온-프레미스 Exchange UM 배포</span><span class="sxs-lookup"><span data-stu-id="5c989-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="5c989-133">Lync Server 2013 users 사용자에 게 호스팅된 Exchange UM에 대 한 음성 메일 제공</span><span class="sxs-lookup"><span data-stu-id="5c989-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="5c989-134">Exchange Online과 온-프레미스 Lync Server 2013의 통합 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="5c989-135">Lync Server 2013에서 고급 Enterprise Voice 기능 배포</span><span class="sxs-lookup"><span data-stu-id="5c989-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="5c989-136">Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보</span><span class="sxs-lookup"><span data-stu-id="5c989-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="5c989-137">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5c989-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="5c989-138">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5c989-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="5c989-139">Lync Server 2013에서 서브넷을 네트워크 사이트에 연결</span><span class="sxs-lookup"><span data-stu-id="5c989-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="5c989-140">Lync Server 2013에서 통화 허용 제어 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="5c989-141">Lync Server 2013에서 향상 된 9-1-1 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="5c989-142">Lync Server 2013에서 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="5c989-143">Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="5c989-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5c989-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c989-144">See Also</span></span>


[<span data-ttu-id="5c989-145">Lync Server 2013에서 분기 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="5c989-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="5c989-146">Lync Server 2013에서 전화 접속 회의 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="5c989-147">Lync Server 2013에서 통화 대기 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="5c989-148">Lync Server 2013에서 할당 되지 않은 번호에 대 한 알림 구성</span><span class="sxs-lookup"><span data-stu-id="5c989-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="5c989-149">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="5c989-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

