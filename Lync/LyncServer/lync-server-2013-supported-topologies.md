---
title: Lync Server 2013 지원되는 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295d0cfc212fcf09b9752c43e918861f49ec7a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="55c55-102">Lync Server 2013의 지원되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="55c55-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55c55-103">_**마지막으로 수정한 주제:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="55c55-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="55c55-104">Lync Server 2013는 조직에서 온-프레미스 배포를 지원 하 고 Lync Online 배포를 사용 하 여 하이브리드 배포 라고 하는 on-premises deployment를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="55c55-105">하이브리드 배포에서 일부 사용자는 온-프레미스이 고 일부 사용자는 온라인으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="55c55-106">온-프레미스 배포의 경우 Lync Server 2013는 고가용성 및 위치 요구 사항에 맞게 확장할 수 있는 하나 이상의 사이트 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="55c55-107">이러한 사이트와 해당 구성 요소를 조직에 대 한 액세스 및 탄력성 요구 사항에 맞게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="55c55-108">Lync Server 2013 온-프레미스 배포는 다음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="55c55-109">배포에는 하나 이상의 중앙 사이트 (데이터 센터가 라고도 함)가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="55c55-110">각 중앙 사이트에는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버가 하나 이상 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="55c55-111">이러한 작업은 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="55c55-112">하나 이상의 프런트 엔드 서버로 구성 되는 Enterprise Edition 프런트 엔드 풀 (일반적으로 최소 두 개의 프런트 엔드 서버와 확장 가능) 및 별도의 백 엔드 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="55c55-113">프런트 엔드 풀에는 최대 12 개의 프런트 엔드 서버가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="55c55-114">여러 프런트 엔드 서버에 대 한 부하 분산이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="55c55-115">SIP 트래픽의 경우 DNS 부하 분산을 권장 하지만 하드웨어 로드 균형 조정도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="55c55-116">SIP 트래픽에 대 한 DNS 부하 분산을 사용 하는 경우에도 HTTP 트래픽에 대 한 하드웨어 부하 분산 장치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="55c55-117">데이터베이스의 고가용성을 위해 SQL Server 미러링을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="55c55-118">백 엔드 데이터베이스에는 별도의 인스턴스가 필요 하지만, 보관 데이터베이스, 모니터링 데이터베이스, 지속적인 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="55c55-119">Lync Server 2013는 배포의 파일 공유에 대 한 공유 클러스터의 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="55c55-120">데이터베이스 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="55c55-121">파일 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md)참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="55c55-122">Lync Server 데이터베이스를 collocate 경우 가용성 및 성능에 영향을 줄 수 있는 모든 요인을 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="55c55-123">장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="55c55-124">Collocated SQL Server Express 데이터베이스를 포함 하는 Standard Edition 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="55c55-125">배포에는 중앙 사이트와 연결 된 지점 사이트가 하나 이상 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="55c55-126">이 섹션에서는 Lync Server 2013 배포의 사이트 및 구성 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="55c55-127">Lync Server 2013 사이트, 토폴로지 및 구성 요소 계획에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 Lync server 2013 및 [참조 토폴로지](lync-server-2013-reference-topologies.md) 를 [계획 하기 전에 알아야 할 토폴로지 기본 사항](lync-server-2013-topology-basics-you-must-know-before-planning.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="55c55-128">이전 릴리스의 구성 요소 통합에 대 한 자세한 내용은 [Lync Server 2013에서 지원 되는 마이그레이션 경로 및 공존 시나리오](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55c55-129">스트레치 된 풀은 프런트 엔드, Edge, 중재 및 디렉터 서버 역할에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="55c55-130">중앙 사이트 토폴로지 및 구성 요소 (온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="55c55-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="55c55-131">중앙 사이트 토폴로지에는 프런트 엔드 풀 또는 표준 버전 서버 하나가 포함 되어야 하지만 각 중앙 사이트에는 다음이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="55c55-132">여러 프런트 엔드 풀 (동일한 도메인 또는 다른 도메인에 있을 수 있음)</span><span class="sxs-lookup"><span data-stu-id="55c55-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="55c55-133">그러나 프런트 엔드 풀의 모든 프런트 엔드 서버와 해당 풀의 백 엔드 서버는 동일한 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="55c55-134">여러 스탠더드 버전 서버.</span><span class="sxs-lookup"><span data-stu-id="55c55-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="55c55-135">Lync Server 2013의 Office 웹 응용 프로그램에서 Microsoft PowerPoint 프레젠테이션 공유 및 렌더링을 처리 하는 데 사용 되는 office Web Apps 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="55c55-136">경계 네트워크의 edge 서버 또는 Edge 풀 배포에 페더레이션 파트너, 공용 IM 연결, 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이, 원격 사용자 액세스, 모임에서 익명 사용자 참가 등을 원하는 경우 또는 Exchange UM (통합 메시징).</span><span class="sxs-lookup"><span data-stu-id="55c55-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="55c55-137">Edge 서버를 사용 하 여 다른 서버 역할을 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="55c55-138">적절 한 경우 DNS 부하 분산을 유지 하는 것이 좋지만 하드웨어 로드 균형 조정도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="55c55-139">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="55c55-140">즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="55c55-141">부하 분산 요구 사항 및 지원에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="55c55-142">중앙 사이트의 프런트 엔드 풀에서 엔터프라이즈 음성 또는 전화 접속 회의를 지원 하려는 경우 중재 서버 또는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="55c55-143">엔터프라이즈 음성 기능을 배포 하는 방법에 따라 프런트 엔드 풀의 중재 서버를 collocate (기본값) 또는 독립 실행형 중재 서버 또는 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="55c55-144">DNS, 하드웨어 또는 응용 프로그램 부하 분산 (적절 한 경우)을 사용 하 여 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크 세션 경계 컨트롤 (SBC)을 포함 하는 중재 서버 풀의 게이트웨이 피어에서 트래픽을 분산할 수 있습니다. 적절 한 중재 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="55c55-145">사용자가 시간에 따라 유지 되는 단체의 주제 기반 대화에 참여할 수 있게 하려는 경우 영구 채팅 서버.</span><span class="sxs-lookup"><span data-stu-id="55c55-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="55c55-146">용량 향상과 안정성이 높은 안정성을 제공 하기 위해 토폴로지에 영구 채팅 서버를 실행 하는 여러 대의 컴퓨터가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="55c55-147">엔터프라이즈 풀의 다른 서버 역할과 영구 채팅 서버를 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="55c55-148">그러나 Standard Edition 서버에서 영구 채팅 서버를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="55c55-149">영구 채팅에는 데이터베이스가 필요 하며 지속적인 채팅 준수 데이터베이스를 구현 하는 경우 데이터베이스를 보관 데이터베이스, 모니터링 데이터베이스 또는 엔터프라이즈 에디션의 백 엔드 서버와 collocated 수 있습니다. 프런트 엔드 풀.</span><span class="sxs-lookup"><span data-stu-id="55c55-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="55c55-150">적절 한 영구 채팅 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="55c55-151">모니터링-오디오/비디오 품질 (체감 품질) 및 배포에서 A/V 회의에 대 한 데이터 수집을 지원 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="55c55-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="55c55-152">필요한 경우 모니터링 CDR 및 체감 품질 데이터를 사용 하 여 통화 안정성 및 미디어 품질의 상태를 표시 하는 가까운 실시간 알림을 생성 하는 Microsoft System Center Operations Manager (이전의 Microsoft Operations Manager)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="55c55-153">모니터링을 배포 하는 경우 프런트 엔드 서버 또는 Standard Edition 서버에서 collocated.</span><span class="sxs-lookup"><span data-stu-id="55c55-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="55c55-154">모니터링에는 데이터베이스가 필요 하지만, 데이터베이스는 보관 데이터베이스, 영구 채팅 데이터베이스, 지속적인 채팅 준수 데이터베이스 또는 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버와 collocated 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="55c55-155">배포에서 IM 통신 및 모임 콘텐츠 (규정 준수 사유)를 보관 하려는 경우 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="55c55-156">보관 하는 경우 collocated는 프런트 엔드 서버 또는 Standard Edition 서버에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="55c55-157">보관 저장소에는 보관 데이터베이스 배포 또는 Exchange 2013 저장소 통합이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="55c55-158">*혼합 모드*라고 하는 둘 다를 사용 하는 경우 exchange 2013 저장소를 사용 하 여 exchange 2013에 속한 사용자의 보관 데이터를 저장 하 고 배포의 다른 모든 사용자에 대 한 데이터를 보관 하는 데 보관 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="55c55-159">보관 데이터베이스가 필요한 경우 모니터링 데이터베이스, 영구 채팅 데이터베이스, 지속적인 채팅 준수 데이터베이스 또는 프런트 엔드 풀의 백 엔드 서버에서 데이터베이스를 collocated 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="55c55-160">적절 한 보관 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="55c55-161">사용자의 홈 풀 (Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버)으로 Lync Server 2013 사용자 요청을 복구 하 고 리디렉션할 수 있도록 하려면 디렉터 또는 디렉터 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="55c55-162">외부 사용자 액세스를 지 원하는 각 중앙 사이트에서 하나 이상의 프런트 엔드 풀을 배포 하는 각 중앙 사이트에 디렉터 또는 디렉터 풀을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="55c55-163">각 디렉터 풀에는 최대 10 개의 이사회이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="55c55-164">다른 서버 역할을 사용 하 여 디렉터를 collocated 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="55c55-165">적절 한 디렉터 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="55c55-166">역방향 프록시-Lync Server 2013 구성 요소가 아니지만 페더레이션 사용자를 위해 웹 콘텐츠를 공유 하거나 이동성 트래픽을 지원 하려는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="55c55-167">역방향 프록시 서버에 Lync Server 2013 서버 역할을 collocate 수는 없지만, 다른 사용자에 게 사용 되는 조직의 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다. 프로그램도.</span><span class="sxs-lookup"><span data-stu-id="55c55-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="55c55-168">리버스 프록시 서버에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 리버스 프록시 서버 설정을](lync-server-2013-setting-up-reverse-proxy-servers.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55c55-169">Lync Server 2013에서 A/V 회의, 모니터링, 보관은 프런트 엔드 서버에서 실행 되며 더 이상 별도의 서버 역할이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="55c55-170">중앙 사이트에서 배포 하는 모든 프런트 엔드 풀 및 Standard Edition 서버는 중앙 사이트에 대해 배포 하는 다음 중 하나를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="55c55-171">이사 또는 이사 은행</span><span class="sxs-lookup"><span data-stu-id="55c55-171">Director or Director pool</span></span>

  - <span data-ttu-id="55c55-172">독립 실행형 중재 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="55c55-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="55c55-173">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="55c55-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="55c55-174">Edge 서버 또는 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="55c55-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="55c55-175">영구 채팅 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="55c55-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="55c55-176">모니터링</span><span class="sxs-lookup"><span data-stu-id="55c55-176">Monitoring</span></span>

  - <span data-ttu-id="55c55-177">보관</span><span class="sxs-lookup"><span data-stu-id="55c55-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55c55-178">Exchange 2013 통합 메시징의 통합을 지원 하려는 경우에는 Lync server 2013 배포를 사용 하 여 Exchange UM 서버를 구현할 수 있지만 Lync Server 2013 사이트의 구성 요소가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="55c55-179">여러 중앙 사이트는 한 중앙 사이트에서 배포 하는 다음 중 하나를 공유할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="55c55-180">독립 실행형 중재 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="55c55-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="55c55-181">Edge 서버 또는 Edge 풀</span><span class="sxs-lookup"><span data-stu-id="55c55-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="55c55-182">영구 채팅 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="55c55-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="55c55-183">보관</span><span class="sxs-lookup"><span data-stu-id="55c55-183">Archiving</span></span>

  - <span data-ttu-id="55c55-184">모니터링</span><span class="sxs-lookup"><span data-stu-id="55c55-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55c55-185">Exchange UM 서버는 Lync Server 2013 배포로 구현 하 고 여러 중앙 사이트에서 공유할 수 있지만 Lync Server 2013 사이트의 구성 요소는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="55c55-186">Lync Server 2013 서버 역할 및 기능에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 서버 역할](lync-server-2013-server-roles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="55c55-187">Lync Server 2013 서버 collocation 지원에 대 한 요약 정보는 [Lync server 2013에서 지원 되는 서버 위치](lync-server-2013-supported-server-collocation.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="55c55-188">이 섹션의 앞부분에 설명 된 서버 역할 및 기능 외에도 Lync Server 2013에는 다음과 같은 추가 구성 요소와 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="55c55-189">들</span><span class="sxs-lookup"><span data-stu-id="55c55-189">Firewalls</span></span>

  - <span data-ttu-id="55c55-190">PSTN 게이트웨이 (Enterprise Voice를 배포 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="55c55-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="55c55-191">Exchange UM 서버</span><span class="sxs-lookup"><span data-stu-id="55c55-191">Exchange UM Server</span></span>

  - <span data-ttu-id="55c55-192">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="55c55-192">DNS load balancing</span></span>

  - <span data-ttu-id="55c55-193">하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="55c55-193">Hardware load balancers</span></span>

  - <span data-ttu-id="55c55-194">SQL Server 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="55c55-194">SQL Server databases</span></span>

  - <span data-ttu-id="55c55-195">파일 공유</span><span class="sxs-lookup"><span data-stu-id="55c55-195">File shares</span></span>

<span data-ttu-id="55c55-196">모든 Lync Server 2013 기능, 구성 요소 및 옵션에 대 한 자세한 내용은 계획 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55c55-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="55c55-197">지점 사이트 토폴로지 및 구성 요소 (온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="55c55-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="55c55-198">지점 사이트는 중앙 사이트와 연결 되며, 지점 사이트의 각 Survivable Branch 기기는 Enterprise Edition 프런트 엔드 풀 또는 연결 된 중앙 사이트의 스탠더드 버전 서버와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="55c55-199">분기 사이트는 대부분의 기능에 종속 되어 있으므로 지점 사이트의 구성 요소에는 다음만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="55c55-200">PSTN (공개 통신 네트워크) 게이트웨이와 일부 Lync Server 기능을 결합 하는 Survivable Branch 기기입니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="55c55-201">중재 서버는 Survivable Branch 기기의 레지스트라 인스턴스와 collocated 수 있으며, 독립 실행형 중재 서버 또는 중재 서버 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="55c55-202">Lync Server 2013 등록자 및 조정 서버 소프트웨어가 설치 된 Windows Server를 실행 하는 서버인 Survivable Branch 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="55c55-203">독립 실행형 PSTN 게이트웨이 (Survivable Branch 기기의 일부가 아님) 및 독립 실행형 중재 서버.</span><span class="sxs-lookup"><span data-stu-id="55c55-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="55c55-204">Survivable 분기 서버에 대 한 요구 사항은 Lync Server 2013 서버 역할의 요구 사항과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="55c55-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

