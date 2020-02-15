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
ms.openlocfilehash: 73b9947cf77df8d0c3baedcb27d8e13cc728e52b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a><span data-ttu-id="f1c25-102">Lync Server 2013에서 모니터링 배포</span><span class="sxs-lookup"><span data-stu-id="f1c25-102">Deploying monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1c25-103">_**마지막으로 수정 된 항목:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="f1c25-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="f1c25-104">모니터링 서버 역할이 더 이상 사용 되지 않으므로 Microsoft Lync Server 2013 모니터링 인프라가 크게 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-104">Major changes have been made to the Microsoft Lync Server 2013 monitoring infrastructure, beginning with the fact that the Monitoring Server role has been deprecated.</span></span> <span data-ttu-id="f1c25-105">별도의 모니터링 서버 역할을 제공하는 대신(일반적으로 조직이 모니터링 서버로 작동할 전용 컴퓨터를 설정해야 했음), 이제는 모니터링 서비스가 각 프런트 엔드 서버에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-105">Instead of separate Monitoring Server roles (which typically required organizations to set up dedicated computers to act as Monitoring servers) monitoring services are now collocated on each Front End server.</span></span> <span data-ttu-id="f1c25-106">이 변경으로 인해 제공되는 주요 이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-106">Among other things, this change helps to:</span></span>

  - <span data-ttu-id="f1c25-107">Lync Server 2013를 구현할 때 필요한 서버 역할의 수를 줄이십시오.</span><span class="sxs-lookup"><span data-stu-id="f1c25-107">Decrease the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="f1c25-108">이 경우 모니터링 서버 서버 역할이 감소하므로 모니터링 전용 서버를 유지 관리할 필요가 없어져 비용도 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-108">In this case, decrementing the Monitoring Server server role also helps to reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="f1c25-109">Lync Server 설치 및 관리의 복잡성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-109">Reduce the complexity of Lync Server setup and administration.</span></span> <span data-ttu-id="f1c25-110">각 프런트 엔드 서버에 모니터링 서비스를 자동으로 배치함으로써 더 이상 모니터링 서버 역할을 설치, 구성 및 관리하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-110">By automatically collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1c25-111">또한 Lync Server 2013에서는 보관 서버 역할도 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-111">The Archiving Server role has also been deprecated in Lync Server 2013.</span></span> <span data-ttu-id="f1c25-112">모니터링 서비스와 마찬가지로 Lync Server 2013 보관 서비스는 이제 각 프런트 엔드 서버에서 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-112">Like the monitoring services, Lync Server 2013 archiving services are now collocated on each Front End server.</span></span> <span data-ttu-id="f1c25-113">모니터링 및 보관은 같은 SQL Server 데이터베이스 인스턴스를 공유하는 경우가 많으므로, 이러한 변화는 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-113">This is important to note simply because monitoring and archiving often share the same SQL Server database instance.</span></span>



</div>

<span data-ttu-id="f1c25-114">사용자들이 예상한 것처럼, 이러한 변경은 모니터링 서비스 설치 및 관리 방법에 큰 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-114">As you might expect, these changes have a major impact on how monitoring services are installed and managed.</span></span> <span data-ttu-id="f1c25-115">예를 들어 모니터링 서버 역할이 더 이상 존재 하지 않으므로 모니터링 서버 노드가 Lync Server 토폴로지 작성기에서 제거 되었습니다. 그러면 토폴로지에 새 모니터링 서버를 추가 하기 위해 토폴로지 작성기의 새 모니터링 서버 마법사를 더 이상 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-115">For example, because the Monitoring Server role no longer exists, the Monitoring Server node has been removed from the Lync Server Topology Builder; in turn, that means you no longer use Topology Builder's New Monitoring Server Wizard in order to add a new Monitoring Server to your topology.</span></span> <span data-ttu-id="f1c25-116">(해당 마법사가 더 이상 존재 하지 않습니다.) 대신, 일반적으로 다음 두 단계를 완료 하 여 토폴로지 내에서 모니터링 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-116">(That wizard no longer exists.) Instead, you will typically implement monitoring services within your topology by completing the following two steps:</span></span>

