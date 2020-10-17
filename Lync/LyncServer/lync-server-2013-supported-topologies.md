---
title: Lync Server 2013 지원 되는 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523965"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="ec5e7-102">Lync Server 2013에서 지원 되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="ec5e7-102">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec5e7-103">_**마지막으로 수정 된 항목:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="ec5e7-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="ec5e7-104">Lync Server 2013에서는 온-프레미스에 사이트를 배포할 수 있도록 지원 하 고 하이브리드 배포 라고도 하는 Lync Online 배포와의 통합을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="ec5e7-105">하이브리드 배포에서는 온-프레미스와 온라인에 각각 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="ec5e7-106">온-프레미스 배포의 경우 Lync Server 2013은 고가용성 및 위치 요구 사항을 충족 하기 위해 확장할 수 있는 하나 이상의 사이트 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="ec5e7-107">이러한 사이트와 해당 구성 요소를 조직의 액세스 및 복구 요구 사항을 충족하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="ec5e7-108">Lync Server 2013 온-프레미스 배포는 다음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="ec5e7-p103">배포에 중앙 사이트(데이터 센터라고도 함)가 하나 이상 포함되어야 합니다. 각 중앙 사이트는 하나 이상의 Enterprise Edition 프런트 엔드 풀 또는 하나의 Standard Edition 서버를 포함해야 합니다. 이러한 풀 또는 서버는 다음으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="ec5e7-112">Enterprise Edition 프런트 엔드 풀은 하나 이상의 프런트 엔드 서버와 별도의 백 엔드 서버로 구성되며, 일반적으로 확장성을 위해 둘 이상의 프런트 엔드 서버를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="ec5e7-113">프런트 엔드 풀은 최대 12 개의 프런트 엔드 서버를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="ec5e7-114">프런트 엔드 서버가 여러 개인 경우 부하 분산이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="ec5e7-115">SIP 트래픽의 경우 DNS 부하 분산이 권장되지만 하드웨어 부하 분산도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="ec5e7-116">SIP 트래픽에 DNS 부하 분산을 사용하는 경우에도 HTTP 트래픽에 대한 하드웨어 부하 분산 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="ec5e7-117">데이터베이스의 고가용성을 위해 SQL Server 미러링을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="ec5e7-118">백 엔드 데이터베이스에는 별도의 인스턴스가 필요하지만 보관 데이터베이스, 미러링 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="ec5e7-119">Lync Server 2013에서는 배포의 파일 공유에 대 한 공유 클러스터 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="ec5e7-120">데이터베이스 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="ec5e7-121">파일 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="ec5e7-122">Lync Server 데이터베이스를 함께 배치할 경우 가용성 및 성능에 영향을 줄 수 있는 모든 요소를 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="ec5e7-123">장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="ec5e7-124">Standard Edition 서버는 함께 배치된 SQL Server Express 데이터베이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="ec5e7-125">배포에 중앙 사이트와 연결된 하나 이상의 분기 사이트를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="ec5e7-126">이 섹션에서는 Lync Server 2013 배포의 사이트 및 구성 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="ec5e7-127">Lync Server 2013 사이트, 토폴로지 및 구성 요소 계획에 대 한 자세한 내용은 계획 설명서에서 lync server 2013 및 [참조 2013 토폴로지](lync-server-2013-reference-topologies.md) 를 [계획 하기 전에 알아야 할 토폴로지 기본 사항을](lync-server-2013-topology-basics-you-must-know-before-planning.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="ec5e7-128">이전 릴리스의 구성 요소를 통합 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 지원 되는 마이그레이션 경로 및 동시 사용 시나리오](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec5e7-129">스트레치 된 풀은 프런트 엔드, Edge, 중재 및 디렉터 서버 역할에 대해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="ec5e7-130">중앙 사이트 토폴로지 및 구성 요소(온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="ec5e7-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="ec5e7-131">중앙 사이트 토폴로지는 하나의 프런트 엔드 풀 또는 하나의 Standard Edition 서버를 포함해야 하지만 각 중앙 사이트는 다음을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="ec5e7-p107">같은 도메인 또는 다른 도메인에 있을 수 있는 여러 프런트 엔드 풀. 그러나 프런트 엔드 풀의 모든 프런트 엔드 서버와 해당 풀에 대한 백 엔드 서버는 같은 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="ec5e7-134">여러 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="ec5e7-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="ec5e7-135">Lync Server 2013의 Office 웹 응용 프로그램에서 사용 하는 office Web Apps 서버는 Microsoft PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="ec5e7-136">경계 네트워크의에 지 서버 또는에 지 풀 배포를 통해 페더레이션 파트너, 공용 IM 연결, 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이, 원격 사용자 액세스, 모임에서 익명 사용자의 참여 또는 Exchange UM (통합 메시징)을 지원 하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="ec5e7-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="ec5e7-137">다른 서버 역할을 에지 서버와 함께 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="ec5e7-138">해당되는 경우 DNS 부하 분산이 권장되지만 하드웨어 부하 분산도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="ec5e7-139">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="ec5e7-140">즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="ec5e7-141">부하 분산 요구 사항 및 지원에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync Server 2013의](lync-server-2013-deploying-external-user-access.md) 배포 설명서에서 external user access 배포를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ec5e7-142">중재 서버 또는 풀 (중앙 사이트의 프런트 엔드 풀에서 Enterprise Voice 또는 전화 접속 회의를 지원 하려는 경우)</span><span class="sxs-lookup"><span data-stu-id="ec5e7-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="ec5e7-143">Enterprise Voice support를 배포 하는 방법에 따라 프런트 엔드 풀에 중재 서버를 함께 배치할 (기본값) 아니면 독립 실행형 중재 서버 또는 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="ec5e7-144">DNS, 하드웨어 또는 응용 프로그램 부하 분산 (해당 하는 경우)을 사용 하 여 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크 세션 테두리 조절 (SBC)을 포함 하 여 중재 서버 풀의 게이트웨이 피어에서 트래픽을 분산할 수 있습니다. 적절 한 중재 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="ec5e7-145">영구 채팅 서버 (사용자가 시간에 따라 지속 되는 단체의 항목 기반 대화에 참가할 수 있도록 하려는 경우)</span><span class="sxs-lookup"><span data-stu-id="ec5e7-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ec5e7-146">더 많은 용량과 안정성을 제공 하기 위해 토폴로지에 영구 채팅 서버를 실행 하는 여러 컴퓨터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="ec5e7-147">엔터프라이즈 풀의 다른 서버 역할과 영구 채팅 서버를 함께 배치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="ec5e7-148">그러나 Standard Edition 서버에서 영구 채팅 서버를 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="ec5e7-149">영구 채팅에는 데이터베이스가 필요하며, 영구 채팅 준수를 구현하는 경우에는 영구 채팅 준수 데이터베이스도 필요하지만 이러한 데이터베이스는 보관 데이터베이스/모니터링 데이터베이스와 함께 배치하거나 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="ec5e7-150">적절 한 영구 채팅 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 " [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="ec5e7-151">모니터링(배포에 포함된 Enterprise Voice 및 A/V 회의의 CDR(통화 정보 기록) 및 오디오/비디오 QoE(체감 품질)에 대한 데이터 수집을 지원하려는 경우).</span><span class="sxs-lookup"><span data-stu-id="ec5e7-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="ec5e7-152">필요에 따라 모니터링 CDR 및 QoE 데이터를 사용 하 여 통화 안정성 및 미디어 품질의 상태를 표시 하는 거의 실시간 경고를 생성 하는 Microsoft System Center Operations Manager (이전 Microsoft Operations Manager)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="ec5e7-153">모니터링은 배포하는 경우 프런트 엔드 서버 또는 Standard Edition 서버에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="ec5e7-154">모니터링에는 데이터베이스가 필요하지만 해당 데이터베이스는 보관 데이터베이스/영구 채팅 데이터베이스/영구 채팅 준수 데이터베이스와 함께 배치하거나 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="ec5e7-155">보관(준수용으로 배포의 IM 통신 및 모임 콘텐츠를 보관하려는 경우).</span><span class="sxs-lookup"><span data-stu-id="ec5e7-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="ec5e7-156">보관은 배포하는 경우 프런트 엔드 서버 또는 Standard Edition 서버에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="ec5e7-157">보관 저장소를 사용 하려면 보관 데이터베이스를 배포 하거나 Exchange 2013 저장소와 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="ec5e7-158">*혼합 모드*라고 하는 둘 다 사용 하는 경우 exchange 2013 저장소는 exchange 2013에 있는 사용자에 대 한 보관 데이터를 저장 하는 데 사용 되며, 배포의 다른 모든 사용자에 대 한 데이터를 보관 하는 데 보관 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="ec5e7-159">보관 데이터베이스가 필요한 경우 해당 데이터베이스는 모니터링 데이터베이스/영구 채팅 데이터베이스/영구 채팅 준수 데이터베이스와 함께 배치하거나 프런트 엔드 풀의 백 엔드 서버에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="ec5e7-160">적절 한 보관 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="ec5e7-161">디렉터 또는 디렉터 풀-사용자의 홈 풀에 대 한 Lync Server 2013 사용자 요청을 복구 및 리디렉션하는 것을 용이 하 게 하려면 (Enterprise Edition 프런트 엔드 풀 또는 Standard Edition Server 일 수 있음)</span><span class="sxs-lookup"><span data-stu-id="ec5e7-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="ec5e7-162">외부 사용자 액세스를 지원하는 각 중앙 사이트 및 하나 이상의 프런트 엔드 풀을 배포한 각 중앙 사이트에 디렉터 또는 디렉터 풀을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="ec5e7-163">각 디렉터 풀은 최대 10개의 디렉터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="ec5e7-164">디렉터를 다른 서버 역할과 함께 배치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="ec5e7-165">적절 한 디렉터 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="ec5e7-166">역방향 프록시-Lync Server 2013 구성 요소가 아니지만, 페더레이션 사용자에 대해 웹 콘텐츠를 공유 하거나 모바일 트래픽을 지원 하려는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="ec5e7-167">역방향 프록시 서버를 Lync Server 2013 서버 역할을 사용 하 여 함께 배치할 수는 없지만, 다른 응용 프로그램에 사용 되는 조직의 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="ec5e7-168">역방향 프록시 서버에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 역방향 프록시 서버 설정을](lync-server-2013-setting-up-reverse-proxy-servers.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec5e7-169">Lync Server 2013에서는 A/V 회의, 모니터링 및 보관이 프런트 엔드 서버에서 실행 되며 더 이상 별도의 서버 역할이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="ec5e7-170">중앙 사이트에 배포한 모든 프런트 엔드 풀 및 Standard Edition 서버는 중앙 사이트용으로 배포한 다음 항목을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="ec5e7-171">디렉터 또는 디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-171">Director or Director pool</span></span>

  - <span data-ttu-id="ec5e7-172">독립 실행형 중재 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="ec5e7-173">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="ec5e7-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="ec5e7-174">에지 서버 또는 에지 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="ec5e7-175">영구 채팅 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="ec5e7-176">모니터링</span><span class="sxs-lookup"><span data-stu-id="ec5e7-176">Monitoring</span></span>

  - <span data-ttu-id="ec5e7-177">보관</span><span class="sxs-lookup"><span data-stu-id="ec5e7-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec5e7-178">Exchange 2013 통합 메시징의 통합을 지원 하려고 하지만 Lync Server 2013 사이트의 구성 요소가 아닌 경우 Lync Server 2013 배포를 사용 하 여 Exchange UM 서버를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="ec5e7-179">또한 하나의 중앙 사이트에 배포한 다음 항목을 여러 중앙 사이트에서 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="ec5e7-180">독립 실행형 중재 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="ec5e7-181">에지 서버 또는 에지 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="ec5e7-182">영구 채팅 서버 또는 풀</span><span class="sxs-lookup"><span data-stu-id="ec5e7-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="ec5e7-183">보관</span><span class="sxs-lookup"><span data-stu-id="ec5e7-183">Archiving</span></span>

  - <span data-ttu-id="ec5e7-184">모니터링</span><span class="sxs-lookup"><span data-stu-id="ec5e7-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec5e7-185">Exchange UM 서버는 Lync Server 2013 배포를 사용 하 여 구현 하 고 여러 중앙 사이트에서 공유할 수 있지만 Lync Server 2013 사이트의 구성 요소는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="ec5e7-186">Lync Server 2013 서버 역할 및 기능에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 서버 역할](lync-server-2013-server-roles.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="ec5e7-187">Lync Server 2013 서버 위치 지원에 대 한 요약은 [Lync server 2013에서 지원 되는 서버 위치](lync-server-2013-supported-server-collocation.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="ec5e7-188">이 섹션의 앞 부분에서 설명한 서버 역할 및 기능 외에도 Lync Server 2013에는 다음과 같은 추가 구성 요소와 옵션이 포함 되어 있으며,이는 다음 중 일부 또는 모두를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="ec5e7-189">방화벽</span><span class="sxs-lookup"><span data-stu-id="ec5e7-189">Firewalls</span></span>

  - <span data-ttu-id="ec5e7-190">PSTN 게이트웨이(Enterprise Voice를 배포하는 경우)</span><span class="sxs-lookup"><span data-stu-id="ec5e7-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="ec5e7-191">Exchange UM 서버</span><span class="sxs-lookup"><span data-stu-id="ec5e7-191">Exchange UM Server</span></span>

  - <span data-ttu-id="ec5e7-192">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="ec5e7-192">DNS load balancing</span></span>

  - <span data-ttu-id="ec5e7-193">하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="ec5e7-193">Hardware load balancers</span></span>

  - <span data-ttu-id="ec5e7-194">SQL Server 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="ec5e7-194">SQL Server databases</span></span>

  - <span data-ttu-id="ec5e7-195">파일 공유</span><span class="sxs-lookup"><span data-stu-id="ec5e7-195">File shares</span></span>

<span data-ttu-id="ec5e7-196">모든 Lync Server 2013 기능, 구성 요소 및 옵션에 대 한 자세한 내용은 계획 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="ec5e7-197">분기 사이트 토폴로지 및 구성 요소(온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="ec5e7-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="ec5e7-p115">분기 사이트는 중앙 사이트와 연결되며, 분기 사이트의 각 SBA(Survivable Branch Appliance)는 연결된 중앙 사이트의 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버와 연결됩니다. 분기 사이트는 대부분의 기능을 중앙 사이트에 의존하므로 다음 구성 요소만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="ec5e7-200">공중 전화망 (PSTN) 게이트웨이와 일부 Lync Server 기능을 결합 하는 Sba (survivable Branch 기기입니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="ec5e7-201">중재 서버는 Sba (survivable 분기 기기의 등록자 인스턴스와 함께 배치 된 수 있으며 독립 실행형 중재 서버 또는 중재 서버 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="ec5e7-202">Lync Server 2013 등록자 및 중재 서버 소프트웨어가 설치 된 Windows Server를 실행 하는 서버에 해당 하는 Sba (survivable 분기 서버</span><span class="sxs-lookup"><span data-stu-id="ec5e7-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="ec5e7-203">독립 실행형 PSTN 게이트웨이(SBA(Survivable Branch Appliance)의 일부가 아님) 및 독립 실행형 중재 서버</span><span class="sxs-lookup"><span data-stu-id="ec5e7-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="ec5e7-204">Sba (survivable 분기 서버에 대 한 요구 사항은 Lync Server 2013 서버 역할에 대 한 요구 사항과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec5e7-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

