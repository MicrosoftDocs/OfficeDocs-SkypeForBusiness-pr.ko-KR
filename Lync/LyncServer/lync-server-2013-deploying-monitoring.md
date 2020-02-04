---
title: 'Lync Server 2013: 모니터링 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637897bce0a160a8cc3b199ec6aee3ffd7375852
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="0fa9e-102">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="0fa9e-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fa9e-103">_**마지막으로 수정한 주제:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="0fa9e-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="0fa9e-104">모니터링 서버 역할이 더 이상 사용 되지 않는 것을 고려 하 여 Microsoft Lync Server 2013 모니터링 인프라에 대 한 주요 변경 사항이 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="0fa9e-105">별도의 모니터링 서버 역할 (일반적으로 모니터링 서버로 작동 하도록 전용 컴퓨터를 설정 하는 데 조직이 필요한 경우) 하는 대신 각 프런트 엔드 서버에서 collocated 모니터링 서비스를 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="0fa9e-106">그 외에, 다음과 같은 변경 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="0fa9e-107">Lync Server 2013을 구현할 때 필요한 서버 역할 수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="0fa9e-108">이 경우 모니터링 서버 서버 역할을 감소 하면 모니터링을 위해 전용 서버를 유지 관리할 필요가 없어지므로 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="0fa9e-109">Lync Server 설정 및 관리의 복잡도를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="0fa9e-110">각 프런트 엔드 서버에서 자동으로 모니터링 서비스를 collocating 모니터링 서버 역할을 설치, 구성, 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fa9e-111">또한 Lync Server 2013에서 보관 서버 역할도 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="0fa9e-112">모니터링 서비스와 마찬가지로, Lync Server 2013 보관 서비스는 이제 각 프런트 엔드 서버에서 collocated.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="0fa9e-113">모니터링 및 보관이 동일한 SQL Server 데이터베이스 인스턴스를 공유 하는 경우가 많으므로 참고 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="0fa9e-114">예상 대로 이러한 변경 사항은 모니터링 서비스를 설치 하 고 관리 하는 방법에 큰 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="0fa9e-115">예를 들어 모니터링 서버 역할이 더 이상 존재 하지 않기 때문에 모니터링 서버 노드가 Lync Server 토폴로지 작성기에서 제거 되었습니다. 다시 말해, 토폴로지에 새 모니터링 서버를 추가 하기 위해 더 이상 토폴로지 작성기의 모니터링 서버 마법사를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="0fa9e-116">(마법사가 더 이상 존재 하지 않습니다.) 대신 일반적으로 다음 두 단계를 완료 하 여 토폴로지 내에 모니터링 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="0fa9e-117">동시에 모니터링 기능을 사용 하도록 설정 하는 것이 새로운 Lync Server 풀을 설정할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="0fa9e-118">(Lync Server 2013에서는 풀 단위 기준으로 모니터링을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.) 모니터링 데이터를 실제로 수집 하지 않고 풀에 대 한 모니터링을 사용 하도록 설정할 수 있으며,이 설명서의 통화 세부 정보 기록 및 품질 설정 구성 섹션에서 설명 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="0fa9e-119">모니터링 저장소 (즉, 모니터링 데이터베이스)를 새 풀에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-119">Associating a monitoring store (that is, a monitoring database) with the new pool.</span></span> <span data-ttu-id="0fa9e-120">단일 모니터링 저장소는 여러 풀에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-120">Note that a single monitoring store can be associated with multiple pools.</span></span> <span data-ttu-id="0fa9e-121">레지스트라 풀에 속한 사용자 수에 따라 각 풀에 대해 별도의 모니터링 데이터베이스를 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-121">Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools.</span></span> <span data-ttu-id="0fa9e-122">대신 여러 풀에서 단일 모니터링 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-122">Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="0fa9e-123">새 풀을 만들 때 동시에 모니터링을 사용 하는 것이 더 쉽지만 모니터링을 사용 하지 않도록 설정 하 여 새 풀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-123">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled.</span></span> <span data-ttu-id="0fa9e-124">이렇게 하는 경우 나중에 토폴로지 작성기를 사용 하 여 서비스를 사용 하도록 설정할 수 있습니다. 토폴로지 작성기에서는 풀에 대 한 모니터링을 사용 하거나 사용 하지 않도록 설정 하거나 풀을 다른 모니터링 저장소에 연결 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-124">If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store.</span></span> <span data-ttu-id="0fa9e-125">모니터링 서버 역할이 남아 있지 않더라도 모니터링 서비스에서 수집한 데이터를 저장 하는 데 사용 되는 백엔드 데이터베이스인 하나 이상의 모니터링 저장소를 만들어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-125">Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service.</span></span> <span data-ttu-id="0fa9e-126">이러한 백 엔드 데이터베이스는 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012를 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-126">These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fa9e-127">풀에 대해 모니터링을 사용 하도록 설정 하면 토폴로지를 변경할 필요 없이 모니터링 데이터를 수집 하는 프로세스를 사용 하지 않도록 설정할 수 있습니다. Lync Server Management Shell을 사용 하 여 사용자가 나중에 다시 사용 하도록 설정 하는 방법을 제공 합니다 (예: CDR) 또는 품질 (체감 품질) 데이터 수집을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="0fa9e-128">자세한 내용은이 문서의 통화 세부 정보 기록 및 품질 설정 구성 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="0fa9e-129">Lync Server 2013에서 모니터링할 수 있는 또 다른 중요 한 기능으로는 Lync Server 모니터링 보고서에서 IPv6을 지원 하기 때문에 IP 주소 필드를 사용 하는 보고서에는 다음에 따라 IPv4 또는 IPv6 주소가 표시 됨: 1) 사용 되 고 있는 SQL 쿼리입니다. and, 2) 모니터링 데이터베이스에 IPv6 주소가 저장 되어 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fa9e-130">SQL Server 에이전트 서비스 시작 유형이 자동이 고 SQL Server 에이전트 서비스가 모니터링 데이터베이스를 보유 하 고 있는 SQL 인스턴스에 대해 실행 되 고 있는지 확인 하 여 기본 모니터링 SQL Server 유지 관리 작업을 예약 된 기준으로 실행할 수 있도록 합니다. SQL Server 에이전트 서비스의 제어 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="0fa9e-131">이 설명서는 Lync Server 2013에 대 한 모니터링 및 모니터링 보고서를 설치 하 고 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="0fa9e-132">이 설명서는 다음을 수행 하는 데 도움이 되는 단계별 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="0fa9e-133">토폴로지에서 모니터링을 사용 하도록 설정 하 고 모니터링 저장소를 프런트 엔드 풀에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="0fa9e-134">SQL Server Reporting Services 및 Lync Server 모니터링 보고서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="0fa9e-135">모니터링 보고서는 모니터링 데이터베이스에 저장 된 정보로 다양 한 보기를 제공 하는 미리 구성 된 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="0fa9e-136">CDR (통화 정보 기록) 및 체감 품질 (경력 품질) 데이터 수집을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="0fa9e-137">통화 정보 기록은 VoIP (Voice over IP) 전화 통화와 같은 Lync Server 기능의 사용 현황을 추적 하는 방법을 제공 합니다. 인스턴트 메시지 (IM); 파일 전송 오디오/비디오 (A/V) 회의 및 응용 프로그램 공유 세션</span><span class="sxs-lookup"><span data-stu-id="0fa9e-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="0fa9e-138">체감 품질 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음 및 "지터"의 양과 같은 작업을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다 (패킷 지연의 차이).</span><span class="sxs-lookup"><span data-stu-id="0fa9e-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="0fa9e-139">모니터링 데이터베이스에서 수동으로 CDR 및/또는 체감 품질 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa9e-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