1.  <span data-ttu-id="f1c25-117">새 Lync Server 풀을 설정할 때 동시에 모니터링을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f1c25-117">Enabling monitoring at the same time you set up a new Lync Server pool.</span></span> <span data-ttu-id="f1c25-118">Lync Server 2013에서는 풀이 풀 단위로 사용 하거나 사용 하지 않도록 설정 되어 있습니다. 모니터링 데이터를 실제로 수집 하지 않고 풀에 대해 모니터링을 사용 하도록 설정할 수 있으며,이 설명서의 통화 정보 기록 및 품질 설정 구성 섹션에서 설명 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-118">(In Lync Server 2013, monitoring is enabled or disabled on a pool-by-pool basis.) Note that you can enable monitoring for a pool without actually collecting monitoring data, a process explained in the Configuring Call Detail Recording and Quality of Experience Settings section of this documentation.</span></span>

2.  <span data-ttu-id="f1c25-p107">모니터링 저장소(모니터링 데이터베이스)를 새 풀과 연결합니다. 단일 모니터링 저장소를 여러 풀과 연결할 수 있습니다. 즉, 등록자 풀에 있는 사용자의 수에 따라서는 각 풀에 대해 별도의 모니터링 데이터베이스를 설정하지 않아도 됩니다. 대신 단일 모니터링 저장소를 여러 풀에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-p107">Associating a monitoring store (that is, a monitoring database) with the new pool. Note that a single monitoring store can be associated with multiple pools. Depending on the number of users homed on your Registrar pools, that means that you do not have to set up a separate monitoring database for each of your pools. Instead, single monitoring store can be used by multiple pools.</span></span>

<span data-ttu-id="f1c25-p108">새 풀을 만들 때 모니터링도 동시에 사용하도록 설정하는 것이 더 쉬운 경우가 많지만, 모니터링을 사용하지 않도록 설정한 상태에서 새 풀을 만들 수도 있습니다. 이렇게 하는 경우 나중에 토폴로지 작성기를 사용하여 서비스를 사용하도록 설정할 수 있습니다. 토폴로지 작성기를 사용하면 풀에 대해 모니터링을 사용 또는 사용하지 않도록 설정하거나, 풀을 다른 모니터링 저장소와 연결할 수 있습니다. 모니터링 서버 역할은 더 이상 없지만 모니터링 저장소(모니터링 서비스를 통해 수집되는 데이터를 저장하는 데 사용되는 백 엔드 데이터베이스)는 하나 이상 만들어야 합니다. 이러한 백 엔드 데이터베이스는 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012를 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-p108">Although it's often easier to enable monitoring at the same time that you create a new pool, it's also possible to create a new pool with monitoring disabled. If you do that, you can later use Topology Builder to enable the service: Topology Builder provides a way to enable or disable monitoring for a pool, or to associate a pool with a different monitoring store. Keep in mind that even though there is no longer a Monitoring Server role you will still need to create one or more monitoring stores: backend databases used to store the data gathered by the monitoring service. These backend databases can be created using either Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1c25-127">풀에 대해 모니터링을 사용 하도록 설정한 경우에는 토폴로지를 변경 하지 않고 모니터링 데이터를 수집 하는 프로세스를 사용 하지 않도록 설정할 수 있습니다. Lync Server 관리 셸을 사용 하지 않도록 설정 하는 방법을 제공 합니다. (QoE) 데이터 수집 (환경)</span><span class="sxs-lookup"><span data-stu-id="f1c25-127">If monitoring has been enabled for a pool you can disable the process of collecting monitoring data without having to change your topology: Lync Server Management Shell provides a way for you to disable (and then later re-enable) call detail recording (CDR) or Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f1c25-128">자세한 내용은이 문서의 통화 정보 기록 및 품질 설정 구성 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1c25-128">For more information, see the Configuring Call Detail Recording and Quality of Experience Settings section of this document.</span></span>



</div>

<span data-ttu-id="f1c25-129">Lync Server 2013의 모니터링에 대 한 또 다른 중요 한 향상 된 기능으로, lync server 모니터링 보고서에서 이제 IPv6을 지원 한다는 사실은 IP 주소 필드를 사용 하는 보고서에 따라 IPv4 또는 IPv6 주소가 다음과 같이 표시 됨: 1) 사용 중인 SQL 쿼리 3, 2) 모니터링 데이터베이스에 IPv6 주소가 저장 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-129">One other important enhancement to monitoring in Lync Server 2013 is the fact that Lync Server Monitoring Reports now support IPv6: reports that use the IP Address field will display either IPv4 or IPv6 addresses depending on : 1) the SQL query being used; and, 2) where or not the IPv6 address is stored in the monitoring database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1c25-130">SQL Server 에이전트 서비스 시작 유형이 자동이 고 모니터링 데이터베이스를 보유 하 고 있는 SQL 인스턴스에 대해 SQL Server 에이전트 서비스가 실행 되 고 있는지 확인 하 여 기본 모니터링 SQL Server 유지 관리 작업을 예약 된 시간에 실행할 수 있도록 합니다. SQL Server 에이전트 서비스의 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-130">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Monitoring databases, so that the Default Monitoring SQL Server Maintenance Jobs can run on their scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

<span data-ttu-id="f1c25-131">이 설명서에서는 Lync Server 2013에 대 한 모니터링 및 모니터링 보고서를 설치 및 구성 하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-131">This documentation walks you through the process of installing and configuring monitoring and Monitoring Reports for Lync Server 2013.</span></span> <span data-ttu-id="f1c25-132">또한 다음 작업을 수행할 수 있도록 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-132">The documentation provides step-by-step instructions that will help you to:</span></span>

  - <span data-ttu-id="f1c25-133">토폴로지에서 모니터링을 사용하도록 설정하고 프런트 엔드 풀과 모니터링 저장소를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-133">Enable monitoring in your topology and associate a monitoring store with a Front End pool.</span></span>

  - <span data-ttu-id="f1c25-134">SQL Server Reporting Services 및 Lync Server 모니터링 보고서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-134">Install SQL Server Reporting Services and the Lync Server Monitoring Reports.</span></span> <span data-ttu-id="f1c25-135">모니터링 보고서는 모니터링 데이터베이스에 저장된 정보에 대한 여러 가지 보기를 제공하는 미리 구성된 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-135">Monitoring Reports are preconfigured reports that provide different views into the information stored in a monitoring database.</span></span>

  - <span data-ttu-id="f1c25-136">CDR(통화 정보 기록) 및 QoE(체감 품질) 데이터 수집을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-136">Configure call detail recording (CDR) and Quality of Experience (QoE) data collection.</span></span> <span data-ttu-id="f1c25-137">통화 정보 기록은 VoIP (Voice over IP) 전화 통화와 같은 Lync Server 기능의 사용 현황을 추적할 수 있는 방법을 제공 합니다. IM (인스턴트 메시징); 파일 전송; A/V (오디오/비디오) 회의 응용 프로그램 공유 세션을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-137">Call detail recording provides a way for you to track usage of Lync Server capabilities such as Voice over IP (VoIP) phone calls; instant messaging (IM); file transfers; audio/video (A/V) conferencing; and application sharing sessions.</span></span> <span data-ttu-id="f1c25-138">QoE 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-138">QoE metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span>

  - <span data-ttu-id="f1c25-139">모니터링 데이터베이스에서 CDR 및/또는 QoE 레코드를 수동으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c25-139">Manually purge CDR and/or QoE records from the monitoring database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

